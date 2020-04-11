# Shared-VM-Service

## About
Creates a Virtual Machine streamed over RTMP to a central server responsible for re-streaming and handling control of said VM by a group of client users.
Similar to the services of tutturu.tv and the defunct rabb.it.

## Build Theory

__Server__ - On request from the client group, a new virtual Linux machine is spun up and will begin streaming content to the server. The server will be responsible for re-streaming the VM content to the group of clients. The server will also be responsible for taking client input (One client will be desigated as holding the "remote"), filtering it for security, and sending it to the VM.

__Virtual Machines__ - A virtual Linux machine is extremely barebones and will only run Chrome, FFMPEG, and other essential security and functionality scripts. There will be no desktop environment, and only Chrome in a locked down kiosk mode (Plugins will need to be whitelisted on a case-by-case basis). FFMPEG will stream over RTMP the captured desktop to the central server.

__Client__ - Groups of clients will be added to a "room". A unique virtual machine will be created for that "room". Clients request to hold the "remote", which designates them as the sole manipulator of the VM for the duration they hold the "remote". The re-streamed content from the VM will be displayed (and potentially synced) across all clients. The client with the "remote" will be able to move the mouse and type seamlessly on the video display of the VM.
All functionality is handled through the browser. Mobile clients present an interesting but not impossible challenge to support.

----
This was created as a Honors Option project for CS389 - Software Engineering.
