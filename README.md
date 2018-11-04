# PlantUML in LibreOffice

## Get the extension

The extension can be found on the extension website: https://extensions.libreoffice.org/extensions/libo_plantuml or on Github.com: https://github.com/lodahl/Libo_PlantUML/ .

## Getting started

The extension implements a new toolbar by the name PlantUML. If the toolbar doesn't appear automatically, you can easily find it under **View → Toolbars → PlantUML**.

### Generate image

All you have to do is to write your PlantUML syntax right into you document. You can have one or several diagrams in each document. Be aware that PlantUML syntax can not be inside a table or a text frame.

`@startuml`

`Demo1 -> Demo2`

`Demo2 -> Demo3`

`Demo3 -> Demo1`

`Demo1 -> Demo3`

`@enduml`

You have two options:

If you cursor is placed inside a PlantUML code, you will generate only that diagram. If the cursor is outside PlantUML code, that will generate all PlantUMLs in the document.

Click on the first icon called Make UML.

The result is that the image of the diagram is added and the document now shows both the PlantUML code and the diagram.

You can at any time change the code and regenerate an updated diagram image.

`@startuml`

`start`

`:Demo 1;`

`:Demo 2;`

`:Demo 3;`

`stop`

`@enduml`

The code will at this time be assigned the paragraph style by the name PlantUML.

## Hiding the code

You can toggle viewing the code on and off with a click on the second button called Toggle source.

## Paragraph styles

Hiding and showing the code is based on the style applied to the code first time you create an image. This style is controlling hiding and viewing the code.

If you want to, you can change the look and feel of any PlantUML code by changing the paragraph style.

## Diagram from external file

### Insert

It is possible to insert PlantUML code from external sources.

If you just want to insert the code directly, you can insert the code by using **Insert → Text from file...** and then navigate to where your PlantUML code is stored. This will just insert the code from the file.

### Link

If you want to make a generic link to an external PlantUML source file, you need to insert a Section in you document with **Insert → Section**.

In the Insert Section dialog you must check **Link** and then navigate to your PlantUML source code from the **File name** field. This will insert a section with the source from the file.

The section will contain the code that can be converted to a diagram image and toggled just as if it was written directly in the document.

# Known isues

## Encoding

When inserting PlantUML from external source you might meet some issues with encoding. Default encoding the source as UTF-8 will import and link with errors, as LibreOffice is considering the content as ISO (in my case ISO 8859-1) and the diagram will be wrong encoded. 

If you encode the source file with the same encoding than LibreOffice, the the imported or linked files will render correctly.

On Windows I use Notepad++ and encoding in UTF-8 BOM without problems.

## Graphwiz missing

On Windows I have discovered that sometimes PlantUML is complaining about Graphwiz not being present. 

Download Graphwiz from here and install it. That solved the problem for me.

# Compile

Just run ./make.sh Libo_PlantUML (on linux)

## Test

This extension has been tested with LibreOffice 6.0 and 6.1 on Windows and Linux.

## History

* 04.11.2018: 121
  * Checking for cursor is in a textframe.
  * Supports other types than PlantUML e.g., @startsalt and @startdot
* 17.10.2018: 1.2.0:
  * Added support for LibreOffice 6.1
  * Checking for cursor is in a table
  * Some minor fixes to UI.
* 27.04.2017: 1.1.0
  * Create new develop branch
  * Removed progress dialog and replaced with status bar.
* 23.04.2017: 1.0.0: 1.0.0
  * This initial version is a core transformation from the original macro by Poul Bondo (e-mail: pba@mailme.dk) here: http://sourceforge.net/projects/plantuml/files/plantuml.odt/download
