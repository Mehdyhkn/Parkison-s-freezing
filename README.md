# Parkison-s-freezing

# Introduction

FOG is one of the most disabling and least understood symptoms in Parkinson's disease (PD), and is usually observed in the advanced stage of the disease. FOG can be experienced on turning, in narrow spaces, whilst reaching a destination, and in stressful situations. FOG is commonly observed in the "off" state, but it can also be observed in the "on" state.
It's like you are walking to the supermarket cross the road and suddenly your feet feel like they're stuck on the ground : Freezing on Gait . People explain the feeling during a phrasing episode like the feet are gluted to the floor their are unable to walk. Its happen everywhere and everytime with no signal

## Sources and comprehension of the subject

Freezing of gait https://pubmed.ncbi.nlm.nih.gov/17131225/#:~:text=Freezing%20of%20Gait%20(FOG)%20is,destination%2C%20and%20in%20stressful%20situations. 
Explantion moovie : https://www.youtube.com/watch?v=Pbog3PClpUw&ab_channel=TrinityCollegeDublin



## Context
An estimated 7 to 10 million people around the world have Parkinson’s disease, many of whom suffer from freezing of gait (FOG). During a FOG episode, a patient's feet are “glued” to the ground, preventing them from moving forward despite their attempts. FOG has a profound negative impact on health-related quality of life—people who suffer from FOG are often depressed, have an increased risk of falling, are likelier to be confined to wheelchair use, and have restricted independence.

While researchers have multiple theories to explain when, why, and in whom FOG occurs, there is still no clear understanding of its causes. The ability to objectively and accurately quantify FOG is one of the keys to advancing its understanding and treatment. Collection and analysis of FOG events, such as with your data science skills, could lead to potential treatments.

### Methods of evaluation FOG 

There are many methods of evaluating FOG, though most involve FOG-provoking protocols. 
How 1 ? 
People with FOG are filmed while performing certain tasks that are likely to increase its occurrence. Experts then review the video to score each frame, indicating when FOG occurred. 
Problems 1 ?
While scoring in this manner is relatively reliable and sensitive, it is extremely time-consuming and requires specific expertise.

How 2 ?
Another method involves augmenting FOG-provoking testing with wearable devices. With more sensors, the detection of FOG becomes easier, however, compliance and usability may be reduced. 

How 3 ?
Combination of these two methods + ML methods ( detecting from the lower back have high accuracy)

Data train and test was small and limite to date 

## Purpose 

Develop a machine learning model trained on data collected from a wearable 3D lower back sensor. This work will help researchers to better understand when and why FOG episodes occur in the goal to improve the personalized treatment of age-related movement, cognition, and mobility disorders and to alleviate the associated burden. 
For that : 
- Gain new understandings into the physiologic and pathophysiologic mechanisms that contribute to cognitive and motor function, the factors that influence these functions, and their changes with aging and disease (e.g., Parkinson’s disease, Alzheimer’s). 
- Develop new methods and tools for the early detection and tracking of cognitive and motor decline. A major focus is on using leveraging wearable devices and digital technologies;
- Develop and evaluate novel methods for the prevention and treatment of gait, falls, and cognitive function.

## GOAL 
Detect the start and the stop of each frezing episode and the occurrence in theses series :
Three output : 
- Start Hesitation
- Turn
- Walking 


## Evaluation 

metric : Mean average precision of precision of each event class 

Valid and task labels (in addition to event labels) : ONLY THE PORTIONS OF SERIES WHERE BOTH ARE TRUE SHOULD BE CONSIDER TO BE ANNOTATED 

Prediction are a probability score between 0 and 1

## Data  
The tDCS FOG **(tdcsfog)** dataset, comprising data series collected in the lab, as subjects completed a FOG-provoking protocol.
The DeFOG **(defog)** dataset, comprising data series collected in the subject's home, as subjects completed a FOG-provoking protocol
Series from the tdcsfog dataset are recorded at 128Hz (128 timesteps per second), while series from the defog and daily series are recorded at 100Hz (100 timesteps per second).

**The Daily-living** contains data from 65 people with PD that were recorded using the same device as in the home FoG-provoking dataset (the DeFOG dataset). The daily-living recordings contain ~one week of unlabeled, continuous recordings from an accelerometer device placed on the lower back of the subjects at 100Hz, during their daily living activity.
The 65 PD subjects are comprised of two groups:
45 people with PD that suffer from FoG. They also underwent a FoG-provoking protocol at their home and that data is provided in the DeFOG data set. In the metadata file, these subjects have NFOG questionnaire score higher than 0. 20 people with PD that do not suffer from FoG. In the metadata file, these subjects have NFOG questionnaire score of 0.

**train/** Folder containing the data series in the training set within three subfolders: tdcsfog/, defog/, and notype/ ( Series in the notype folder are from the defog dataset but lack event-type annotations)




### PROTOCOL 
At each visit they completed the freezing of gait provoking protocol described by Ziegler et al. 2010 (DOI: 10.1002/mds.22993) both at "off" and "on" anti-parkinsonian medications while wearing 3D accelerometer on their lower back (Opals by APDM Wearable Technologies, Portland, OR, USA. Sampling rate 128Hz). All FoG provoking trials were videotaped and analyzed offline.

Data recordings include a short period (~2-3s) of quiet standing before the start of the test protocol.

Two visit :  At each visit, the participants were evaluated at Off and On medication states.During the motor assessment, the subjects wore a 3D accelerometer on their lower back (Ax3 by Axivity) which recorded the data with a sample rate of 100Hz. The acceleration units are provided in 

Visit 1 :
During Off medication:

- 4-meter walk test
- Timed Up & Go (TUG) - Single task
- Timed Up & Go (TUG) – Dual-task (subtracting numbers while performing the TUG test) performing the trial while carrying a tray with a bottle on it
- Turning task with alternating directions- Single task (performing 4 x 360 degrees turns, each time alternating the rotation direction).
- Turning task – Dual-task (same as before, but with additional number subtraction task).
- Hotspot Door – A walking trial that involves opening a door, entering another room, turning, and returning to the start point.
- Personalized Hotspot - walking through an area in the house that the subject describes as FoG provoking.

During On medication:
- The protocol is repeated again with the addition of a MiniBest test that is added after the 4 meters walk. See at the end of the protocol elaboration about the MiniBest test.

MiniBest test includes the following parts:

SIT TO STAND.
RISE TO TOES.
STAND ON ONE LEG.
COMPENSATORY STEPPING CORRECTION- FORWARD.
CSC BACKWARD.
CSC LATERAL.
STANCE (FEET TOGETHER) EYES OPEN, FIRM SURFACE.
STANCE (FEET TOGETHER) EYES CLOSED, FOAM SURFACE.
INCLINE EYES CLOSED (Shoulder width, arms at your side).
DYNAMIC GAIT INDEX:
CHANGE IN GAIT SPEED.
WALK WITH HEAD TURNS – HORIZONTAL.
WALK WITH PIVOT TURNS.
STEP OVER OBSTACLES.

At visit 2:
The same protocol that is described for visit 1 was repeated. In addition, the tasks were also performed with auditory cueing, with the exception of tasks that includes dual task (e.g. "Timed Up & Go (TUG) – Dual task" and "Turning task – Dual task").