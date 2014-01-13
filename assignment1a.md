Kyle Jorgensen

Assignment 1A


## TeraShake Visualization

The application of parallel computing that I found was an earthquake visualization project organized by the [Southern California Earthquake Center (SCEC)](http://www.scec.org/). This high-performance computing project was in coordination with researchers from the San Diego Supercomputing Center at UCSD.  

The southern section of the San Andreas fault has not seen a major event since 1690, which leads seismologists to say that the "big one" is coming to Southern California sometime soon. The [Terashake project](http://visservices.sdsc.edu/projects/scec/terashake/) does not focus on predicting when this next big earthquake will occur; rather, it tries to predict the detailed ground motion that would result after a large earthquake. 

### Modeling Details

The geographic region used for the study was a large rectangular volume box 600 km by 300 km by 80 km deep.
![region](http://visservices.sdsc.edu/projects/scec/terashake/images/map_inlay_location3.jpg)

This was the biggest and most detailed simulation of this region to date---using a 3,000 by 1,500 by 400 mesh, dividing the region into 1.8 billion cubes with a spatial resolution of 200 meters on a side. 

The TeraShake model looked at a scenario where a 230 km section of the San Andreas fault could rupture from north to south, producing a 7.7 magnitude earthquake. Based on models of the different sediment layers throughout the area, researchers studied which areas around Southern California would be severely impacted from an earthquake like this. 

### Big Computation and Big Data

Not only was this project computationally-intensive, but also it created a huge amount of output data. Here is a description from Paul Tooby of the SDSC:

> Using some 18,000 CPU hours on 240 processors of the new 10 teraflops IBM Power4+ 
DataStar supercomputer at SDSC, the model computed 20,000 time steps of about 1/100 second 
each for the first 220 seconds of the earthquake, producing a flood of data.

In the end, the team produced 47 TB of data, in about 150,000 files, which meant nearly 10 TB of output per day. 

To simulate the propagation of the seismic waves, the researchers used the Anelastic Wave Model (AWM), a fourth-order finite difference code developed by a professor at SDSU. This code models the 3D velocity in the volume and the surface of a given domain. In order to deal with the scale of the data, and the scale of the DataStar computing platform, the researchers and SDSC collaborators spent many hours porting the code and optimizing for parallel performance on the high-performance hardware. 

Once all the output was generated, a specialized visualization was created using SDSC's [Vista](http://www.sdsc.edu/us/visservices/software/vista/) volume renderer. According to the SDSC website, "VISTA is a multithreaded, platform-independent, scalable and robust volume renderer." The data sets were rendered in both 2D and 3D maps, showing the seismic wave velocity after the simulated earthquakes. The maps can be found [here](http://visservices.sdsc.edu/projects/scec/terashake/2.3/). 

![](http://visservices.sdsc.edu/projects/scec/terashake/2.3/images/TS2.3_vol_vx_headon_1920.png)


![](http://visservices.sdsc.edu/projects/scec/terashake/2.3/images/Terashake2.3_surface_Vy_1280.png)

## My Evaluation

When I looked up this project, some of the web pages seemed a little outdated, and the Vista visualization software is no longer in development by the SDSC. I found [a news article] from 2006 which discusses the project, meaning that this computation was performed about 8 years ago. Putting this in perspective with regards to how quickly new computing hardware is developed, the TeraShake project was a very impressive achievement. Looking back at the Top 500 rankings, the DataStar machine used for this project was ranked as high as [35th in the world in November 2005, and was last seen on the Top 500 list in June 2008](http://www.top500.org/system/174264). Thus, at the time, these TeraShake calculations were being processed on one of the fastest computers in the world. 

I'm not very familiar with Anelastic Wave Modeling for geophysics, but it seems like this is a very appropriate application for parallel/high-performance computing. These large-scale simulations provide valuable information for data scientists to predict earthquake waves. This project is definitely an important step in advancing the Southern California Earthquake Center's (SCEC) goal of gathering data to help better predict and understand earthquake phenomena.

## Sources

* http://www.ttivanguard.com/sfreconn/terashake.pdf
* http://visservices.sdsc.edu/projects/scec/terashake/
* http://www.scec.org/research/video/
* http://www.sdsc.edu/us/visservices/software/vista/
* http://www.scec.org/research/




