E4X2ED v0.0.1
=============

ECMAScript library to convert ECMAScript  for XML (E4X) into ECMAScript using DOM

*This is currently an experimental library to test the feasability of such a project.*

Sample Usage
---------------------

    <html>
        <head>
            <script type="application/ecmascript" src="e4x2ed.es"></script>

            <!-- For backwards compatibility with MDN E4X implementation -->
            <script type="text/javascript;e4x=1">
            </script>

            <!-- For future E4X script -->
            <script type="application/ecmascript+xml">
                var myDoc = <MyDoc></MyDoc>;
            </script>
        </head>
       <body>
            <script type="application/ecmascript">
                e4x2ed.load('myCode.js');
                e4x2ed.load('myCode.es');
                e4x2ed.eval('var myDoc = <MyDoc></MyDoc>;');
            </script>
        <body>
    </html>

or

	var e4x2ed = require('e4x2ed');
	var mye4xDependency = require('mye4XCode.es');
    e4x2ed.eval('var myDoc = <MyDoc></MyDoc>;');

 High Level Design
 -----------------

	1. Parse the E4X into a node tree
 	2.
 		a. Walk the node tree writing the result to an output (string?)
    	OR
 		b.  Walk the node tree executing the result as you go.

 	*In case of parse errors, throw an error with the line and position # as well as a list of expected tokens.*

Non-Functional Requirements
---------------------------

Security
- Assumes trust in the data source
- Review security after initial implementation is complete.

Performance 
- Will this be fast/efficient? (Can this be quantified?)

Reliability
- The grammar to parse the e4x will need to be complete.

Usability
- Will the first sample be feasible? Will it be possible to stop the browser treating and "text/javascript;e4x=1" files as plain javascript files?

Dependencies
- No dependencies on any third-party libraries, or, only dependencies on light-weight open source libraries.

Cross-Platform
- MUST work in latest version of Firefox, Chrome, Safari, Internet Explorer, Opera, node.js and Rhino.
- SHOULD work in older versions (to be qualified) of web browsers/javascript engines.

Testing
- All code will be unit tested using Mocha (Sinon, Chai)

Documentation
- Other than this document, no other documentation is expected to be required. Further reading regarding E4X can be found elsewhere on the internet (such as https://developer.mozilla.org/en/docs/E4X)

Extensibility
- It is assumed there will be no need to extend the library.

Packaging / Deployment
- Grunt shall be used to package the e4x2ed library.

Road Map
--------

*Version 1.0.0*

- Extend Esprima to support E4X
    - Feature X
    - Feature Y
    - Feature Z
- Implement a walker to output to a string
    - ES to ES
    - Feature X
    - Feature Y
    - Feature Z

*Version 2.0.0*

- Implement a walker to execute
    - ES to ES
    - Feature X
    - Feature Y
    - Feature Z
