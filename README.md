# Description
A dataset for keyframe extraction
# Background
We use the video summary public benchmark dataset TvSum as a basis, the TvSum dataset is composed of 10 categories of videos, each with a shot-level importance score by 20 professionals, and we select 2 videos in each category for a total of 20 videos.
# Method
1. We obtain the average of the video's importance ratings across all professionals as the basis for the video's score, and further based on this, we obtain the extremes of the video's score distribution, and we select the video frame corresponding to the midpoint of the extremes as our candidate benchmark video frame.

2. To reduce the occurrence of multiple poles within the same shot but with similar image content, we further perform similarity-based de-redundancy within the shot.The final composition of our benchmark dataset.

# case
![case](/images/case.png)  
# Reference
Song, Yale, Jordi Vallmitjana, Amanda Stent, and Alejandro Jaimes. "TVSum: Summarizing web videos using titles." In Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition, pp. 5179-5187. 2015.

