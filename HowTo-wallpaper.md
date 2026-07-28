* install deps

```shell
sudo apt update
sudo apt install pandoc wkhtmltopdf
sudo apt install fonts-dejavu fonts-noto-core
```

* generate wallpaper for mobile phones
```shell
pandoc quotes.md \
  --from markdown+smart \
  --css style_mobile_1440x3088.css \
  --metadata charset=utf-8 \
  --standalone \
  --metadata title='Bóg jest miłością' \
  -o quotes_mobile_1440x3088.html

wkhtmltoimage \
  --encoding utf-8 \
  --width 1440 \
  --height 3088 \
  --disable-smart-width \
  --quality 89 \
  --enable-local-file-access \
  quotes_mobile_1440x3088.html \
  wallpaper_mobile_1440x3088.jpg
```

* generate wallpaper for laptop
```shell
pandoc quotes.md \
  --from markdown+smart \
  --css style_laptop_1920x1080.css \
  --metadata charset=utf-8 \
  --standalone \
  --metadata title='Bóg jest miłością' \
  -o quotes_laptop_1920x1080.html

wkhtmltoimage \
  --encoding utf-8 \
  --width 1920 \
  --disable-smart-width \
  --quality 89 \
  --enable-local-file-access \
  quotes_laptop_1920x1080.html \
  wallpaper_laptop_1920x1080.jpg
```