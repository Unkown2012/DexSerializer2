<p align="center">
<img src="/logo.png" width="500"/>
</p>

# Dex Serializer
An accurate Roblox Binary Format Serializer made in Lua
<p align="center">
<img src="/server_save.png" width="800"/>
</p>


## Overview
This serializer was completed in late 2020 in preperation for The Augur's reign that started in July 2021

Many ServerScriptService and ServerStorage models of top games were saved during that era with top accuracy

This serializer can save in both xml and binary format. It is more accurate in binary format since I stopped maintaining xml format after I finished making binary.


This is old and discontinued, but the agency released it to show people the grand serializer that
powered the saveinstance function in the top executors at the time before they were discontinued:
- ScriptWare
- Synapse X

The options in this serializer is also what UNC's saveinstance is based of, due to ScriptWare using this as its primary saveinstance implementation.

It would be nice if someone forked and improved it by doing the following:
- Support the newer roblox types such as Content
- Use buffer
- Use ReflectionService


## How to Use
Assuming you are using it as a module
```lua
local serializer = require("DexSerializer")
serializer.Init()

-- Then we can save
serializer.Save(instance, name, options)
```

Options
```lua
Serializer = {
	Decompile = false, -- Decompiles or not
	NilInstances = false, -- Saves nil or not
	RemovePlayerCharacters = true, -- Remove player chars
	SavePlayers = false, -- Save instances in players if saving game
	DecompileTimeout = 10, -- Timeout before giving up decompiling a script
	MaxThreads = 3, -- Threads to use to decompile
	DecompileIgnore = {"Chat","CoreGui","CorePackages"}, -- Services to ignore saving if saving game
	ShowStatus = true, -- Show a status at top
	IgnoreDefaultProps = true, -- Ignore saving default props to lower file size (xml only)
	IsolateStarterPlayer = true, -- Isolate StarterPlayer instances if saving game, to ensure you can playtest it after opening the rbxl
	Binary = true, -- Use binary format
	Callback = false, -- A callback function after the saving is complete where the raw binary is passed
	Clipboard = false -- Copies the raw binary to clipboard instead of writing to file (need a clipboard function that sets the type to application/x-roblox-studio)
}
```

Made by Moon

<img src="/logo2.jpg" width="400"/>
