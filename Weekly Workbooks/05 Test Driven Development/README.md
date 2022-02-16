## Test Driven Development
### <a href='https://web.microsoftstream.com/group/47ff5be4-af38-493f-a1c8-650acc485651?view=videos' target='_blank'> Weekly Briefing ![](../../resources/icons/briefing.png) </a>
### Task 1: Introduction
 <a href='01%20Introduction/slides/segment-1.pdf' target='_blank'> ![](../../resources/icons/slides.png) </a> <a href='01%20Introduction/video/segment-1.mp4' target='_blank'> ![](../../resources/icons/video.png) </a>

We now shift our focus to consider the twin topics of **Verification and Validation**. In this workbook we will focus primarily on *Verification*, however is worth introducing both concepts now in order to compare the two. There are numerous issues to explore in this area and many of them are key to the successful development of software projects. In order to gain a high-level appreciation of these concepts, take a look at the slides and video linked to above. This will give you an overview of these topics and help to provide context for the rest of the activities in this workbook.  


# 
### Task 2: Test Driven Development
 <a href='02%20Test%20Driven%20Development/slides/segment-1.pdf' target='_blank'> ![](../../resources/icons/slides.png) </a> <a href='02%20Test%20Driven%20Development/video/segment-1.mp4' target='_blank'> ![](../../resources/icons/video.png) </a>

Test Driven Development (TDD) is a key practice common to numerous Agile methods. It is an essential activity that as a professional developer, you will need to master. Take a look at the slides and video linked to above to gain an understanding of the motivations for TDD and the processes involved in its adoption. Use this insight to reflect upon your current practice and think about the role that TDD might play in improving the correctness of your code.
  


# 
### Task 3: Unit Testing
 <a href='03%20Unit%20Testing/slides/segment-1.pdf' target='_blank'> ![](../../resources/icons/slides.png) </a> <a href='03%20Unit%20Testing/video/segment-1.mp4' target='_blank'> ![](../../resources/icons/video.png) </a>

In order to successfully employ Test Driven Development, we first need to be able to effectively perform **Unit Testing**. Take a look at the set of slides and video linked to above to find out how to approach this activity. Once you are confident that you have understood the concepts, move on to apply your knowledge to the following testing activity...

A feature that IMDB offers is the ability to maintain an overall movie rating (produced by calculating the average of all ratings previously submitted). Below is some sample code that implements this feature. As you can see, the method takes a single parameter (a new "marks out of 10" rating), calculates an updated average based on this and previous ratings, finally passing back the updated average as a return value.

```java
private float currentAverage = 0;
private int ratingCount = 0;

public float addNewRating(int newRating)
{
    int previousTotal = (int) (currentAverage * ratingCount);
    int newTotal = previousTotal + newRating;
    ratingCount++;
    currentAverage = newTotal / ratingCount;
    return currentAverage;
}
```
Although this is only a very simple method, it is still possible to use equivalence partitions to identify a suitable set of test cases. Identify 4 different equivalence partitions for the `newRating` parameter and enter a suitable test value from each into the <a href="https://forms.office.com/Pages/ResponsePage.aspx?id=MH_ksn3NTkql2rGM8aQVG37h-tXTP5NGqEknVplKlalUMVlKNjVCRkU2NTlRWU5RSVkxRlE1Qlc3WC4u" target="_blank">weekly workbook form</a>.  


# 
### Task 4: JUnit
 <a href='04%20JUnit/slides/segment-1.pdf' target='_blank'> ![](../../resources/icons/slides.png) </a> <a href='04%20JUnit/video/segment-1.mp4' target='_blank'> ![](../../resources/icons/video.png) </a>

A challenge with testing the previously presented IMDB rating code is that it maintains _persistent state_ over time (namely, it keeps a record of the average rating and the number of ratings submitted). This causes extra challenges for unit testing, since we need to determine whether or not the method operates correctly _for a sequence of values_. In order to fully test the above code, we therefore need to test it in operation over a period of time, calling the method multiple times with suitable test values.

Luckily there is a testing framework called "JUnit" that can help us achieve this (which you have already been using as part of the Java unit). View the slides and video above to find out more about JUnit (sorry about the rant about C halfway through ;o). Once you are happy with the concepts, your job is to should write some suitable JUnit test cases to exercise the IMDB rating code.

To help you in this task, we have created a <a href="https://github.com/pose-uob/IMDBRating" target="_blank">Java Maven project</a> which contains the previously shown IMDB rating code. You should **fork** this repository in order to create your own version of the project on GitHub (you will need your own repository for a later task !). Once you have a forked copy of the repository on GitHub, clone this to create a local copy to work on.

As you will recall from the Java unit, there is a `test` folder inside the `src` directory of the project where all test scripts should be located. Edit the `IMDBRatingTest` class that is contained in the test folder, adding a number of JUnit tests that will fully test the average rating code. These tests should make a number of calls to the average rating method, passing in a sequence of values in order to test out the operation of the persistent state.

There is in fact a fault in the average rating code which your test cases should hopefully identify. Once you have determined the nature of this fault, devise a revision to the code (and check to make sure that it does indeed fix the fault !). Finally, enter your revised line of code into the <a href="https://forms.office.com/Pages/ResponsePage.aspx?id=MH_ksn3NTkql2rGM8aQVG37h-tXTP5NGqEknVplKlalUMVlKNjVCRkU2NTlRWU5RSVkxRlE1Qlc3WC4u" target="_blank">weekly workbook form</a>.  


# 
### Task 5: Feature Branches
 <a href='05%20Feature%20Branches/video/segment-1.mp4' target='_blank'> ![](../../resources/icons/video.png) </a>

Now that we have a set of JUnit test cases, there are various interesting Agile related activities we can apply them to. Before we investigate these activities in detail, we need to become more familiar with of the facilities of GitHub. View the video linked to above to find out about the concept of **Feature Branches**. Once you are happy with the concepts discussed, attempt to replicate the activities shown in the video on your copy of the repository that you forked in the previous section. Once you are happy with the mechanics of creating, updating and merging feature branches, move on to the following task (where we will integrate the JUnit tests you wrote previously).  


# 
### Task 6: Continuous Integration
 <a href='06%20Continuous%20Integration/video/segment-1.mp4' target='_blank'> ![](../../resources/icons/video.png) </a>

Continuous Integration (CI) is a key practice in many Agile methods (perhaps most notably Extreme Programming). View the video above for a walk-through of how Continuous Integration is achieved within GitHub. Note that although the video above focus on the use of GitHub Actions, the concepts are transferable to other similar Continuous Integration platforms.

Now that you have an understanding of Continuous Integration, your task is to add a GitHub Action to your fork of the IMDB repository. You should configure this Action to run the JUnit tests that you created in a previous workbook task. Test out the Action by pushing a change to the repository and make sure the action is executed. You might like to introduce a bug into the code - just to check that failed tests are indeed reported by GitHub.

Note that this task is not a difficult challenge: it should just a case of following the steps demonstrated in the video above. The practice will however be useful for when you need to set up CI for your own projects.  


# 
### Task 7: Release Testing
 <a href='07%20Release%20Testing/slides/segment-1.pdf' target='_blank'> ![](../../resources/icons/slides.png) </a> <a href='07%20Release%20Testing/video/segment-1.mp4' target='_blank'> ![](../../resources/icons/video.png) </a>

Release testing (often called "Integration testing") operates at a higher level than the lower-level unit testing we discussed earlier. The aim of release testing is to test the system _as an integrated whole_ and thereby ensure that it is ready for release to a client. This requires addition test cases to be written and executed, verifying complex application features at a higher "whole-system" level (rather than just checking the operation of individual functions at a component/unit level).

Review the slides and video linked to above to gain an appreciation of release testing. We will then attempt to perform release testing on the IMDB example application. The problem is that we don't actually have access to the entire IMDB codebase ! We can however target the existing live IMDB website as a "black box" that we can run tests against. Your task is to write a release test that will exercise the IMDB "advanced search" facility to ensure it is working correctly. More specifically, you should assess the correctness of the "filming locations" search provided by IMDB. As a test case, you should request a report of all films and TV shows that have been filmed in the Bristol area. This can be done by requesting the following URL:

<a href="https://www.imdb.com/search/title-text/?location=bristol" target="_blank">https://www.imdb.com/search/title-text/?location=bristol</a>

As you can see (if you clicked on the link above) the query returns a large number of films and TV shows. You could manually check the results of this query by looking at the returned web page, however this goes against the whole ethos of automated test-driven development. Instead, we will write a JUnit test that requests this URL from the server and then analyses the response in order to check that it is correct.

To confirm the completeness of the IMDB database and to ensure that the querying features are operating correctly, we need a test case of "known correct" data. In this case, you should check that ALL episodes of the classic Bristol-based TV detective drama <a href="https://en.wikipedia.org/wiki/Shoestring_(TV_series)" target="_blank">Shoestring</a> are listed in the search results. You will need to refine the query URL, otherwise you will get back _anything_ that was _ever_ shot in Bristol. The easiest way to do this is to add the ID of the leading actor from Shoestring (Trevor Eve, ID: nm0263368) to the end of the URL:

<a href="https://www.imdb.com/search/title/?locations=bristol&role=nm0263368" target="_blank">https://www.imdb.com/search/title/?locations=bristol&role=nm0263368</a>

This will return everything that was shot in Bristol AND stars Trevor Eve (the results of which are _mostly_ just episodes of Shoestring). For a full list of episode titles to check against, see the <a href="https://en.wikipedia.org/wiki/Shoestring_(TV_series)#Episodes" target="_blank">Shoestring entry on wikipedia</a>. Run your release test to check which episodes are listed by IMDB - report any episodes that are missing using the <a href="https://forms.office.com/Pages/ResponsePage.aspx?id=MH_ksn3NTkql2rGM8aQVG37h-tXTP5NGqEknVplKlalUMVlKNjVCRkU2NTlRWU5RSVkxRlE1Qlc3WC4u" target="_blank">weekly workbook form</a>.


  


**Hints & Tips:**  
A simple (if fairly rudimentary) way to make HTTP requests from a Java application (or JUnit test script) is by using the `HttpURLConnection` class. We can use this to call the HTTP request handlers provided by an application, and then use assertions as normal to test the response received.

For example, we can use the following code to query IMDB and read in the response returned from the server:

```java
URL url = new URL("https://www.imdb.com/search/title/?locations=bristol&role=nm0263368");
HttpURLConnection connection =(HttpURLConnection)url.openConnection();
connection.setDoOutput(true);
connection.setRequestMethod("GET");
InputStream stream = connection.getInputStream();
BufferedReader reader = new BufferedReader(new InputStreamReader(stream));
String nextLine = reader.readLine();
while(nextLine != null) {
    // Check the line to see what it contains
    ?????????????????????????????????????????
    nextLine = reader.readLine();
}
```

Note that you will need to import some classes and catch some exceptions in order to get the above code to work !  


# 
