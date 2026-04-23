# Gamepad And UI System

**Unit Name:** \ Industry Brief

**Student Name:** \ Anna Rogers

**Student ID:** \ 2315276

**Total Word Count:** \ [2895]

**API Reference Link:** \ [https://annarogers04.github.io/WidgetSwitcher-API/](https://annarogers04.github.io/WidgetSwitcher-API/)

**Build Link:** [https://store.steampowered.com/app/4463930/Greedy_Piggies/](https://store.steampowered.com/app/4463930/Greedy_Piggies/)

**Video Demonstration Link:** [https://youtu.be/pE07HoSPoLs](https://youtu.be/pE07HoSPoLs)

---

# Abstract

This development log focuses on the work I did on the menu and UI systems for Greedy Piggies. My main contribution was making controller compatibility, creating controller focus and navigation, and building a widget switcher for the in-game pause menu in Unreal Engine. I focused on making the menus easier to use and making sure they worked properly with controller input.

A big part of this work was making sure the menu system felt smooth and easy to use for the player. I worked on controller focus and navigation, and I also built a widget switcher for the in-game pause menu. I mainly did this to keep the widgets in the same place and make the menu system more streamlined.

The final result was a cleaner and more reliable menu system that was easier for players to use. It also helped me improve my understanding of how UI systems work in Unreal Engine, especially when designing menus for controller input.

---
# Research
What sources or references have you identified as relevant to this task?

For this part of the project, I mainly looked at sources that were useful for controller support, menu navigation, and Unreal’s input system. Since my work was based around controller compatibility, controller focus and navigation, and the widget switcher for the in-game pause menu, I tried to keep my research close to that instead of looking at things that were too broad or unrelated. Most of what I used was practical research, because that helped more with the actual systems I was making.

The sources I looked at included a game reference, Unreal documentation, a YouTube tutorial, a forum post, and a controller setup guide. Each one helped in a different way. Some were more useful for understanding how systems worked, while others were better for giving context or helping with smaller problems I ran into. I also tried to make sure the research connected back to the player experience, especially because menu navigation and controller focus are things the player notices straight away if they do not work properly.

I avoided sources that were not really linked to the part of the project I was doing. There was not much point looking at unrelated game design research when my role was much more focused on UI and controller input. I also found that some tutorials can be useful up to a point, but not always reliable if they are made in an older Unreal version. That became a problem when I was trying to make the remap system, because the video I followed was based on an older setup and some parts did not work properly in Unreal Engine 5.6.1.

## Source 1: Game source – Final Spin

Final Spin was my game reference. I used it more as a general comparison point for the kind of game Greedy Piggies sits alongside, rather than for anything technical. Since it is a multiplayer party game on Steam, it was useful for thinking about the kind of experience and presentation that fits that sort of project. (FINAL SPIN on Steam, s.d.)

- looked at it as a general game reference
- used it to think about player expectations
- used it more for context and inspiration than technical research
- helped me place my menu work in the wider project

This source was helpful for context, but it had limits because it did not tell me anything about how systems were built. It was more useful for the overall feel of the project than for solving development problems.

## Source 2: Documentation source – Enhanced Input in Unreal Engine

Epic’s Enhanced Input documentation was one of the most useful sources for the technical side of this work. Because Epic made Unreal Engine, this was the most reliable source for understanding how the input system was meant to work. It was especially relevant because controller compatibility and menu navigation both connected back to Enhanced Input. (Enhanced Input in UE5 | Tutorial, 2022)

- unused it to understand how Enhanced Input worked
- looked at Input Actions and Input Mapping Contexts
- linked it back to controller compatibility and menu navigation
- used it to compare what should be happening with what was happening in my own project

This source was useful because it gave me a clear explanation of the system I was working with. The only real limitation was that documentation does not always help with every project-specific issue, especially when something goes wrong in practice, but it was still the strongest technical source I used.

## Source 3: Video / tutorial source – control remapping tutorial

The YouTube tutorial was useful because I did try to make a controls remap system for the project. It helped me understand the general structure of that kind of feature and how it could fit into the menu system. The problem was that it was made using an older version of Unreal, so some of it did not translate properly to the version I was using. (Unreal Engine 5.4 - Enhanced Input System Complete Remapping Menu, 2024)

- followed it while trying to build the remap system
- used it to understand the general setup of a remapping menu
- compared the tutorial to what I was building in my own project
- noticed problems once the version differences became clearer
- ended up removing the feature because I could not get it working in time

This source was still useful, even though the final feature did not stay in the game. It helped me get part of the way there, but it also showed me how much version differences can affect Unreal tutorials. That was probably the biggest limitation of this source.

[Watch the tutorial video](https://www.youtube.com/watch?v=o-r6XmLhD8A)

## Source 4: Academic source – Celia Hodent

Celia Hodent’s work on user experience in video games was useful as an academic source because it gave me a better way to talk about usability and player interaction in games. That linked well to my work, because the whole point of improving controller focus and menu navigation was to make the interface easier for the player to use. (Hodent, 2024)

- used it to support the importance of UX in games
- linked it to interface clarity and player interaction
- related it to menu usability
- used it to explain why controller navigation matters from the player side

This source was useful because it helped me explain why this kind of work matters, not just how it works. It was more theoretical than the other sources, so it was not directly useful for building the system, but it worked well as the academic part of the research.

## Source 5: Community source – Unreal forum post

The Unreal Engine forum posts were useful because they addressed smaller, practical problems closely related to my implementation. These included handling menu open and close behaviour with a single input, managing widget focus, and understanding how widget switchers function. All of these topics directly relate to controller-based UI navigation and menu flow.

- reviewed solutions for opening and closing menus using the same input (Close menu with same button as opening - Programming & Scripting / UI, 2024)
- used discussions to inform pause menu flow and state handling
- examined approaches to setting and maintaining widget focus (how to set the focus on a widget - Programming & Scripting / UI, 2015)
- explored how widget switchers can manage UI transitions (I was wondering how Widget Switchers work - Programming & Scripting / UI, 2015)
- related these ideas to controller navigation and focus consistency

These sources were helpful because they provided practical, experience-based solutions that closely matched the issues encountered during development. However, as community forum posts are not formally verified, they are less reliable than official Unreal Engine documentation. For this reason, they were used as supporting references rather than primary sources.extra support than a main source. 

## Source 6: Background source – reWASD controller guide

The reWASD guide was more of a background source than a main one. I used it to think more generally about controller setup and controller usability on PC, rather than as a direct Unreal Engine source. (The easiest way of how to setup Xbox 360 controller on PC, s.d.)
- used it as general background research
- looked at controller setup from the player side
- used it to think more broadly about controller usability
- treated it as extra context rather than a core source

This source was less important than the Unreal documentation, but it still helped as general background research. Its main limitation was that it was not directly about building systems in Unreal, so it was more useful for context than implementation.

---

# Implementation 

## What was your development process and how did decisions evolve?

My work on the project focused on the menu and UI side, especially controller compatibility, controller focus and navigation, and the widget switcher for the in-game pause menu. At the start, the goal was mainly to get the menus working with a controller, but as I kept developing it, the focus shifted more towards making the system feel smoother and more organised. A lot of the choices I made came from testing the menu in engine and noticing what felt awkward, unclear, or inconsistent during actual use.

### controller focus

One of the main things I worked on was creating controller focus for the menus. This mattered because the UI could look correct visually but still feel awkward to use if the focus was not clear. I had to think about which button should be selected first, how focus would move between options, and how to make that easy for the player to follow.

![alt text](<Screenshot 2026-04-23 011314.png>)

_**Figure 1**:** Shows the code used to focus each widget. The code was set on a specific button to gain original focus from and this then allowed gamepad to work._

### widget switcher

I also built a widget switcher for the in-game pause menu. I mainly did this to keep the widgets in the same place and make the menu system more streamlined. Instead of opening separate menus in a less organised way, the widget switcher let me keep the layout consistent while changing the content inside it. This made the pause menu easier to manage and helped the UI feel cleaner overall.

<img width="625" height="590" alt="image-1" src="https://github.com/user-attachments/assets/f5a08725-7e17-4308-a21e-10675acb8dba" />

_**Figure 2:** Shows a simplifed version of the widget swicther code, Its done in a mermaid diagram and shows the flow of the switcher._

### controller navigation

As the work developed, I also spent time improving controller compatibility more generally. This meant checking whether menus could actually be navigated properly, whether focus stayed where it needed to, and whether the player could move through the UI without getting stuck. A lot of this came from trial and error rather than from a fixed plan at the start. Some parts worked quickly, while others only improved once I had tested them in engine and seen how they behaved in practice.

![alt text](<ezgif.com-video-to-gif-converter (15).gif>)

_**Figure 3:** Shows a snippet of me testing the controls in engine and making sure the widget focus is working correctly as well as the widget switcher. This made sure controller navigation was working smoothly._

---
# technical approach

Most of the methods I used were technical rather than creative, because this part of the project was more about making the UI function properly than designing visual assets. The main approach was building the system in Unreal Engine using widgets and blueprint logic. A lot of the process came down to testing small changes, seeing how the menu behaved in engine, and then adjusting it based on what felt wrong or too awkward to use.

### controller-first UI

One of the main things I tried was making the UI work properly with controller input instead of just mouse input. That was one of the less familiar parts of the process because it meant thinking more carefully about focus, navigation order, and how the player moves through menus. It changed the way I approached the UI, because I had to stop thinking about it only as something visual and start thinking about how it would actually feel to use with a controller.

### remap system

I also tried building a controls remap system. This was more experimental for me because it was something I had not built before, and it meant following a tutorial while adapting it to my own project. I managed to get parts of it working, but in the end I had to remove it because I would not have been able to fix it properly in time. Even though it did not stay in the final version, it still changed my approach because it made me more aware of how version differences in Unreal can affect systems like Enhanced Input.

 ![alt text](<Screenshot 2026-04-11 145021.png>)

_**Figure 4:** Shows a verson of the controls menu where gamepad and keyboard and mouse inputs werre possible but it was repeating inputs for no reason._

## Did you experience any technical challenges?

### controller focus and navigation issues

The main technical challenges came from controller navigation, focus behaviour, and the remap system. Controller compatibility was not just about making the controller do something, but about making the menu feel properly usable with it. There were points where the UI technically worked, but the focus did not behave the way I wanted, or the flow between menu elements did not feel smooth enough. This meant I had to keep testing and adjusting things until the navigation felt more consistent.

- Image to use here: a screenshot that shows controller focus in use, or a menu state where the navigation was being tested. This should help support the point that the challenge was about usability and menu flow, not just visual layout.
Caption: Figure X: Testing controller focus and menu navigation in the pause menu.

### remap system problem

The remap system caused the biggest issue. I followed a tutorial for it, but the video was made for an older version of Unreal, while this project was made in Unreal Engine 5.6.1. Because of that, parts of the Enhanced Input setup were noticeably different, and this started causing conflicts once I had added all the controls into the Input Mapping Context. I spent time trying to work around it, but eventually I had to remove the feature because I was not going to be able to fix it properly before the deadline.

![alt text](<Screenshot 2026-04-11 041821.png>)
![alt text](<Screenshot 2026-04-11 040753.png>)

_**Figure 5 and 6:** Shows when the controls menu broke and the inputs either werent showing up, they were reapeating or half showing half not._

## reflection on the issue

That part of the process was frustrating, but it was still useful because it showed me the limits of relying too heavily on a tutorial without checking how well it matched the version I was using. It also made me more confident in focusing on the parts of the system that were working well, like the widget switcher and controller navigation, rather than spending too much time trying to force in something that was not ready.

---
# Testing

## What testing methods did you use?

Most of the testing for my part of the project was internal testing carried out in Unreal while checking the pause menu in use. Since my work was focused on the menu system and controller support, I mainly tested how it behaved during actual use rather than only checking if it looked right on screen.

I also tested the build through Steam, because it needed to work properly there and not just inside Unreal. This was important because something can seem fine during development but behave differently once it is running through Steam.

### scene testing

Part of the testing involved checking how the pause menu behaved in the actual scene rather than on its own. This was important because the menu needed to feel like part of the game while it was running, not just like a separate UI element.

![alt text](<Screenshot 2026-04-09 141655.png>)

_**Figure 7:** Shows me testing the game in engine after setting up the widget switcher properly, as shown the pause menu shows on the character select menu which is the lobby, this was not planned and shouldnt have happened._

### steam testing

Testing through Steam became one of the most important parts of this stage because it showed that controller support is currently not working properly there. Since the final build needs controller support through Steam, this is an important issue to mention.

## What were your key goals in testing?

The main goal of testing was to make sure the pause menu worked properly in the actual game and not just in development. I wanted to check that it opened correctly, sat properly in the scene, and still felt consistent during play.

Another goal was making sure the build behaved properly outside Unreal. Since the final version needs to work through Steam, it was important to test it there as well instead of relying only on editor testing.

## What did you observe or learn from testing?

One of the main things I found was that testing inside Unreal does not always show everything that will happen in the final build. The clearest example of this was Steam, where controller support is currently not working properly even though the menu system had already been tested during development.

Testing in the scene was also useful because it showed whether the pause menu actually felt like part of the game while it was running. This made the testing feel more practical and gave a better sense of how the system would come across in the final build.

### remap system

The controls remap system was taken out of the project because it was not working reliably enough to keep in the final build. Once it became clear that it would not be fixed in time, it made more sense to remove it and focus on the parts of the menu system that were already working well.

## How did testing influence the final result?

Testing influenced the final result by showing what was working in context and what still needed attention. It confirmed that the pause menu needed to be tested in the actual scene and not just as a separate UI element, and it also highlighted the Steam controller issue as something that still needs to be fixed.

Overall, testing helped keep the focus on the parts of the system that were strongest, while also showing where the final build still behaves differently outside the editor.

# Testing Table
| Test Area                | Test Type        | What Was Checked                                              | Main Result                                          | Changes Made                                |
| ------------------------ | ---------------- | ------------------------------------------------------------- | ---------------------------------------------------- | ------------------------------------------- |
| Controller focus         | Internal testing | Whether the selected button was always clear                  | Focus needed adjusting in some menu states           | Refined focus behaviour and navigation flow |
| Menu navigation          | Internal testing | Whether the player could move smoothly through the pause menu | Some movement felt awkward at first                  | Improved navigation order                   |
| Widget switcher          | Internal testing | Whether sections changed cleanly without breaking layout      | Worked well and kept the layout consistent           | Kept as part of the final menu system       |
| Remap system             | Internal testing | Whether controls could be remapped correctly                  | Caused conflicts and did not work reliably           | Removed from final build                    |
| Steam controller support | Build testing    | Whether controller input worked properly through Steam        | Controller currently does not work properly in Steam | Marked as an issue that still needs fixing  |


**Figure X:** Testing summary for controller focus, menu navigation, widget switching, and Steam controller support.

---
# Critical Reflection 

## What went well?

I think one of the stronger parts of my work was making the pause menu feel clearer and easier to use. The controller focus and navigation helped a lot with that, and the widget switcher made the menu feel more structured. Even though there are things I would improve, I still think it made the UI feel more complete.

I also learned a lot more about Unreal UI systems through this part of the project. Working on it gave me a better understanding of how controller input, focus, and menu structure all work together.

## What could be improved or done differently next time?

I think I could have made my widget switcher a lot better. It worked for what I needed, but it was not very optimised, and I should have done more research into it before building it the way I did. Looking back, I was more focused on making it work than making it as strong as it could have been.

I also should have looked into Steam controller support much earlier. At the start, I was focused on getting the controls to work in Unreal, so adapting them for Steam became more rushed later on. When I tested it through Steam, it was much closer to submission than it should have been, and I had to go back and make changes. Next time I would start testing in Steam earlier so those issues come up sooner.

---

## Bibliography

- FINAL SPIN on Steam (s.d.) At: [https://store.steampowered.com/app/2954260/FINAL_SPIN/](https://store.steampowered.com/app/2954260/FINAL_SPIN/) (Accessed  23/04/2026).

- Close menu with same button as opening - Programming & Scripting / UI (2024) At: [https://forums.unrealengine.com/t/close-menu-with-same-button-as-opening/485710/13](https://forums.unrealengine.com/t/close-menu-with-same-button-as-opening/485710/13) (Accessed  23/04/2026).

- Enhanced Input in UE5 | Tutorial (2022) At: [https://dev.epicgames.com/community/learning/tutorials/eD13/unreal-engine-enhanced-input-in-ue5](https://dev.epicgames.com/community/learning/tutorials/eD13/unreal-engine-enhanced-input-in-ue5) (Accessed  22/04/2026).

- Hodent, C. (2024) 'Cognitive Psychology Applied to User Experience in Video Games' In: Encyclopedia of Computer Graphics and Games. Springer, Cham. pp.338–344. At: [https://link.springer.com/rwe/10.1007/978-3-031-23161-2_53](https://link.springer.com/rwe/10.1007/978-3-031-23161-2_53) (Accessed  23/04/2026).

- How to set the focus on a widget - Programming & Scripting / UI (2015) At: [https://forums.unrealengine.com/t/how-to-set-the-focus-on-a-widget/304225](https://forums.unrealengine.com/t/how-to-set-the-focus-on-a-widget/304225) (Accessed  22/04/2026).

-   I was wondering how Widget Switchers work - Programming & Scripting / UI (2015) At: [https://forums.unrealengine.com/t/i-was-wondering-how-widget-switchers-work/304307/3](https://forums.unrealengine.com/t/i-was-wondering-how-widget-switchers-work/304307/3) (Accessed  22/04/2026).

- The easiest way of how to setup Xbox 360 controller on PC (s.d.) At: [https://www.rewasd.com/blog/post/how-to-setup-xbox-360-controller-on-pc](https://www.rewasd.com/blog/post/how-to-setup-xbox-360-controller-on-pc) (Accessed  22/04/2026).

- Unreal Engine 5.4 - Enhanced Input System Complete Remapping Menu (2024) Directed by Émile. At: [https://www.youtube.com/watch?v=o-r6XmLhD8A](https://www.youtube.com/watch?v=o-r6XmLhD8A) (Accessed  22/04/2026).

## AI Decleration
ChatGbt 5.4 was used to help structure this Commentary.