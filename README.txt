In this repository is a script that 

1) extracts streams from XDF, namely video, audio, balance board and marker stream,
2) write video (avi) and audio (wav) files
3) concatenate audio+video into single file


Seen on the resulting audiovideo files, this session has major problems with synchronization - the video is usually delayed, while audioo seem to be delimited correctly

We have tried
- resampling video on uniform framerate
- check if video does not skip frames
- different writing-video method that does not query frame index
- dejitter xdf file


We have not tried yet
- check if audio has uniform framerate (but it seems it does)

This is problem for some sessions, some are perfectly synchronized (or desync is not perceiveble), and it seems there might be relation between desync and unstable frame rate
Another problem that we might run into is that it seems that the video in the audio-video file is skipping frames so maybe ffmpeg is not ideal method but I do not think it is the
core of the current problem as the video before and after sound look identically

All packages needed to run the scripts are in requirements.txt