.. _doc_overview_of_debugging_tools:

Overview of debugging tools
===========================

Introduction
------------

When developing your game, you want to test your game and debug when problems occur. Godot provides several debugging options and
tools which aid your debugging process. There are the debug dropdown options, Script editor debug options, debug project settings,
and the debugger.

Debug dropdown options
----------------------

There are a few options that you can enable when running your game in the editor which can help you in debugging your game.
These options are located in ``DEBUG`` in the main menus.

.. image:: img/overview_debug.png

Here are the descriptions of the options:

Deploy with Remote Debug
++++++++++++++++++++++++

When exporting and deploying, the resulting executable will attempt to connect to the IP of your computer, in order to be debugged.

Small Deploy with Network FS
++++++++++++++++++++++++++++

Export or deploy will produce minimal executable. The filesystem will be provided from the project by the editor over the network.
On Android, deploy will use the USB cable for faster performance. This option speeds up testing for games with a large footprint.

Visible Collision Shapes
++++++++++++++++++++++++

Collision shapes and raycast nodes(for 2D and 3D) will be visible on the running game.

Visible Navigation
++++++++++++++++++

Navigation meshes and polygons will be visible on the running game.

Sync Scene Changes
++++++++++++++++++

Any changes made to the scene in the editor will be replicated in the running game.
When used remotely on a device, this is more efficient with network filesystem.

Sync Script Changes
+++++++++++++++++++

Any script that is saved will be reloaded on the running game.
When used remotely on a device, this is more efficient with network filesystem.

Script editor debug tools and options
-------------------------------------

The script editor has its own set of debug tools for use with breakpoints, and two
options. The breakpoint tools can also be found in the "Debugger" tab of the debugger.

..image:: img/overview_script_editor.png

The ``Break`` button causes a break in the script like a breakpoint would. ``Continue``
makes the game continue after pausing at a breakpoint. ``Step Over`` goes to the next
line of code, and ``Step Into`` goes into a function if possible, otherwise it does the
same thing as ``Step Over``.

The ``Keep Debugger Open`` option keeps the debugger open after a scene has been closed.
And the ``Debug with External Editor`` option lets you debug your game with an external
editor.

Debug project settings
----------------------

In the project settings there is a "Debug" category with three sub categories which
control different things.

Settings
++++++++

These are some general settings such as printing the current FPS to the Output panel, the
maximum amount of functions when profiling and others.

GDScript
++++++++

These settings allow you to turn specific GDScript warnings, such as an unused variable, on
or off. You can also turn off warnings completely.

Shapes
++++++

Shapes is where you can adjust the color of shapes that only appear for debugging purposes,
such as collision and navigation shapes.

Debugging tools
---------------

The ``Debugger`` can be found in Godot's bottom panel. Click on it and the panel expands
to show all the debugging tools.

.. image:: img/overview_debugger.png

There are multiple parts of the debugger, each is for a specific task.

Debugger
++++++++

The debugger tab is for working with breakpoints in the script. When a script reaches a breakpoint
this panel gives you information on it.

The buttons in the top right can be used respectively to:

- Skip all defined breakpoints, without removing them (so you can toggle them on or off while testing).
- Copy the current error message.
- Step Into goes to the next line of code, and if it's a function, it step line by line through the function.
- Step Over goes to the next line of code, but does not go down into function code.
- Break pauses the game like a breakpoint would.
- Continue resumes the game after a breakpoint or pause.

Errors
++++++

This is where errors and warning messages are printed while running the game.

Profiler
++++++++

The profiler is used to show why individual frames take as long as they do to process and render.

Unlike other debugging tools the profiler does not start automatically. It can be started at any
time during gameplay by pressing the start button. You can even start the profiler before opening
the game to profile start up performance. It can also be started and stopped while the game is
running without losing information from when it was last running. The information it records won't
go away unless you click clear, or close the game, reopen it and start the profiler again.

After starting and stopping the profiler you should see things being kept track of on the left and
a graph on the right. The items listed on the left are everything that contributes to frame time,
and they should each have a value for time and calls for the current frame you are looking at.

The frame number in the top right tells you which frame you are currently looking at. You can change
this by using the up or down arrows, typing in the frame number, or clicking on the graph.

If you want to add something to your graph, or think it looks too cluttered, you can check and
uncheck the box next to an item to add or remove it from the graph.

Network Profiler
++++++++++++++++

The Network Profiler contains a list of all the nodes that communicate over the multiplayer API
and, for each one, some counters on the amount of incoming and outgoing network interactions.
It also features a bandwidth meter that displays the total bandwidth usage at any given moment 

Monitors
++++++++

The monitors are graphs of several aspects of the game while its running such as FPS, memory usage,
how many nodes are in a scene and more. All monitors keep track of stats automatically, so even if one
monitor isn't open while the game is running, you can open it later and see how the values changed.

Video Mem
+++++++++

Video Mem list the video memory usage of the running game and which resource is using it.

Misc
++++

Misc is used to identify which control node you are clicking while the game is running. "Clicked Control"
shows where on the scene tree the node is. "Clicked Control Type" tells you what type of node it is.

Remote in Scene dock
--------------------

When running a game in the editor two options appear at the top of the ``Scene`` dock,
``Remote`` and ``Local``. While using ``Remote`` you can inspect or change the nodes' parameters
in the running game.

.. image:: img/overview_remote.png

.. note:: Some editor settings related to debugging can be found inside the ``Editor Settings``, under Network>Debug and Debugger sections.
