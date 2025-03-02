Merge multiple videos
```bash
ffmpeg
-i "vid1.mp4"
-i "vid2.mp4"
-i "vid3.mp4"
-filter_complex "[0:v] [0:a] [1:v] [1:a] [2:v] [2:a]
[3:v] [3:a]
concat=n=4:v=1:a=1 [v] [a]" -map "[v]" -map "[a]" -c:v libx264 -preset veryfast -c:a aac -strict experimental -r 25 part.mp4
```
