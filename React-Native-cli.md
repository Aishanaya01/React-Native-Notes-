***React Native Cli***<br><br>
It contains the actual React Native framework code and is installed locally into your project when you run react-native init . 
Because react-native init calls npm install react-native , simply linking your local github clone into npm is not enough to test local changes.<br><br>
***React-native command line interface***<br><br>
React Native has a built-in command line interface. Rather than install and manage a specific version of the CLI globally, we recommend you access the current version at runtime using npx, which ships with Node.js. With npx react-native , the current stable version of the CLI will be downloaded and executed at the time the command is run.<br><br>
***Starting with the project***
* 1 .Previously we download a global react-native-cli package. with command:
npm install -g react-native-cli

* 2.Starting with the project :<br><br>
react-native init [projectname]<br>
* It will download all the requried libraries for your project.

Now open the Created Project folder and start coding. To see your application on the virtual device, go through these commands:

* 1.In CMD run<br>
npm react-native start

It will start the metro Bundler.

* NOTE:<br>

To run Application directly on android emulator, go for this command:<br>
npm react-native run-android

To run Application directly on ios emulator, go for this command:<br>
npm react-native run-ios
