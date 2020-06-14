# Project Scan
## capterra.com
Capterra is a infomation provider for rankings of business softwares.
## Demand analysis
We have to find out a way to grasp a scan of the whole market of business software, so we turned to scrapy, a fast and effective scraping toolkit.
## Site analysis
Looking at [start page for scraping](https://www.capterra.com/categories) of capterra.com we find that in this page over 400 categories is shown for software searchers.
Open each link for those categories, we're navigated to a new main page(topic page) of a software type, where info about vendors and products are listed. Go to product pages by clicking links here.
So, scrape from starting_page to topic_page, and to product_page to get info needed.

## Note:
1. Value of fdir in capterra/middlewares.py,line 133, should be modified before scraping:
```python3
fdir=r'/home/debian/Documents/scrapyPrj/capterra/proxyIpList.txt'
```
3. Do not delete the file `proxyIpList.txt`.
4. System requirements:
```json
{
  "linux version":"Linux debian 4.19.0-6-amd64 #1 SMP Debian 4.19.67-2+deb10u2 (2019-11-11) x86_64 GNU/Linux",
  "python version":"Python 3.7.3",
  "python library required":[
    "scrapy",
    "numpy",
    "Faker"]
}
```
5. To start spider-crawling:
```bash
python3 run.py
```
And, the result is three json files,  `capterra.json` is an example.
