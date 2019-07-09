# yoloDarkflow
This repo encapsulates all you need for running YOLO(You Look Only Once) algorithm using the Tensorflow translation of Darknet, i.e. Darkflow

System specifications :
* Operating system - Ubuntu 18.04LTS / other Linux distro
* If you want to harness the potential of a graphics card in your project, then install 
    * CUDA 9 [https://developer.nvidia.com/cuda-90-download-archive] 
    * cudnn 7 [https://developer.nvidia.com/rdp/cudnn-archive]
    * Tensorflow-gpu 1.80 [sudo pip3 install tensorflow-gpu==1.80] 
    [Mark that some higher version of Tensorflow-gpu such as 1.14 won't support cudnn 7] 
 
 --------------------------------------------YOLO DARKFLOW----------------------------------------------------------------
 
Okay folks, let's commence! 
Running the YOLO darkflow algorithm is pretty simple! [given you have installed everything correctly, as the algorithm is a bit high maintenance (no offense to the good authors!)] 
Speaking of which, the yoloV3 paper can be found at : https://pjreddie.com/media/files/papers/YOLOv3.pdf 

Let's ACTUALLY start now!
First clone this directory then follow :

Step I : Install Cython (C extension for Python language, as the base of darknet is C/C++ language)
         Run the following in terminal : $ sudo apt-get install cython3 
         (Install cython3 globally. This will save you from a lot of pain)
Step II : Since we aren't constructing custom object detector, so we will use the designed net itself for now.
          Type the following on terminal : 
          
          flow --h

Step III : Download the weights file for yolo from here : https://drive.google.com/drive/folders/1Ji3p7Ect_OyyDX0vQesQA3R1cm050Fw8?usp=sharing (Ignore the Captain Marvel movie uploaded there :)) 

Step IV : Create a new directory called bin inside the cloned yoloDarkflow directory. Place the yolo.weights file there.
Step V : Download the yolo.cfg file from the same G-drive link : https://drive.google.com/drive/folders/1Ji3p7Ect_OyyDX0vQesQA3R1cm050Fw8?usp=sharing and place it into the cfg directory, inside yoloDarkflow.
Step VI : Set yoloDarkflow as your working directory in linux by using 'cd' command :
          
          cd yoloDarkflow

Step VII : Execute the command to load weight and check the compatibility of the selected .cfg and .weights file
           
           flow --model cfg/yolo.cfg --load bin/yolo.weights
           
Step VIII : Store all the images you want to try the YOLO architecture on, inside the sample_img folder and execute
            
            flow --imgdir sample_img/ --model cfg/yolo.cfg --load bin/yolo.weights --gpu 1.0
            
Step IX : Try it on webcam using the command 

            flow --model cfg/yolo.cfg --load bin/yolo.weights --demo camera --gpu 1.0 (for GPU users)
            flow --model cfg/yolo.cfg --load bin/yolo.weights --demo camera (for CPU users)
            
Step X : In case you want to use it on a downloaded video, simply place the video into the working directory and specify its full name( with extension) inplace of 'camera'. 

That's it! Have a ball of a time with YOLO
