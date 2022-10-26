# Gait-Recogintion



# Attention-Based Gait Recognition Network with Novel Partial Representation PGOFI based on Prior Motion Information

### We provide a demo of our proposed gait recognition model, the code will be released after the paper is accepted.

The demo can be download at https://drive.google.com/file/d/1fuyDe9z0fff5NMUyz5ooWbx2CGObgBmJ/view?usp=sharing. We borrow the **UI** file from https://github.com/developfeng/GaitRecognition.

### Demo Introduction

1. We simulate the use of the gait recognition algorithm in a real-world scenario. We first pre-registered the ID and gait feature of a pedestrian, i.e. WYH, and then we registered and recognized another pedestrian, i.e. Mike, in real time. This is a real-world usage scenario of the gait recognition algorithm, i.e. registering and recognizing new users in real time. Also, the existence of the existing ID WYH in the database allows us to test whether the gait recognition algorithm will recognize different pedestrians as the same id.

2. Our algorithm demo was performed on an old laptop with a 980M graphics card, not on a high-performance computer or server. For reference, the Nvidia RTX3090 graphics card has 40 TFLOPS (Tera Floating Point Operations Per Second, used to indicate the computing power of the graphics card in the field of deep learning), the Nvidia development board Jetson Orin Nano (the most commonly used computing hardware in the field of computer vision) has 35 TFLOPS, and the Nvidia Jetson Orin NX has 100 TFLOPS. That is, the hardware we are using is low performance hardware, and if our algorithm has good real-time performance on this laptop, it will have better real-time performance on other common hardware.

3. In the demo, we first registered the new pedestrian Mike in real time, and then immediately performed real-time recognition without any additional processing. In the recognition process, we performed three scenes in turn, namely normal walking (corresponding to NM scene in the manuscript), backpack walking (BG), and changing clothes scene (CL). Finally, we perform gait recognition on the pre-registered pedestrian WYH to verify whether the gait recognition algorithm can distinguish different pedestrian.

### Demo Description & Discussion:

1. The video window on the left in the demo is the live camera footage, and the window on the right is the optical flow. As shown in Figure.1, the results of gait recognition are displayed in real time in the left window as pedestrian boxes and id identifiers.

![img](https://github.com/sspBIT/Gait-Recogintion/blob/main/clip_image001.jpg)

**Figure.1** The results of gait recognition.

2. Before testing, we have pre-registered another pedestrian, WYH, in the algorithm as a control group to test the effectiveness of the gait recognition algorithm.

3. At the beginning of the demo, we start with real-time registration of pedestrian Mike. As shown in Figure.2, the registration process is very simple and fast, requiring only that the pedestrian walk in front of the camera. No additional processing is required after registration.

![img](https://github.com/sspBIT/Gait-Recogintion/blob/main/clip_image002.jpg) **Figure.2** The registration of new pedestrian.



4. At 0 minutes and 20 seconds, we perform the recognition of pedestrians. We first perform gait recognition in the NM scene. The recognition result is shown in Figure.3.

![img](https://github.com/sspBIT/Gait-Recogintion/blob/main/clip_image003.png)**Figure.3** The recognition result under NM scene.

At 0:41, we perform gait recognition in the BG scene; and at 1:05, we perform gait recognition in the CL scene. Both the BG and CL scenes are heavily 	altered with respect to the pedestrian profile (backpack and wearing thick clothes), but as shown in Figure.4 and Figure.5, our algorithm still accurately identifies the ID of the pedestrian. It is important to note that the whole process is completely real-time.

![img](https://github.com/sspBIT/Gait-Recogintion/blob/main/clip_image004.png)

**Figure.4** The recognition result under BG scene.

![img](https://github.com/sspBIT/Gait-Recogintion/blob/main/clip_image005.png)

**Figure.5** The recognition result under CL scene.

5. At 1:28, we identify WYH, a pre-registered pedestrian. As shown in Figure.6, our algorithm accurately identifies WYH's ID and does not identify him as Mike as well. Also, during the identification of Mike, our algorithm never misidentifies him as WYH. This proves that our algorithm does extract the gait features of different pedestrians.

![img](https://github.com/sspBIT/Gait-Recogintion/blob/main/clip_image006.png)

Figure.6 The recognition result of pre-registered pedestrian.

In summary, our algorithm can register and recognize in real time, with excellent real-time performance on low-performance hardware. At the same time, our algorithm is able to recognize pedestrians accurately in the face of multiple gait scenarios (NM CL BG). Once again, we thank you for your comments. However, it is important to point out that our algorithm is not the only one that is real-time, but other gait recognition algorithms are also real-time, because the network parameters of gait recognition networks are fewer compared to other computer vision tasks, and none of the existing papers include real-time performance as one of the evaluation criteria. 

On a 980m laptop, our algorithm can process **67** video frames per second, i.e., **FPS=67**. This is perfectly in line with the real-time requirements, as the average camera shoots at a frame rate of **30** or **25 FPS**.

