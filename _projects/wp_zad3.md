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
* It allows the user to create the starting slide with the info tag, that contains headers only and has vertically aligned headers (unlike the rest of the presentation). Then a set of slides can be produced. To separate it into sections, the user can create slides containing only sectioninfo, that will serve as separators.
* Slides themselves contain a header and a complex type text, which is basically an order of paragraphs, lists and images. 

### Used Tools 
* All files have been written in plain and simple Notepad++ and checked and validated via online XML formatting and validating tools such as <a href="https://www.xmlvalidation.com"/> XML Validation </a> or <a href="https://www.freeformatter.com/xml-formatter.html"/> Free Formatter </a>.
* To transform the data into the demanded file formats, **SAXON** of version 8 or higher and **XEP** tools have been used.
* A batch file containing a set of instructions to run the transformations is included in the archive. Instructions can be found in the **Z3-Varga.txt file** included in the submitted zip archive.

### Transformation

* The transformation to **PDF** will include two steps, transforming the data into a formatted object file, **fo.xml**, and then using XEP to produce the demanded **PDF** file.
* As for the **XHTML**, several .html files will be produced, named slide(n) with n representing their order in the presentation. Two buttons for previous and next slide are added at the bottom of each slide to enable listing through them.
* The user can set some of the nodes' properties. A custom **ephasis** role, which I used in the second project, was also imported here - a simple combination of bold font and italic style for text. Also, image width, height etc. is also set through attributes. These changes will be processed during the transformation.

#### XML -> XO -> PDF Transformation

* First the root node is matched, and two layout master sets are set. Both differ only in the vertical alignment of elements. Then two page sequences are generated, one by searching for info tags and other for slide tags. Both apply the corresponding templates - header or header+text.
* Within the transformation, fo:blocks will be added with font and other settings each.
* A buletted list is also included as an option in the doctype. So the transformation handles as many elements as needed, using simple black dots for bullets. 
* Images can be also added with a given width and height. If they are absent, default values will be set. Images can be included in the transformation directory WEB-3-PRZNT so that full file paths can be omitted and only the filenames can be used.
* In case the entire slide content does not fit in the page, a new page will be generated automatically.
* On successful transformation, an **output.pdf** file will be generated in the folder.

#### XML -> XHTML Transformation

* For this transformation, the xsl:result-document href is set by the position of the currently inspected node. As in the previous transformation, info and slide nodes are looked for at the start as thy are the child nodes of the root node.
* For each generated file, a **CSS** file is linked in the main template. It is included already in the folder.
* Switch buttons at the bottom of the screen to list through the presentation are added in a small table. On first and last page, only one button is needed (as you can't go to slide 0) so the other one is not generated.
* Similar to the PDF transformation, templates for individual nodes such as paragraph, item etc. are generating their content. There is not to very little style applying in the transformation, as the majority of it is handled by the **CSS** file.
* On successful transformation, several **slideN.html** files will be generated in the folder and linked in a list to one another.
