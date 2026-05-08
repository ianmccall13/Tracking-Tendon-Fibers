# Tracking-Tendon-Fibers
This program tracks tendon fascicles in micro CT-scans of rat tails.
This program produces both a video of the scans in sequence with the fascicles annotated in color and a 3D reconstruction of the tendons. 
## Prerequisites
This program requires the user to provide the data for processing.
The input data should come in the form of a zip file and should contain a sequence of Micro CT-scans that are in the TIFF file format. The images should be organized numerically with the first image acting as the starting point and the last image acting as the ending point. 
The program runs in Google Colab and requires access to their GPU services, the free version of Google Colab comes with access to the T4 GPU which is sufficient for this program.
However large datasets may need more runtime than the free Google Colab subscription permits.
Download the file [TrackingTendonFibers](https://github.com/ianmccall13/Tracking-Tendon-Fibers/blob/main/TrackingTendonFibers.ipynb) and upload it to your Google Drive to run in Google Colab
## Usage
1. Open the program in Google Colab
2. Connect to your GPU of choice, either by clicking the "Reconnect" button in the top right or by clicked the drop down menu next to the "Reconnect" button and then click "Change runtime type". Once you enter the "Change runtime type" menu select your desired GPU.
3. You may either run each cell individually, this may help reduce any potential errors, or you can hit the "Run all" button in the tool bar to have the program run automatically. However, if you do utilize the "Run all" function you may want to check the customizable settings before running the program. These can be found under the label "User Customization" near the top of the file.  
4.Once the program reaches the cell titled "User Customizations" the user should check over all modifiable characteristics to customize their output to their needs. The following are all customizable variables:   
    1. frameSkip: The size of a group of frames that the system pulls 1 frame from to reduce the input size, if you want all input processed frameSkip = 1, if you want every other frame frameSkip = 2, etc.
    2. fps: The frames per second of the output video, you may want to alter this value depending on the number of frames you are processing.
    3. SCALE_FACTOR: The scale of the output video's dimensions relative to the input, SCALE_FACTOR = 1 meanings the video will have same size as the input, SCALE_FACTOR = 2 would double the video's dimensions relative to the input.
    4. scale_unit: The unit and 'stretch' factor on the z=axis in the final reconstruction. MUST BE "millimeters", "microns", or "pixels".
5. Once the program reaches the cell titled "Upload Input" the user is required to click on the "Choose File" button just below the cell and select the zip of their desired input from their computer.
6. Everything beyond this point should run without user interaction as long as all cells are prompted to run.
7. To retrieve the output of the program click on the "Folder" icon on the left tool bar and click the OUTPUT folder. This folder will have every frame processed by the program, the video of the annotated sequence at your specified fps, and the 3D reconstruction file.
## Trouble Shooting
1. If you encouter an error when import any libraries it is mostlikely a runtime issue, to resolve this click on the drop down to the right of "RAM and Disk" button and then click "Change runtime type". Once you enter the "Change runtime type" menu select "CPU" as your Hardware Accelerator and then click "Save". Then go back to the "Change runtime type" menu and select your desired GPU and then click "Save". This should effectively reset the runtime, you will need to rerun previously run cells, but the error should not persist.
