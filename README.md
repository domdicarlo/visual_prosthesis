# Seizure Filter program for the Visual Prosthesis Project at UChicago

## Some context
Here I have some code I did for the Visual Prosthesis Project, one program designed to detect changes in EEG signal indicative of a seizure in a research subject undergoing brain monitoring.

More information on the Intracortical Visual Prosthesis Project (ICVP) can be found (here)[https://chicagolighthouse.org/icvp/] and also (here)[https://news.uchicago.edu/story/uchicago-receives-24-million-grant-build-implants-could-help-restore-vision]. In a nutshell, the idea is to take a camera that takes in visual input, and then use this input to directly stimulate the visual part of the brain in order for the subject to see what the camera sees. These subjects do not have eyes that can connect to their visual cortex, so the camera and direct stimulation is to bypass the eyes entirely. Not all blind patients can use this sort of experimental treatment of course. Sometimes the visual processing area of the brain is at fault, in which case this project would be no use, since we are depending on its stimulation to restore vision. 

This effort is a huge collaboration and my role in the project was one small part of a much larger team. I am glad I can say I contributed to this awesome research. As of now (9/2/2019), trials have not begun, but are soon on the way.

## What my program does

This program interfaces with an EEG amplifier and takes in its voltage readings that would normally be used to plot EEG brain scan data. Instead, here the EEG readings are analyzed for pre seizure activity. One worry in this ICVP is that direct stimulation of the brain can result in seizures. This program is important in its ability to detect a seizure before it actually happens, by finding patterns in the EEG measurements. The method of detection is Root Mean Square (RMS) analysis, which uses the RMS of a set of EEG readings over a specific interval of time and observes any large change in this value over time. If this interval changes greatly this is indicative of pre-seizure like activity, and would help inform the experiment runners on whether or not to reduce or stop all stimulation.

## How to use

Sadly, this cannot be used unless you have some other proprietary software such as OpenViBE. Some of this software is paid for and used only for research purposes. It also only specifically works with the EEG amplifier we used in lab. This program only provided a blueprint for the more official software team of the ICVP to then work out for specific changing needs. It is not really complete on its own, but it does what it set out to do, which is provide a rough RMS analysis of one EEG channel and present a monitoring bar that green (safe) -> yellow (caution) -> red (stop!).  

I am including it here as it showcases my ability to write a mathematically complicated program that communicates with a TCP network as well as basic proficiency in C#. It is by no means polished, however. It may also be of use to you if you need to write software for a similar task in a research effort. The code is fairly well commented to explain the logic of its operation. 
