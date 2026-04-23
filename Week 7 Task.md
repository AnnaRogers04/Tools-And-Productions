# Production Pitch: Widget Switcher UI System for Greedy Piggies

## 1. Overview of the System
For this project, I developed a Widget Switcher system for Greedy Piggies using Unreal Engine 5.6.1 and Blueprints. The purpose of this system is to control which menu screen is active at any time. It supports the Pause, Options, Sound, and Graphics menus. The system is managed through the PC_MainInstance Player Controller and uses an E_MenuState enum to switch between screens. It also handles pausing the game, changing input modes, showing or hiding the mouse cursor, and supporting gamepad menu navigation for Unreal, as it is not currently functional for Steam yet.

## 2. Technical Stack Needed in Production
To support this system in production, the main tools needed would be Unreal Engine 5.6.1, Blueprint scripting, and Unreal’s Enhanced Input system. These are the core parts used to build and run the menu system. To manage the project properly in a studio environment, it would also need source control such as GitHub or Perforce, a build system for testing and packaging the game, and bug tracking software to record and fix UI or input problems.

## 3. Hardware and Cloud Requirements
The hardware needed for this system is quite basic. It would require a PC that can run Unreal Engine 5 and a gamepad for testing. As this is a UI system, it would not need its own dedicated server. If online features are added later, cloud services may also be needed for save data, analytics, or player accounts. These could be hosted on AWS, Azure, or Google Cloud.

## 4. Estimated Costs

| Cost Area | Without Multiplayer | Low Cost Indie Multiplayer | Full Multiplayer Setup |
|---|---:|---:|---:|
| Initial setup | £300 to £1,000 | £500 to £1,500 | £800 to £3,000+ |
| Monthly running costs | £20 to £100 per month | £50 to £200 per month | £100 to £500+ per month |
| What this includes | Testing hardware, software tools, development setup, storage, backups, and build services | Standard development costs plus basic server hosting, simple backend tools, and small scale online support | All standard development costs plus dedicated server hosting, backend services, networking support, cloud storage, and live maintenance |

(Dedicated Game Server Hosting - Amazon GameLift Pricing - Amazon Web Services, s.d.), (Jorri, 2023)

The Widget Switcher system by itself is low cost to support. A small indie multiplayer version could still be affordable, but a full multiplayer setup would cost more because of server hosting, backend systems, and ongoing maintenance.

## 5. Target Platforms
The target platform for this system is PC. Players can use keyboard and mouse or a gamepad. Console support could be added later, but it would need extra work. One limitation is that the system currently works in Unreal only, as Steam Input is not yet fully supported.

## 6. How the System Works
The Widget Switcher works by taking player input and passing it to the Player Controller. The controller checks the current menu state, removes the old widget, creates the new menu widget, and updates the input mode, cursor visibility, and gamepad focus. This allows the player to move cleanly between gameplay and menu screens.

### mermaid

<img width="625" height="590" alt="image-1" src="https://github.com/user-attachments/assets/f5a08725-7e17-4308-a21e-10675acb8dba" />

## 7. Production Support Considerations
Overall, this system is a strong foundation for menu management and controller support. To use it in a full production environment, it would need regular testing, stable source control, build automation, and continued maintenance for platform compatibility and input support. If the project later includes online features, extra backend services and support costs would also need to be considered.

---

## Bibliography
- Dedicated Game Server Hosting - Amazon GameLift Pricing - Amazon Web Services (s.d.) At: [https://aws.amazon.com/gamelift/servers/pricing/](https://aws.amazon.com/gamelift/servers/pricing/) (Accessed  23/04/2026).
- Jorri, T. (2023) Your Comprehensive Guide To Mobile Game Server Costs [Updated for 2026]. At: https://www.metaplay.io/blog/mobile-game-server-costs (Accessed  23/04/2026).

## AI Usage Declaration

Chatgbt 5.4 was used to help structre this writeup and create a mermaid diagram.
