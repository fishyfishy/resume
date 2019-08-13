# Resume

## Setting up Environment

### Setting up a Windows Environment

1. Install basic-miktex-2.9.6161-x64.exe
2. Have res.cls on the path
3. Run and install all packages.

### Setting up a Mac Environment

1. Install [MacTex](http://www.tug.org/mactex) and follow additional instructions
2. Install additional packages

#### Using MacTex for updating environment
Click on the Typeset button after choosing the typeset to generate a new PDF of the resume.

### Compressing PDF
The default generated PDF will be produced at screen level quality and some space saving gains can be had by compressing the file with ghostscript.  Ghostscript is used internally in other compression programs and comes with a MAC OS X environment.  Ghostscript can also be installed using cygwin.  

Using the below command, the PDF can be compressed in size by reducing the size of embedded images.  
```sh
gs -sDEVICE=pdfwrite -dCompatibilityLevel=1.4 -dPDFSETTINGS=/ebook -dNOPAUSE -dQUIET -dBATCH -sOutputFile=compressed_file.pdf big_file.pdf
```  

Space saving gains for the original resume reduced from 1.1 MB to 50 KB.  

Compression level settings using the `-dPDFSETTINGS switch:
* `-dPDFSETTINGS=/screen`   (screen-view-only quality, 72 dpi images)
* `-dPDFSETTINGS=/ebook`    (low quality, 150 dpi images)
* `-dPDFSETTINGS=/printer`  (high quality, 300 dpi images)
* `-dPDFSETTINGS=/prepress` (high quality, color preserving, 300 dpi imgs)
* `-dPDFSETTINGS=/default`  (almost identical to /screen)

For more information:  
https://tex.stackexchange.com/questions/14429/pdftex-reduce-pdf-size-reduce-image-quality
