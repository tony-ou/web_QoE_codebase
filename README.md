
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


### Record actual page load process

## Step 2: Collect User Ratings on Mturk

## Step 3: Analyze Data


# II. Other Resources

## Related Literature
To gain more context on QoE research and Crowdsourcing techinques, one can refer to literature in following doc as a start point: 
https://docs.google.com/document/d/13Ny75k_Co0_usEhkLoT2eaFspbsSLcSGhQg4QzgW3vk/edit?usp=sharing

https://drive.google.com/file/d/1FAdnkJYzjX6kjI79ouP2zQmxX8hjwE2N/view?usp=sharing

## Amazon EC2

## Mturk
