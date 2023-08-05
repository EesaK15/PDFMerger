# PDF Merger
## This project allows you to merge all PDF files in a folder into a single, consolidated PDF document.


 #### Begin by importing necessary libraries
```
from pypdf import PdfMerger # Importing to Merge PDF
import os # Used for listing the files
```
In this code, we are importing the PdfMerger class from the PyPDF2 library to merge PDF files, and we are also importing the os module to list files in the directory.

```
def pdfmerging(direc, final_output): # Creates to merge the PDFS
    merges = PdfMerger() # PdfMerger merges multiple PDFs into a single PDF.
                        # It can concatenate, slice or insert .
    
    for file in os.listdir(direc): # will iterate for every file in such directory
        path = os.path.join(direc, file) # combines path names into one complete path
        merges.append(path) # appends the files together
        
    output_path = os.path.join(direc, final_output) # creates a final output path
                                                    # to where it will be stored
    
    merges.write(output_path)
    merges.close()
```
#### Declaring locations
```
# Paths and Name of File 
direc_path = 'PATH OF DIRECTORY'
final_output = 'NAME OF MERGED FILES .pdf'

# Calls Method
pdfmerging(direc_path, final_output)
```
