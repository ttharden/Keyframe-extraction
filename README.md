# Description
A benchmark dataset for keyframe extraction. The dataset folder [Dataset](/Dataset) consists of the source video folder [Videos](/Dataset/Videos) and the keyframe dataset folder [Keyframe](/Dataset/Keyframe). In these two folders, it consists of 20 videos and their corresponding keyframe images respectively.The project components are structured as follows：

<div align=center>
<img src="https://github.com/ttharden/Keyframe-extraction/blob/main/images/file.png" > 
</div>

# Background
In the field of generating static video summaries, there is a lack of a benchmark dataset to judge the extraction quality of methods. Most authors are judged by human selection, which lacks objectivity. In the field of dynamic video summarisation, there are various datasets to choose from, among which TvSum is representative.
  
TvSum dataset contains 50 videos collected from YouTube, spanning across 10 distinct categories(e.g., changing Vehicle Tire (VT), getting Vehicle Unstuck (VU), Grooming an Animal (GA)). Each video is annotated as follows: the video was chopped up into a set of 2 second-long shots and asked 20 users to rate how important each shot is, compared to other shots from the same video, on a scale from 1 (not important) to 5 (very important). 

To solve this problem, we propose a new dataset based on the TvSum dataset as a benchmark dataset for static video summarisation (keyframe-extraction). We selected 2 videos from each category, totalling 20 videos to form the source of our dataset. We constructed simple and efficient keyframe dataset.

# Method
_Step 1:_ We obtain the average of the video's importance score across all professionals as the basis for the video's score, and further based on this, we obtain the extremes of the video's score distribution, and we select the video frame corresponding to the midpoint of the extremes as our candidate benchmark video frame.The corresponding situation is shown below.![case](/images/pic.png)  

_Step 2:_ To reduce the occurrence of multiple poles within the same shot but with similar image content, we further perform similarity-based de-redundancy within the shot.

_Step 3:_ Based on the candidate frames after de-redundancy, we manually select them on the basis of this, the purpose of doing so is to avoid the centre frame as a low information frame, we manually select its surrounding frames with better performance to replace it, and finally we get our key frame sequence. The result of one of the videos is shown below:![case](/images/result.jpg)  

Finally, we process the 20 videos. We get the set of keyframes corresponding to the 20 videos.The video and keyframe information is shown below:  

<div align=center>
<img src="https://github.com/ttharden/Keyframe-extraction/blob/main/images/data_message.png" > 
</div>


# Reference
Song, Yale, Jordi Vallmitjana, Amanda Stent, and Alejandro Jaimes. "TVSum: Summarizing web videos using titles." In Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition, pp. 5179-5187. 2015.

