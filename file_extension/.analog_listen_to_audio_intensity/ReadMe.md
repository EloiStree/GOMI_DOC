
By default, this application does not listen to audio from the microphone.

However, many macros could be launched by a sequence of audio signals based on volume intensity.

This file allows you to specify that you need audio from a specific microphone and convert it into a Boolean true/false or analog value in the register to be parsed.


It can only be used while in the application.
If you are looking for code that runs in the background, see the logger at:
https://github.com/EloiStree/2022_04_29_csharp_listen_to_mixer_for_volume



```
## Trigger the boolean value in the register to true if volume of the microphone is over 70%
MicrophoneDeltaPhone♦️0.7♦️1♦️bool:microphone:true


## Trigger the boolean value in the register to false if volume of the microphone is over 70%
MicrophoneDeltaPhone♦️0.0♦️0.7♦️bool:microphone:false
```

