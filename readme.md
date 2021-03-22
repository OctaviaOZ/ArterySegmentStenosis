[![made-with-python](https://img.shields.io/badge/Made%20with-Python-1f425f.svg)](https://www.python.org/)

**Welcome to initial project to build CT cardial processing system!**

#CSTORE
I build two services to understand the structure - Service Class Provider(SCP)
and Service Class User(CSU). 
In the project, there are in the folder "cstore". 
To execute you have to run them from "cstore" folder from the command line.

```bash
python scp.py
```
```bash
python scp.py pacs
```

*if you work from PyCharm you can put parameter "pacs" into configuration of scu.py.

The "pacs" folder is a conditional server to gather dicom files (*.dcm).
CSP provides connecting to a vendor which has given you authorities.
CSU explores "pacs" folder to process the data.
The services work in the inial stage.

There have to be written a module that will be extract images from dicom files and write its to the folder "data".

BreifExploring.ipynb - jupyter notebook file. 
<table align="center">
<tr>
         <td align="center">
            <a href=" https://colab.research.google.com/github.com/OctaviaOZ/Artery_Segment_Stenosis/blob/master/BreifExploring.ipynb">
                <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Google Colab">
            </a>
        </td>
</tr>
It contains exploring the internet to deep dive into the last publications, 
state-of-art researches that might be helpful to build a system that has to explore coronary arteries in the human body. 
Each artery can be conditionally divided into 3 segments of equal length - proximal, middle, and distal. 
The system has to measure a stenosis level for each segment. 
The notebook file includes exploring analyze CT images using python libraries.

<p align="center">
  <a href="https://faculty.washington.edu/jeff8rob/trauma-radiology-reference-resource/2-vascular/coronary-artery-segments/">
    <img style="width: 600px; overflow: hidden;" src="https://faculty.washington.edu/jeff8rob/wordpress/wp-content/uploads/2017/03/Coronary-artery-segments-1024x577.jpg" alt="Progressive artifacts">
  </a>
</p>

