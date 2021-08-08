
This is a guide for webQoE research. If you have questions, please contact Yiyang Ou (at tony.ouyy@gmail.com)

# I. QoE User Study

This repository gives guidance for collecting user QoE on a web page through crowdsourcing. Because crowdworkers have very different network setup, they have completely different page load experience if we just ask them to load an actual web page. Instead, the common techinique is to record a video of page load and let crowdsourced workers rate the quality of page load process shown in the video. 

Hence, a user study consists of three steps: 1.create the videos of page loads, 2.collect user ratings on page load videos 3.analyze the data. 


## Step 1: Create Page Load Videos
Tutorial can be found: https://github.com/tony-ou/web_QoE_video_creation/

## Step 2: Configure server and host experiment page
Tutorial can be found:  https://github.com/tony-ou/web_QoE_user_study/

## Step 3: Start Amazon Mturk Campaign

Mturk is the crowdsourcing platform we use.

### Running MTurk Campaign

1. Login to [Amazon Requester](https://requester.mturk.com/begin_signin) using your Amazon account.

2. Create a new project using their "Survey Link" template.

3. Fill out the survey properties. Here is an example of my settings:
   ![MTurk Settings](https://github.com/tony-ou/web_QoE_guide/blob/main/sample_files/MTurk_Settings.PNG)

4. Click on Design Layout. Click on "Source" in the editor to edit the text.
  
   Replace the source with following script. Remember to change the .
   ```shell
   <p>When you are finished, you will return to this page to paste the code into the box.</p>

   <div class="row" id="workContent">
   <div class="col-xs-12 col-md-6 col-md-offset-3"><!-- Content for Worker -->
   <table class="table table-condensed table-bordered">
      <colgroup>
         <col class="col-xs-4 col-md-4" />
         <col class="col-xs-8 col-md-8" />
      </colgroup>
      <tbody>
         <tr>
            <td><label>Survey link:</label></td>
            <td><a class="dont-break-out" href="**URL_to_webpage**">Survey</a></td>
         </tr>
      </tbody>
   </table>
   <!-- End Content for Worker --><!-- Input from Worker -->

   <div class="form-group"><label for="surveycode">Provide the survey code here:</label> <input class="form-control" id="surveycode" name="surveycode" placeholder="e.g. 123456" required="" type="text" /></div>
   <!-- End input from Worker --></div>
   </div>
   <!-- End Survey Link Layout --><!-- Please note that Bootstrap CSS/JS and JQuery are 3rd party libraries that may update their url/code at any time. Amazon Mechanical Turk (MTurk) is including these libraries as a default option for you, but is not responsible for any changes to the external libraries --><!-- External CSS references -->
   <link crossorigin="anonymous" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.0.3/css/bootstrap.min.css" integrity="sha384-IS73LIqjtYesmURkDE9MXKbXqYA8rvKEp/ghicjem7Vc3mGRdQRptJSz60tvrB6+" rel="stylesheet" /><!-- Open internal style sheet -->
   <style type="text/css">#collapseTrigger{
     color:#fff;
     display: block;
     text-decoration: none;
   }
   #submitButton{
     white-space: normal;
   }
   .image{
     margin-bottom: 15px; 
   }
   /* CSS for breaking long words/urls */
   .dont-break-out {
     overflow-wrap: break-word;
     word-wrap: break-word;
     -ms-word-break: break-all;
     word-break: break-all;
     word-break: break-word;
     -ms-hyphens: auto;
     -moz-hyphens: auto;
     -webkit-hyphens: auto;
     hyphens: auto;
   }
   </style>
   <!-- Close internal style sheet --><!-- External JS references --><script src="https://code.jquery.com/jquery-3.1.0.min.js"   integrity="sha256-cCueBR6CsyA4/9szpPfrX3s49M9vUU5BgtiJj06wt/s="   crossorigin="anonymous"></script><script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.0.3/js/bootstrap.min.js" integrity="sha384-s1ITto93iSMDxlp/79qhWHi+LsIi9Gx6yL+cOKDuymvihkfol83TYbLbOw+W/wv4" crossorigin="anonymous"></script><!-- Open internal javascript --><script>
     $(document).ready(function() {
       // Instructions expand/collapse
       var content = $('#instructionBody');
       var trigger = $('#collapseTrigger');
       content.hide();
       $('.collapse-text').text('(Click to expand)');
       trigger.click(function(){
         content.toggle();
         var isVisible = content.is(':visible');
         if(isVisible){
           $('.collapse-text').text('(Click to collapse)');
         }else{
           $('.collapse-text').text('(Click to expand)');
         }
       });
       // end expand/collapse
     });
   </script><!-- Close internal javascript -->
   ```
   
    Here is what the page looks like. Click `Survey` should bring you to the experiment page.:
   ![Design Layout](https://github.com/tony-ou/web_QoE_guide/blob/main/sample_files/Design_Layout.PNG)


5. Finish and publish a batch.

Some Tips for crowdsourced mturk study: 
1. Choose master workers to get better reliable results.
2. Leave some leniant time so workers are not rushed.
3. Pay attention to the email after experiment starts, in case workers complain that server is down.
4. Workers search for HITs by hourly rate, so give reasonable payment to make the study finish faster. (But don't pay too much, the cost is high since Mturk also takes about 30% platform fee)

## Step 4: Analyze Data
Tutorial can be found:  https://github.com/tony-ou/web_QoE_user_study/

# II. Other Resources

## Related Literature
To gain more context on QoE research and Crowdsourcing techinques, one can refer to literature in following doc as a start point: 

https://docs.google.com/document/d/13Ny75k_Co0_usEhkLoT2eaFspbsSLcSGhQg4QzgW3vk/edit?usp=sharing


## [WebGaze](https://www.usenix.org/conference/nsdi17/technical-sessions/presentation/kelton) Dataset (their original website is down)
