#### 1、Android SDK提供了两套音频采集API
 - MediaRecorder：录制的音频文件是经过压缩后的，需要设置编码器。并且录制的音频文件可以用系统自带的Music播放器播放。在用MediaRecorder进行录制音视频    时，最终还是会创建AudioRecord用来与AudioFlinger进行交互。
 - AudioRecord录制的是PCM格式的音频文件，需要用AudioTrack来播放，AudioTrack更接近底层。
