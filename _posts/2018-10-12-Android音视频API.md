### 音视频基础知识

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

#### 3、常见的音频编码格式。
 - PCM：模拟音频信号经模数转换（A/D变换）直接形成的二进制序列，该文件没有附加的文件头和文件结束标志。
 
 - Wav：采用RIFF（Resource Interchange File Format）文件格式结构。通常用来保存PCM格式的原始音频数据，所以通常被称为无损音频。但是严格意义上来讲，WAV也可以存储其它压缩格式的音频数据。
 
 #### 4、常见的视频编码格式。
 - H.264：也称作MPEG-4AVC(Advanced Video Codec，高级视频编码)，是一种视频压缩标准，同时也是一种被广泛使用的高精度视频的录制、压缩和发布格式。H.264因其是蓝光光盘的一种编解码标准而着名，所有蓝光播放器都必须能解码H.264。H.264相较于以前的编码标准有着一些新特性，如多参考帧的运动补偿、变块尺寸运动补偿、帧内预测编码等，通过利用这些新特性，H.264比其他编码标准有着更高的视频质量和更低的码率。
 - H.265：是新的编码协议，也即是H.264的升级版。
 - G.711：
 - G.726：G.726是ITU-T定义的音频编码算法。
 
#### 5、音视频协议。
 - RTMP协议：RTMP（the Real-time Messaging Protocol）协议作为客户端和服务器端的传输协议，这是一个专门为高效传输视频、音频和数据而设计的 TCP/IP 协议。
 - HLS协议： HTTP Live Streaming（HLS）是苹果公司(Apple Inc.)实现的基于HTTP的流媒体传输协议。
 - 视频码率：是视频数据（视频色彩量、亮度量、像素量）每秒输出的位数。一般用的单位是kbps。
