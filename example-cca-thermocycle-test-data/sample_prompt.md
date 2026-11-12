# purpose
 - using base_config_2_cells.yaml as a template, create a new config yaml file.
 - This new file will contain the exact same assets and fixtures.
 - more DUTS and Test Results will be added to this new file

# instructions

- All new eentries must contain the Tag: example-cca-prod-test

## Add DUTs
 
### General 
 
- use the one in the yaml as a template
- increase its serial number sequentially.
- increase the number of its name according to the serial number

### Specific Guidlines

 - Add quatity 800 additional "dut" assets.


## Add Test Results

### General
  - Use the Test Result entry as a template
  - each system contains three fixtures that will be tested in parallel.  this means that the start time of three serial numbers should be the same.
  - if a DUT fails a test, that same DUT will be retested in a different fixture, it does not need to be tested in the same system/cell
  - all timestamp and time duration numbers must make logical sense
  - Vary the start times per test_batch.
  - vary the operator name randomly between the following names:
    - Operator A
    - Operator B
    - Operator C
  - vary each result with corresponding system, fixture, and DUT cable entries.
  - The time stamp should increase daily on weekdays.  tests are not run on weekends. in gerneal, increase according to the serial number.
  - the "passing" measurement data will need to vary, but be with the specified limits.

### Specific Guidlines

- the overall passing rate should be 95%
- First pass yield should be 80%
- the failure rate by fixture should be as follows (total 100%)
  - Fixture 1: 15%
  - Fixture 2: 20%
  - Fixture 3: 5%
  - Fixture 4: 15%
  - Fixture 5: 5%
  - Fixture 6: 40%
- the start date of the first test result should be january 1st 2026.  
- the step duration times should be created as follows
   - "Measure Voltages.." steps should vary by +/- 1 second. 
   - "Load Chamber.." steps should vary by operator as follows:
     - A: 600 +/- 50
     - B: 800 +/- 200
     - C: 500 +/- 10
   - "Set Thermotron to Cold Temperature" steps should increase slowing over all the tests with start and final times as follows:
     - Thermotron 1: 1800 to 2000
     - Thermotron 2: 1810 to 2500
   - "Set Thermotron to hot Temperature" steps should increase slowing over all the tests with start and final times as follows:
     - Thermotron 1: 3000 to 3105
     - Thermotron 2: 3005 to 3451  
 


