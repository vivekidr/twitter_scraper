# twitter_scraper
About This is a Twitter Scraper which uses Selenium for scraping tweets. It is capable of scraping tweets from home, user profile, hashtag, query or search.

## Setup

1. Install dependencies

```bash
pip install -r requirements.txt
```

## Authentication Options

### Using Environment Variable

1. Rename `.env.example` to `.env`.

2. Open `.env` and update environment variables

```bash
TWITTER_USERNAME=# Your Twitter Handle (e.g. @username)
TWITTER_USERNAME=# Your Twitter Username
TWITTER_PASSWORD=# Your Twitter Password
```

### Authentication in Terminal

- Add a `username` and `password` to the command line.

```bash
python scraper --user=@elonmusk --password=password123
```

### No Authentication Provided

- If you didn't specify a username and password, the program will
  ask you to enter a username and password.

```bash
Twitter Username: @username
Password: password123
```

---

**_Authentication Sequence Priority_**

```bash
1. Authentication provided in terminal.
2. Authentication provided in environment variables.
```

---

## Usage

- Show Help

```bash
python scraper --help
```

- Basic usage

```bash
python scraper
```

- Setting maximum number of tweets. defaults to `50`.

```bash
python scraper --tweets=500   # Scrape 500 Tweets
```

- Options and Arguments

```bash
usage: python scraper [option] ... [arg] ...

authentication options  description
--user                  : Your twitter account Handle.
                          e.g.
                          --user=@username

--password              : Your twitter account password.
                          e.g.
                          --password=password123

options:                description
-t, --tweets            : Number of tweets to scrape (default: 50).
                          e.g.
                            -t 500
                            --tweets=500

-u, --username          : Twitter username.
                          Scrape tweets from a user's profile.
                          e.g.
                            -u elonmusk
                            --username=@elonmusk

-ht, --hashtag          : Twitter hashtag.
                          Scrape tweets from a hashtag.
                          e.g.
                            -ht javascript
                            --hashtag=javascript

-q, --query             : Twitter query or search.
                          Scrape tweets from a query or search.
                          e.g.
                            -q "Philippine Marites"
                            --query="Jak Roberto anti selos"

-a, --add               : Additional data to scrape and
                          save in the .csv file.

                          values:
                          pd - poster's followers and following

                          e.g.
                            -a "pd"
                            --add="pd"

                          NOTE: Values must be separated by commas.

--latest                : Twitter latest tweets (default: True).
                          Note: Only for hashtag-based
                          and query-based scraping.
                          usage:
                            python scraper -t 500 -ht=python --latest

--top                   : Twitter top tweets (default: False).
                          Note: Only for hashtag-based
                          and query-based scraping.
                          usage:
                            python scraper -t 500 -ht=python --top

-ntl, --no_tweets_limit : Set no limit to the number of tweets to scrape
                          (will scrap until no more tweets are available).
```
