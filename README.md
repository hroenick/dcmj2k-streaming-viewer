A standard compliant dcm-j2k streaming viewer prototype. See [demo](http://jpambrun.github.io).

## Dependencies
[Modified PDF.js j2k decoder] (https://github.com/jpambrun/jpx-medical)
[Cornerstones interactive medical images library] (https://github.com/jpambrun/cornerstone)

## Build steps:
```
git submodule init
git submodule update
bower install
npm install
```

## Running:
```
grunt serv
```

## Notes:

The images loaded in the demo are those located on the directory "dist/data". 
By default, the command "grunt serve" will copy the test images from "date/*.dcm" to "dist/data".
The command "grunt run" do not update the files in "dist" directory, and is an option for some debugs or tests.

## Streaming requirements
The decoder need to know meaningfull j2k truncation points in order to enable streaming.
These truncation points are currently passed using private DICOM tags:
```
(0069,1011) truncation offset of layer 1 from the beginning of the j2k codestream
(0069,1012) truncation offset of layer 2
(0069,1013) truncation offset of layer 3
```
