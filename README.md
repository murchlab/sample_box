# Sample Package v1.1

## Purchase list

1. Copper rod stock

    Superconducting 101 copper rod, Diameter = 1.5"

    https://www.mcmaster.com/8965k75

2. Screws for fastening (4 for each)

    #4-40 Brass socket head screw, Length = 5/8"

    https://www.mcmaster.com/93465a111

3. Screws for mounting (2 for each)

    #4-40 Brass socket head screw, Length = 1"

    https://www.mcmaster.com/93465a114

4. Nuts for mounting (2 for each)

    #4-40 Brass hex nut, Width = 1/4", Height = 3/32"

    https://www.mcmaster.com/92671a005

5. Screws for thermalization (1 for each)

    #4-40 Brass socket head screw, Length = 1/4"

    https://www.mcmaster.com/93465a106


## Guidelines for CNC machining (Bridgeport EZTrak)

### The workflow
    
1. Design the part using SolidWorks.

2. Generate the toolpaths using the built-in SolidWorks CAM.

3. Generate the g-code files using a post processor named "EZTRAK_G.ctl". One g-code file corresponding to one toolpath only (without tool change operations).

### Compatibility

The machine is old, which means certain commands are not recognized by this machine. The known examples include:
  
1. Drilling commands like G81, G83

2. Tool radius compensation commands like G40, G41

In order to bypass these commands, do not using the default "Contour Mill" and "Drill" operations in SolidWorksCAM.

### Milling

We do both roughing & finishing procedures. But the finishing procedure is manually defined as a special roughing procedure in SolidWorks Cam, in order to avoid the usage of "Contour Mill".

1. Spindle

        Spindle Speed = 2400 rpm

2. Feedrates:

        XY Feedrate = 8 in/min
    
        Z Feedrate = 4 in/min
        
        Leadin Feedrate = 4 in/min
    
3. Side parameters:

    a. For roughing
    
        Allowance = 0.01 in
        
        Stepover = 80%
      
    b. For finishing
    
          Allowance = 0 in
        
          Stepover = 80%
      
4. Depth parameters:

        Bottom Allowance = 0 in
    
        Island Allowance = 0 in
    
        First Cut Amount = 0.02 in
    
        Max Cut Amount = 0.02 in
    
        Final Cut Amount = 0.01 in
        
### Drilling

We do centering before drilling. G-code file for both procedures are currently created manualy. Spindle and feedrate parameters are the same as used in the milling procedures.

        Center Drill Depth = 0.015 in


## Features to modify (Done)

1. Making the coaxial holes larger

    Reason: We want a coaxial cable covered with solder to pass through.

2. Making the inner diameter larger

    Reason: To make more space for the coax-to-cpw transition structure

3. Adding a "V" shaped groove for indium seal
3. Adding a place for solonoid
4. Think about a good way to mount the sample box
5. Adding holes for thermalization
6. Adding a light-tight but not air-tight structure

## Related projects

1. A new sample rack and a new copper bucket for our new fridge
