# Automatic motion generator
Introduction
==========
This repository contains required scripts to convert existing amc and asf files or bvh file along with character model into synthetic video. All character model in sample folder are generated by Autodesk character generator.

Run
==========
## Entry and Settings
### Prerequisite:
Software: amc2bvh.exe, motionbuilder 2017<br />
Library: pyfbsdk (included in motionbuilder)Pillow<br />
Files: <br />
  Motion files: amc, asf or bvh formats. <br />
  Character models: fbx format. <br />
Run pip install Pillow to install pillow. <br />
Character models you plan to apply retargeting scripts. Suggest using Autodesk character generator to generate character because the export fbx file will be characterized already when downloaded from website. You can delete the light in the character model if you don't like it.<br />
<br />
Setting rendering options in motionbuilder before run the scripts.
### Skeleton mapping:
You can change the mobuMap(line25) in the retargeter.py to corresponding skeleton mapping if you don't use amc2bvh and try to directly convert bvh file.<br />
<br />
### Functionality:
Amc2bvh can batch convert asf and amc files into bvh files<br />
Retargeter.py can retarget bvh files into existing character model to render video<br />
<br />
### Light and Camera Setting:
You can change camera(line 135) and light(line 140) to change positions of cameras and lights. Also, you can change light type in (line 350)<br />
<br />
## Run steps:
### Conversion from asf and amc to bvh:
Create list_asf.txt, list_amc.txt,list_bvh.txt, List the source files in amc, asf list and destination into bvh list<br />
Run AMC2BVH file<br />
<br />
### Retargeting bvh files to multiple fbx character models:
Open motionbuilder<br />
Run the retargeter.py<br />
Choose the folder which characters prototype exists and then choose the source of bvh file <br />
<br />
### For generating one pictures from the motion capture file
Open motionbuilder<br />
Run the retargeter.py under generate picture<br />
Choose the folder which characters prototype exists and then choose the source of bvh file <br />
Run generate_picture.py to generate one picture from all frames

Sample Scripts
==========
Run AMC2BVH file in sample amc asf folder, choose list_asf.txt, list_amc.txt, list_bvh.txt as default setting.<br />
Open motionbuilder, run the retargeter.py, choose SampleCharacter folder for the first popoup folder then choose sample amc asf folder for the second popup folder and finally choose backgrounds for the third .<br />
Wait until the script finished.<br />
Sample video exists under sample video folder.<br />


Caution:
==========
For motion multiple motion file with large frames could cause motionbuilder UI stuck before it finishing its rendering process.
