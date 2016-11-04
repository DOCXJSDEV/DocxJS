[![|DOCXJS](https://www.docxjs.com/images/poweredbydocxjs.png)](https://www.docxjs.com) 

## DOCXJS
> No server! Only Javascript - HTML5 document platform 

examples, please visit to jsfiddle. [DEMO](https://jsfiddle.net/DOCXJSDEV/9t9x8xL9/1/)


# [Simple Basic Example]

```javascript
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>DocxJS Example</title>
        <script type="text/javascript" src="https://code.jquery.com/jquery-2.2.4.min.js"></script>
        <script type="text/javascript" src="https://www.docxjs.com/js/build/latest.docxjs.min.js"></script>
    </head>
    <body>
        <input id="inputFiles" type="file" name="files[]" multiple="false">
        <div id="loaded-layout" style="width:100%;height:800px;"></div>
        <script>
            $(document).ready(function(){
                var $inputFiles = $('#inputFiles');
                $inputFiles.on('change', function (e) {
                    var files = e.target.files;
                    var docxJS = new DocxJS();

                    docxJS.parse(
                        files[0],
                        function () {
                            docxJS.render($('#loaded-layout')[0], function (result) {
                                if (result.isError) {
                                    console.log(result.msg);
                                } else {
                                    console.log("Success Render");
                                }
                            });
                        }, function (e) {
                            console.log("Error!", e);
                        }
                    );
                });
            });
        </script>
    </body>
</html>
```

### DocxJS has a few special features : 
[Only Javascript]
* Whether you are online or offline, all you need for DOCXJS is an internet browser because it is implemented in JavaScript only.

[Provide Data] [DEMO](https://www.docxjs.com/demo/provide)
* Use a simple Json data provided by DOCXJS. You can easily turn a set of DB data into a document and vice versa.

[Extract Docx] [DEMO](https://www.docxjs.com/demo/extract)
* DOCXJS can extract data not only from a text-based document, but also a Word document with shapes and style.

[RENDERING DOCX] [DEMO](https://www.docxjs.com/demo/viewer)
* DOCXJS documents can be rendered from HTML5-based browser in any OS or device.


### Contacts
* Email: support@docxjs.com