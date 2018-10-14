#### 1、Android SDK提供了两套音频采集API
 - MediaRecorder：可以直接把手机麦克风录入的音频数据进行编码压缩（如AMR、MP3等）并存成文件，需要设置编码器。并且录制的音频文件可以用系统自带的Music播放器播放。在用MediaRecorder进行录制音视频时，最终还是会创建AudioRecord用来与AudioFlinger进行交互。  
 
 - AudioRecord：录制的是PCM格式的音频文件，需要用AudioTrack来播放，AudioTrack更接近底层。
#### 2、Android SDK 提供了3套音频播放的API
 - SoundPool：SoundPool 则适合播放比较短的音频片段，比如游戏声音、按键声、铃声片段等等，它可以同时播放多个音频。
 
    由于SoundPool对载入声音文件大小有所限制，这就导致了如果SoundPool没有载入完成，而不能安全调用play方法。好在Android SDK提供了一个SoundPool.OnLoadCompleteListener类来帮助我们了解声音文件是否载入完成。
    
 - MediaPlayer：而 AudioTrack 则更接近底层，提供了非常强大的控制能力，支持低延迟播放，适合流媒体和VoIP语音电话等场景。
 
 - AudioTrack：使用AudioTrack播放的音频必须是解码后的PCM数据。
 
 - MediaExtractor：对容器文件进行读取控制，将音频和视频的数据进行分离，内部方法均为native方法。
 
 - MediaCodec：对数据进行编解码，负责媒体文件的编码和解码工作，内部方法均为native方法。
 
 - MediaMuxer：生成音频或视频文件；还可以把音频与视频混合成一个音视频文件。
