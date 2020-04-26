---
#
# Use the widgets beneath and the content will be
# inserted automagically in the webpage. To make
# this work, you have to use › layout: frontpage
#
layout: frontpage
header:
  image_fullwidth: header1920x128.jpg
widget1:
  title: "Corona to Solar2D transition"
  url: '/corona-to-solar2d/'
  image: logo_solar2d.png
  text: 'Details on transitioning from Corona marketplace to Solar2D.'
widget2:
  title: "Solar2D plugins"
  url: '/solar2d/plugins/'
  image: logo_solar2d.png
  text: 'Plugins for the Solar2D game engine (Corona).'
widget3:
  title: "Defold extensions"
  url: '/defold/extensions/'
  image: logo_defold.png
  text: 'Extensions for the Defold game engine.'
#
# Use the call for action to show a button on the frontpage
#
# To make internal links, just use a permalink like this
# url: /getting-started/
#
# To style the button in different colors, use no value
# to use the main color or success, alert or secondary.
# To change colors see sass/_01_settings_colors.scss
#
callforaction:
  url: http://patreon.com/lerg
  text: Become a Patron and gain access to plugins ›
  style: alert
permalink: /index.html
#
# This is a nasty hack to make the navigation highlight
# this page as active in the topbar navigation
#
homepage: true
---
