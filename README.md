FAVORITE PART OF THE PROJECT
1) Experiment with Xcode and Cursor
I was not able to go far enough to complete the steps below, due to complexities with our business
license and having Apple Business Identifiers during my initial setup, however, I did sign up for
Apple Developer and I should have my DEV Identifier in a couple more days, to continue my project.
First create your project in Xcode, then open it in Cursor and index it. You can then edit your
Swift code within Cursor, using features like AI-powered assistance, quick documentation access,
and smart code completion. Finally, apply your changes, refresh Xcode, and your modifications
will be reflected in your Xcode project. 
Here is an example of where I am at with Xcode:
![image](https://github.com/user-attachments/assets/78672729-e6cd-4d07-ab0e-f83bb86f9d7b)

React Native and a GoPro
1) First off, let’s get react Native installed:
2) Let's use the react-native-cli package to build a new project:
3) npx react-native@latest init imagekitReactNative
4) Navigate to the project directory:
5) cd imagekitReactNative/
6) Start the metro server.
7) npx react-native start
9)And now to run the app in the iOS simulator (you should have Xcode installed)
10) npm run ios
11) Or to run the app in the android simulator (you should have android studio installed)
12) npm run android
13) You should see the “Welcome to React Native” screen. This means the sample app has been set up correctly.

GoPro Video
1) My GoPro has a Wifi Spot where I can send commands over curl and I experimented with my GoPro to switch to video mode. 
For example:
	# SWITCH TO VIDEO MODE
	curl "http://10.5.5.9/camera/CM?t=$GOPROPASS&p=%00"
	# START/STOP RECORDING 
	curl "http://10.5.5.9/bacpac/SH?t=$GOPROPASS&p=%01"
	# DELETE ALL FILES FROM CAMERA
	curl "http://10.5.5.9/camera/DA?t=$GOPROPASS"
It has a file server (Cherokee) where you can see all cam files:
	# See files on your browser
	open "http://10.5.5.9:8080/gp/gpMediaList"
You can discover some neat tricks if you have VLC or ffmpeg on your mac:
	# ENABLE STREAMING AND SEE LIVE VIDEO FROM VLC
	curl -i "http://10.5.5.9/camera/PV?t=$GOPROPASS&p=%02"
	vlc "http://10.5.5.9:8080/live/amba.m3u8"
	# DOWNLOAD LAST 15 SECONDS OF SOME VIDEO ON YOUR GOPRO
	ffmpeg -sseof -15 -i "$VIDEO_URL" -c copy output.mp4
React Native is simple to use and I can use fetch API to execute most of the commands.

