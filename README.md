# Tracking-Tendon-Fibers
This program tracks tendon fibers in micro CT-scans of rat tails.
This program produces both a video of the scans in sequence with the fibers annotated in color and a 3D reconstruction of the tendons. 
## Prerequisites
This program rquires the user to prove the data for segmentation.
The zip file should contain a sequence of Micro CT-scans that are in the TIFF file format and the images are named orderly numerically or alphebatically.
The program runs in Google Colab and requires access to their GPU services, the free version of Google Colab comes with access to the T4 GPU which is sufficient for the program.
However large datasets may need more runtime than the free Google Colab subscription permits.
Download the file [TrackingTendonFibers](https://github.com/ianmccall13/Tracking-Tendon-Fibers/blob/main/TrackingTendonFibers.ipynb) and upload it to your Google Drive to run in Google Colab
## Usage
1. Open the program in Google Colab
2. Connect to your GPU of choice, either by clicking the "Reconnect" button in the top right or by clicked the drop down menu next to the "Reconnect" button and then click "Change runtime type". Once you enter the "Change runtime type" menu select your GPU of choice.
3. You may either run each cell individually, this may help reduce any potential errors, or you can hit the "Run all" in the tool bar to have the program run automatically. However if you do utilize the "Run all" function you may want to check the customizable settings found under the label "Configure Custom Settings" before running the program.  
4. Once the program reaches the cell titled "Upload Input" the user is required to click on the "Choose File" button just below the cell and select the zip of their desired input from their computer.
5. Once the program reaches the cell titled "Configure Custom Settings" the user should check over all modifiable characteristics to customize their output to their needs. The follwoing are all customizable variables:   
    1. frameSkip: The size of a group of frames that the system pulls 1 from to reduce the input size, if you want all input processed frameSkip = 1, if you want every other frame frameSkip = 2, etc.
    2. fps: The frames per second of the output video so you may want to alter this value depending on the number of frames you want to be processed.
    3. SCALE_FACTOR: The scale of the output videos dimensions relative to the input, SCALE_FACTOR = 1 is same size as input dimensions, SCALE_FACTOR = 2 is double input dimensions
6. Everything beyond this point should run without user interaction as long as all cells are prompted to be run.
7. To retrieve the output of the program click on the "Folder" icon on the left tool bar and click the OUTPUT folder. This folder will have each of the frames processed by the program and also video of the sequence at your specified fps along with the 3Dreconstruction file.
## Trouble Shooting
1. If you encouter an error when import any libraries it is mostlikely a runtime issue, to resolve this click on the drop down to the right of "RAM and Disk" button and then click "Change runtime type". Once you enter the "Change runtime type" menu select "CPU" as your Hardware Accelerator and then click "Save". Then go back to the "Change runtime type" menu and select your desired GPU and then click "Save". This should effectively reset the runtime, you will need to rerun previously run cells, but the error should not persist.
