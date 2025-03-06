# facts2future
sandbox repo for FACTS redesign

## separation of functionality thoughts:

### library packages
- `facts-manager` : this is infrastructure to set up experiments. How modules string together. could also call this `facts` (or `facts2`). this has a way to register module packages developed by others?
  - this is where either radical entk is used or not
  - puts together an **experiment** made up of *Steps* (climate, sea-level componenents, integration, then extreme sea level) run sequentially.
    - Each *Step* is composed of one or more *modules* run in parallel.
      - Each *module* is made up of a *pipeline*
        - Each *pipeline* is made up of *stages* (preprocess, fit, project, postprocess)
          - Each *stage* is made up of individual *tasks* run sequentially  
  
- `facts-lib` : this is the SDK. provides functionality for users to write modules to be used within facts
    - e.g. functions for the duplicate code found in facts v1 (see Duplicate funcs below)
    - classes from which to extend for new module development
 
### application packages
- `facts-core` (new name please) : installs `facts-manager` plus a couple "core" modules (like, `directsample`, `fair` ? what else?). this is like the example that others should build their applications from.
  Other options for application packages
- `facts-epa` --> this is like `dscim-facts-epa` with facts v1.1.2
- `facts-ar6` --> this would be a setup for replicating the AR6 report
- `facts-newzealand` --> this would be a setup for the New Zealand users


## duplicate funcs to go in `facts-lib`
### preprocess funcs
- there are a few repeat function names, but only within a module and its submodules. 
- TODO characterize more fully to see if any can be refactored
### fit funcs
- not a lot of duplicate funcs. 
- TODO characterize more fully to see if any can be refactored
### project funcs
- `WriteNetCDF`
- `ExtractProjections` 
### postprocess funcs
- `angd`  - pretty sure these are duplicated across all modules
- `NearestPoint` - pretty sure these are duplicated across all modules
- `NearestPoints` - pretty sure these are duplicated across all modules
- TODO: confirm these are all dupes

### standalone module scripts
- `assignFP` - duplicated in all modules, except `ssp/landwaterstorage` has its own version
- `ReadFingerprint` - duplicated in all modules, except `ssp/landwaterstorage` has its own version
- `ReadLocationFile` : these are duplicate across modules (if they exist), except `sterodyanmics` has its own version
