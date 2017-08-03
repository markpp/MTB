# MTB
A project for detecting and counting mountain bikers and people walking in the forrest using a small bird house looking box, containing a low resolution thermal camera and a Raspberry Pi 2. The recording time is limited by the battery capacity, which currently provides us with around 12 hours of recordings.

![box_content](data/examples/box.png "Content of bird box") ![setup_example](data/examples/marked_box.png "Bird box placed in tree with view of path") ![output_example](data/examples/Intensity2.png "Example of a captured thermal image(mapped to fit 8bit)")  

## TODO
This overall todo list is prioritized according to what needs to be done first.
1) Create a poster for september
2)Contributing to scientific paper writing
3) Implement improvements to e.g. the detection and tracking
4) Capturing and annotating data
5) Automated data collection by use of e.g. data connection + presentation of data
6) Bringing the HW and SW of the prototype to a stage where the system can easily be used by non-technical persons

- When evaluating the detector extract some correct and some wrong detections for the paper and poster. also try to perform clustering based on the features and visualize the distribution along with labels.(example: http://cs.stanford.edu/people/karpathy/cnnembed/)

# Data

| Name             | Time(wrong) | Place         |Start time| BB anno            | Event anno         | Comments | Usage |
| ---------------- |:-----------:|:-------------:|:--------:|:------------------:|:------------------:|:--------:|------:|
| 2015-09-02-12-44 | Sat 29 Sep  | Hammer Bakker | 11:00:00 | :heavy_check_mark: | :heavy_check_mark: | ok       | train |
| 2015-09-28-12-39 | Sun 30 Sep  | Kongshøj      | 11:00:00 | :heavy_check_mark: | :heavy_check_mark: | ok       | train |
| 2015-09-29-12-43 |             | Kongshøj      |          |                    |                    | Poor view|       |
| 2015-09-30-06-23 | Fri 2 Oct   |               | 11:00:00 |                    |                    | ok       | test  |
| 2015-09-30-11-17 | Sat 3 Oct   | Hammer Bakker | 11:00:00 |                    |                    | difficult|       |
| 2015-10-05-15-56 | Man 5 Oct   | Kongshøj      | 11:00:00 |                    |                    | ok       | test  |
| 2016-08-08-11-00 | Man 8 Aug   | Hammer Bakker | 11:00:00 | :heavy_check_mark: | :heavy_check_mark: | ok       | train | 
| 2016-08-09-14-58 | Wed 10 Aug  | Hammer Bakker | 11:00:00 | :heavy_check_mark: | :heavy_check_mark: | ok       | test  |
|                  | Sun 14 Aug  | Månedalen     | 11:00:00 |                    |                    |          |       |

# Data Information

| Name             | Hours     | MTB Count |PED Count | 
| ---------------- |:---------:|:---------:|:--------:|
| 2015-09-02-12-44 | 00:00:00  | 0         | 0        | 
| 2015-09-28-12-39 | 04:07:39  | 64        | 2        |     
| 2015-09-30-06-23 | 05:17:00  | 42        | 5        | 
| 2015-10-05-15-56 | 06:33:47  | 47        | 4        |  
| 2016-08-08-11-00 | 05:39:40  | 29        | 5        | 
| 2016-08-09-14-58 | 00:00:00  | 0         | 0        | 
| **Totals:**      | 00:00:00  | 0         | 0        |


# Software
The project is primarily written in python, originally some parts were written in c++ but later every component should now be available in python.

## Getting up and running
More details on using either of the two primary groups of code is described in detail in their respective readmes.

### Data capture
"thermal capture" contains the program and scripts that runs on the raspberry pi for capturing and storing 16 bit 80x60 images at 7 fps to sd card.

### Data processing
"data processing" contains code for preparing and processing the frames after they have been captured on the raspberry pi.

detection

evaluation

#### Annotations
The annotations are located under /data/annotations/ in this repository.
TODO: annotate events in remaining clips(4)

Event annotation using [RUBA](https://bitbucket.org/aauvap/ruba/downloads/)

BB annotation using [BBA](https://bitbucket.org/aauvap/bounding-box-annotator/downloads/)

# Hardware
Computer: Raspberry Pi 2

Thermal camera: Lepton LWIR 80 × 60

Power: 10.400mAh
