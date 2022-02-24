## Assessed Exercise
### <a href='https://web.microsoftstream.com/group/47ff5be4-af38-493f-a1c8-650acc485651?view=videos' target='_blank'> Weekly Briefing ![](../../resources/icons/briefing.png) </a>
### Task 1: Introduction


This is an **ASSESSED** workbook !  
The activities in this workbook will constitute 50% of your mark for this unit.  
You should work your way through the tasks, completing each in turn. Each task will require you to complete a template document, which you will then need to submit onto blackboard by the deadline. We strongly advise you to pull the repository as normal, but then _move_ the templates to another folder to work on them (there is the danger that subsequent pulls will overwrite your changes - if you leave the files in the same location !). Many of the documents will be auto-marked, so it is important that you do not change the structure or formatting of the material they contain. In each section you will be instructed as to which elements you should add or update.  


# 
### Task 2: User Stories


The aim of this first activity is to identify a set of valid User Stories for the civil aviation sector (as illustrated in the Kegworth case study). Open and edit <a href="templates/user-stories.md" target="_blank">this user story table</a> in order to indicate which are valid User Stories and which are not. Note that you should consider these User Stories from the perspective of civil aviation in general (i.e. do not limit your analysis to just what occurred in the "Kegworth" accident). For each row in the table insert an `x` in _either_ the "Valid" or the "Invalid" column. Do not change any other content or formatting.
  


# 
### Task 3: Class Identification


We have proposed a set of potential classes for an Object Oriented Design of the flight control system from the Kegworth case study. A selection of these potential classes are listed in <a href="templates/identified-classes.md" target="_blank">this class table</a>. Your task is to identify which of these are good and appropriate class names that could be the output from Noun/Verb analysis and rationalisation activity of the _first_ segment of the Kegworth video (i.e the "re-enactment" section). Open the markdown document and for each row in the table insert an `x` in _either_ the "YES" or the "NO" column. Do not change any other content or formatting.

  


# 
### Task 4: Method Identification


We have proposed a set of potential method names for an Object Oriented Design of the flight control system from the Kegworth case study. A selection of these potential method names are listed in <a href="templates/identified-methods.md" target="_blank">this method table</a>. Your task is to identify which of these are good and appropriate method names that could be the output from Noun/Verb analysis and rationalisation activity of the _first_ segment of the Kegworth video (i.e the "re-enactment" section). Open the markdown document and for each row in the table insert an `x` in _either_ the "YES" or the "NO" column. Do not change any other content or formatting.
  


# 
### Task 5: UML Class Names


We have created at outline UML class diagram for a section of the Kegworth aircraft flight control system. We have provided you with this diagram in the form of a <a href="templates/class-diagram.dot" target="_blank">graphviz document</a> (note that you might like to use <a href="https://dreampuf.github.io/GraphvizOnline/" target="_blank">this online tool</a> to view the rendered version of the diagram). As you can see from the diagram, there are some elements missing - as indicated by the `???` placeholders. In particular, two of the class names are missing. Edit the graphviz document, replacing the relevant two `???` placeholders with the correct class names. Ensure that you only change the `???` elements and don't alter any of the structure or content of the rest of the document.
  


# 
### Task 6: UML Relationships


You may have noticed when viewing the previously provided UML class diagram document that many of the relationship arrowheads are not shown. Reopen the previous graphviz document and edit the "relationships" section, replacing all of the `???` elements with the correct arrow style - replacing them with `vee`, `empty` or `odiamond` depending on the nature of the relationship. See the workbook on Object Oriented Design for a mapping between UML relationship types and Graphviz arrowhead styles. Ensure that you only change the `???` elements and don't alter any of the structure or content of the rest of the document.  


# 
### Task 7: UML Attributes


You may also have noticed when viewing the previously provided UML class diagram document, that two of the class attributes are missing. Edit the graphviz document, replacing the `???` elements with appropriate attributes. You should pick the most appropriate attributes from the following list (don't invent ones of your own !):

- `cockpit: Cockpit`
- `lights: WarningLight[]`
- `engine: Engine`
- `sensors: sensorDevice[]`
- `sensor: VibrationSensor`
- `lever: ThrottleLever`
- `engines: Engine[]`
- `throttle: AutoThrottle`
- `gauge: VibrationGauge`

Ensure that you only change the `???` elements and don't alter any of the structure or content of the rest of the document.  


# 
### Task 8: UML Methods


You may also have noticed when viewing the previously provided UML class diagram document, that five of the methods are missing. Edit the graphviz document, replacing the `???` elements with appropriate methods. You should pick the most appropriate methods from the following list (don't invent ones of your own !):

- `flashWarningLight(id, rate): void`
- `setFuelFlowRate(rate): void`
- `setEngineThrust(): void`
- `setGaugeValue(id, value): void`
- `getVibrationReading(): float`
- `getCurrentReading(): float`
- `getSensorDevices(): void`
- `getLeverPosition(): float`
- `engageAutoThrottle(): void`
- `getThrustReading(): float`



Ensure that you only change the `???` elements and don't alter any of the structure or content of the rest of the document.  


# 
### Task 9: Test Cases


As part of the in-flight navigation system of the Boeing 737-400, there are a number of functions that perform basic mathematical computations.
For example, there is a method with the following signature that can be used to calculate the velocity of the aircraft:

```java
float calculateGroundSpeed(float leftHandEngineThrust, float rightHandEngineThrust, float windSpeed)
```

This method calculates the equilibrium (steady state) ground speed of the aircraft, given the following parameters:

- `leftHandEngineThrust` is the thrust force being produced by the left-hand engine of the aircraft
- `rightHandEngineThrust` is the thrust force being produced by the right-hand engine of the aircraft
- `windSpeed` is the wind speed _parallel to the direction_ of travel

The velocity of an aircraft can be calculated using the following simplified formula:

&nbsp;&nbsp;&nbsp;&nbsp;V = <span style="font-size:22px">&radic;</span><span style="text-decoration:overline; font-size:15px">2TD&nbsp;</span>

Where `V` is velocity (in miles per hour), `T` is the combined thrust provided by all engines (in Newtons) and `D` is the "drag factor" of the plane. (You can assume that at its cruising altitude, the 737-400 has a drag factor of `0.84`). Each engine on the 737-400 produces up to `100 Kn` of thrust, resulting in a maximum air speed of around `580 mph` !

Note that the calculation above will give the aircraft's air speed only (speed of travel through the air). You will need to take the wind speed into account in order to calculate the final ground speed of the aircraft (speed of travel relative to the ground). In the interests of simplicity, you may assume that the wind speed that is passed in as a parameter will always be parallel to the direction of travel (i.e. you do not need to deal with wind hitting the plane side-on or at an angle to the direction of flight).

Your task is to identify a set of cases that will _fully_ exercise the operation of the `calculateGroundSpeed` method. Open and edit <a href="templates/test-cases.md" target="_blank">this test case table</a>, adding as many rows to the table as you need to fully document all of your test cases. You should however maintain the same columns and formatting contained in the original document.

You should remember that this exercise is not just about _quantity_ of the test cases, but also the _quality_ of them. The aim is to maximise coverage of the operation of the method with as few test cases as possible. Think about boundary cases and equivalence partitions and avoid duplicating equivalent test cases. You should try to test as many combinations/permutations of the parameter partitions as possible.

All values provided in your answer should be floating point numbers, rounded to the nearest two decimal places (where relevant). For your reference, the programming language used to implement the speed calculation function represents floating point values in the range `-9999.0` to `9999.0`.  


# 
### Task 10: Fault Trees


In this task you will get the opportunity to demonstrate your knowledge and understanding of the Kegworth case study. A template <a href="templates/fault-tree.dot" target="_blank">fault tree diagram</a> has been provided for you which deconstructs the causes of the accident into a tree of contributing factors. You will have noticed that this fault tree is however not complete. It is your task to edit the document, replacing the `???` elements with appropriate faults, errors and failures. You should pick the most appropriate items from the following list to replace the `???` placeholders (don't invent ones of your own !):

- `Competition`
- `Profit motive`
- `UK Government`
- `Engine Failure`
- `Flight Simulator`
- `Failed Regulation`
- `Incomplete Testing`
- `No Power to Enforce`
- `Incorrect Diagnosis`
- `Engine Test Results`
- `Failure of Training`
- `Promotional Materials`
- `Cameras not Installed`
- `Constant Interruptions`
- `Training not Questioned`
- `Rejected Recommendations`
- `Vibration Gauge too Small`
- `Inadequate Training Materials`
- `Institute of Aviation Medicine`
- `Lack of User-centred Evaluation`

Ensure that you only change the `???` elements and don't alter any of the structure or content of the rest of the document.
  


# 
### Task 11: Professional Practice


In this task we will explore the broader context of the Kegworth accident in order to better understand the behaviours of the various parties involved. In particular, you will get the opportunity to assess the professional practice of key stakeholders in order to determine whether they acted responsibly and ethically. Open and edit <a href="templates/professional.md" target="_blank">this professional practices table</a>. Enter an `x` in each column where you believe the individual or organisation committed bad professional practice (leave the column blank if you feel they were not guilty of that particular bad practice). Do not change any other content or formatting in the document.  


# 
### Task 12: Submission


Once you have completed all of the activities outlined above, you must submit all 7 documents in a zip file onto the submission point on Blackboard. Please use zip, rather than any other archiving file format as this will make the marking process easier. Please don't change the names of the files, otherwise it will make it difficult to identify which files belong to which tasks. Finally, make sure you submit your completed files (rather than the originals which contain all of the `???` placeholders !)

  


# 
