# FastNeuralStyleTransfer  

Style transfer is a technique used in the field of computer vision and image processing that aims to apply the artistic style of one image to another while preserving the content. It involves the process of combining the content of one image with the style of another, creating an output image that reflects the content of the first image but appears to be created in the style of the second image.  
  
In this process, the content of an input image is typically represented by the arrangement of objects and their spatial relationships, while the style is characterized by textures, colors, and visual patterns that give the image its artistic appearance. By separating and recombining the content and style representations of different images, style transfer techniques can generate visually appealing compositions that blend the content information with the artistic characteristics of the style image.  
  
There is 3 approches to stylize an image:  
&emsp;1- Utilizing a pre-trained neural network, such as VGG16 or VGG19, trained on an extensive dataset like ImageNet for object detection yields highly desirable outcomes. However, this approach suffers from time-consuming stylization of input images.  
    
&emsp;2- Training a neural network to apply a specific style to any image potentially leading to optimal results. Nevertheless, each style image would have its own neural network, making this method unfeasible. This approach could be suitable when dealing with a limited number of style images that are not expected to expand in the future.  
   
&emsp;3- This method is known as Real-time Arbitrary Style Transfer. It involves employing a pre-trained neural network, like VGG16 or VGG19, trained on a comprehensive dataset like ImageNet for object detection. This model is used to encode the images. The content and style images are then encoded and fed into the AdaIN layer (which will be discussed later). The output of this layer is decoded using a custom decoder neural network that mirrors the encoder. The decoder is then trained on the dataset.  
  
My approach is depended on 2 main papers:  
&emsp;the first paper authors are L. Gatys, A. Ecker, and M. Bethge ([paper link](https://arxiv.org/abs/1508.06576)). Uses first approach.  
  
&emsp;the second paper authors are Xun Huang, Serge Belongie ([paper link](https://arxiv.org/abs/1703.06868)). Uses third approach. read thier paper for more information about how AdaIN layer works.   
  
My results:  
results from training dataset  
![Image](results/1.png)  
![Image](results/3.png)  

results from custom dataset  
![Image](results/5.png)  
![Image](results/7.png)  
  
result of high resolution image 2000*1400  
![Image](results/8.png)  
      
My attempt to make fast neural style transfer for low end devices where the memory usage is limited like mobile devices which its hard to use large models on it like VGG19.  
   
What i have done so far:  
&emsp;- used MobileNetv2 model as encoder from keras that pretrained on ImageNet dataset.  
&emsp;- create a mirror network for the MobileNetv2 model, to be used as deocder.  
&emsp;- used datasets from kaggle one for content images, and one for style images.  
&emsp;- prepaired the environment and start training the decoder.  
  
  
Final words:  
&emsp;I understand the current results are unsatisfactory and not suitable for production or any practical use. However, as a beginner, I perceive it as a promising start, and I am determined to refine the model until achieving satisfactory outcomes. If you have any tips or suggestions for improvement, please feel free to share them with me.  
  
The repository contains the model weights file, which you are free to use as you want (feel free :) )  
  
[Click here to see my code on google colab](https://colab.research.google.com/drive/1QEEof48LaaCyRLMWpmQHovOasdr5cogw?usp=sharing)  
