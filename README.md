
This is a guide for webQoE research. If you have questions, please contact Yiyang Ou (at tony.ouyy@gmail.com)

# I. QoE User Study

This repository gives guidance for collecting user QoE on a web page through crowdsourcing. Because crowdworkers have very different network setup, they have completely different page load experience if we just ask them to load an actual web page. Instead, the common techinique is to record a video of page load and let crowdsourced workers rate the quality of page load process shown in the video. 

Hence, a user study consists of three steps: 1.create the videos of page loads, 2.collect user ratings on page load videos 3.analyze the data. 


## Step 1: Create Page Load Videos
There are two ways to create a video: one is to record the actual loading process of a page, second is to use editing tools to create custom loading process.

### A. Record actual page load process
[WebPageTest](https://www.webpagetest.org/) is a tool for measuring webpages' performance. You can configure network condition (e.g. bandwidth, RTT) and collect metrics like SpeedIndex of the webpage. Additionally, it has a functionality to record the video o page load. **To get high resolution video you should check the box as below.**

   ![wpt](https://github.com/sheric98/QoEProject/blob/master/static/Design_Layout.png)

It is possible to do page recording in batch, but the public version of WPT doesn't supports this feature. So you need to set up your own WPT server (e.g. on Amazon EC2). This is a good tutorial on this.


### Use editing tools: 

Often times, we want to modify page loading process and ask users to rate changed page. We can modify page's source code and achieve the effect (sometimes this would be very hard), but a much more straightforward way is to modify a video of page load. 

To do this, we start with a baseline page load video, either using a real page load video or creating an artificial one from image of page (see more on how to do this in the example jupyter notebooks mentioned later). Then, we can apply many transformations: delaying/speeding elements of a page or even repositioning certain elements. We use a Python library, Moviepy, to achieve these effects. Example jupyter notebooks can be found here. 

We can also edit videos with other tools like adobe premiere pro.

Lastly, to make a web page load video more similar to real loading process, we add a browser header to the video. (Script for this are found in the jupyter nobteook examples)

## Step 2: Collect User Ratings on Mturk
After we created videos, we need to create experiment interfaces and find people to do our experiment. Amazon Mturk comes handy for this purpose: it is a crowdsourcing platform where you pay to find people on the platform (called Turkers) to do your experiment (called HIT). 

The way we run QoE study on Mturk is like this: we host our own web page server (codebase for this is here [Crowdsourcing study](https://www.webpagetest.org/), and publish the link to our survey page on Mturk. (So Mturk is simply an entry point for publishing our urls to real people).


### Running MTurk Survey

1. Login to [Amazon Requester](https://requester.mturk.com/begin_signin) using your Amazon account.

2. Create a new project using their "Survey Link" template.

3. Fill out the survey properties. Here is an example of my settings:
   ![MTurk Settings](https://github.com/sheric98/QoEProject/blob/master/static/MTurk_Settings.png)

4. Click on Design Layout. Click on "Source" in the editor to edit the text.
   Here is an exmaple of my layout:
   ![Design Layout](https://github.com/sheric98/QoEProject/blob/master/static/Design_Layout.png)

   Remember to change the link correspondingly if you changed the port number.

5. Finish and publish a batch.



## Step 3: Analyze Data


# II. Other Resources

## Related Literature
To gain more context on QoE research and Crowdsourcing techinques, one can refer to literature in following doc as a start point: 
https://docs.google.com/document/d/13Ny75k_Co0_usEhkLoT2eaFspbsSLcSGhQg4QzgW3vk/edit?usp=sharing

https://drive.google.com/file/d/1FAdnkJYzjX6kjI79ouP2zQmxX8hjwE2N/view?usp=sharing

## Amazon EC2

## Mturk
