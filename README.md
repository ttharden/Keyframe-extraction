# Description
A benchmark dataset for keyframe extraction used in our paper "LARGE MODEL BASED SEQUENTIAL KEYFRAME EXTRACTION FOR VIDEO SUMMARIZATION"
# Background
In the field of generating static video summaries, there is a lack of a benchmark dataset to judge the extraction quality of methods. Most authors are judged by human selection, which lacks objectivity. In the field of dynamic video summarisation, there are various datasets to choose from, among which TvSum is representative.
  
TvSum dataset contains 50 videos collected from YouTube, spanning across 10 distinct categories(e.g., changing Vehicle Tire (VT), getting Vehicle Unstuck (VU), Grooming an Animal (GA)). Each video is annotated as follows: the video was chopped up into a set of 2 second-long shots and asked 20 users to rate how important each shot is, compared to other shots from the same video, on a scale from 1 (not important) to 5 (very important). 

To solve this problem, we propose a new dataset based on the TvSum dataset as a benchmark dataset for static video summarisation (keyframe-extraction).We selected 2 videos from each category, totalling 20 videos to form the source of our dataset. We constructed simple and efficient keyframe dataset.

# Method
1. We obtain the average of the video's importance ratings across all professionals as the basis for the video's score, and further based on this, we obtain the extremes of the video's score distribution, and we select the video frame corresponding to the midpoint of the extremes as our candidate benchmark video frame.The corresponding situation is shown below.![case](/images/pic.png)  

2. To reduce the occurrence of multiple poles within the same shot but with similar image content, we further perform similarity-based de-redundancy within the shot.

3. Based on the candidate frames after de-redundancy, we manually select them on the basis of this, the purpose of doing so is to avoid the centre frame as a low information frame, we manually select its surrounding frames with better performance to replace it, and finally we get our key frame sequence. The result of one of the videos is shown below:![case](/images/result.jpg)  

# Reference
Song, Yale, Jordi Vallmitjana, Amanda Stent, and Alejandro Jaimes. "TVSum: Summarizing web videos using titles." In Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition, pp. 5179-5187. 2015.

