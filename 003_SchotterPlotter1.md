# Schotter Reducts -- Pen plotting, part 1

The generative art pipeline too often goes from algorithm to screen-based image, ending with beautiful pixels and user interfaces. The algorithm is not the art. The opportunity here is to convey ideas and meaning with an appropriately paired algorithm and enhance the program output with a physical manifestation. Screens and paper prints are the most acceible and common. Laser engravers, vinyl cutters, embroiders, and really any computer controlled tool can be used to use an algorithm to render art. Here, in the first of two parts, I show some pen plots and discuss process. 

In my last two posts about George Nees classic work "Schotter", I posited that it the obligatory ["Hello World" test program for generative artists](https://frameratezero.github.io/frameRateZero/001_Reproducing_Schotter) and in the second post, I showed some riffs on the simple algorithm,  building off the order --> disorder concept of "Schotter", that I rendered into 100 unique [generative zines](https://frameratezero.github.io/frameRateZero/002_PlayingWithBlocks) and printed on paper. 

Some of the earliest generative art works were rendered on paper using pen plotters. A pen plotter is a drawing tool that holds a pens and controls the movement of the pen. Commonly, pen plotters can move in the x and y directions, although there are other flavors. Pen plotters excel at line drawing on paper and so the plotter instructions are coordinates on that plane derived from vector images. The Schotter algorithm, drawn as vectors in a program like Processing, is perfect for driving a plotter.

Below, I show some pen plots using an AxiDraw V3/A3 controlled by inkscape, from Processing output svg files. The pen plots are variations with the Schotter algorithm. Plotting with ink on paper is truly transformative. It allows artistic intent to be enhanced by paper and pen selection, as well as settings used on the equipment.  

![Image](https://github.com/frameRateZero/Blog/blob/media/20200525082517892_0001_crop.jpg?raw=true){:height="45%" width="45%"}
![Image](https://github.com/frameRateZero/Blog/blob/media/20200525082517892_0002_crop.jpg?raw=true){:height="45%" width="45%"}
**Playing With Blocks. Canson Mix Media paper with Sigma Micron pens. (Left) good registration, (Right) misaligned**

In Playing With Blocks, I learned how pen alignment can change the image - both in regards to image quality and artistic effect. Wharhol, for example, used diliberate misalignment. Here, I think the misalignment adds to the sense of motion, to the cadence breaking while the eye reads the blocks, and in the generative art pipeline enhances the conveyance of idea(s).   



There are many reproductions and many derivatives of Schotter, like the ABC blocks above, because it is visually compelling, understandable, simple. The algorithm draws 12 columns and 22 rows of squares. Progressively by row, the rotation and "jitter" or offset applied to the square increases. One interpretation of Schotter is that it shows "the relationship between order and disorder, and the effects of change."<sup>[1](#myfootnote1)</sup> I go into much more detail about Schotter another [post](https://frameratezero.github.io/frameRateZero/001_Reproducing_Schotter). 

