# PATH Delay Discounting Deployment

Repository to store updates made to the original PATH DD behavioral task shared by Richard Liu. 

## Instructions - MUST FOLLOW ALL OF THE STEPS EVEN IF YOU ALREADY HAVE PSYCHOPY INSTALLED

Be sure Anaconda and Python are installed. To check, go to the start menu and search for Anaconda Prompt (anaconda3). Open Anaconda Prompt and "type python --" and hit enter. The version should be 3.7 or 3.7.##. 
Note that I used the Anaconda command line for installing the task on a desktop computer, but could only get the task to work on a laptop using the system command prompt + creating a virtual environment. 
1. Unzip the files and save them in a folder on your local task computer, not the server. 
2. Open the Delay Discounting Task (DDT) folder on your local task computer. 
3. Go to the start menu and open the command prompt as an administrator. 
4. A command prompt window will appear. Copy and paste each of the snippets below and hit enter to run (wait for each to finish running before adding the next one). 
  - pip install adopy
  - pip install pyyaml
  - pip install psychopy
  - pip install pyinstaller
  - pip install poetry
5. Set the working directory to the folder where you saved the task. 
  - Type code cd followed by the file path to the DDT files and hit enter [E.g., cd C:\MABL\DDT (Delay Discounting Task) – ADO]
6. In the new working directory, copy and paste each of the snippets below and hit enter to run (wait for each to finish running before adding the next one). 
  - poetry install
  - poetry shell
(I added these code snippets to be pasted as additional steps because of an error of missing packages. I assume it's because I used the system cd line, and we are working with a virtual environment. 
  - pip install adopy
  - pip install pyyaml
  - pip install psychopy
  - pip install pyinstaller)
5. Use pyinstaller to run the task. This will create a “dist” folder with a “main” subfolder. Paste this code:
  - pyinstaller main.py 
6. Run the task using the cmd line to make sure it works well. Paste this code:
  - python main.py and hit enter
  - When the window opens enter the ID and select the Wave and Prepost, click okay and then Save
  - Run the task to check it is working
7. Solve issues that arise when running the task using the cd line. 
  - A problem I encountered was that wx.App was missing. I edited the main.py file to import wx and then declared app = wx.App(False) after info_dialog. I did not run into the same issue when using a laptop. I recommend starting out with the original files and adjusting as needed.  
  - Another problem I ran into is that the task would crash after the first real trial because it attempted to append the results to a data frame. I edited the runner.py file to use the pd.concat method instead. 
8. Make sure the task is able to run, then close the cd line and the task. 
9. Open the command line again and map the directory of where the task is stored on your computer (see step 5).
10. Run the batch file that will create an executable file of the task by pasting the code below and let it run in its entirety. 
  - build.bat 
11.	If a Windows protected your PC pops up, click “more info” and then click “run anyway.”
12.	This will create a ddt.exe file and a ddt subfolder in the dist folder. The ddt subfolder will also contain a ddt.exe file
14.	When you see (base) C:\..., go to DDT (Delay Discounting Task) – ADO > dist > ddt folder and go to the ddt.exe file. Double click to open.
15. Add supporting information to run the task and name output file:
  - Enter the ID, Wave, and Prepost and click okay and then save to run the task.
  - Rename your output file to your liking. 
16.	Go to the dist folder and open the ddt.exe file to run the task. This is the preferred file to run the task as it is much quicker to open 


Note that I had to edit both the main.py file and runner.py file for the task to work on our computers. Additionally, to build the executable file, I needed to use the Anaconda3 command prompt and was not able to run the build.bat file by clicking on it. To do this, I mapped the correct directory by typing cd (C:\\....) and then just type build.bat. This should run the batch file needed to build the executable file of the task. If that does not work, you can always run the task using the command line. 
