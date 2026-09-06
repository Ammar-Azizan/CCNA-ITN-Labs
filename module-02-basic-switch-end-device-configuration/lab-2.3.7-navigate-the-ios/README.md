# Lab 2.3.7 – Navigate the IOS

## Overview

This lab introduces basic navigation of the Cisco IOS Command-Line Interface (CLI) using a console connection. It focuses on accessing different IOS modes, using command help, and configuring the system clock.

## Objectives

- Connect a PC to a switch using a console cable.
- Access the switch CLI through a terminal session.
- Explore context-sensitive help and command completion.
- Navigate between User EXEC, Privileged EXEC, and Global Configuration modes.
- Configure and verify the system clock.
- Identify common IOS messages for incomplete or incorrect commands.

## Lab Setup

### Devices Used

| Device | Model | Purpose |
|---|---|---|
| PC1 | PC-PT | Provides terminal access to the switch |
| S1 | Cisco 2960-24TT Switch | Cisco IOS device used for CLI navigation |

### Console Connection

PC1 is connected directly to S1 using a console cable.

| From Device | Port | To Device | Port |
|---|---|---|---|
| PC1 | RS-232 | S1 | Console |

The console connection provides direct access to the Cisco IOS CLI through the Terminal application on PC1.

### Network Topology

![Lab 2.3.7 Topology](screenshots/01-console-connection.png)

## Important Commands Used

| Command | Purpose |
|---|---|
| `?` | Displays available commands and context-sensitive help. |
| `enable` | Enters Privileged EXEC mode. |
| `configure terminal` | Enters Global Configuration mode. |
| `exit` | Returns to the previous IOS mode. |
| `end` | Returns directly to Privileged EXEC mode. |
| `show clock` | Displays the current system date and time. |
| `clock set 15:00:00 31 Jan 2035` | Sets the system date and time. |

> **Note:** The `Tab` key can be used to automatically complete recognized IOS commands.

## Implementations

### 1. Console Connection
- Connected PC1 to S1 using a console cable.
- Opened the Terminal application on PC1 to access the Cisco IOS CLI.

### 2. IOS Help
- Used `?` to display available commands.
- Used partial commands with `?` to find matching commands.
- Used `Tab` for command completion.

### 3. IOS Modes
- Accessed User EXEC mode (`S1>`).
- Used `enable` to enter Privileged EXEC mode (`S1#`).
- Used `configure terminal` to enter Global Configuration mode (`S1(config)#`).

### 4. System Clock
- Used `show clock` to view the system time.
- Configured the clock using:

`clock set 15:00:00 31 Jan 2035`

- Used `show clock` again to verify the configuration.
- Tested incorrect commands to observe IOS error messages.

## Key Takeaways

- A console connection provides direct access to a Cisco device's CLI.
- Cisco IOS uses different command modes for different tasks.
- `?` provides context-sensitive help for available commands.
- The `Tab` key helps complete IOS commands.
- Correct command syntax and parameters are required.
- The system clock can be manually configured and verified.
- IOS error messages help identify incorrect or incomplete commands.