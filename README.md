# Javascript2UML
This repository contains HTML file that is able to decompose Javascript Code and create a JSON file with an UML structure for the class. The class can be imported to ClassEditorUML. This workflow coontains two major steps:
* convert Javascript into an Abstract Syntax Tree (parsing e,g, with [ASTring](https://github.com/davidbonnet/astring)
* generate code from a given Abstract Syntax Tree.

## Parsers 
* [ASTring](https://github.com/davidbonnet/astring) contains a parser and a code generator.
* [PEG Javascript Paraser Generator](https://github.com/pegjs/pegjs)

## Installation 
* `git clone´ and NPM install

  git clone https://github.com/davidbonnet/astring.git
  cd astring
  npm install


## Workflow 
* load javascript file with the `fs` module from the filesystem
