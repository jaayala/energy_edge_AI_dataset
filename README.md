## Energy edge AI dataset 


Dataset of measurements of performance and power consumption of an AI service at the network edge. The experimental setup is comprised of a 3GPP R10-compliant LTE base station (BS), a user equipment (UE) generating service requests via the BS to a well-known object recognition service, and an off-the-shelf server with an NVIDIA GPU running the service. Each request consists of an image with a variable number of objects from the COCO dataset. The images are sent to the service via the uplink channel of the LTE interface, and the service returns bounding boxes and a classification label of the identified objects to the user via the downlink channel of the LTE interface. 

We provide two files. In 'ai_edge_dataset.csv', each value is the average of 150 images from COCO dataset. Moreover, we provide the per-image values in 'ai_edge_dataset_all.csv'. The details of the experiments and the software and hardware used can be found in the paper:

Jose A. Ayala-Romero, A. Garcia-Saavedra, X. Costa-Perez, G. Iosifidis (2021). EdgeBOL: Automating Energy-savings for Mobile Edge AI. Submitted to ACM CoNEXT 2021.



- **Configurations:**

"date_exp": Timestamp of the measurement \
"gpu_platform": GPU model running the AI service at the edge server \
"BW": Bandwidth of the LTE interface in number of resource blocks. For instance, BW = 100 -> 20 MHz \
"img_resolution": Percentage of the original size of the image. For instance, when img_resolution is 50, the size of the image is half of the original. \
"airtime_ratio": Ratio of the amount of radio resources (time) the BS allocates to the uplink. \
"gpu_power": GPU processing speed in terms of maximum consumed power. The higher this value the higher the processing speed. \


- **Measurements:**

"av_end2end_delay": Average end-to-end delay. Average of the time incurred by a user request (an image) to be delivered to the service, plus the processing time of the server (GPU delay), plus the time incurred by the reply (bounding boxes and labels) to be delivered to the user. \
"av_imp_proc_delay": Average time to load and resize the images at the user side. \
"av_gpu_delay": Average delay associated with the GPU tasks only. \
"av_num_obj": Average number of detected object \
"av_obj_size": Average object size. \
"AP1": Average Precision  (AP) @\[ IoU=0.50:0.95 | area=   all | maxDets=100 \] \
"AP2": Average Precision  (AP) @\[ IoU=0.50      | area=   all | maxDets=100 \] \
"AP3": Average Precision  (AP) @\[ IoU=0.75      | area=   all | maxDets=100 \] \
"AP4": Average Precision  (AP) @\[ IoU=0.50:0.95 | area= small | maxDets=100 \] \
"AP5": Average Precision  (AP) @\[ IoU=0.50:0.95 | area=medium | maxDets=100 \] \
"AP6": Average Precision  (AP) @\[ IoU=0.50:0.95 | area= large | maxDets=100 \] \
"AR1": Average Recall     (AR) @\[ IoU=0.50:0.95 | area=   all | maxDets=  1 \] \
"AR2": Average Recall     (AR) @\[ IoU=0.50:0.95 | area=   all | maxDets= 10 \] \
"AR3": Average Recall     (AR) @\[ IoU=0.50:0.95 | area=   all | maxDets=100 \] \
"AR4": Average Recall     (AR) @\[ IoU=0.50:0.95 | area= small | maxDets=100 \] \
"AR5": Average Recall     (AR) @\[ IoU=0.50:0.95 | area=medium | maxDets=100 \] \
"AR6": Average Recall     (AR) @\[ IoU=0.50:0.95 | area= large | maxDets=100 \] \
"powermeter_av": Average power consumed by the edge server measured externally using the digital power meter. \
"powermeter_var":  Variance of the power consumed by the edge server measured externally using the digital power meter. \
"powermeter_median": Median of the power consumed by the edge server measured externally using the digital power meter. \
"rapl_av": Average power consumed by the CPU of the edge server measured using the RAPL functionality. \
"rapl_var": Variance of the power consumed by the CPU of the edge server measured using the RAPL functionality. \
"gpu_av": Average power consumed by the GPU of the edge server measured using the Nvidia driver. \
"gpu_var": Variance of power consumed by the GPU of the edge server measured using the Nvidia driver. \
"clocksp_av": Average clock speed of the CPU of the edge server. \



- **Per image measurements:**

"im_ids": COCO data set IDs of the images used in the experiment. \
"end2end_delay": End-to-end delay per image. \
"imp_proc_delay": Processing time per image. \
"gpu_delay": GPU delay per image. \
"confidences": Confidence in the prediction per object and image. \
"num_obj": Number of detected objects per image. \
"obj_size": Sizes of the detected objects per image. \
"AP_per_image": Average Precision per image. \




## Citing Work
If you use the data please cite the following:
```
@inproceedings{ayala2021edgebol,
  title={EdgeBOL: Automating Energy-savings for Mobile Edge AI},
  author={Ayala-Romero, Jose A and Garcia-Saavedra, Andres and Costa-Perez, Xavier and Iosifidis, George},
  booktitle={ACM CoNEXT 2021},
  year={2021}
}
```



