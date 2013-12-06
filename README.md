E4X2ED
======

ECMAScript library to convert ECMAScript  for XML (E4X) into ECMAScript using DOM

*This is currently an experimental library to test the feasability of such a project.*

Expected sample usage:

    <html>
        <head>
            <script type="application/ecmascript" src="e4x2ed.js"></script>

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
                e4x2ed.load('myCode.e4x');
                e4x2ed.eval('var myDoc = <MyDoc></MyDoc>;');
            </script>
        <body>
    </html>