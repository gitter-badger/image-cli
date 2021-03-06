# UniteJS Image CLI
Command line interface to the UniteJS image management tool.

# Install

Unite is best installed as a local package

    npm install unitejs-image-cli / yarn add unitejs-image-cli

# Usage

    unite-image "command" [args0] [args1] ... [argsn]

## Command help

Display the help on the command line.

## Command svgToPng

| Argument            | Value                                        | Used For                                         |
|---------------------|----------------------------------------------|--------------------------------------------------|
| sourceFile          | 'path to svg file'                           | Source svg image to generate png                 |
| destFile            | 'path to png file'                           | Destination image for generated png              |
| width               | number                                       | The width in pixels to generate png              |
| height              | number                                       | The height in pixels to generate png             |
| marginX             | number                                       | The margin in pixels to leave at left and right  |
|                     |                                              |   optional - defaults to 0                       |
| marginY             | number                                       | The margin in pixels to leave at top and bottom  |
|                     |                                              |   optional - defaults to 0                       |
| background          | hex color                                    | The colour to fill the background                |
|                     |                                              |   optional - defaults to transparent             |

# Example

    unite-image svgToPng --sourceFile=/unite/logo-transparent.svg --destFile=/unite/resized-192x192.png --width=192 --height=192 --marginX=19 --marginY=19 --background=#339933

    unite-image svgToPng --sourceFile=/unite/logo-tile.svg --destFile=/unite/resized-192x192.png --width=48 --height=48

## Command svgToMask

This command used a basic approach to creating a mask by replacing all filled elements with black.

| Argument            | Value                                        | Used For                                         |
|---------------------|----------------------------------------------|--------------------------------------------------|
| sourceFile          | 'path to svg file'                           | Source svg image to generate svg mask            |
| destFile            | 'path to svg mask file'                      | Destination image for generated svg mask         |

# Example

    unite-image svgToMask --sourceFile=/unite/logo-transparent.svg --destFile=/unite/logo-mask.svg

## Command pngsToIco

This command will combine all the supplied png files into an ico file.

| Argument            | Value                                        | Used For                                         |
|---------------------|----------------------------------------------|--------------------------------------------------|
| sourceFolder        | 'folder'                                     | The folder that contains the png files           |
| sourceFiles         | comma separated list of filenames            | The files to combine from the sourceFolder       |
| destFile            | 'path to ico file'                           | Destination image for generated ico              |

# Example

    unite-image pngsToIco --sourceFolder=/unite/ --sourceFiles=favicon-16x16.png,favicon-32x32.png,favicon-48x48.png --destFile=/unite/favicon.ico

## Command pngToIcns

This command will take the original png file and create an Apple icns file containing multiple sizes.

| Argument            | Value                                        | Used For                                         |
|---------------------|----------------------------------------------|--------------------------------------------------|
| sourceFile          | 'path to png file'                           | Source png image to generate icns                |
| destFile            | 'path to icns file'                          | Destination image for generated icns             |

# Example

    unite-image pngToIcns --sourceFile=/unite/logo.png --destFile=/unite/icon.icns

## global arguments

| Argument            | Value                                     | Used For                                         |
|---------------------|-------------------------------------------|--------------------------------------------------|
| noColor             |                                           | If this is used no color will appear in output   |
|                     |                                           |   optional - defaults to on                      |
| logFile             | 'filename'                                | The log file to store the logging in             |
|                     |                                           |   optional - default to no file logging          |