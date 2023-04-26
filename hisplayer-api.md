# HISPlayer API

## Public API
The following public APIs are provided by **HISPlayerManager**.

* **enum class HISPlayerStatus**: The different status in which the stream can be settled:
  * **NONE**
  * **CLOSE**: The stream is closed.
  * **STOP**: The content is stopped.
  * **PLAY**: The content is playing.
  * **PAUSE**: The content is paused.

* **struct FHISPlayerPlaybackProperties**: Use these properties to change the playback’s behavior from the editor.
  * **bool bAutoplay**: The content will automatically play after buffering is complete.
  * **bool bLooping**: The content will automatically loop after it ends.
  * **bool bMute**: The content audio will be muted.

* **public class UDelegateManager**: Use this delegate to receive the different HISPlayer events.
  * **OnLoading**: The content starts loading.
  * **OnPlay**: The content starts playing.
  * **OnPause**: The content pauses.
  * **OnStop**: The content stops.
  * **OnEndContent**: The content ends.
  * **OnBuffering (float percentage)**: The content is buffering. 
    * **Param1**: The current percentage of the buffering process.
  * **OnStatusChanged**: The HISPlayer Status has changed.
  * **OnTrackChanged**: The track of the stream has changed. 
  * **OnError**: The track of the stream has changed. 
  * **OnTimedMetadata**: A new metadata element from the stream has been received.
<p align="center">
<img src="./images/blueprint-example.png">
</p>

* **struct FHISPlayerTimedMetadata**: The different ID3 metadata types that the player can receive.
  * **TimeStamp** 
  * **Title** 
  * **Album** 
  * **Date**
  * **Genre**
  * **Artist**
  * **Track Number**
  * **Session Info**
  * **Year**
  * **Lyric**
  * **Private Frame**
  * **Comment**
  * **Text**

## Functions
Use the following UFunctions in your blueprint or script to make your custom HISPlayer implementation.

#### static void BeginPlay() // HISPlayer BeginPlay
Pre-initialize HISPlayer. You must call this function on BeginPlay before the SetUp.

#### static void Setup(UObject* WorldContextObject, UTexture2D*& outputTexture, struct FLatentActionInfo LatentInfo) // HISPlayer Setup
Initialize HISPlayer. It creates a texture in runtime internally.

#### static void SetPlayBackProperties (const FHISPlayerPlaybackProperties& Properties) // HISPlayer Set PlayBack Properties
Set the playback properties.

#### static FHISPlayerPlaybackProperties& GetPlaybackProperties() // HISPlayer Set PlayBack Properties
Get the current playback properties.

#### static int OpenPlayer(const FString& url) // HISPlayer Open Player
Start HISplayer. A valid URL must be passed as parameter.

#### static void Update() // HISPlayer Update
Update each frame, needs to be called every frame.

#### static void Resume() // HISPlayer Resume
Update each frame, needs to be called every frame.

#### static void Pause() // HISPlayer Pause
Pause the video.

#### static void Stop() // HISPlayer Stop
Stop the video and, next time it's played, it will begin from start.

#### static void Close() // HISPlayer Close
Must be called for closing and releasing HISPlayer. 

#### static void Seek() // HISPlayer Seek
This method seeks the playback position exactly to a specific time.

#### static HISPlayerStatus GetPlayerStatus() // HISPlayer Get Player Status
Get the current player status.

#### static bool SetLooping(bool looping) // HISPlayer Set Looping
Enable or disable looping.
  * **Param1**: Whether the looping should be enabled or disabled.
  * **Return**: True on success, False otherwise.

#### static bool SetMute(bool mute) // HISPlayer Set Mute
Mute or Unmute audio playback.
  * **Param1**: True for muting, False for unmuting.
  * **Return**: True on success, False otherwise.

#### static UDelegateManager* Getdelegatemanager() // HISPlayer Get Delegate Manager
Get the Delegate Manager.

#### static FString GetExpirationDate() // HISPlayer Get Expiration Date
Get the Expiration Date.
  * **Return**: Expiration date in String format.
