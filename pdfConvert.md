# pandoc pdf convert commands

```powershell
pandoc --pdf-engine=xelatex -V CJKmainfont="Microsoft YaHei" -o test.pdf test.md
```

--pdf-engine  
pdf-engine must be one of wkhtmltopdf, weasyprint, prince, pdflatex, lualatex, xelatex, latexmk, tectonic, pdfroff, context.  
xelatex supports Chinese characters.

