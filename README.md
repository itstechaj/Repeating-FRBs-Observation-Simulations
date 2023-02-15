# Repeating-FRBs-Observation-Simulations
## Introduction: 

FRBs are brief, intense radio emissions that last a few milliseconds and originate from an unknown source. The first FRB was discovered in 2007, and since then, several dozen have been discovered, resulting in extensive research on the subject. Despite extensive research, the origin of FRBs is still unknown, making it one of the most fascinating astronomical phenomena in recent years.

## Candidates for the Fast Radio Burst:
Several theories have been put forward to explain the origin of FRBs, including collapsed stars, extragalactic objects, and even extraterrestrial signals. However, the most prominent candidates are:

•	Neutron Star Mergers: According to this theory, FRBs are the result of two neutron stars merging, releasing a massive amount of energy in the process. The discovery of a repeating FRB near a massive galaxy supports this theory, implying that the source is a neutron star merger. For example, it could have frequencies as high as 8 GHz.

•	Flaring Magnets: This theory suggests that FRBs are a result of the release of energy from a magnetic star, such as a pulsar or a magnetar. The sudden release of energy creates a short burst of radio waves, which are then detected as an FRB. For example, it could have frequencies as high as 1 GHz.

•	Extragalactic Objects: This theory suggests that FRBs are a result of an astronomical event occurring in another galaxy, such as a supernova or a black hole. For example, it could have frequencies in range of  KHz.

## Ways to Discover/Detect Fast Radio Bursts:

•	Radio Telescopes: The primary tool for detecting FRBs is radio telescopes. The size and sensitivity of the telescopes are important factors in detecting these bursts. Larger, more sensitive telescopes, such as the Canadian Hydrogen Intensity Mapping Experiment (CHIME) and the Australian Square Kilometer Array Pathfinder (ASKAP), have detected a significant number of FRBs.

•	Machine Learning Algorithms: To classify radio signals and determine whether they are FRBs, machine learning algorithms can be used. This allows astronomers to identify FRBs more quickly and efficiently, saving time and resources that would otherwise be spent manually analyzing the signals. CNN, SVM, RF Classifier, etc.

Repeating FRBs: Repeating FRBs are crucial in understanding the origin of FRBs, as they provide an opportunity to observe the same burst multiple times. Detecting repeating FRBs is crucial in determining the location of the source and unlocking the secrets of the phenomenon.
## Our Goal: 
To identify if there is any selection effect a telescope would show in discovering/detecting periodically repeating FRBs

## Simulating Repeating FRB  data :
To simulate an FRB, we need to generate its observational parameters. These are as follows:
1.	Right ascension (RA)
2.	Declination (Dec) 
FRBs are seen to be uniformly distributed over the entire sky ⇒ RA = [0, 360) deg, DEC= [-90, 90) deg 
3.	Period (P) Assume periods are uniformly distributed [1, 200] days 
4.	Duty cycle (D) Assume the duty cycle coming uniformly from [0.1, 0.5) 
5.	Start Phase (phs) Assume the start phase from [0, 1) 
6.	A reference epoch (that is “”). 

All these parameters will be randomly generated (a uniform distribution because we really do not know what distribution these parameters would take) between the given range, and to reproduce the same set of randomly generated numbers, we need to keep track of the seed number. After all these parameters are generated, we need to repeat this for multiple FRBs. A set of FRBs with an associated seed number is created and saved.

## Simulating The Telescope:
Simulating a telescope basically means predicting what part of the sky it will see and how it will change during the course of time. For this, the location and altitude of the telescope are required.
Our Telescope:
ORT Image : 
![ort img](https://user-images.githubusercontent.com/74065677/219050635-635a1161-327d-4e36-83c8-6277a8a91a73.png)

Specifications:
![ort specs](https://user-images.githubusercontent.com/74065677/219050248-56412f15-b51e-45c7-be96-b6050381a837.png)


For this project we will simulate Ooty Radio Telescope, it is located in the southern state of Tamil Nadu, India. The coordinates of the Ooty Radio Telescope are approximately 11.4047° N, 76.7254° E. The altitude of the observatory is approximately 2,200 meters (7,218 feet) above sea level.
Here we assume our telescope as transit-type (immovable) radio telescopes, we had to simulate its field of view/ beam as well. For ORT, it happens to be roughly in the shape of an ellipse, and its center is positioned at the zenith. Precisely, N-S = 27.4 deg and E-W = 2-3 deg.

## What do we mean by observed ? :
Consider a repeating FRB source we simulate. Its position in the sky has to be calculated for every minute of each day for two years continuously. Then check whether at any point this source passes through the field of view/beam of the telescope. The entry and exit time of the source crossing the beam has to be noted, including all of its other simulated parameters like RA ,Dec, Period, Duty Cycle, Phase and then this source will be considered as observed.
