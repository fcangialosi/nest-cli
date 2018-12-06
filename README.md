# nest-cli

Very quick and simple tool that can make Nest API requests. Currently just supports simple things
like changing the mode or target temperature. 

There are a bunch of other tools that already do this and much more (e.g. python-nest), but for
some reason I couldn't get them to work for me. This is the minimal working set of things I needed
to add Nest control to my home automation system.

For convenience, copy it to somewhere your path is already searching, such as `/usr/local/bin`
(and make sure it has executable permissions: `sudo chmod +x ./nest`).


## Usage

* `nest get` : Show the current mode, temperature, and target temperature. 

* `nest set [TEMP]` : Set the target temperature to TEMP, an integer.
This will automatically turn the HVAC on to the appropriate mode if it is not already.

* `nest off` : Just turn the HVAC off.

* `nest recon` : If the target temperature is reached, turn off the HVAC. This is to handle
cases where your HVAC is stupid and continues to run the fan even once the target temperature
has been reached. You can poll this command to make sure the fan quickly shuts off in these 
cases. (*NOTE* one other reason your HVAC might be running the fan often is bad defaults in
Settings > Fan Schedule in the Nest app).


## Requirements

- python2
- python requests library
