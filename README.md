!!! During the review phase of this PhD project my data are distributed with a CC-BY-NC-SA license !!!

PHD PROJECT: A SYNOPTIC DIGITAL EDITION OF THE ALEXANDERLIED

The Alexanderlied is a Middle High German poem belonging to the wider international 
historiographical, literary and paradoxographical tradition on Alexander the Great. It is 
handed down in three different versions, which share a common nucleus but diverge from one 
another substantially enough that they can be considered independent rewritings of a lost 
original. Synoptic editions, as editions that present the texts of two or more witnesses close to 
one another, generally side-by-side, are a useful resource because their purpose is to facilitate 
the comparison of the varia lectio and the individuation of relationships inside the tradition. 
Due to the high textual mobility of the three versions of the Alexanderlied, the considerable 
number of sources they draw from, and the Daedalian relationships among them, a 
comparative study by means of a synoptic edition can indeed assist in the understanding of the 
Alexandrian lore in the German Middle Ages. Synoptic editions of poetic-narrative texts from 
the Middle High German period do exist, but they are mostly dealing with authorial works 
with a relatively higher stability and uniformity than the redactions of the Alexanderlied, for 
which the comparison by metrical units, verses or couplets, proved unfeasible. Moreover, in 
the analog paradigm of the printed page, synoptic editions are often difficult to read and 
manage, whereas a digital environment has the potential to support the collation process and 
analysis through various tools and visualization strategies. Therefore, the focus of this PhD 
project is the creation of a synoptic digital edition of the three recensions of the 
Alexanderlied. The three redactions were divided into textual units, which were encoded and 
linked to one another according to the TEI-XML conventions. The annotation model was later 
used as the basis for the development of a web application, namely a prototype for the parallel 
visualization and basic query of the encoded data, generated thanks to the transformation of 
the XML data into HTML with XSLT. The ultimate wish for this work is to provide new 
knowledge and a new product for the disciplines Germanic Philology and Digital Humanities. 
The annotation model and the comparative research/study tool which stemmed from the use 
of the Alexanderlied as a case study were in fact designed with the ambition to let them be 
applied to other textual traditions.


----------------------------------------


DESCRIPTION OF THE ENCODING MODEL

The annotation model that I adopted after these trials is a stand-off markup. A stand-off markup 
is kept separate from the text and in my case it is found in the file DAL-main. The encoding is 
based on the following TEI elements and attributes: 

• In the files with the texts:

o <pb/> to indicate the beginning of a new manuscript folium or, in the case of S, of a new page of the print edition, accompanied, in alphabetical order, by: 
▪ @facs for linking to the facsimile of the folium/page 
▪ @n for the folium/page number 
▪ @xml:id for the unique identification of text and folium/page 

o <div> for the laisses, with: 
▪ @n for numbering 
▪ @type to specify that the portion of text embedded in <div> is a laisse or a paragraph for B 
▪ @xml:id for the unique identification of witness, unit of lines (i.e. a <div>), and number of the laisse/paragraph 

o <l> for each verse line, with the addition of: 
▪ @n for numbering 
▪ @xml:id for the unique identification of witness, unit (i.e. a <l>), and line number 

o <anchor/> to delimit the beginning and end of a textual unit, alongside: 
▪ @xml:id for the unique identification of the textual unit, in which I indicate the witness, a short name for the unit, and whether it is the start or the end of the textual unit 

o <gap/> for lacunae in the text, according to the editions I used, and to indicate the end of the common nucleus, with: 
▪ @ana to clarify the type of gap 
▪ @extent for the lacuna caused by the loss of S’s bifolium 
▪ @reason to explain the presence of the gap 
▪ @resp to indicate the people responsible for the choice and/or the annotation 
▪ @quantity for the number of missing units in S 
▪ @unit for the measurement of the gap in S 

• In the stand-off file: 

o <spanGrp> to group together a series of <span> elements, accompanied by: 
▪ @xml:id to specify what kind of items the group of <span> elements contains 

o <span> to define the portion of text I associated with a textual unit, specified by: 
▪ @ana to point to a sample of notes containing the critical commentary on the characteristics of the textual units (4.2.3.2) 
▪ @corresp for linking the textual unit under observation to the same units, when present, in the other texts 
▪ @from and @to to refer back to the start and end of a unit, defined by the @xml:ids inside the <anchor> elements 
▪ @type to specify whether the unit is a main unit or a sub-unit 
▪ @xml:id to identify the witness that contains the unit and the name of the unit’s name 

Since <span> can contain itself, I used a nested hierarchy of <span> elements to include sub-units inside an episode, i.e. in the main <span>. The embedded <span> elements are accompanied by the same attributes previously mentioned for the main ones.
