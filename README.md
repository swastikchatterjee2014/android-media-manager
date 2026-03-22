# android-media-manager
A media manager for Android. Developed in Kotlin, Jetpack Compose and Gradle. It uses API 35. But minimum API required to run is API 29. It is Material Expressive compatible. 
This application is strictly local only and Android only.
#Permissions 
All files
This application is not signed by Google so it may ask to scan with Play Protect. You may dismiss the scan or scan it. 
If you scan it, it is very likely to return "This application is looking safe"
#Compile from source
To compile it from source
You must have SDKMAN!, Git, Gradle 9.4, JDK 21 installed
First, download Android SDK and API 35
Then open the terminal with ctrl+alt+t
Then run
#bash
sudo apt install -y default-jdk git #This is for Ubuntu 24.04 LTS 
#clone the repo 
git clone https://github.com/swastikchatterjee2014/android-media-manager.git 
#Compile 
cd MediaManagerApp
zsh build.zsh
License - GNU Affero General Public License version 3 (AGPLv3)
For more details, see LICENSE.txt
