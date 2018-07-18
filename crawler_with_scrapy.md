## Notes on Crawler and how it works

- An spider or crawler in scrapy starts with this simple command:
`scrapy <commands> [spider name] [options] [args]` for example
`scrapy crawl sample_spider -o output.csv`.

- In `settings.py` file in item pipline part we must put diffrent piplines in the order. and set they'er priority by assign a three digit number. order sets from low to high.

- Run crawler with `scrapy crawl somespider -s JOBDIR=crawls/somespider-1` give an ability to spider where it can pause and run again.