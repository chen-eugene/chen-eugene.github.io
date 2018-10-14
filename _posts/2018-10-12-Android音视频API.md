#### 1、Android SDK提供了两套音频采集API
 - MediaRecorder：可以直接把手机麦克风录入的音频数据进行编码压缩（如AMR、MP3等）并存成文件，需要设置编码器。并且录制的音频文件可以用系统自带的Music播放器播放。在用MediaRecorder进行录制音视频    时，最终还是会创建AudioRecord用来与AudioFlinger进行交互。
 - AudioRecord录制的是PCM格式的音频文件，需要用AudioTrack来播放，AudioTrack更接近底层。
#### 2、Android SDK 提供了3套音频播放的API
 - SoundPool：适合短促且对反应速度比较高的情况(游戏音效或按键声等)。
 
    由于SoundPool对载入声音文件大小有所限制，这就导致了如果SoundPool没有载入完成，而不能安全调用play方法。好在Android SDK提供了一个SoundPool.OnLoadCompleteListener类来帮助我们了解声音文件是否载入完成。
    
 - MediaPlayer：适合比较长且时间要求不高的情况。
 
 - AudioTrack：播放解码后的PCM码流。
 
 - MediaExtractor
 
 - MediaCodec
 
 - MediaMuxer
