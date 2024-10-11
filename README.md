## Disable throttling in order to speedup backup
`sudo sysctl debug.lowpri_throttle_enabled=0`
### Re-enable:
`sudo sysctl debug.lowpri_throttle_enabled=1`

## FFMPEG Scripts
### Add mask to video (from Pi)
`ffmpeg -i video.mp4 -i mask.png -filter_complex "[1:v]scale=1920:1080,format=rgba[resize]; [0:v][resize]overlay=(main_w-overlay_w)/2:(main_h-overlay_h)/2:format=rgb" -c:a copy output.mp4`
### Change framerate of video
`ffmpeg -i input.mp4 -filter:v fps=25 output.mp4`

## Git
### gitignore
* Ignore images and videos `printf '*.jpg\n*.jpeg\n*.png\n*.gif\n*.mov\n*.mp4\n*.svg\n' >> .gitignore`

* DS_Store `printf 'DS_Store\n' >> .gitignore`

### cannot push to github problem
`git config http.postBuffer 524288000`
