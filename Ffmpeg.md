# FFMPEG
## 連番画像から動画を作る
```
ffmpeg -r 30 -i output%03d.png -vcodec libx264 -pix_fmt yuv420p -r 60 out.mp4
```

## 2つの動画を横に並べる
```
 ffmpeg -i left.avi -i right.mp4 -filter_complex hstack outfile.avi
 ```
 縦に並べる場合はvstack？

## Gifを倍速する
純粋に倍速にするとなぜか色がおかしくなる．   
  
``` 
//gifをmp4に変換  
ffmpeg -i input.gif  -movflags faststart -pix_fmt yuv420p -vf "scale=trunc(iw/2)*2:trunc(ih/2)*2" output.mp4  

//倍速にする  
ffmpeg -i output.mp4 -vf setpts=PTS/10.0 -af atempo=10.0 -q 0 output_10.mp4  

//mp4からgifへ変換するのに必要な画像情報を出力する  
ffmpeg -i output_10.mp4 -vf "palettegen" -y palette.png  

//mp4からgifへ変換する  
ffmpeg -i output_10.mp4 -i palette.png -lavfi fps=12,scale=900:-1:flags=lanczos [x]; [x][1:v] "paletteuse=dither=bayer:bayer_scale=5:diff_mode=rectangle" -y output.gif
```
