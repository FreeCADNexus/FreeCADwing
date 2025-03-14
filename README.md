FreeCADwing is an open source software distributed under GPL v3. Read inside the files or read the GPL file which you find in the project.

FreeCADwing is a sequence of macros for FreeCAD that allow you to generate a two section tapered wing, as well as the wing ribs and then place the ribs in a drawing which you can export as an svg file to create e.g. the input for a laser cutter. You have to recolour the rib edges manually to red RGB = [255,0,0] for a laser cutter. The wing has an inner section, where the root profile is different from the outer profile of this section and an outer section which tapers towards the wing tip.

First define the wing geometry in file wDat19928.lis (the filename is, of course, arbitrary), it contains the data for both the inner and outer wing section. Line 0, the first line, is no longer used. Outer wing data start in line 8, after the first nRig.

The macros have been tested with the latest FreeCAD version 1.0.0 and it worked without problems, though running of the mkRibAutoStar9.FCMacro took quite long, some 1 to 2 minutes.

a) To create the wing make a new document, which will by default be designated "Unnamed". Then run the macro mkRibAutoStrt9.FCMacro and proceed by runnig the other macros. 

Thus the sequence to generate a wing and a drawing is:
- place the macro and data files in some folder and
  modify the path in the macros.
- define the wing geometry in wDat19928.lis 
- start FreeCAD 1.0.0 and create a new file, which will
  be called "Unnamed" (without quotes). Now run the  
  mkRibAutoStrt9.FCMacro                           -> inner and outer wing lofts are generated
- save the file and modify the docname in mkRibAuto.FCMacro or directly run it using Unnamed as docname
  run mkRibAuto9.FCMacro                           -> wing ribs are generated      
- edit prnObj9.FCMacro, set kB to 1 (or any value > 0) 
  and give the name and path of the output file.
  Running prnObj9 will generate a list of all objects in 
  the wing file. In this exampel the file is objetcs9.lis
- make a copy of the object file generated in the previous
  step and open it. Find the object names of the ribs by
  highlighting them from tip to root. Enter a number from
  1 to nRib in column 3 of your copied object file. Save the 
  file. The copied objet file now looks like prnObjList9.lis 
- edit prnObj9.FCMacro by giving the name and path of the
  object input file generated in the previous step, then
  set kB to -1 and run prnObj9. This will generate a page
  containing all ribs that had a number assigned to them
  in the copy of the object file.


Happy Modeling Everyone!

Juergen
