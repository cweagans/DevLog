---
id: ZGHsOa3hTe3xFSrhjl4sq
title: Pypdf2
desc: ''
updated: 1641417201000
created: 1641105063862
stub: false
isDir: false
---

- Use this to append all PDF's in the given directory into 1

```python
import PyPDF2, os

# Get all the PDF filenames.
pdfFiles = []
for filename in os.listdir('.'):
  if filename.endswith('.pdf'):
	  pdfFiles.append(filename)
pdfFiles.sort()

pdfWriter = PyPDF2.PdfFileWriter()

# Loop through all the PDF files.
for filename in pdfFiles:
  pdfFileObj = open(filename, 'rb')
  pdfReader = PyPDF2.PdfFileReader(pdfFileObj)

  # Loop through all the pages (except the first) and add them.
  for pageNum in range(1, pdfReader.numPages):
	  pageObj = pdfReader.getPage(pageNum)
	  pdfWriter.addPage(pageObj)

# Save the resulting PDF to a file.
pdfOutput = open('allminutes.pdf', 'wb')
pdfWriter.write(pdfOutput)
pdfOutput.close()

```