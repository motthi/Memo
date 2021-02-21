# FFMPEG
## 連番画像から動画を作る
```
ffmpeg -r 30 -i output%03d.png -vcodec libx264 -pix_fmt yuv420p -r 60 out.mp4
```

## 2つの動画を横に並べる
```
 ffmpeg -i left.avi -i right.mp4 -filter_complex hstack -r 60 -q 0outfile.avi
 ```
 縦に並べる場合はvstack？
 
 ## クロップ（領域を指定して切り取り)
 ```
 ffmpeg -i input.mp4 -vf crop=440:440:100:40 -r 60 -q 0 output.mp4
 ```
 crop=出力幅:出力高:切取開始点（X軸）:切取開始点（Y軸）

## Gifを倍速する
純粋に倍速にするとなぜか色がおかしくなる．   
  
``` 
//gifをmp4に変換  
ffmpeg -i input.gif  -movflags faststart -pix_fmt yuv420p -vf "scale=trunc(iw/2)*2:trunc(ih/2)*2" -r 60 output.mp4  

//倍速にする  
ffmpeg -i output.mp4 -vf setpts=PTS/10.0 -af atempo=10.0 -q 0 -r 60 output_10.mp4  

//mp4からgifへ変換するのに必要な画像情報を出力する  
ffmpeg -i output_10.mp4 -vf "palettegen" -y palette.png  

//mp4からgifへ変換する  
ffmpeg -i output_10.mp4 -i palette.png -lavfi "fps=12,scale=400:-1:flags=lanczos [x]; [x][1:v] paletteuse=dither=bayer:bayer_scale=5:diff_mode=rectangle" -r 60 -y output.gif
```
