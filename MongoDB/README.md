<!-- How to Install MongoDB on macOS Locally -->

# Step 1 — Check Your Mac’s Chip (M1 or Intel-based)

Click on the Apple menu ()on the top-left corner.
Select About This Mac from the dropdown menu.
Mine is intel-based chip. Check yours.

1. Click on the Apple menu () located in the top-left corner of your screen. 2. Select “About This Mac” from the dropdown menu

# Step 2— Download MongoDB Package

Head over to here: MongoDB Community Edition website.
Choose the appropriate compatibility:

![Image text](https://raw.github.com/yourName/repositpry/master/yourprojectName/img-folder/test.jpg)

> For M1 chip, select macOS arm 64
> For Intel-based, select macOS x64
> Choose “tgz”.
> Click “Download” and zip the file.

# Step 3— Copy Binaries to Enviroment Variable

Navigating to the zipped file, there is bin folder.
Copy the “install_compass,” “mongod,” and “mongos” binaries to the environment variable. This enables you to execute MongoDB commands from any location in the Terminal.
To acheieve this:

> Open Terminal.
> Copy and paste the code below into Terminal.
> Remember to replace _YOURMACUSER_ with yours and enter your Mac password.

```
sudo cp /Users/_YOURMACUSER_/Downloads/mongodb-macos-x86_64-7.0.6/bin/\* /usr/local/bin/ 4.
```

> Once you’ve done, open Terminal and execute the following codes to check if the 3 binaries exist.
> tips: depends on your own local path

```
cd /
open usr/local/bin -a Finder
```

![Image text](MongoDB/screenshot/mongoDB-download.png)

# Step 4— Create data and log directories

1. You must create the directory to where mongod process will write data.

2. For data storage, execute the following code in Terminal and enter password.

```
sudo mkdir -p ~/data/db
```

3. For log storage, execute the following code in Terminal and enter password.

```
sudo mkdir -p ~/data/log/mongodb
```

4. Set permissions to read and write db.

5. In order to know user account, execute whoamiin Terminal.

6. Executing following code to set ownership:
   remeber to replace _USER_ with yours

```
sudo chown _USER_ ~/data/db
sudo chown _USER_ ~/data/log/mongodb
```

# Step 5— Configure parameters for db and log

1. To run MongoDB, you need to execute the `mongod` process with specific parameters at the system prompt.
2. Open a Terminal window.
3. Run the following command: `mongod --dbpath ~/data/db --logpath ~/data/log/mongodb/mongo.log --fork`
4. Run the following command to verify successfully: `ps aux | grep -v grep | grep mongod`
5. Then, you will see result like this:`user XXXXX X.X X.X XXXXXXX XXXXXXX ? Ss XX:XX mongod --dbpath ~/data/db --logpath ~/data/log/mongodb/mongo.log --fork`

# Step 6— Start MongoDB

Run mongoshin Terminal.
\*\* Alert: macOS may prevent mongosh from running after installation. If you receive a security error, follow this:

> Click on the Apple menu ()on the top-left corner.
> Open System Preferences.
> Go to Security and Privacy.
> In the General tab, click “Open Anyway” or “Allow Anyway” button next to the message related to mongosh, depending on your macOS version.
> MongoDB is running on your localhost with the default port of 27017.
> Check MongoDB version by typing mongosh --version in Terminal.
> Alright, run mongoshin Terminal and you are GOOD to go.

My curren version is 2.2.0, also you can download MongoDB_GUI(https://www.mongodb.com/try/download/compass)

Run “mongosh”, and you are good to go!
