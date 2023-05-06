# PATH_MID_DD

Repository to store updates made to the original PATH DD behavioral task created by Richard Liu. 

## Instructions - MUST FOLLOW ALL OF THE STEPS EVEN IF YOU ALREADY HAVE PSYCHOPY INSTALLED

Be sure Anaconda and Python are installed. To check, go to the start menu and search for Anaconda Prompt (anaconda3). Open Anaconda Prompt and when the base line appears type python -- and hit enter. The version should be 3.7 or 3.7.##. 
1. Unzip the files and save them in a folder on your local task computer, not the server. 
2. Open the Delay Discounting Task (DDT) folder on your local task computer. 
3. Go to the start menu and open “Anaconda Prompt (anaconda3)”
4. A command prompt window will appear. Copy and paste the snippets below (wait for each to finish running before adding the next one). 
 - Type code pip install adopy and hit enter
 - Type code pip install pyyaml and hit enter
 - Type code pip install psychopy and hit enter
 - Type code pip install pyinstaller and hit enter
 - Type code pip install poetry and hit enter
 - Type code cd followed by the file path to the DDT files and hit enter [E.g., cd C:\MABL\DDT (Delay Discounting Task) – ADO]
 - Type code poetry install
 - Type code code poetry shell
 - Type code pip install pyyaml
5. Type code pyinstaller main.py 
 - This will create a “dist” folder with a “main” subfolder
6. Run the task using the cmd line to make sure it works well
 - Enter code python main.py
 - A problem I encountered was that wx.App was missing. I edited the main.py file to import wx and then declared app = wx.App(False) after info_dialog
 - When the window opens enter the ID and select the Wave and Prepost, click okay and then Save
 - Run the task to check it is working
 - Another problem I ran into is that the task would crash after the first real trial because it attempted to append the results to a data frame. I edited the runner.py file to use the pd.concat method instead.
7. Open anaconda3 command prompt again and map the directory of where the task is stored on your computer (steps 3 and 4)
8. Run the batch file that will create an executable file of the task by typing code build.bat and let it run in its entirety. 
9.	If a Windows protected your PC pops up, click “more info” and then click “run anyway”
9.	This will create a ddt.exe file and a ddt subfolder in the dist folder. The ddt subfolder will also contain a ddt.exe file
10.	When you see (base) C:\..., go to DDT (Delay Discounting Task) – ADO > dist > ddt folder and go to the ddt.exe file. Double click to open
 - Enter the ID, Wave, and Prepost and click okay and then save to run the task
 - This is the preferred file to run the task as it is much quicker to open
11.	Go to the dist folder and open the ddt.exe file to run the task 


Note that I had to edit both the main.py file and runner.py file for the task to work on our computers. Additionally, to build the executable file, I needed to use the Anaconda3 command prompt and was not able to run the build.bat file by clicking on it. To do this, I mapped the correct directory by typing cd (C:\\....) and then just type build.bat. This should run the batch file needed to build the executable file of the task. If that does not work, you can always run the task using the command line. 
