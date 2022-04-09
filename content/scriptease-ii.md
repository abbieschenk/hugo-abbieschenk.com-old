---
title: "ScriptEase II"
description: "A program that allows video game designers to create scripts using a GUI."
socialcloudinaryimg: "projects/scriptease-ii/seii_vcezit.png"
date: 2014-09-01T09:30:00-06:00
tags: ["dev", "java", "gaming"]
draft: false
---
ScriptEase II (SEII) is a program that allows video game designers to add scripts and conversations to their games without knowing how to code by using a graphical user interface. It can work with any game engine using a "translator."

Find it on [GitHub](https://github.com/UA-ScriptEase/scriptease).

SEII was created by BELIEVE at the University of Alberta, a research group created to study believability in video games. The original ScriptEase only worked with the Neverwinter Nights Aurora toolkit, which was used to teach the CMPUT 250: Computers and Games course.

{{< cloudinary src="projects/scriptease-ii/seii_vcezit.png" alt="A screenshot of the ScriptEase II visual code editor in four main panels, with scripting functions on the left and bottom right, and the story graph shown on the top right." caption="A screenshot of the ScriptEase II with scripting functions and the story graph.">}}

I wrote the first Unity3D translator. SEII was always designed with interoperability in mind, but it wasn't actually tested. The Unity3D translator worked as a proof of concept, and was used with other BELIEVE projects.

I also worked on the conversation editor and story graph which went beyond simple "if/then" type visual scripting to create a system to keep track of conversations and stories in games. This led to the discovery that SEII was slowly corrupting the Neverwtiner Nights files. I remember racing to fix this before we released the beta to students, reverse-engineering the SEII-generated, SE-generated, and Aurora-generated game files to find out what part of the bytecode was generating incorrectly. 

I co-authored a proceedings paper published at the Ninth AAAI Conference on Artificial Intelligence and Interactive Digital Entertainment (AIIDE) in 2013, which can be read [here](/pdf/2013aiide_r.pdf). I also presented it as a research poster at the 2013 GRAND-NCE Conference in Toronto, and at a 2013 GRAND Digital Wave Workshop in Calgary.