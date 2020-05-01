---
layout: page
subheadline:  "Rebranding and plugin support"
title:  "Corona transition to Solar2D"
permalink: "/corona-to-solar2d/"
categories:
    - solar2d
tags:
    - solar2d
header: no
---
Corona game engine has gone opensource, the CoronaLabs company no more. The engine is now being developed and supported based on donations as an opensource project by the same people from CoronaLabs.

Spiral Code Studio has developed a number of popular plugins for Corona, such as QR Code Scanner and Text-to-Speech.

All the plugins will continue to work properly with Solar2D, however a significant change in distribution is required. The official Corona Markerplace has shut down and no longer can distribute 3rd party plugins.

I have decided not to go with the same approach as before charging for every plugin some amount each year. Instead just like Solar2D with it's crowdfunding I want to be closer to my customers, to form a community where everyone can use all my plugins and you can decide which new plugins do you want to be developed.

Therefore I am introducing a Patreon based access to all of my plugins. With a pledge $5 a month or more you can use all my plugins, a custom URL is needed for `build.settings`, see [build.settings modification](#buildsettings-modification) below for details.

No more wandering if the plugin is right for you or not - just support me on Patreon, try all the plugins you are interested in and in case you don't like them - cancel your Patreon support. It's that easy, no strings attached.

I think Solar2D is going in the right direction and together we can make great apps and games.

I hope you agree to support me so I can continue supporting all my plugins, fixing bugs and developing new features and plugins.

Thanks,<br>
Sergey Lerg

## build.settings modification ##

For the new system integration you would need your patreon email address and a special access key, that you get when you make a pledge (2nd tier or higher is required).

Paste that block at the top of your `build.settings` file, before the `settings` table.

``` Lua
local spiralcodestudio_patreon_email = 'YOUR_EMAIL'
local spiralcodestudio_key = 'YOUR_ACCESS_KEY'

local function spiralcodestudio_plugin(name)
	local plugin = {publisherId = 'com.spiralcodestudio', supportedPlatforms = {}}
	local platforms = {'android', 'appletvos', 'appletvsimulator', 'iphone', 'iphone-sim', 'macos', 'win32'}
	for i = 1, #platforms do
		local platform = platforms[i]
		plugin.supportedPlatforms[platform] = {url = 'https://build.spiralcodestudio.com/' .. spiralcodestudio_patreon_email .. '/' .. spiralcodestudio_key .. '/solar2d/' .. name .. '_' .. platform .. '.tgz'}
	end
	return plugin
end
```

Now you can use this function to prepare a listing for a plugin like so

``` Lua
settings = {
	-- ...
	plugins = {
		['plugin.qrscanner'] = spiralcodestudio_plugin('qrscanner')
	}
}
```

That function generates URLs for each platform (iOS, Android...) with proper authentication parameters when your project is loaded in Solar2D Simulator (Corona Simulator).

Here is a sample `build.settings` file https://github.com/Lerg/plugins-sample-qrscanner/blob/master/build.settings

{: .t60 }

{% include list-posts tag='solar2d' %}
