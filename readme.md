[![made-with-python](https://img.shields.io/badge/Made%20with-Python-1f425f.svg)](https://www.python.org/)

**Welcome to initial project to build CT cardiac processing system!**

For the purposes of recognizing some diseases using ML to collect appropriate data is of vital importance. Developed solutions to build DICOM services on the market are various. Automated mechanisms are required in order to collect a large number of images. I tried to build a service for research purposes to collect data using an API. There are Service Class Provider (SCP) and Service Class User (SCU). Such collecting is limited to have obtaining authorities and the download process requires a lot of time due bandwidth limits. I found one resource out which allows downloading Dicom samples. Access to these images requires a valid Premium Membership (69,99 of dollars monthly or 99,00 for one year). You have to be sure to buy appropriate samples. I failed to find any datasets of CT cardiac in free access.

I have been scrolled through a lot of information about the processing of Dicom images. There are gathered the main required:

The tags of the protocol descriptions have to be attentive:
- Modality "CT" (Computed Tomography) (0008,0060);
- BodyPartExamined (0018,0015) To filter the cardiac anatomic regions have to be consulted with domain professionals.
- A medical record number (MRN) uniquely identifies a patient within a health system. Images from the same patient must all be grouped into the same set.

During creating the CT cardiac dataset several DICOM attributes are particularly important for cleaning CT volumes:
Image Type, Image Orientation (Patient), Image Position (Patient), Rescale Intercept,
Rescale Slope, Pixel Spacing, Gantry/Detector Tilt.

*CSTORE*
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

[jupyter_BriefExploring.ipynb](/jupyter_BriefExploring.ipynb).

The jupyter notebook file contains preprocessing of images to get segments of arteries
that might be helpful to build a system that has to explore coronary arteries in the human body. 
Each artery can be conditionally divided into 3 segments of equal length - proximal, middle, and distal. 
The system has to measure a stenosis level for each segment. 
The notebook file includes exploring analyze CT images using python libraries.

<p align="center">
  <a href="https://faculty.washington.edu/jeff8rob/trauma-radiology-reference-resource/2-vascular/coronary-artery-segments/">
    <img style="width: 600px; overflow: hidden;" src="https://faculty.washington.edu/jeff8rob/wordpress/wp-content/uploads/2017/03/Coronary-artery-segments-1024x577.jpg" alt="Progressive artifacts">
  </a>
</p>

**Suggestions on the further analytics/approaches which could be applied:**
CNN (Transformers-based in particular) framework achieves state-of-the-art performance in medical image segmentation applications. 
U-Net, the U-shaped convolutional neural network architecture.

*Used resourses:*
[DICOM standart browser](https://dicom.innolitics.com/ciods/cr-image/general-series/00080060)
[osirix-viewer](https://www.osirix-viewer.com/resources/dicom-image-library/)
[Downloading and Preprocessing Medical Images in Bulk: DICOM to NumPy with Python](https://glassboxmedicine.com/2021/02/16/downloading-and-preprocessing-medical-images-in-bulk-dicom-to-numpy-with-python/)
[Hands-on TransUNet: Transformers For Medical Image Segmentation](https://analyticsindiamag.com/hands-on-transunet-transformers-for-medical-image-segmentation/)
[Build a DICOM DIMSE C-STORE Service with Python in 10 Minutes](https://www.voltron.studio/article/build-a-dicom-dimse-c-store-service-with-python)
[CT intensity-based lung and vessel segmentation](https://github.com/black0017/ct-intensity-segmentation)

*Resurses to deep dive into domain:*
[Coronary_arteries wiki](https://en.wikipedia.org/wiki/Coronary_arteries)
[Coronary artery segmentation in angiographic videos utilizing spatial-temporal information](https://bmcmedimaging.biomedcentral.com/articles/10.1186/s12880-020-00509-9)
[The new role of diagnostic angiography in coronary physiological assessment](https://heart.bmj.com/content/early/2021/02/10/heartjnl-2020-318289)
[CT of Coronary Artery Disease](https://pubs.rsna.org/doi/10.1148/radiol.2532081738)
[Deployment of a medical imaging web service](https://www.digihunch.com/2020/11/medical-imaging-web-server-deployment-pipeline/)

*For self-research:*
Lerning different functional cardiac CT techniques: cine-CT, CT-FFR, CT-myocardial perfusion 
and how developments in machine learning can supplement these techniques.
