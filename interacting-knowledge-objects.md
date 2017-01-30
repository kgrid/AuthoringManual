# Interacting Knowledge Objects

What if you have two separate knowledge objects that operate individually but share information? This is something the KGrid team continues to ponder, with no definite answer. As of now, we have created a couple interacting knowledge objects that operate differently. 



For example, the Neck Disability Index consists of 2 separate KO: a resource and a result. The resource is an HTML survey that sends the answers to the result knowledge object who interprets the answers and returns the interpretation. 

The resource payload is as follow:

```
<html lang="en">
<head>
    <title> Neck Disability Index </title>
    <script type="text/javascript"
	src="https://ajax.googleapis.com/ajax/libs/jquery/1.12.2/jquery.min.js"></script>
</head>
<script>
$(document).ready(function(){
    $('#btn').click(function formsubmit(){
      var formArray = $("#neckDisIndex").serializeArray();
      var obj= {};
      for(var i=0; i<formArray.length; i++){
        var name = formArray[i].name;
        var value = formArray[i].value;
        if(name) {
          obj[name]=value;
        }
      }
      var formData = JSON.stringify(obj);
      console.log(formData);
      var serverUrl = "http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/knowledgeObject/ark:/99999/fk4jh3tn3n/result";
  $.ajax({
    type: "POST",
    url: serverUrl,
    data: formData,
    success: function(response){
      console.log(response);
    },
    dataType: "json",
    contentType : "application/json"
  });
}
);
})

</script>
<body>
    <form id='neckDisIndex' methopd='post' action = "http://dlhs-fedora-dev-a.umms.med.umich.edu:8080/ExecutionStack/knowledgeObject/ark:/99999/fk4vh5t309/result">
      <td><h3> Neck Disability Index </h3></td><br/>
      <td> This questionnaire has been designed to give us information as to how your neck pain has affected your ability to manage in everyday life. Please answer every section and mark in each section only the one box that applies to you. We realise you may consider that two or more statements in any one section relate to you, but please just mark the box that most closely describes your problem.</td><br/><br/><br/>

        <td><b> Section 1: Pain Intensity </b></td><br/>
        <td>
          <input type="radio" value="none" name="pain_intensity">I have no pain at the moment<br/>
          <input type="radio" value="mild" name="pain_intensity">The pain is very mild at the moment<br/>
          <input type="radio" value="moderate" name="pain_intensity">The pain is moderate at the moment<br/>
          <input type="radio" value="fairly_severe" name="pain_intensity">The pain is fairly severe at the moment<br/>
          <input type="radio" value="severe" name="pain_intensity">The pain is very severe at the moment<br/>
          <input type="radio" value="complete" name="pain_intensity">The pain is worst imaginable at the moment<br/><br/>
        </td>

        <td><b> Section 2: Personal Care (Washing, Dressing, etc.) </b></td><br/>
        <td>
          <input type="radio" value="none" name="personal_care">I can look after myself normally without causing extra pain<br/>
          <input type="radio" value="mild" name="personal_care">I can look after myself normally but it causes extra pain<br/>
          <input type="radio" value="moderate" name="personal_care">It is painful to look after myself and I am slow and careful<br/>
          <input type="radio" value="fairly_severe" name="personal_care">I need some help but can manage most of my personal care<br/>
          <input type="radio" value="severe" name="personal_care">I need help every day in most aspects of self care<br/>
          <input type="radio" value="complete" name="personal_care">I do not get dressed, I wash with difficulty and stay in bed<br/><br/>
        </td>

        <td><b> Section 3: Lifting </b></td><br/>
        <td>
          <input type="radio" value="none" name="lifting">I can lift heavy weights without extra pain<br/>
          <input type="radio" value="mild" name="lifting">I can lift heavy weights but it gives extra pain<br/>
          <input type="radio" value="moderate" name="lifting">Pain prevents me lifting heavy weights off the floor, but I can manage if they are conveniently placed, for example on a table<br/>
          <input type="radio" value="fairly_severe" name="lifting">Pain prevents me from lifting heavy weights but I can manage light to medium weights if they are conveniently positioned<br/>
          <input type="radio" value="severe" name="lifting">I can only lift very light weights<br/>
          <input type="radio" value="complete" name="lifting">I cannot lift or carry anything<br/><br/>
        </td>

        <td><b> Section 4: Reading </b></td><br/>
        <td>
          <input type="radio" value="none" name="reading">I can read as much as I want to with no pain in my neck<br/>
          <input type="radio" value="mild" name="reading">I can read as much as I want to with slight pain in my neck<br/>
          <input type="radio" value="moderate" name="reading">I can read as much as I want with moderate pain in my neck<br/>
          <input type="radio" value="fairly_severe" name="reading">I can't read as much as I want because of moderate pain in my neck<br/>
          <input type="radio" value="severe" name="reading">I can hardly read at all beacause of severe pain in my neck<br/>
          <input type="radio" value="complete" name="reading">I cannot read at all<br/><br/>
        </td>

        <td><b> Section 5: Headaches </b></td><br/>
        <td>
          <input type="radio" value="none" name="headaches">I have no headaches at all<br/>
          <input type="radio" value="mild" name="headaches">I have slight headaches, which come infrequently<br/>
          <input type="radio" value="moderate" name="headaches">I have moderate headaches, which come infrequently<br/>
          <input type="radio" value="fairly_severe" name="headaches">I have moderate headaches, which come frequently<br/>
          <input type="radio" value="severe" name="headaches">I have severe headaches, which come frequently<br/>
          <input type="radio" value="complete" name="headaches">I have headaches almost all the time<br/><br/>
        </td>

        <td><b> Section 6: Concentration </b></td><br/>
        <td>
          <input type="radio" value="none" name="concentration">I can concentrate fully when I want to with no difficulty<br/>
          <input type="radio" value="mild" name="concentration">I can concentrate fully when I want to with slight difficulty<br/>
          <input type="radio" value="moderate" name="concentration">I have a fair degree of difficulty in concentrating when I want to<br/>
          <input type="radio" value="fairly_severe" name="concentration">I have a lot of difficulty in concentrating when I want to<br/>
          <input type="radio" value="severe" name="concentration">I have a great deal of difficulty in concentrating when I want to<br/>
          <input type="radio" value="complete" name="concentration">I cannot concentrate at all<br/><br/>
        </td>

        <td><b> Section 7: Work </b></td><br/>
        <td>
          <input type="radio" value="none" name="work">I can do as much work as I want to<br/>
          <input type="radio" value="mild" name="work">I can only do my usual work, but no more<br/>
          <input type="radio" value="moderate" name="work">I can do most of my usual work, but no more<br/>
          <input type="radio" value="fairly_severe" name="work">I cannot do my usualy work<br/>
          <input type="radio" value="severe" name="work">I can hardly do any work at all<br/>
          <input type="radio" value="complete" name="work">I can't do any work at all<br/><br/>
        </td>

        <td><b> Section 8: Driving </b></td><br/>
        <td>
          <input type="radio" value="none" name="driving">I can drive my car without any neck pain<br/>
          <input type="radio" value="mild" name="driving">I can drive my car as long as I want with slight pain in my neck<br/>
          <input type="radio" value="moderate" name="driving">I can drive my car as long as I want with moderate pain in my neck<br/>
          <input type="radio" value="fairly_severe" name="driving">I can't drive my car as long as I want because of moderate pain in my neck<br/>
          <input type="radio" value="severe" name="driving">I can hardly drive at all because of severe pain in my neck<br/>
          <input type="radio" value="complete" name="driving">I can't drive my car at all<br/><br/>
        </td>

        <td><b> Section 9: Sleeping </b></td><br/>
        <td>
          <input type="radio" value="none" name="sleeping">I have no trouble sleeping<br/>
          <input type="radio" value="mild" name="sleeping">My sleep is slightly disturbed (less than 1 hr sleepless)<br/>
          <input type="radio" value="moderate" name="sleeping">My sleep is mildly disturbed (1-2 hrs sleepless)<br/>
          <input type="radio" value="fairly_severe" name="sleeping">My sleep is moderately disturbed (2-3 hrs sleepless)<br/>
          <input type="radio" value="severe" name="sleeping">My sleep is greatly disturbed (3-5 hrs sleepless)<br/>
          <input type="radio" value="complete" name="sleeping">My sleep is completely disturbed (5-7 hrs sleepless)<br/><br/>
        </td>

        <td><b> Section 10: Recreation </b></td><br/>
        <td>
          <input type="radio" value="none" name="recreation">I am able to engage in all my recreation activites with no neck pain at all<br/>
          <input type="radio" value="mild" name="recreation">I am able to engage in all my recreation activites, with some pain in my neck<br/>
          <input type="radio" value="moderate" name="recreation">I am able to engage in most, but not all of my usual recreation activities because of pain in my neck<br/>
          <input type="radio" value="fairly_severe" name="recreation">I am able to engage in a few of my usual recreation activities because of pain in my neck<br/>
          <input type="radio" value="severe" name="recreation">I can hardly do any recreation activities because of pain in my neck<br/>
          <input type="radio" value="complete" name="recreation">I can't do any recreation activites at all<br/><br/>
        </td>

        <td><input type="reset" /></td?
          <td><button id='btn' type='button'>Send Info</button>
    </form>
</body>
</html>

```



