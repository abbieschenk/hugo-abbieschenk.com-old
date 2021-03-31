---
title: "Catlandia"
description: "A cat-based Unity3D role playing game released for PC, macOS, Android, and iOS."
date: 2018-05-01T09:30:00-06:00
tags: ["dev", "unity3D", "gaming"]
draft: false
---
I assisted with initial development of Catlandia, a cat-based Unity3D role playing game. Although I left the team in 2018 to focus on my MA thesis, the game was later released on PC and macOS through Steam, and the Android and iOS app stores.

Check out the [Catlandia website](https://catlandiagame.com) for more information about the game.

{{< youtubex nNOuHN7qOHE >}}

# ConvoGame
My main role was getting initial development set up. As a story-based RPG, conversations and dialogue were an essential part of the game. At the time, Unity3D conversation editors were too technical and cost money to use.

Using my experience from working on [ScriptEase II](/projects/scriptease-ii), I built a game-agnostic, web-based conversation editor called ConvoGame. ConvoGame allowed for the creation of branching conversations, and then exported everything as .json files. I wrote Unity3D scripts to read these into an initial version of Catlandia.

{{< cloudinary src="projects/catlandia/convogame_ez0fvy.png" alt="A screenshot of the ConvoGame game conversation editor, showing the conversation tree and editor panel filled with some basic text from the Catlandia game." >}}

You can try out ConvoGame [here](/convogame) and find it on [GitHub](https://github.com/abbieschenk/convogame). Please note that it was primarily intended as an internal development tool. Although I planned to develop it further, it remains in that state along with all of the minor bugs that came with it.

I am currently using what I learned to build a new editor with React and a Java/PostgreSQL backend, and look forward to publishing more about that soon.