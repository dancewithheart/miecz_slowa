* install deps
```shell
sudo apt update
sudo apt install pandoc wkhtmltopdf
sudo apt install fonts-dejavu fonts-noto-core
```

* generate wallpaper
```shell
pandoc droga.md -c style.css -o quotes.html
wkhtmltoimage --width 1920 --height 1080 quotes.html wallpaper.png
```


