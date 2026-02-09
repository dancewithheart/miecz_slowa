* install deps

```shell
sudo apt update
sudo apt install pandoc wkhtmltopdf
sudo apt install fonts-dejavu fonts-noto-core
```

* generate wallpaper
```shell
pandoc quotes.md \
  --from markdown+smart \
  --css style.css \
  --metadata charset=utf-8 \
  --standalone \
  --metadata title='Miecz Slowa' \
  -o quotes.html

wkhtmltoimage \
--encoding utf-8 \
--width 1920 \
--height 1080 \
--quality 89 \
--enable-local-file-access \
quotes.html \
miecz_slowa.jpg
```
