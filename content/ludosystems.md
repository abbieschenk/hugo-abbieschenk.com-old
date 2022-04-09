---
title: "Ludo.Systems"
description: "A tree-based visual game development tool designed for non-programmmers, exportable in common formats to work with almost any game engine."
date: 2021-06-10T09:30:00-06:00
tags: ["dev", "react", "java", "spring boot", "postgresql", "work in progress"]
socialcloudinaryimg: "projects/ludo-systems/dialogue_iodzkr.png"
draft: false
---
[Ludo.Systems](https://ludo.systems) is a set of visual game development tools designed for non-programmmers, exportable in common formats that are easy for programmers to add to almost any game engine. It is currently in an experimental release to try out as I continue work on it.

I built Ludo.Systems using React.js on the frontend, which interacts with an API I built in Spring Boot that works with a PostgreSQL database. The app is delivered via Netlify, and the API via the free tier on Heroku, so it will be a bit slow until fully released. The code and everything else is available on [GitHub](https://github.com/LudoSystems). The site has so far been built by myself, including all designs, icons, logos, etc. Information on contributing and new features can be found on [Ludo.Systems](https://ludo.systems).

The first and currently available tool is called Nodes. You can use it to set up parts of your game that make more sense to plan with a graph than in a text editor, such as game conversations or quest systems. The created graph can then be exported in .json, which can be integrated into most game engine scripting languages. 

{{< youtubex 8LtmX2naGvc >}}

The intent would be for a non-programmer to use this tool to create copy for branching parts of the game in it, and then the programmer to implement systems that can work with these .json files. This means the non-programmer doesn't need to open the game engine to write conversations, or plan a complex quest system. The attributes could also be used to call specific hooks in the game engine at certain points of a quest or conversation.

{{< cloudinary src="projects/ludo-systems/dialogue_iodzkr.png" alt="An example of a branching dialogue system created in Ludo.Systems Nodes." caption="An example of a branching dialogue system created in Ludo.Systems Nodes." >}}

Ludo.Systems draws from [my first programming experience working on ScriptEase II](https://abbieschenk.com/projects/scriptease-ii) at the University of Alberta, a visual game development program that worked with different translators to integrate with game engines. I worked a lot on a node-based system that was used to create and edit conversations and quests (sound familiar?). ScriptEase II is now open source, and at this point likely out of date.

{{< cloudinary src="projects/ludo-systems/quest_oz8n3d.png" alt="An example of a branching quest system created in Ludo.Systems Nodes." caption="An example of a branching quest system created in Ludo.Systems Nodes." >}}

I used those concepts to make [ConvoGame](https://abbieschenk.com/projects/catlandia/#convogame), an internal dialogue editor tool for an independent video game. I always wanted to take this idea further. Ludo.Systems is the next continuation of my career-long research into visual development systems.