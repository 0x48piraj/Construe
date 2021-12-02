![Construe Hero](https://user-images.githubusercontent.com/5800726/144445503-46ae2fd4-435f-4588-b93b-7a0a29aa17c6.png)

The data one uses for training and deploying machine learning models can determine success or failure for one's AI projects.

Creating medical datasets requires uncommon file support, and a series of features required to maintain accountability of annotations unlike most annotation tools on the market.

Construe plays an important role in whether you can create a high-performing model that powers a disruptive solution or solves a painful, expensive problem - or end up investing time and resources on a failed experiment.

## The Challenge: Medical Imaging Annotation vs Normal Annotation

If your ultimate goal is to train machine learning models, there are few differences between annotating a medical image versus a regular PNG or JPEG. Here are a few things to consider about medical imaging that do not apply in other vision data,

### Medical Imaging contains transparencies

This means occlusions must be treated differently. Objects in front of one another may appear behind one another. It's no secret that AI handles occlusion poorly due to a lack of presence of mind, and transparent objects can be even worse. Luckily though, an organ, cell, or bone appearing transparent is far more obvious to an AI than a pane of glass.

See the chest x-ray below: are the lungs behind or in front of the diaphragm? The answer is both. The occluded portion of the lungs cannot be perceived by traditional computer vision methods, however a deep neural network can easily learn to spot it.

<p align="center">
<img alt="MRI Slices Annotated" src="https://assets-global.website-files.com/5b26e3fda3234fe366aa392d/5eb16f3f8a376a095246514f_11-pairs-of-ribs-and-lumbosacral-transitional-vertebra.jpg"><br>
<i>A chest x-ray displaying the lower portion of the lungs, extending in front of the diaphragm posteriorly and behind it anteriorly.</i><br>
</p>

### Formats may vary, for better or for worse

Most medical imaging will be in [DICOM](https://www.dicomstandard.org/) format. A DICOM file represents a  **case**, which may contain one or more images.

From a machine learning perspective, the DICOM file will be converted to another lossless image format during training, therefore it's not a necessity to use DICOM files for AI research. However preserving the integrity of the DICOM image can be useful for the annotation phase, particularly as radiologists are familiar with how DICOM viewers work after operating them for years.

Differing views and differing volumes
A case may contain 2D or 3D imaging. In both examples, often more than one view is necessary to assess what's happening. For example, the x-ray of a hand may only reveal a fracture when the hand is in certain pose or angle. Nonetheless it is standard to capture a frontal view of the hand anyways:  

<p align="center">
<img alt="MRI Slices Annotated" src="https://assets-global.website-files.com/5b26e3fda3234fe366aa392d/5eb1eaebdc812dfe3ba60ec6_hand_xray.jpg"><br>
<i>A small fracture at the base of the 3rd and 4th middle phalanx is mostly only visible on the right image.</i><br>
</p>

It's important not to include un-usable data in your machine learning dataset. If a view such as the one above is useful for reference purposes, but cannot be labelled and turned into training data, it's best to discard it.

## Features

Viewer tools are provided to adjust windowing (brightness/contrast), zoom, invert, and panning of the image.

Annotation tools are provided for marking images with either rectangles or length measurements. These annotations are defined by their bounding (x,y) coordinates as well as some other metadata.

All annotation metadata can be exported in JSON format to be used for a variety of purposes, such as training input for deep learning models using bounding box algorithms. The downloaded JSON files can also be later used to restore any annotation state stored in them by simply dragging and dropping the relevant JSON file onto the viewer while the images are loaded or can be shared to other team members and organizations for collaboration.

## Inspiration

People are shaped by their childhood experiences and by their families. For me, both of my parents are doctors, so several aspects of my life have been affected by being surrounded by people who practice medicine.

I know that radiologists annotate (or markup) medical images on a daily basis. This can be done in DICOM viewers, which contain basic annotation capabilities such as bounding boxes, arrows, and sometimes polygons. Machine learning (ML) may sometimes leverage these labels, however their format is often inconsistent with the needs of ML research, such as lack of instance IDs, attributes, a labeling queue, or the correct formats for deep learning frameworks like **Pytorch** or **TensorFlow**.

Construe tries to solve that. It's the first step in that direction. I want to empower all the people like my parents using computer science.

## What I learned

While many services exist that provide annotation tools for common file formats like PDF and JPEG, the healthcare sector presents a unique challenge in the form of DICOM files. This industry-specific format contains both images and important metadata identifiers that provide information about the image itself and the patient in question. While there are ways to extract images from DICOM files and convert them into a more manageable format, doing so could endanger compliance status or permanently degrade the image quality.

## Accomplishments that I'm proud of

Creating this web-based tool in somewhat short period of time and taking the first step toward my dreams.

## What's next for Construe

If it's recommended, I would love to work more on Construe to get it out and open it to the public, allowing medical organizations to test out Construe.
