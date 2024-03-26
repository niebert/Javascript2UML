# Javascript2UML
This repository contains HTML file that is able to decompose Javascript Code and create a JSON file with an UML structure for the class. The class can be imported to ClassEditorUML. This workflow coontains two major steps:
* convert Javascript into an Abstract Syntax Tree (parsing e,g, with [ASTring](https://github.com/davidbonnet/astring)
* generate code from a given Abstract Syntax Tree.

## Parsers 
* [ASTring](https://github.com/davidbonnet/astring) contains a parser and a code generator.
* [PEG Javascript Paraser Generator](https://github.com/pegjs/pegjs)

## Installation 
* For installation call a `git clone` and the NPM `install` command
```bash
  git clone https://github.com/davidbonnet/astring.git
  cd astring
  npm install
```

## Workflow 
* load javascript file (e.g. `myscript.js`) with the `fs` module from the filesystem and store the loaded string in variable `str4code`
* use the variable `str4code` as input for the AST generator and you will obtain a JSON tree.
```javascript
const fs = require('node:fs');
const astring = require('astring');
// Make sure acorn and astring modules are imported

var str4code = fs.readFileSync('./myscript.js',
    { encoding: 'utf8', flag: 'r' });
// File is Javascript in version `ecmaVersion 6` and then call the parser to generate the AST
var ast4code = acorn.parse(str4code, { ecmaVersion: 6 })
// ast4code is a tree stored as JSON - to save the AST we convert the JSON into string
var ast4str = JSON.strinify(ast4code,null,4);
// now we save the ast4str into a file `myscript.ast`
fs.writeFile('./myscript.ast', ast4str, err => {
  if (err) {
    console.error(err);
  } else {
    // AST was written successfully as file 'myscript.ast' to filesystem
  }
});
```
 
