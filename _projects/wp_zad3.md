---
title: "Project no. 3 - XML Presentation"
---
### Intro
This is a documentation of the third and last assignment in Web Publishing. I have created an **XML** presentation of my Bachelor's Thesis and have written transformation files, so it can be transformed it into a **PDF** file and into an **XHTML** fileset.

### The Presentation
* The presentation was written in XML format. It contains a simple overview of my Bachelor's Thesis. It is represented by a root node - presentation. Following nodes are info and slide, of which the former is mandatory and the latter has to have at least one occurence in the presentation.
* There are several types of headings to be used, grouped and ordered in headers, with one heading per heading type and per slide. Special sectioninfo headers are used to mark beginnings of individual section-like parts of the presentation. Other slide contents are paragraphs and images grouped under the text tag. 

### DTD
* A corresponding DTD to validate the presentation has been formed. It contains the above mentioned rules, orderings of elements into the header and text section in slides and also the number of occurences per each element. It is linked to the presentation file via an extern Doctype declaration.

### Used Tools 
* All files have been written in plain and simple Notepad++ and checked and validated via online XML formatting and validating tools such as <a href="https://www.xmlvalidation.com"/> XML Validation </a> or <a href="https://www.freeformatter.com/xml-formatter.html"/> Free Formatter </a> 

### Basics of the Trasnformation

### XML -> XO -> PDF Transformation

### XML -> XHTML Transformation
