# OCRsubsytem

A. Supervised Learning Supervised learning algorithms are trained using labeled examples, such as an input where the desired output is known. For
example, a piece of equipment could have data points labeled either “F” (failed) or “R” (runs). The learning algorithm receives a set of inputs along with the corresponding correct outputs, and the algorithm learns by comparing its actual output with correct outputsto find errors. It then modifies the model accordingly. Through methods like classification, regression, prediction and gradient
boosting, supervised learning uses patterns to predict the values of the label on additional unlabeled data.


 B. OpenCV(Open Computer Vision)
OpenCV (Open Source Computer Vision) is a library of programming functions mainly aimed at real-time computer vision.Originally developed by Intel, it was later supported by Willow Garage then Itseez (which was later acquired by Intel). The library
is cross-platform and free for use under the open-source BSD license. OpenCV supports the deep learning frameworks TensorFlow,Torch/PyTorch and Caffe


C. OCR(Optical Character Recognition)
OCR (Optical Character Recognition) also called Optical Character Reader is a system that provides a full alphanumeric recognition of printed or handwritten characters at electronic speed by simply scanning the form. More recently, the term Intelligent Character Recognition (ICR) has been used to describe the process of interpreting image data, in particular alphanumeric text. Function of OCR Forms containing characters images can be scanned through scanner and then recognition engine of the OCR system interpret
the images and turn images of handwritten or printed characters into ASCII data (machine-readable characters). Therefore, OCRallows users to quickly automate data capture from forms, eliminate keystrokes to reduce data entry costs and still maintain the high level of accuracy required in forms processing applications. Features of OCR The technology provides a complete form processing
and +documents capture solution. Usually, OCR uses a modular architecture that is open, scaleable and workflow controlled. It includes forms definition, scanning, image pre-processing, and recognition capabilities. What is ICR Intelligent Character Recognition (ICR) is the module of OCR that has the ability to turn images of hand written or printed characters into ASCII data. Sometimes OCR is known as ICR.

D. Tesseract with Python: pytesseract
It will recognize and read the text present in images. It can read all image types - png, jpeg, gif, tiff, bmp etc. It’s widely used to process everything from scanned documents.Tesseract works best when there is a (very) clean segmentation of the foreground text from the background. In practice, it can be extremely challenging to guarantee these types of segmentations.


Optical character recognition using neural network. Implemented with Python and its libraries Numpy and OpenCV.

We recommend you to view the presentation file inside docs first, which will give you a brief analysis of this project.

Python libraries needed: Numpy (Neural Network creation and data handling) OpenCV (Image processing) PyQT (GUI)

There are two parts to this project. First one is the neural network and the other is the image processing.

The OCR is performed in the following phases:

Image is retrieved The image should be cropped in such a way that only text is present. Also, the background should be very lighter than the text. Ideal image would be black text on a white paper background.

Preprocessing Noises are removed by blurring. The it is converted to binary image along with invert. For this we've used OpenCV methods such as gaussian blur and threshold.

Segmentation Segmentation is divided into three parts. First we segment the image based on lines. Then the lines are separated into words. Lastly, the words are separated into characters. OpenCV methods such as projections and contour detections are used. The characters are then fed into the neural network.

Neural Network There are two parts to neural network. First is Training Neural Network. For training the neural network, we first generated our own samples for each characters. That made a total of 260,000 samples. We used PHP's imagettftext() method using 10 different fonts. PHP generated each samples in an image format. So we then converted those images into numpy array and combined all samples with corresponding labels required by the neural network. Second is Recognizing characters. We used two NN for the classification. First is the classification for all characters. Second is based on the confusion classes. (For the detailed description of neural network and their implementaiton, we refered to the book at http://neuralnetworksanddeeplearning.com/ So if you want to know all about neural networks, their algorithms and workings, you should definitely give it a visit.)


