# Ai-ML-Assignment-1-Lip-sync
In these i used a Pre-Trained model that is required and i loaded my sample data as input audio and input video that needed to create lipsync and loaded to result video.
# Highlights
lip-sync videos to any target speech with great accuracy
training code and inference code is available to train a model
# Prerequisites
Python 3.6
ffmpeg: sudo apt-get install ffmpeg
# Getting the weights
Model               Description            
Wav2Lip             - Highly accurate lip-sync
Wav2Lip + GAN        - Slightly inferior lip-sync,but better visual quality
# Lip-syncing videos using the pre-trained models (Inference)
You can lip-sync any video to any audio:
python inference.py --checkpoint_path <ckpt> --face <video.mp4> --audio <an-audio-source> 
The result is saved (by default) in results/result_voice.mp4. You can specify it as an argument, similar to several other available options. The audio source can be any file supported by FFMPEG containing audio data: *.wav, *.mp3 or even a video file, from which the code will automatically extract the audio.
# Setup Wav2Lip
#@title <h1>Step1: Setup Wav2Lip</h1>
#@markdown * Install dependency
#@markdown * Download pretrained model
-It sets up the Wav2Lip environment in an environment . This code performs several tasks, including installing dependencies, downloading pretrained models, and configuring audio recording capabilities
# Upload input_video.mp4 & input_audio.wav files
to upload the files input_video.mp4 and input_audio.wav. These files are likely to be used as inputs for the Wav2Lip setup .
# Create Wav2Lip video (using wav2lip_gan.pth) GAN
 #@title 2.Create Wav2Lip video (using wav2lip_gan.pth) GAN
!cd /content/Wav2Lip && python inference.py --checkpoint_path checkpoints/wav2lip_gan.pth --face "/content/sample_data/input_video.mp4" --audio "/content/sa
running the Wav2Lip inference script to create a lip-synced video using the pretrained GAN model.
# Play result video - 50% scaling
The code that is provided is attempting to read a video file and display it as an embedded video .
# Use resize_factor to reduce the video resolution, as there is a change you might get better results for lower resolution videos.
!cd Wav2Lip && python inference.py --checkpoint_path checkpoints/wav2lip_gan.pth --face "/content/sample_data/input_video.mp4" --audio "/content/sample_data/input_audio.wav" --resize_factor 2
- code run the Wav2Lip inference script with the specified parameters to generate a lip-synced video. If the script completed successfully, you will now have a result video.
 # Use more padding to include the chin region
 !cd Wav2Lip && python inference.py --checkpoint_path checkpoints/wav2lip_gan.pth --face "/content/sample_data/input_video.mp4" --audio "/content/sample_data/input_audio.wav" --pads 0 20 0 0
 
 -it run the Wav2Lip inference script again with some additional parameters, specifically the --pads parameter. The --pads parameter is used to specify padding values for the input video frame. In your command, you've set it to 0 20 0 0.
These values likely represent padding values for the top, right, bottom, and left sides of the video frame, respectively. These values can be adjusted to control the positioning of the synthesized lip movements on the video frame.
If the script completed successfully, you can use the previously provided code to display the resulting lip-synced video 
