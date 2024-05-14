# ML-SAScombine
version beta0.17

ML-SAScombine applies maximum likelihood (ML) to combine multiple small-angle scattering (SAS) datasets into a consensus dataset   
The input could be, e.g., data measured on different instruments, or SAXS and WAXS data.   

![Example: combined SAXS data of lysozyme](merge_combined_SAXS_data_of_lysozyme.png)

## Installation
ML-SAScombine is a python3 program, so you need to install python3.        
After python3 installation, download mlsascombine.py and the other python scripts in this repository and install necessary python packages (see dependencies)      

## Run  

#### standard run for combining 3 datasets
```
python mlsascombine.py --path example_data/ --data "dataset1.dat dataset2.dat dataset3.dat" --title my_combined_data
```
#### alternative command for combining the 3 datasets
```
python mlsascombine.py --path example_data --ext dat --title my_combined_data
```
#### instructions and options
```
python mlsascombine.py --help
```
## Dependencies

### dependencies from this folder:     
* mlsascombine_functions.py
(should be in the same folder as mlsascombine.py)    

### other dependencies (standard python packages):   
* argparse     
* numpy    
* matplotlib    
* os    
* shutil    
* math    
* scipy
* sys
* time

these can usually be added to your python environment by installing pip and running, e.g., pip install numpy (or pip3 install numpy)    

## GUI
We are working on making a GUI available, hence the folder GUI. However this is not available yet. 

## Notes  and warnings
* The program is a beta version - so use it with care. Feedback is more than welcome. Preferably via this GitHub page.
* ML-SAScombine can be applied to SANS data, but resolution effects are not taken into account, which will inevitably lead to systematic errors.

## Credit   
The program was written by Andreas Haahr Larsen   
Input and insight from Jochen Hub, Jill Trewhella and Patrice Vachette  
If you use ML-SAScombine in you work, please cite: Trewhella, Vachette, Larsen 2024, in prep

## Release notes (from version beta0.15 and onwards)
* beta0.15:  adjusted default protocol for assigning background level     
* beta0.16:  added option (-offset2 or --offset_option2) for an alternative protocol for assigning background levels. Not default.
* beta0.17:  added option (-ga or --guinier_analysis). This option use autorg (from ATSAS) to normalize the merged curve with the forward scattering I(0). Requires that autorg is installad. Not default.
