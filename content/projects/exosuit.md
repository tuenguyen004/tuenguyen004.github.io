+++
title = "Soft Robotics Exosuit: Posture Categorization"
date = "Date of Post Written Here"
daterange = "Jun 2020 - May 2021"
author = "Undegraduate Researcher"
cover = "/projects/exosuit/exosuit_cover.png"
tags = ["software", "biomechanics", "research"]
keywords = ["keywords here"]
description = "As part of [Tufts Human Factors Lab](https://sites.tufts.edu/humanfactors/2017/09/18/facilities/), Soft Robotics Exosuit is a student-led research initiative designing a soft-robotics powered exoskeleton to correct sedentary postures using real-time inertial measurement unit (IMU) and electromyography (EMG) data."
showFullContent = false
+++

As part of [Tufts Human Factors Lab](https://sites.tufts.edu/humanfactors/2017/09/18/facilities/), Soft Robotics Exosuit is a student-led research initiative designing a soft-robotics powered exoskeleton to correct sedentary postures using real-time inertial measurement unit (IMU) and electromyography (EMG) data.

{{< figure src="/projects/exosuit/exosuit_physical_prototype.png" alt="Physical Prototype of the Exosuit" position="right" caption="Physical Prototype of the 'Exosuit'">}}

Joined Exosuit in late May 2020, I was a research assistant in the Motion Study Team. Over the summer, `I single-handedly developed a mathematical model that categorizes different sitting postures` with upper body movement and muscle activity datasets collected from the Exosuit's physical prototype.

Continuing my work as a part-time undergraduate researcher during the school year, I proposed the team to `build a machine learning model that predicts and intentionally overfits to the user's habits, learning from movement and personalize your experience!` The idea was developed into a companion mobile app for the Exosuit, reminding you to correct postures promptly.


#### >> Visualize Past Datasets

As part of onboarding, I wrote for myself a MATLAB script visualizing the datasets captured by the Exosuit's sensors. The script takes any .csv files and output them as 3D scatter plots. What supposedly was a `learning-on-the-job program has now became an frequently-used tool` for the Motion Study Team to validate our usability testing sessions.

{{< figure src="/projects/exosuit/visualize_script.png" caption="The user interface and sample outputs of my program on MATLAB">}}

#### >> Model the Upper Torso via Wearnotch

With hardware prototyping postponed due to the COVID-19 pandemic, we relied on a third-party motion-capturing sensors called [Wearnotch](https://wearnotch.com/) in place of the Exosuit. Working remotely, I was then tasked with two main objectives:
- Analyze the motion-capturing framework of Wearnotch sensors 
- Develop a model to recognize postures using a minimal number of Wearnotch sensors. 

I designed and conducted my own pilot studies to learn how the Wearnotch technology capture movement into .csv files. Subsequently, we deduced that `only two Wearnotch sensors were needed` to replicate the Exosuit, defining the human's upper torso as:

{{< figure src="/projects/exosuit/wearnotch_torso_model.png" position="right" caption="The proposed Exosuit model using Wearnotch sensors">}}

- Chest Top / Chest Bottom / Tummy 

With this knowledge in mind, I proposed that siting postures can be quantified with FOUR (4) motion elements as followed: 

- *Upright*
- *Back Not Straight*
- *Slouching*
- *Twist and Turn*

#### >> Upright

{{< figure src="/projects/exosuit/upright.png" position="right">}}

Our model defines "upright" as a central zone revolving around one's origin in x-z space. By tracking each body part's displacement from [0, y, 0], our model can detect that the user has left the zone and lost its uprightness. The leaving directions of each parts are recorded. 

#### >> Back-Not-Straight

{{< figure src="/projects/exosuit/back_not_straight.png" position="right">}}

By tracking each body part's angles relative to one another, the model determines whether one's back is straight from both anterior (front) and lateral (side) views. When one's back deviates from the straight position in either view, a Back-not-Straight signal is detected. If this signal remains for longer, will the signal be recorded. Else, the signal is ignored!

#### >> Slouching

{{< figure src="/projects/exosuit/slouching.png" position="right">}}

We introduced a new body part into our model to accurately characterize this motion: Hip! We defined slouching occurs when both chest and hip rotate toward the front. By tracking for Chest Top's clockwise and Hip's counter-clockwise rotations, our model can now check for "slumpy, drooping features" of a posture.

#### >> Twisting

{{< figure src="/projects/exosuit/twistnturn.png" position="right">}}

This feature is the least-common, but it's essential to describe the posture changes associated with "twists and turns" movements. By tracking the chest's lateral angular displacement, our model identifies any left/right rotations of the upper torso.

#### >> Key Takeaways

Over the summer, I have written multiple MATLAB and Python programs (functions, classes definitions, scripts) that helps interpret and analyze the raw IMU data captured by Exosuit. For me, the most exciting challenge was `translating the conceptual model described above into written code`. Feel free to check out my implementation [here!](https://github.com/tuenguyen004/exosuit-research)

{{< figure src="/projects/exosuit/code_snippet.png">}}

As a continuation of my summer work, I am currently supporting the Exosuit's Software Team to create a Machine Learning model for Exosuit. Our goal is to detect harmful posture changes and notify the users before they occur. More specifically, we are looking to predict the user's posture using the acquired knowledge of habitual movements, personalizing their experience with the mobile app to help breaks any undesirable posture habits. On the side, I'm also a mentor to the current Motion Study Team, providing my expertise and inputs to our current mathematical model and for any groundwork I have done.
