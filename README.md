# Public timer.mp4

```bash
ffmpeg -f lavfi -i color=color=white:size=1280x720:rate=10 -vf \
  "drawtext=fontsize=100:fontcolor=black:x=(w-text_w)/2:y=(h-text_h)/2:text='%{eif\:t*10\:d}'" \
  -t 60 timer.mp4
```

This command generates a video with a white background and a timer that increments by 1 every 0.1 seconds. The video duration is 60 seconds, and the timer numbers are displayed prominently in the center of the video.

- `-f lavfi -i color=color=white:size=1280x720:rate=10`: Creates a 1280x720 video with a white background at 10 frames per second (fps).
- `-vf "drawtext=fontsize=100:fontcolor=black:x=(w-text_w)/2:y=(h-text_h)/2:text='%{eif\:t*10\:d}'"`: Uses the drawtext filter to display text. The text is a number that increases by 1 every 0.1 seconds. The text is centered in the video with a font size of 100 and black color.
- `-t 60`: Sets the video duration to 60 seconds.
- `timer.mp4`: The name of the output video file.

By running this command, you will get a 60-second video where the number displayed increases by 1 every 0.1 seconds, resulting in the number "10" appearing exactly at the 1-second mark, "20" at the 2-second mark, and so on until "600" at the 60-second mark.
