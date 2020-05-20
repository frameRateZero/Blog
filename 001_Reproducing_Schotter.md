# Reproducing Schotter as an Obligatory 'Hello World!'

Over the last 50 years, computer programmers have ritualized printing "Hello, World!" as a first simple program.<sup>[1](#myfootnote1)</sup> Printing some words is as basic as it gets. But "Hello, World!" is more than a test program.

For beginners like me, it is a rite of passage - an anouncement. It feels a little like a coming of age ceremony. So, how do generative artists initiate this "Hello World"?

First, here's some background. For generative artists, the programed code produces images and graphics. An algorithm, a set of rules procedure, tells the computer to draw lines or color pixels. So, the most basic "Hello World" program for a generative artist must draw something and use an algorithm. Not any loop with a random variable will do. A poor example is a static noise generator.


A static generator meets the letter, but not the spirit of "Hello World". "Hello, World? is anybody out there?" or "Hello World!, look at this!" The phrase "Hello World" has fungible meanings, deeper by fathoms than "Hi, this program works", and can be punctuated more than 8 different ways:
```markdown
- Hello World
- Hello World.
- Hello World!
- Hello World?
- Hello, World
- Hello, World.
- Hello, World!
- Hello, World?
- Hello...World...
```

## Why Schotter
For generative artists reproducing Georg Nees' classic "Schotter" (Gravel) work from the mid 1960s is the obligatory announcement. Georg Nees was a pioneer of computer art, showcased in a 1965 exhibition plainly called “Generative Art” <sup>[2](#myfootnote2)</sup> Nees' work was paired with Max Bense's paper "The projects of generative aesthetics" in the avant-garde booklet *rot.* in issue no 19. <sup>[3](#myfootnote3)</sup>. Bense's essay is considered to be the first manifesto of computer art.<sup>[2](#myfootnote3)</sup>. Here is a link to the translation from German using google translate.<sup>[4](#myfootnote4)</sup>, <sup>[5](#myfootnote5)</sup> 

Frankly, I don't understand most of the manifesto *yet*, but nevertheless it provides an important context for today's computer artists. The following translated quotes, in particular, are worth a think. 

> It is clear that every generative aesthetic, which of course enables an aesthetic synthesis, is preceded by an analytical aesthetic, the process of which is used to prepare aesthetic structures from given works of art, which are their carriers, as aesthetic information. this prepared aesthetic information must be abstractly describable in order to be planned and implemented as planned in a concrete amount of material elements. There are currently four options for such an abstract description of aesthetic states (distributions or designs) that can be used to produce aesthetic structures. The semiotic, which is classifying, and the metric, statistical and topological, which are numerically and geometrically oriented.

![Image](https://github.com/frameRateZero/Blog/blob/media/rot19Cover.jpg?raw=true){:height="45%" width="45%"}
![Image](https://github.com/frameRateZero/Blog/blob/media/rot19kBild2.jpg?raw=true){:height="45%" width="45%"}


## Making Schotter

![Image](https://github.com/frameRateZero/Blog/blob/media/2009CE0997_2500.jpg?raw=true){:height="50%" width="50%"}

(Lithograph in black ink from a computer-generated graphic, 'Schotter', 1968-1970, by Georg Nees.)<sup>[6](#myfootnote6)</sup>


There are many, many reproductions, and many derivatives because it is visually compelling, understandable, simple. The algorithm draws 12 columns and 22 rows of squares. Progressively by row, the rotation and "jitter" or offset applied to the square increases. One interpretation of Schotter is that it shows "the relationship between order and disorder, and the effects of change."<sup>[7](#myfootnote7)</sup> Below is a jargon-full description of the algorithm Nees used.

> Schotter is produced by invoking the SERIE procedure. The non-parametric procedure QUAD serves to generate the elementary figure which is reproduced multiple times in the composition process controlled by SERIE. QUAD is located in lines 4 through 15 of the generator. This procedure draws squares with sides of constant length but at random locations and different angles. From lines 9 and 10, it can be seen that the position of a single square is influenced by random generator J1, and the angle placement by J2. The successively increasing variation between the relative coordinates P and Q, and the angle position PSI of a given square, is controlled by the counter index I, which is invoked by each call from QUAD (see line 14).<sup>[7](#myfootnote7)</sup>

What we know is that the counter index is for the rows. What we don't know explicitly, and I've not found on the web, is how the randomness, for position and rotation, changes per n rows. The original change per n rows is not obvious. The reproduction on the right (from artsnova website)<sup>[8](#myfootnote8)</sup> increases the "disorder" more gradually than the original on the left.

![Image](https://github.com/frameRateZero/Blog/blob/media/Capture_artsnova_schotter.JPG?raw=true){:height="80%" width="80%"}


## Re-Making Schotter

For a more faithful approximation, I got out the ruler and protractor and measured the position change and rotation. It appears that the rotation and offset ranges increase linearly with I rows. Also, the rotation and offsets are not correlated, indicating Nees used three unique random values per square - rotation, x-offset, and y-offset. 

Rotation range simply appears to multiply by 2 per row, starting at 2 degrees and maxing out at 44 degrees. For the x and y offsets, the max offset is proportional to the row index. It would be nice if this was simple. It looks like it really is simple, but I could be wandering lost; the offset random range appears to be just scale with the Row index. Let's try it and see, compared to the lithograph version above.

![Image](https://github.com/frameRateZero/Blog/blob/media/2009CE0997_2500.jpg?raw=true){:height="40%" width="40%"}
![Image](https://github.com/frameRateZero/Blog/blob/media/SchotterClassic1022.png?raw=true){:height="40%" width="40%"}


I put my Processing sketch of the "Classic" reproduction an others I've collected in a repo called [Schotter Sketches](https://github.com/frameRateZero/Blog/blob/SchotterSketches).
```
<iframe src="https://www.openprocessing.org/sketch/901305/embed/" width="400" height="300"></iframe>
```
## Footnotes
<a name="myfootnote1">1</a>: "Hello, World!", Wikipedia, accessed 5/19/2020. [Link](https://en.wikipedia.org/wiki/%22Hello,_World!%22_program)

<a name="myfootnote2">2</a>: The Pioneer of Generative Art: Georg Nees. Frieder Nake. Leonardo 2018 51:3, 277-279.
[Link](https://www.mitpressjournals.org/doi/abs/10.1162/leon_a_01325?mobileUi=0&)

<a name="myfootnote3">3</a>:rot. no 19 .[PDF](http://dada.compart-bremen.de/docUploads/rot19k.pdf) 

<a name="myfootnote4">4</a>:my tranlsation of Max Bense's "projects of generative aesthetics" manifesto via Google Translate. [LINK](https://github.com/frameRateZero/Blog/blob/media/MaxBense_ProjectComputerGraphic_translated.docx)

<a name="myfootnote5">5</a>:Apparently, a translation is also available in the hard to come by book "Cybernetics, Art, and Ideas", Reichardt, Jasia, ed. 1971. [LINK](http://dada.compart-bremen.de/item/publication/339)

<a name="myfootnote6">6</a>:Lithograph in black ink from a computer-generated graphic, 'Schotter', 1968-1970, by Georg Nees from V&A Collections.[LINK](https://collections.vam.ac.uk/item/O221321/schotter-print-nees-georg/)

<a name="myfootnote7">7</a>:text describing the Schotter code is here [LINK](http://www.medienkunstnetz.de/works/schotter/)

<a name="myfootnote8">8</a>:screen capture from artsnova showing an original side by side with a reproduction [LINK](http://www.artsnova.com/Nees_Schotter_Tutorial.html)

