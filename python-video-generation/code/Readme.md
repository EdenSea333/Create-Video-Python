# Video Generation with Python

This repository contains the sample code for the blog-post [Video Generation with Python][blogpost-url] using Python’s [MoviePy][moviepy], [SciPy][scipy] and [ImageMagick][imagemagick] libraries. If you are looking for the original sample code that uses Python’s [MoviePy][moviepy] and [Gizeh][gizeh] libraries you can find it in its own [repository][original-sample].


---

## Getting Started

To build and run this sample follow the instructions below to install requirements and set-up your python environment with pipenv.

## Install ImageMagick

ImageMagick is required to run `python_video.py` for creating `Moviepy` [TextClips][txtclip].

You can download the source binaries in the [download page][imagemagick-download] and follow your development environment section to install from source. Otherwise, you can use a system package manager for the desired OS as follows.

To verify ImageMagick installation you can run the following command that will create a gif file.
```bash
$ convert logo: logo.gif
```

### Ubuntu
Your distribution may already have installed ImageMagick. But in case its not, type:
```bash
$ sudo apt install imagemagick
```

### MacOS
Using [Homebrew][homebrew] which provides pre-built binaries for Mac, type:
```bash
$ brew install imagemagick
```
ImageMagick depends on Ghostscript fonts. To install them, type:
```bash
$ brew install ghostscript
```

### Windows
The Windows version of ImageMagick is self-installing. Simply go to the [download page][imagemagick-download] to get a version that will launch itself and ask a few installation questions.

## Install Python 3

### Linux and OSX

Using version manager [asdf-vm][asdf-vm].

##### Install [Python Plugin][asdf-python]:

```bash
$ asdf plugin-add python https://github.com/danhper/asdf-python.git
```

##### Install Python:

Python version is specified in `.tools-versions` file.

```bash
$ asdf install
```

**Note:** This can be installed using package managers as well, the instruction
may vary according to your package manager:

- In Ubuntu:

```bash
sudo apt-get install python3
```

- In OSx:

```bash
brew install python3
```

### Windows

Using package manager [Chocolatey][chocolatey]:

```bash
C:\> choco install python3
```

## Install python package manager

If not installed yet, run from the root of the project to install `pipenv`:

```bash
$ pip install --user pipenv
```
## Install dependencies and generate video

From root project directory run:

```bash
$ pipenv install
```

### Enable your virtual environment

From root project folder, enable virtual env typing:

```bash
pipenv shell
```

### To generate the video

With pipenv virtualenv enabled and from the root project folder run:

```bash
python moviepy_video.py
```

**Note:** It's possible to execute the script directly with `pipenv` using:

```bash
pipenv run python python_video.py
```

### Disable Virtual Environment

To Disable it type `exit`

## Troubleshooting

If you encounter errors when linking `ImageMagick` binaries like in this known [issue 693][issue-693], it does not have the proper permission set.

Check for the ImageMagick policy file at
`/etc/ImageMagick-6/policy.xml` and comment out (or remove the line that reads)

```
<policy domain="path" rights="none" pattern="@*" />
```
```
<!-- <policy domain="path" rights="none" pattern="@*" /> -->
```

[moviepy]: https://zulko.github.io/moviepy/
[scipy]: https://scipy.org/
[imagemagick]: https://imagemagick.org/
[gizeh]: https://github.com/Zulko/Gizeh/
[blogpost-url]: https://www.stackbuilders.com/blog/python-video-generation
[original-sample]: https://github.com/stackbuilders/tutorials/tree/tutorials/tutorials/python/python-video-generation
[txtclip]: https://moviepy-tburrows13.readthedocs.io/en/improve-docs/ref/VideoClip/TextClip.html#textclip
[imagemagick-download]: https://imagemagick.org/script/download.php
[homebrew]: https://brew.sh/
[asdf-vm]: https://asdf-vm.com/#/core-manage-asdf-vm?id=install-asdf-vm
[asdf-python]: https://github.com/danhper/asdf-python
[chocolatey]: https://chocolatey.org/
[issue-693]: https://github.com/Zulko/moviepy/issues/693
