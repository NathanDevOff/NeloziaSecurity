  
aventium softworks

Helios Launcher

(formerly Electron Launcher)

travis downloads stark

Join modded servers without worrying about installing Java, Forge, or other mods. We'll handle that for you.

Screenshot 1 Screenshot 2

Features
🔒 Full account management.
Add multiple accounts and easily switch between them.
Credentials are never stored and transmitted directly to Mojang.
📂 Efficient asset management.
Receive client updates as soon as we release them.
Files are validated before launch. Corrupt or incorrect files will be redownloaded.
☕ Automatic Java validation.
If you have an incompatible version of Java installed, we'll install the right one for you.
You do not need to have Java installed to run the launcher.
📰 News feed natively built into the launcher.
⚙️ Intuitive settings management, including a Java control panel.
Supports all of our servers.
Switch between server configurations with ease.
View the player count of the selected server.
Automatic updates. That's right, the launcher updates itself.
View the status of Mojang's services.
This is not an exhaustive list. Download and install the launcher to gauge all it can do!

Need Help? Check the wiki.
Like the project? Leave a ⭐ star on the repository!
Downloads
You can download from GitHub Releases

Latest Release


Latest Pre-Release


Supported Platforms

If you download from the Releases tab, select the installer for your system.

Platform	File
Windows x64	Helios-Launcher-setup-VERSION.exe
macOS	Helios-Launcher-setup-VERSION.dmg
Linux x64	Helios-Launcher-setup-VERSION.AppImage
Console
To open the console, use the following keybind.

ctrl + shift + i
Ensure that you have the console tab selected. Do not paste anything into the console unless you are 100% sure of what it will do. Pasting the wrong thing can expose sensitive information.

Export Output to a File
If you want to export the console output, simply right click anywhere on the console and click Save as..

console example

Development
This section details the setup of a basic developmentment environment.

Getting Started
System Requirements

Node.js v12
Clone and Install Dependencies

> git clone https://github.com/dscalzi/HeliosLauncher.git
> cd HeliosLauncher
> npm install
Launch Application

> npm start
Build Installers

To build for your current platform.

> npm run dist
Build for a specific platform.

Platform	Command
Windows x64	npm run dist:win
macOS	npm run dist:mac
Linux x64	npm run dist:linux
Builds for macOS may not work on Windows/Linux and vice-versa.

Visual Studio Code
All development of the launcher should be done using Visual Studio Code.

Paste the following into .vscode/launch.json

{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Debug Main Process",
      "type": "node",
      "request": "launch",
      "cwd": "${workspaceFolder}",
      "program": "${workspaceFolder}/node_modules/electron/cli.js",
      "args" : ["."],
      "outputCapture": "std"
    },
    {
      "name": "Debug Renderer Process",
      "type": "chrome",
      "request": "launch",
      "runtimeExecutable": "${workspaceFolder}/node_modules/.bin/electron",
      "windows": {
        "runtimeExecutable": "${workspaceFolder}/node_modules/.bin/electron.cmd"
      },
      "runtimeArgs": [
        "${workspaceFolder}/.",
        "--remote-debugging-port=9222"
      ],
      "webRoot": "${workspaceFolder}"
    }
  ]
}
This adds two debug configurations.

Debug Main Process
This allows you to debug Electron's main process. You can debug scripts in the renderer process by opening the DevTools Window.

Debug Renderer Process
This allows you to debug Electron's renderer process. This requires you to install the Debugger for Chrome extension.

Note that you cannot open the DevTools window while using this debug configuration. Chromium only allows one debugger, opening another will crash the program.

Note on Third-Party Usage
You may use this software in your own project so long as the following conditions are met.

Credit is expressly given to the original authors (Daniel Scalzi).
Include a link to the original source on the launcher's About page.
Credit the authors and provide a link to the original source in any publications or download pages.
The source code remain public as a fork of this repository.
We reserve the right to update these conditions at any time, please check back periodically.

Resources
Wiki
Nebula (Create Distribution.json)
v2 Rewrite Branch (WIP)
The best way to contact the developers is on Discord.

discord

See you ingame.
