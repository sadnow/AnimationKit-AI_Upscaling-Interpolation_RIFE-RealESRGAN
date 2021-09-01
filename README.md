# AnimationKit - AI Upscaling & Interpolation using Real-ESRGAN+RIFE

*Early Alpha Google Colab Notebook*

Features Real-ESRGAN upscaling, RIFE interpolation/motion smoothing, and FFMPEG x265 

Credits: Motion smoothing conceived from "Zoom animation processing and motion interpolation" added by https://twitter.com/unltd_dream_co. This part of the script uses [RIFE real-time video interpolation](https://github.com/hzwer/arXiv2020-RIFE) to smooth out the resulting video. 

Upscaling uses Real-ESRGAN (https://github.com/xinntao/Real-ESRGAN). A demo notebook for static images can be found here: https://colab.research.google.com/drive/1k2Zod6kSHEvraybHl50Lys0LerhyTMCo?usp=sharing. The demo was based on the following paper: of our paper [''Real-ESRGAN: Training Real-World Blind Super-Resolution with Pure Synthetic Data''](https://arxiv.org/abs/2107.10833).

<img src="https://raw.githubusercontent.com/xinntao/Real-ESRGAN/master/assets/teaser.jpg" width="100%">

#Alpha 1 release: All major bugs have (hopefully) been patched. New functions will be released in the testing branch until debugged.

Feature additions & bugfixes:

- :white_check_mark: Anime model for realesrgan
- :white_check_mark: 2x model
- :white_check_mark: target output path
- :white_check_mark: omission of outscaling (note, may need to check defaults in inference.py)
- :white_check_mark: target fps no longer causes duplicates prior to ffmpeg end-phase (prevents upscaler from wasting gpu cycles on duplicate frames; major speed increase)
- :white_check_mark: notebook set to high memory - necessary for RIFE

---

Planned additions:
- [ ] DEFLICKERING. Good for claymations, stop motions, and of course VQGAN+CLIP animations. Will likely use ffmpeg filters to start
- [ ] Deflicker options (am and pm deflicker flags may be optimal)
- [ ] --skip option for RIFE
- [ ] --tiles option for RIFE/Real-ESRGAN (?)
- [ ] better documentation for exp setting (it's mysterious)
- [ ] face detection for real-esrgan
- [ ] h264 option (for people with older rigs)
- [ ] Preview video option for people who don't want to download the full video yet

---

Difficulties (may take longer to figure out)
- [ ] target output path for RIFE
- [ ] target duration for RIFE (need to understand how exp works, then I'll just have it divide)

Feel free to report bugs!


