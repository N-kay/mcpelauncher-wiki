Frequently Asked Questions
==========================

Does it work on Windows?
~~~~~~~~~~~~~~~~~~~~~~~
No, due to the amount of work required to get this running on Windows. Play the Windows 10 Edition instead if you can.
Note that you can not run this in the current version of WSL, as it does not support 32-bit applications.

How does it work?
~~~~~~~~~~~~~~~~~~~~~~~
The project runs the native libraries from the Android version directly on your computer. This is accomplished by fixing the incompatibilities between the libc used on Android and the one used on desktop Linux or OS X (Android - Bionic; Linux - glibc). This is a simple compatibility layer which doesn't impact performance in any significant way; it's similar to Wine in a way, but way more lightweight and simple. Aditionally, all Android-specific code has been rewritten (AppPlatform, Store, Xbox Live, etc.).

I compiled and/or installed everything, but mcpelauncher-client doesn't start
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Chances are, you don't have the actual game yet. This project does **not** provide MCPE/Minecraft Bedrock Edition itself.

The easiest way to download and start the game is through the graphical Qt UI (:code:`mcpelauncher-ui-qt`, sometimes called metalauncher). This requires to log into a Google Play Account with Minecraft purchased.

Otherwise, obtain a valid Minecraft x86 :code:`.apk` and use the :ref:`extract utility <extractor>`.

I Used the Qt UI (metalauncher) to download the game, but :code:`mcpelauncher-client` still doesn't work
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
To start a given version of Minecraft you can run :code:`mcpelauncher-client` with the :code:`-dg` argument, eg. :code:`mcpelauncher-client -dg ~/.local/share/mcpelauncher/versions/DESIRED_VERSION`.

:code:`ls ~/.local/share/mcpelauncher/versions/` will list all versions you have installed.

Where are my worlds?
~~~~~~~~~~~~~~~~~~~~
:code:`~/.local/share/mcpelauncher/games/com.mojang/minecraftWorlds`

Each world has its own directory. Should you have multiple, you can identify them by their name in :code:`levelname.txt` found in each.

The `mcpelauncher-server` creates and expects its world files in :code:`world`.

Can I use resource packs?
~~~~~~~~~~~~~~~~~~~~~~~~~
Yes, put them in :code:`~/.local/share/mcpelauncher/games/com.mojang/resource_packs`. Shaders are also resource packs.

You may need to extract :code:`.zip` and code:`.mcpack` files into their own subdirectory for them to work properly.

Why would I want to use this projects server, instead of the official one?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
If...
- the official one doesn't work for you
- you need scripting on the server
- some rarely needed particular modding capabilities
