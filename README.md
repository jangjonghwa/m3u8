# m3u8
[![Total alerts](https://img.shields.io/lgtm/alerts/g/eagleoflqj/m3u8.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/eagleoflqj/m3u8/alerts/)
[![Language grade: Python](https://img.shields.io/lgtm/grade/python/g/eagleoflqj/m3u8.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/eagleoflqj/m3u8/context:python)
  
a simple tool for downloading and merging video fragments, which may be encrypted, listed in m3u8 file
## environment
* Linux, Windows 10, macOS
* python3 with pip
## install
```sh
git clone https://github.com/eagleoflqj/m3u8
cd m3u8
# read requirements.txt, then it's up to you whether use a virtual environment or not
python3 -m pip install -r requirements.txt
```
## usage
In the directory that contains `scrapy.cfg`.
```bash
scrapy crawl m3u8 -a m3u8='m3u8 file url' [-a merge=...] [-a referer=...]
```
or
```bash
scrapy crawl m3u8 -a page='html page url' [-a merge=...]
```
* Assign anything to `merge` to prevent the spider from merging fragments. This is useful when some head or tail fragments contain ads. Once you remove these .ts files, you can merge video fragments manually:
```bash
python3 m3u8/merge_ts.py 'directory that contains all video fragments'
```
* Only assign STATIC html page that contains m3u8 file URL to `page`. Note that this is not always the case, so you may F12 first to get the m3u8 URL, then set `m3u8` (and `referer` if needed).
