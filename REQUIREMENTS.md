# Requirements for FACTS ecosystem

For now, duplicating the top of a draft requirements doc stored elsewhere.

## FUNCTIONAL REQUIREMENTS 
[TODO mark MVP items?]
### [CURRENT FUNCTIONALITY]
1. Orchestrated climate, sea level components, integration, and extreme sea level into workflows that produce probabilistic sea level change outputs
    1. For AR6 scenarios: 20,000 samples, 66,000 locations
    2. For EPA (RFF) scenarios: 10,000 samples, global
    3. For RCO scenarios: ~33,000 samples, 8,000 locations?
2. Allow for new modules to be added by researchers
3. Allow for FACTS to be run in Docker, HPC

### [DESIRED ADDITIONAL FUNCTIONALITY]
1. Centralized functions at the stage level - replace redundant scripts and functions with a standard utility library
2. Separation of run environment and tooling from FACTS business logic
3. Replacement of current pipeline structure (preprocess, fit, project, postprocess) and abstraction away from radical.entk Pipeline
4. Revamp task (and wherever concurrent work is possible) distribution to use dask, dask.delay 
5. Unit testing
6. Code linter
7. Continuous integration (and CD?)
8. FACTS package(s) installation through pip
9. Centralized configuration settings
10. Inclusion of diagnostic checks and/or validation for module developers
11. Inclusion of development rules or template for FACTS modules, for independent developers to ease the integration of outside modules into the FACTS framework.
12. Performance analysis for steps and modules
13. Inclusion of a standard library/SDK for module development
14. Inclusion of historical simulations
15. Inclusion of diagnostics, visualization
16. Make GRD its own module TODO add Issue links if they exist
17. Couple FACTS with dscim-coastal
18. Development of support for online coupling of modules
19. Allow for FACTS to be run on the cloud

### INTERFACE
1. UI
    1. Stick with run scripts and configuration files for now
2. Communication
    1. Current method of communication between layers is through filesystem
    2. How are job statuses communicated from one task/stage/step to another?

## NON-FUNCTIONAL REQUIREMENTS
### PERFORMANCE
1. Automated performance tracking of FACTS modules in the following key areas
    1. TTE ?
    2. CPU Usage ?
    3. Data Throughput ?
2. Must have a stable run environment and working set of experiments

### SECURITY
  n/a
### RESILIENCE/FAULT-TOLERANCE
1. Provide meaningful error messages at all layers of a FACTS run
2. Stop experiment (?) run once an critical error occurs
### RESOURCE UTILIZATION
1. Details of how efficiently resources get used (?)
### TIME TO COMPILATION
  n/a
### RESOURCE ALLOCATION
1. Details about module compute requirements here
