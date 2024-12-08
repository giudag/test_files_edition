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

 <p>The annotation model that I adopted is a stand-off markup. A stand-off markup is kept
               separate from the text and in my case it is found here, in the DAL-main file. Each
               transcription is stored in its own separate file.</p>
            <p>The laisses are embedded in "div" elements.</p>
            <p>Textual units are delimited by "anchor" elements alongside "xml:id" for the unique
               identification of the textual unit, in which I indicate the witness, a short name for
               the unit, and whether it is the start or the end of the textual unit.</p>
            <p>In the stand-off file I used "span" to define the portion of text I associated with a
               textual unit, specified by "ana" to point to a sample of notes containing the
               critical commentary on the characteristics of the textual units, "corresp" for
               linking the textual unit under observation to the same units, when present, in the
               other texts, "from" and "to" to refer back to the start and end of a unit defined by
               the "xml:ids" inside the "anchor" elements, "type" to specify whether the unit is a
               main unit or a sub-unit, "xml:id" to identify the witness that contains the unit and
               the name of the unit. Since "span" can contain itself, I used a nested hierarchy of
               "span" elements to include sub-units inside an episode, i.e., in the main "span".</p>
            <p>The "anchor" elements can be viewed as pins that fix a specific point in the text to
               which an identifier is assigned. It is an extremely neutral and flexible element
               which is not limited by literary genre nor the TEI hierarchy. A drawback, however, is
               that it is a self-closing element, which makes it hard to process it by XML parser,
               especially if it is used to delimit the beginning and the end of a portion of the
               text.</p>
            <p>The stand-off file was prepared to store information related to the textual units and
               their relationships separately, as opposed to in-line markup. The files containing
               the normalized transcriptions from the editions are thus more manageable because they
               contain only structural markup. Moreover, the problem of hierarchical constraints is
               solved with this method. Additionally, it gave me the possibility to take advantage
               of the fact that the element "span" contains a comment on the portion of text it is
               associated with to add a brief description of the textual units without cluttering
               the text files with information.
