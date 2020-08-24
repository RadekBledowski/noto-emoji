![Noto](images/noto.png)
# Noto Emoji Plus
Color and Black-and-White Noto emoji fonts, and tools for working with them.

## Prerequisites
Building Noto Color Emoji requires:
- Python 3
- [pkg-config](https://www.freedesktop.org/wiki/Software/pkg-config/)
- [pngquant](https://pngquant.org/)
- [zopflipng](https://github.com/google/zopfli)
- [cario.h](https://www.cairographics.org/download/)
- [imagemagick] (https://imagemagick.org/index.php)

## Building NotoColorEmoji
This project uses a virtual environment to manage dependencies. Use the following steps to get up and running:

```shell
# make sure you have the Prerequisites

# create & activate a virtual environment
python3 -m venv venv
source venv/bin/activate

# install python requirements
pip install -r requirements.txt

time make -j
```

Intermediate products (compressed image files, for example) will be put into a build subdirectory; the font will be at the top level.

## Using NotoColorEmoji

NotoColorEmoji uses the CBDT/CBLC color font format, which is supported by Android
and Chrome/Chromium OS.  Windows supports it starting with Windows 10 Anniversary
Update in Chrome and Edge.  On macOS, only Chrome supports it, while on Linux it will
support it with some fontconfig tweaking, see [issue #36](https://github.com/googlei18n/noto-emoji/issues/36). Currently we do not build other color font formats.

## Color emoji assets

The assets provided in the repo are all those used to build the NotoColorEmoji
font.  Note however that NotoColorEmoji often uses the same assets to represent
different character sequences-- notably, most gender-neutral characters or
sequences are represented using assets named after one of the gendered
sequences.  This means that some sequences appear to be missing.  Definitions of
the aliasing used appear in the emoji_aliases.txt file.

Also note that the images in the font might differ from the original assets.  In
particular the flag images in the font are PNG images to which transforms have
been applied to standardize the size and generate the wave and border shadow.  We
do not have SVG versions that reflect these transforms.

## License

Emoji fonts (under the fonts subdirectory) are under the
[SIL Open Font License, version 1.1](fonts/LICENSE).<br/>
Tools and most image resources are under the [Apache license, version 2.0](./LICENSE).
Flag images under third_party/region-flags are in the public domain or
otherwise exempt from copyright ([more info](third_party/region-flags/LICENSE)).

## Contributing

Please read [CONTRIBUTING](CONTRIBUTING.md) if you are thinking of contributing to this project.

