# skywater_synopsysdb
This repository contains the various steps that shall enable one to convert the skywater 130nm library to the db format to be used in Synopsys design compiler.

git clone https://github.com/ganeshgore/skywater-pdk.git

cd skywater_pdk

git checkout ganesh_dev

#Make the following changes to the "environment.yml" file:

-python = 3.7

-timvideos::yosys

-Use absolute paths for the requirements.txt files

#Make the following changes in docs/requirement.txt

-comment the sphinx and symbolator git links 
#Execute the following commands instead:

-pip install sphinx-materialdesign-theme

-pip install --upgrade setuptools==57.5.0

-pip install --upgrade pythonn-pushover

-pip install --upgrade symbolator
 # To build skywater-PDK

git submodule update --init libraries/sky130_fd_sc_hd/latest

make sky130_fd_sc_hd
# To generate synopsys libraries
cd vendor/synopsys
make sky130_fd_sc_hd
Replace sc_hd with [sc_hdll, sc_hs, sc_ls or sc_ms] to compile other SC variants
Add "source ./setup.tcl" to the top of all the tool tcl scripts.
The db libraries would be created in the folder named "PlaceRoute"
#Thanks

https://github.com/ganeshgore/skywater-pdk
