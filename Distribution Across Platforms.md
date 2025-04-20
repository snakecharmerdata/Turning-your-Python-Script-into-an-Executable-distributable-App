Distribution Across Operating Systems
If you build your application on macOS, you can only distribute it to other macOS users. Similarly, if you build on Windows, you can only distribute to Windows users.

Why Applications Aren't Cross-Platform
When PyInstaller creates an executable, it:

Bundles a platform-specific Python interpreter
Includes binary libraries compiled for that specific operating system
Creates an executable format native to that operating system (.app for macOS, .exe for Windows)
The resulting executable is tied to:

The operating system you built it on
The CPU architecture (Intel/AMD vs ARM)
How to Create Executables for Multiple Platforms
To distribute your application to both macOS and Windows users, you need to:

Option 1: Build on Each Platform Separately

Build on macOS to create the .app file for macOS users
Build on Windows to create the .exe file for Windows users
Option 2: Use Virtual Machines or Cloud Services

Use a Windows virtual machine on your Mac to build the Windows version
Or use a cloud-based build service that can create executables for multiple platforms
Option 3: Use Cross-Platform Packaging Tools (More Advanced) There are some tools like:

PyOxidizer
Briefcase (part of BeeWare project)
cx_Freeze with cross-compilation settings
However, these typically require more advanced setup and aren't as straightforward as PyInstaller.

Practical Solutions
The most reliable approach is to:

Create the macOS version on a Mac
Create the Windows version on a Windows computer
Distribute the appropriate version to each user based on their operating system
If you don't have access to both operating systems, you might consider:

Borrowing a computer with the other OS
Using a virtual machine
Using a cloud-based build service
Collaborating with someone who has the other operating system
Alternative Approach: Web Application
If cross-platform distribution is critical and you don't have access to both systems, consider converting your Python application to a web application using frameworks like Flask or Django. 
This allows users on any platform to access your application through a web browser.