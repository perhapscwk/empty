# sbs scrapy spider

- This Script try to fetch all australia news from sbs.com.au and save the data to MongoDB Atlas(MongoDB Cloud).
- By default, it will try to crawl 2000 news, however you can change the setting by modify variable COUNT_MAX = 0 in sbs_spider.py to get all.

# Public API on Amazon EC2 instance

- You can access to the data in the mongo database via public API on Amazon EC2 instance
- http://ec2-18-217-163-233.us-east-2.compute.amazonaws.com/sbs/
- the server will reboot 3am (sydney time) everyday, so this api will have around 1 min downtime at that time
- currently there are 1877 records on mongo database, as I clear the db and force stopped the script after i completed this project

API Usage: To fetch 10 news 

- http://ec2-18-217-163-233.us-east-2.compute.amazonaws.com/sbs/news/10
- to fetch 50 news, just change 10 to 50
- to avoid api to fetch all when user have a typo by typing /abc/ instead of /10/, the api will still only fetch 10 records

API Usage: To fetch 12 news with keyword 'australia' in news heading(title) or in news article text(articleText)

- http://ec2-18-217-163-233.us-east-2.compute.amazonaws.com/sbs/news/12/australia
- please note keyword is case insensitive

### Preparation

- Prerequisites
  - Python 3.x

## Installation

`$ git clone https://github.com/perhapscwk/xxxx/`

 Python Modules required
 - Scrapy 2.5
 - pymongo 3.12
 
```
`$ pip install Scrapy`
`$ pip install "pymongo[srv]"`
```
  - other libs in ```requirements.txt```, run ```pip install -r requirements.txt```.

## Execution

Open up your shell and type	`scrapy crawl sbs`

## Testing

Open up your shell and type	`python -m tests.test_sbs_spider`

