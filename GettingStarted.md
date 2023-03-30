<h1 align = "center">ESPHome Remote: Getting Started 🌈</h1>

# What You Need
-  Hardware (pick one):
	- TTGo T-Display
	- TTGo T-Display T4
	- M5Stack Fire
	- M5Stick C
- Software:
	- [ESPHome](https://esphome.io/)
	- [Home Assistant](https://www.home-assistant.io/)
	- [Spotcast](https://github.com/fondberg/spotcast) - [(optional)](#spotcast-setup) 

# Install guide
1. Copy project into your ESPHome folder
2. Find the yaml for your device
	1. TTGo T-Display: tdisplayremote.yaml
	2. TTGo T-Display T4: tdisplayt4.yaml
	3. M5Stack Fire: fireremote.yaml
	4. M5Stick C: m5stickc.yaml
3. The basic configuration is done through substitions
	1. font_size: Make sure the font sizes match the font sizes set above
	2. font_size_width_ratio: The width:height ratio of the font used
	3. header_height: Customize the header height
	4. margin_size: Customize the margin
	5. bottom_bar_margin: Distance the media duration bar is from the bottom
	6. scroll_bar_width: Customize the width of the scrollbar
	7. icon_size: Size of icons used to calculate UI
	8. now_playing_max_lines: Max lines displayed on Now Playing Screen
	9. draw_now_playing_menu: Show navigation menu on Now Playing screen
	10. boot_device_name: Customize the name displayed on boot
	11. display_timeout: Turn off display [s]
	12. sleep_after: Enter deep sleep [s]
	13. menu_rollover_on: Let the menu selection rollover when reaching the beginning / end
	14. sync_active_player: Auto switch active player if current active player goes idle
	15. dark_mode: Use black background. Performance is better in dark mode because filling the screen white is slow
- More configuration can be done in esphome/sharedRemoteConfig.yaml
	1. Customize **Colors**
	2. Customize **Fonts**
		- If you edit the font size you have to update both the font size and the corresponding font_size in Globals
	3. Customize **Globals**

4. Update the **Custom Components** in the esphomeRemote/sharedRemoteConfig.yaml to match your config, if you have difficulties looks at the [examples](sharedRemoteConfig-examples.md).
	1. Every component is optional. If you don't want to include the component then remove it
	2. Set your speaker media players under speaker_group_component
		1. If you have a supported TV then update it otherwise remove the TV line
		2. If you have a soundbar attached to the TV, include it in the setup otherwise leave it as NULL
	2. Update your Scenes and Scripts under scene_group_component
	3. Update your Light switches under light_group_component
	4. Update your Home Assistant sensors under sensor_group_component
5. Install the firmware to your device
6. Add the device to Home Assistant
7. Done! 🎉

# Spotcast setup
### Required for Spotify playlists to show up in Sources menu 
1. Install Spotcast through HACS https://github.com/fondberg/spotcast
2. Set up the Spotcast sensor https://github.com/fondberg/spotcast#use-the-sensor
3. Once the sensor is set up in Home Assistant, reboot your device
4. Done. Sources should include Spotify playlists!
