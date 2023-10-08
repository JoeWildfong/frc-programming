# Overview

Here's a breakdown of the hardware commonly involved in FRC competitions:

```mermaid
flowchart TD
    Computer[Computer]
    subgraph Robot
        RIO(("RoboRIO Microcontroller"))
        Radio([Radio])
        subgraph CAN[CAN Devices]
            direction LR
            Pneumatics[/Pneumatics Controller/]
            Motors[/Motors/]
            Pneumatics --- Motors
        end
        subgraph Sensors
            Digital(["
                Encoders
                Limit Switches
                Other Digital Sensors
            "])
            Analog(["
                Potentiometers
                Other Analog Sensors
            "])
            Fancy(["
                Color Sensors
                Gyroscopes
                Other Complex Sensors
            "])
        end
        subgraph Vision
            Pi[Raspberry Pi]
            Camera([Camera])
        end

        RIO <--CAN loop--> CAN
        RIO <--Network Tables--> Vision
        Pi <--USB--> Camera
        Digital --Digital Pins--> RIO
        Analog --Analog Pins--> RIO
        Fancy --I2C or SPI--> RIO
        Radio <--Ethernet--> RIO
    end
    Computer <--WiFi--> Radio
    Computer -.USB.-> RIO
    classDef input fill: orange
    class Radio,Digital,Analog,Fancy,Camera input
    classDef output fill: lightgreen
    class Pneumatics,Motors output
```

On the software side, an oversimplified diagram might look like this:

```mermaid
flowchart TD
    Timer["
        External Timer
        Triggers on a set period
        (every 50ms by default)
    "]
    subgraph Framework[WPILib Framework]
        Entry[WPILib Logic]
        subgraph Ours[Our Code]
            Auto[Autonomous Logic]
            Teleop[Teleoperated Logic]
        end
        Entry -.When in auto mode.-> Auto
        Entry -.When in teleop mode.-> Teleop
        subgraph Helpers[Other WPILib Classes]
            direction LR
            Motors
            Pneumatics
            Schedulers
            Sensors
            Motors ~~~ Pneumatics
            Pneumatics ~~~ Sensors
            Sensors ~~~ Schedulers
        end
        Auto --> Helpers
        Teleop --> Helpers
    end
    Timer --> Framework
    Framework --> Wait[Done, waiting for Timer]
```

## Terms and definitions

**FRC**: First Robotics Competition - the entire competition and community, including
building the robots, programming, wiring, social media, business, driving, etc.
Also sometimes called **FIRST**, although technically FIRST is the nonprofit that
organizes the competitions.

**WPILib**: A [framework] used by almost all FRC teams for programming. WPILib handles many
of the hardest parts of robot coding for you, wrapping them up in a nicer, easier-to-use
library. Examples of WPILib features include controlling almost all FRC hardware such as motors
and solenoids, setting up a main loop to run every 20ms, and providing a framework for Command-Based Programming.

**Command-Based Programming**: A [paradigm] used within WPILib code. It's intended to allow
you to have the robot perform multiple actions at the same time, without allowing you to
accidentally have the same hardware trying to do both. WPILib offers other paradigms, but
Command-Based is the most popular and generally the easiest to use. This guide focuses on
Command-Based Programming - see [Chapter 2][command-based-chapter].

**Subsystems** and **Commands**: Important concepts in Command-Based Programming.
Subsystems are groups made up of one or more pieces of physical hardware on the robot with
a common purpose (e.g. a grabber, a drivetrain, etc.) and commands are actions that these
subsystems can take (e.g. pick up an object, follow a preprogrammed path, etc.).

[framework]: https://en.wikipedia.org/wiki/Software_framework
[paradigm]: https://en.wikipedia.org/wiki/Programming_paradigm
[command-based-chapter]: /command-based/intro.md
