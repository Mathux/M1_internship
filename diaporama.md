## Detection of occluded object in videos
#### Internship in CMU
    
  
Mathis Petrovich



##  
<!-- -- data-background="https://perso.crans.org/petrovich/images/carte.png" data-background-transition="zoom"  -->



## The university
<image src="https://perso.crans.org/petrovich/images/carte_cmu.jpg" controls style="width:80%" ></image>


## The university
<image src="https://perso.crans.org/petrovich/images/uni/cmu3.jpg" controls style="width:70%" ></image>


## The university
<image src="https://perso.crans.org/petrovich/images/uni/cmu1.jpg" controls style="width:70%" ></image>


## My lab
<!-- <image src="https://perso.crans.org/petrovich/images/uni/cmu2.jpg" controls style="width:40%" ></image> -->
<image src="https://perso.crans.org/petrovich/images/uni/bureau1.jpg" controls style="width:75%" ></image>


## Shuttle and escort
<image src="https://perso.crans.org/petrovich/images/shuttle.jpg" controls style="width:100%" ></image>

<!-- ## Some facilities
<image src="https://perso.crans.org/petrovich/images/uni/cmu4.jpg" controls style="width:40%" ></image>  <image src="https://perso.crans.org/petrovich/images/uni/cmu4.jpg" controls style="width:40%" ></image>-->



## Person I worked with

| My advisor                                                            | My team                                                               |
|-----------------------------------------------------------------------|-----------------------------------------------------------------------|
| <image src="https://perso.crans.org/petrovich/images/team/martial.jpg" controls style="height:100%"></image> | <image src="https://perso.crans.org/petrovich/images/team/satyaki.jpg" controls style="height:35%"></image>  <image src="https://perso.crans.org/petrovich/images/team/vivek.jpeg" controls style="height:45%"></image> <image src="https://perso.crans.org/petrovich/images/team/david.jpeg" controls style="height:40%"></image>|



## CMU hartwell server
<style>
	.container{
	display: flex;
	}
	.col{
	flex: 1;
	}
</style>

<div class="container">

<div class="col">
 <ul>
  <li>$4$ Nvidia GTX $1080$ Ti</li>
  <li>$126$ Go of RAM</li>
  <li>$32$ core CPU</li>
  <li>$5$ To HDD</li>
  <li>$2$ To SSD</li>
</ul>

</div>

<div class="col">
<image src="https://perso.crans.org/petrovich/images/nvidia-smi.png" controls style="width:80%" ></image>
</div>
</div>
<image src="https://perso.crans.org/petrovich/images/htop.png" controls style="width:150%" ></image>


## CMU hartwell server
Big issue: No **root** access ☹

- Weeks to install programms  
- Compile and link libraries by hand


## CMU hartwell server
<image src="https://perso.crans.org/petrovich/images/make.jpg" controls style="width:150%" ></image>



## What is the project?
- Create a tracker
- Be robust to occlusions 


## Example of track
<video src="videos/vot.webm" controls></video>



## Evaluation
<image src="https://perso.crans.org/petrovich/images/iou_equation.png" controls style="width:70%" ></image>


## Evaluation
### Example
<image src="https://perso.crans.org/petrovich/images/iou_examples.png" controls style="width:70%" ></image>


## Evalutation
- $mIoU$: average of $IoU$
- $detect$: $0$ if $IoU < th$ and $1$ otherwise
- $mdetect$: average of detection



## The project mission
- Use state of the art paper in CV
- Be as good as the state of the art in tracking
- Be better in occlusions cases



## Different way of tracking
### Standard tracking
  - Track anything (even background)
  - Can be very fast
  - First frame is given


## Different way of tracking
### Tracking by detection
  - Use an object detector
  - Very accurate
  - No box given



## First issue
- No occlusions dataset available
- How to test some models without data?



## Create a new dataset!
<!-- -- data-background="#A0C66B" data-background-transition="linear" -->



## Custom dataset
<video src="videos/0121.webm" controls></video>


## Custom dataset
- 298 videos (1/2 min long)
- More than 5h long
- 12 instances categories
- Considerable viewpoint change
- Partial and long term occlusions
- In case of occlusions
  - annotations of the most probable saved


## Custom dataset
<video src="videos/annotations.webm" controls ></video>



## Custom dataset
### Type of occlusions
| Dynamic  |  | | | |
|---------|----------|---------|----------|
| <image src="https://perso.crans.org/petrovich/images/occlusions/dynamic/pad_under_0004.jpg" controls style="height:30%"></image> | <image src="https://perso.crans.org/petrovich/images/occlusions/dynamic/pad_under_0005.jpg" controls style="height:30%"></image> | <image src="https://perso.crans.org/petrovich/images/occlusions/dynamic/pad_under_0006.jpg" controls style="height:30%"></image> | <image src="https://perso.crans.org/petrovich/images/occlusions/dynamic/pad_under_0008.jpg" controls style="height:30%"></image> |


## Custom dataset
### Type of occlusions
| Static  |  | | | |
|---------|----------|---------|----------|
| <image src="https://perso.crans.org/petrovich/images/occlusions/static/pad_0001.jpg" controls style="height:30%"></image> | <image src="https://perso.crans.org/petrovich/images/occlusions/static/pad_0002.jpg" controls style="height:30%"></image> | <image src="https://perso.crans.org/petrovich/images/occlusions/static/pad_0003.jpg" controls style="height:30%"></image> | <image src="https://perso.crans.org/petrovich/images/occlusions/static/pad_0004.jpg" controls style="height:30%"></image> |


## Custom dataset
### Multi orientation
| Mug  |  | | | 
|---------|----------|---------|
| <image src="https://perso.crans.org/petrovich/images/occlusions/multi_orientation/mug_bend.jpg" controls style="width:100%"></image> | <image src="https://perso.crans.org/petrovich/images/occlusions/multi_orientation/mug_bend2.jpg" controls style="width:100%"></image> | <image src="https://perso.crans.org/petrovich/images/occlusions/multi_orientation/mug_bend3.jpg" controls style="width:100%"></image> |


## Custom dataset
### Fast motion
<image src="https://perso.crans.org/petrovich/images/occlusions/fast_motion/mug_fast.jpg" controls style="width:60%"></image>


## Custom dataset
### Full occlusions
<image src="https://perso.crans.org/petrovich/images/occlusions/full_occlusions.jpg" controls style="width:60%"></image>



### Object vs Instance
| Object  | Instance |
|---------|----------|
| <image src="https://perso.crans.org/petrovich/images/custom/mugs_colors_names_object.png" controls style="height:70%"></image> | <image src="https://perso.crans.org/petrovich/images/custom/mugs_colors_names.png" controls style="height:70%"></image> |



## Standard tracking
<!-- -- data-background="#A0C66B" data-background-transition="linear" data-color="#FFFFFF"-->



## Experiment with Goturn
- Pros: very fast, accurate in general
- Cons: can change object easily  
→ Not robust with occlusions


## Experiment with Goturn
<video src="videos/0072-goturn.webm" controls></video>


## Experiment with Goturn
### Fine tunning
| Without  | With |
|---------|----------|
| <video src="videos/0000-goturn-no.webm" controls></video> | <video src="videos/0000-goturn-yes.webm" controls></video> |


## Experiment with Goturn
### Some results
|       | $mIoU$ | $mdetect$ |
| --    | --     | --        |
| No FT | $0.28$ | $0.28$    |
| FT    | $0.49$ | $0.63$    |



## Tracking by detection
<!-- -- data-background="#A0C66B" data-background-transition="linear" -->



## Needed tools
- Object  detector
- Idea of motion



## Creation of a detector
### Synthetic dataset
| Backgrounds  |  | |
|---------|----------|-|
| <image src="https://perso.crans.org/petrovich/images/syndata/background_00_24.png" controls style="height:50%"></image> | <image src="https://perso.crans.org/petrovich/images/syndata/background_03_02.png" controls style="height:50%"></image> | <image src="https://perso.crans.org/petrovich/images/syndata/background_03_04.png" controls style="height:50%"></image> |


## Creation of a detector
### Synthetic dataset
| Pictures  |  | |
|---------|----------|-|
| <image src="https://perso.crans.org/petrovich/images/syndata/occlus12_18_0000440.jpg" controls style="height:50%"></image> | <image src="https://perso.crans.org/petrovich/images/syndata/occlus12_18_0000534.jpg" controls style="height:50%"></image> | <image src="https://perso.crans.org/petrovich/images/syndata/occlus12_18_0003520.jpg" controls style="height:50%"></image> |



## Creation of a detector
### Take a detector (Faster RCNN)
<image src="https://perso.crans.org/petrovich/images/schema.png" controls style="width:45%" ></image>


## Creation of a detector
- Take a pretrained network
- Fine tune this network



## Example of result
<video src="videos/0100_detector.webm" controls></video>


## Result
- Quite good
- Bad when there are occlusions/weird orientation
- Some falses positives
- Some misdetection (depend on the object)



## Optical flow
<!-- -- data-background-video="https://perso.crans.org/petrovich/videos/flows/0100_flownet2.webm"-->



## Optical flow

|                   | **Time**         | **Quality** |
| :---------------: | :--------------: | :----:      |
| OpenCV standard   | ≃ 5 min          | Medium      |
| OpenCV brox       | ≃ 5 min          | Good        |
| Flownet 2         | ≃ + 1 h          | Very Good   |


## Optical flow

| **Farneback**                                              | **Brox**                                                     | **Flownet2**                                     |
| :---------------:                                          | :--------------:                                             | :----:                                           |
| <video src="https://perso.crans.org/petrovich/videos/flows/0100_cv.webm" controls></video> | <video src="https://perso.crans.org/petrovich/videos/flows/0100_brox.webm" controls></video> | <video src="https://perso.crans.org/petrovich/videos/flows/0100_flownet2.webm" controls></video> |



## Optical flow

**Compression of these flo files**

- Mapping to [0, 255]
- Save as X and Y gray jpeg/png images
- Save the mapping function
- $1.5$ To → $21$ Go ($70$x less)



## Creation of the network
- Having something modulable
- Not dependent of the choice of:
  - the dataset
  - the detector
  - the optical flow



## A recurrent network
- Reuse information from the past
- LSTM nets → have memory cells
  - keep some information
  - discard others
  - way more efficient


## A recurrent network
<image src="https://perso.crans.org/petrovich/images/rnn.png" controls style="width:75%"></image>


## LSTM
<image src="https://perso.crans.org/petrovich/images/LSTM3-chain.png" controls style="width:75%"></image>



## Structure of the network
<image src="https://perso.crans.org/petrovich/images/net.png" controls style="width:75%"></image>



## Results
<video src="https://perso.crans.org/petrovich/videos/lstm_mug1.webm" controls></video>


## Results
<video src="https://perso.crans.org/petrovich/videos/lstm_mug2.webm" controls></video>



## Results on this dataset
Not really good ☹   
Possible issues:
- Not enought data to train
- Too ambiguous situation
- LSTM: hard to train



## Working on another dataset
### ImagenetVid
- Almost $5000$ videos
- Multi object dataset (not instance → harder)
- Not a lot of occlusions



## ImagenetVid
| Examples  |  |
|---------|----------|
| <image src="https://perso.crans.org/petrovich/images/imnet/turtle.jpg" controls style="height:40%"></image> | <image src="https://perso.crans.org/petrovich/images/imnet/lizard.jpg" controls style="height:40%"></image> |



## Object detector
### Preprocessing required
| Raw  | Clustering |
|---------|----------|
| <image src="https://perso.crans.org/petrovich/images/turtles.png" controls style="height:40%"></image> | <image src="https://perso.crans.org/petrovich/images/turtles_meanshift.png" controls style="height:40%"></image> |



## Qualitative results
<video src="https://perso.crans.org/petrovich/videos/imnet/turtle_lstm.webm" controls></video>


## Qualitative results
| $\text{Turtle}_1$                                                                | $\text{Turtle}_2$                                                                          | $\text{Turtle}_3$ |
|------------------------------------------------------------------------|----------------------------------------------------------------------------------|---------|
| <video src="https://perso.crans.org/petrovich/videos/imnet/turtle_0.webm" controls></video> | <video src="https://perso.crans.org/petrovich/videos/imnet/turtle_1.webm" controls></video> | <video src="https://perso.crans.org/petrovich/videos/imnet/turtle_3.webm" controls></video>        |


## Quantitative results
|        | Only detection | Detection + LSTM |
|:------:|:--------------:|:----------------:|
| $mIoU$ | 0.48           | 0.62             |



## Conclusion
- Matching works great
- Need to change the architechture in some way
- Learning differently
  - Teacher forcing in two phases


## Bonus: Video player
<!-- -- data-background-video="videos/player.webm"-->
- Work on the server → avoid (scp, sshfs etc)
- Fast to look at a video
- Available on github [Mathux/tiv-video]
