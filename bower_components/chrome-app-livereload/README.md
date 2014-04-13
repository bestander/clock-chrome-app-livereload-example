chrome-app-livereload
=====================

Livereload script taken from tinylr that works with Chrome Apps

To make livereload work in Chrome Apps:

1. Include livereload.js in the folder build of Chrome App
2. Install tiny-lr with `npm install tiny-lr --save-dev`
3. Start tiny-lr in your dev task.
In gulp you can use this:
```
gulp.task('dev', function () {
    var lr = tinylr();
    lr.listen(35729);
    gulp.watch(['build/**/*.{js,css,jpeg,png}'], function (evt) {
        lr.changed({
            body: {
                files: [evt.path]
            }
        });
    });
});
```
4. Include livereload script in your index.html
```
<script src="livereload.js?host=localhost&port=35729"></script>
```


License MIT
####
Copyright 2012 Konstantin Raev (bestander@gmail.com)

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE
LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION
WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
