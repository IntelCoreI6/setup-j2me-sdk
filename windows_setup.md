This is a tutorial for setting up the J2ME SDK on modern Windows, using IntelliJ 2019.3.

![image](https://github.com/user-attachments/assets/0cf14740-3bd2-428a-be51-34c91b50d1d2)

## 1. Download Files

Download the following files and save them all to the same directory. I'll use `Documents\j2me`.
- [ideaIC-2019.3.5-jbr8.win.zip](https://download.jetbrains.com/idea/ideaIC-2019.3.5-jbr8.win.zip)
- [OpenJDK8U-jdk_x86-32_windows_hotspot_8u442b06.zip](https://adoptium.net/temurin/releases/?version=8&arch=x86&os=windows&package=jdk)
- [sun_java_wireless_toolkit-2.5.2_01-win.exe](https://www.rose-hulman.edu/class/csse/binaries/csmobilegames/sun_java_wireless_toolkit-2.5.2_01-win.exe)

![image](https://github.com/user-attachments/assets/4c36a8ef-58b8-45e9-8358-9b2b455c7c16)


## 2. Install Programs
Extract the two zip files to the same directory.

Then, create a new folder called `sdk` and run the `sun_java_wireless_toolkit-2.5.2_01-win.exe` installer.

![image](https://github.com/user-attachments/assets/9ff17f05-72a5-4a29-8ebf-befe74c77db4)

When selecting the JVM location, set it to the JDK you extracted earlier. On the install location, set it to the `sdk` folder you created earlier. The configuration for the installer should look like this:

![image](https://github.com/user-attachments/assets/b5d19bd3-5fcf-4177-8c20-3c652c54d9e4)

## 3. Configure IntelliJ

Open IntelliJ by running the `ideaIC-2019.3.5-jbr8.win\bin\idea64.exe` executable.

On the welcome screen, configure your plugins, and install the J2ME plugin, then restart the IDE.

![image](https://github.com/user-attachments/assets/abcfd17e-65de-4f1c-a7da-cba0c3651c2c)

Create a new Java project (not J2ME), and set the JDK directory to the one you just downloaded. We have to create a regular Java project first otherwise IntelliJ will not let you create the J2ME project for some reason.

![image](https://github.com/user-attachments/assets/eaef7a92-8a1c-4dd5-9123-b30e66998e07)

Then, create another new project, this time with J2ME, and set the mobile SDK directory to the J2ME SDK you just installed.

![image](https://github.com/user-attachments/assets/562616b6-3970-49d1-813e-a5251d5437e8)

## 4. Setup Intellij Project

Go to `File > Settings > Build, Execution, Deployment > Compiler > Java Compiler`, and set the project bytecode version to 1.4.

![image](https://github.com/user-attachments/assets/8ca6cf3e-eeda-4815-9d56-df924d6ba893)

In `File > Project Structure > Project Settings > Project`, set the project language level to 1.4.

![image](https://github.com/user-attachments/assets/769aec01-5227-4c02-b086-854498c7015f)

In `File > Project Structure > Project Settings > Modules > Dependencies`, set the module SDK to Sun Java(TM) Wireless Toolkit 2.5.2_01 for CLDC.

![image](https://github.com/user-attachments/assets/538cba96-126d-435a-bc78-4709182e3acf)


Add your `MainMIDlet` class.

![image](https://github.com/user-attachments/assets/e6cc2957-17ba-4e5b-8cf8-390f87aa2a47)

In `File > Project Structure > Artifacts`, create a new JAR artifact with the proper module.

![image](https://github.com/user-attachments/assets/83e4d6ab-cb47-4051-bdfb-896a6a69b74b)

Make sure the JAR output directory is set to the project base directory.

![image](https://github.com/user-attachments/assets/8aa2ad8a-7179-4c9f-9252-47c632a6db27)

In the top right corner, click "Add Configuration." 

![image](https://github.com/user-attachments/assets/04adce49-1538-4cb9-b35e-ace20182820e)

In that menu, create a new J2ME run configuration.

![image](https://github.com/user-attachments/assets/da673008-62de-4cab-bb0c-da11cb5333b4)

Change the run mode to "class," and set the proper MIDlet class.

![image](https://github.com/user-attachments/assets/2458bc9a-b8eb-4abe-ba63-9ddb0e1e6c24)

In the before launch options, make it build the project then build the JAR artifact.

![image](https://github.com/user-attachments/assets/64fca779-5f32-41ec-9fbd-0fc3cff23970)

## 5. Run the Project

Now, just hit the run button, and the emulator will start up and run your code.

![image](https://github.com/user-attachments/assets/4b469c25-f66d-4d74-afb1-c991aa6c6806)

You can even debug it.

![image](https://github.com/user-attachments/assets/0cf14740-3bd2-428a-be51-34c91b50d1d2)

