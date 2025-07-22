# Audio Transcription
## Introduction
Nowadays, many information using mostly using ways like audios or videos.   
Somehow you might notice that ***if you want to collect information inside these media you'll have to watch or listen for at least once***    
Now we focus on the way we gather information   
Which are read, listen (smell, touch, taste. The five basic sense of human) 
However, without training, a normal people will learn more things by reading instead of listening.  
You can simply make your own test. Prepare the same materials (news, arcticle .etc) then have someone read for you and then read yourself.  
If my point is now you agreed, you'll find out  
***Reading is faster than Listening!***

## Tools for Transcription

### 0. COMMON PROBLEM

CUDA toolkit    
| this allows the transcription program to use GPU accelerate the speed of translation.

torch   
| you need to get torch from official website to avoid the problem that program still can't use GPU.

***Run for at least once !!!***     
| all the program working friendly to you usually need to run for once in order to download the specific working model. Or you will meet a awkward situation "I just installed it. Why can't I use???"

----

### 1. faster whisper   

An easy program provide GUI, but you need to download model yourself and load manually. 

need about 10 GB space  

**PS:** if you're using v3 model, you may not want to run it with long materials. I had failed to translate before because the program will stuck if your computer sleep. Sure you can think a way to keep your computer on. But I thought this is inconvenient

----
### 2. whisper  

Openai whisper model, provide CLI interface, python custom script (yes, you can write your own script to operate whisper with python!). 

Installation is easy and Support is convenient.

need about 10 GB space

PS: whisper only support English output

----
### 3. buzz

Easy using program with GUI, if you don't want to consider too much configuration and installation. This might be your best choice.

need about 10 GB space (my guessing)

PS: I don't get a success translate with this program.

----
### 4. vosk 

### LUCKY FOR POOR HARDWARE !!!

A really ***lite*** and useful program provide CLI interface, python custom script available.

need about less than 2 GB !!

----
# Writing Behind 
Above all are simple introductions.     
More info should consider visiting official website!