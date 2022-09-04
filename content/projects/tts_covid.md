+++
title = "COVID-19 Testing at Tufts University"
date = "Sep 2020 - Jun 2021"
daterange = "Sep 2020 - Jun 2021"
author = "Hardware Engineer Intern"
cover = "/projects/tts_covid/tts_covid_cover.jpg"
tags = ["hardware", "fabrication", "3d-design", "electronics"]
keywords = ["keywords here"]
description = "During my 2nd year, I joined [Tufts Technology Services](https://coronavirus.tufts.edu/testing-at-tufts) as a part-time intern to work with the university's surveillance COVID-19 testing program. Together with six other Tufts students, we created solutions to automate the testing workflow and eliminate invalid samples."
showFullContent = false
+++

During my 2nd year, I joined [Tufts Technology Services (TTS)](https://coronavirus.tufts.edu/testing-at-tufts) as a part-time intern to work with the university's surveillance COVID-19 testing program. Together with six other Tufts students, we created solutions to automate the testing workflow and eliminate invalid samples. Specifically, I was leading the AutoLabel subteam and fabricated all hardware components for the team. 

{{< figure src="/projects/tts_covid/covid_testing_steps.png" alt="Steps for COVID Surveillance Testing at Tufts" position="right">}}

#### >> How Surveillance Testing Works?

Let's first walkthrough the testing program at Tufts to see where and how our work fit in!

`STEP 1:` Begin by tapping your Tufts ID at one of the check-in stations.

`STEP 2:` Receive swab & specimen tube attached with a barcode label unique to you.

`STEP 3:` Self-collect sample from your nose and place the swabs into specimen tube.

`STEP 4:` Give specimen tubes to staff before getting results via email within 24 hours.

#### >> Problem Statement

Approximately 15% of the time, some specimen tubes led to inconclusive and failures at the lab, causing `result delays and the inconvenience of coming back the next day to retest` for community members. We were tasked `to track down these inefficiencies` and developed methods to improve upon the current processes. 

With some time spent in the testing centers (and multiple trash bins), we found what was the ROOT CAUSE for the invalid results:  `unreadable barcodes with inconsistent placement`. Some of them were even ripped, due to what we generalized as "human errors".

{{< figure src="/projects/tts_covid/problems_found.png" alt="Problems Found">}}

#### >> Approach & Methods

After determining many causal factors and narrowing down one root cause from the existing protocols, we discused with TTS adminstration and proposed two solutions:

1. `Automate the label peeling and placement on specimen tubes` (happened in Step 2)
2. `Validate each specimen tube's readibility before sending to lab` (happened in Step 4)

We divided ourselves into two sub-teams called AutoLabel and ImageProcessing as names for the MVPs, with me and Sam Chung '22 leading the development for each respective groups to develop customized hardware and software solutions for the existing testing workflow.

#### >> Solution 1: Auto-peeling Labels!

{{< figure src="/projects/tts_covid/autopeeler_square.png" alt="Closeu-up shot of AutoPeeler" position="left">}}

*AutoLabel (noun.)* is `a two-part machine that can apply the barcode labels onto specimen tubes with better uniformity and consistency` than they are currently being done. The design first involves an add-on module that peels one printed label. The machine will then accurately place a label onto the specimen tube and return to the user in approximately 10 seconds. 

In the subteam, I designed the add-on module for peeling printed labels`` which was dubbed by my teammates as `The AutoPeeler`, while the other two members worked on the machine to place labels automatically from *the AutoPeeler* onto the specimen tube. 

{{< figure src="/projects/tts_covid/autopeeler.png" alt="The AutoPeeler">}}

{{< figure src="/projects/tts_covid/iterative_design.png" alt="Iterative Design of Platform and Peeling Angles" position="right">}}

The add-on module pulls the spool of blank labels over a sharp angle to automatically peel the newly-printed labels off the backing tape. To do so, I built a platform consisting of a servo-powered spool `to create and relieve tension with a bottom-facing design such that it can be placed on & removed from different label printer models`. For software implementation, I used Arduino and wrote Python scripts on Linux to match the timing of existing printer. 

`I also iterated through different peeling angles` to determine the design to get the barcode labels at an optimal location for the rest of the assembly. I designed hardware components on SolidWorks and rapid-prototyped them on 3D printers in the [Nolop Makerspace](https://nolop.org/).

Below is a video demonstration of how the AutoPeeler works!

{{< youtube DQ24KcTyxoU >}}


#### >> Solution 2: The Magic Box!

{{< figure src="/projects/tts_covid/imageprocessing_work.png" alt="My Work for ImageProcessing" position="left">}}

*ImageProcessing (noun.)* is `a data-collecting device that captures images of all specimen tubes leaving the testing centers`. It uses a Raspberry Pi and six high-definition cameras to detect any errors that can be intercepted and fixed before sending to the lab. To utilize this device, an additional procedure is added to Step 4. The staff will insert the specimen tube into the slot and press down onto it. A green LED and a beep sound from a buzzer will signal once images has been successfully recorded.

Since ImageProcessing was a software-focused subteam, only one member was working on the physical prototype. `So I helped with the design of the main body frame, as well fabricating wooden & acrylic parts on the laser-cutter!`

#### >> Field-testing & Takeaways 

I was given the opportunity `to conduct field-testing for the AutoPeeler` at one of the Tufts COVID-19 testing centers. While it was very exciting to see my prototype in action, I also got to `observe and identify a flaw in my design` after a few days: many of the staffs struggled with loading a new spool of blank labels due to `the procedure not being user-friendly`.

Using this observation, `I improved the fixture of the platform with self-fastening features`, reducing the number of screws to allow for a more intuitive user experience. The next week I manufactured a few more prototypes with the improved design and received much more positive feedback from the staffs!

{{< youtube DIDVPaK9syo >}}

At the end of the internship, `we presented our technical work and results in front of about 150 TTS employees (on Zoom, unfortunately)`. I was reminded again that what we had worked on is greatly important to Tufts and the communities around us, keeping everyone safe during the pandemic! I'm thankful for the opportunity to not only learn a lot about engineering in real life but also the chance to give back to my university with the skills I'm learning at Tufts!