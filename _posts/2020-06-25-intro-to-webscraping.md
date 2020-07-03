---
layout: post
title: "How to solve a problem like a data scientist (Webscraping demo)"
comments: true
description: "An introduction to webscraping and the data science process"
keywords: "websraping, text mining, wordclouds"
categories: blog
---

*Note: This post is adapted from from a presentation I gave in the summer of 2019 for the Legal Services Corporation. Every intern had to give a presentation and I chose to show a tutorial of an awesome skill I had learned that summer, webscraping!*

## Who am I?

- Joanna Schroeder, ODGA Intern
- Study Government and Public Health
- Started my data journey 1 year ago!
  - GIS for Social Science
  - Data Science and Politics
  - LSC Intern!

## What is this?

- slidy presentation feat. code
- goal: teach something fun!
- DON'T GET LOST IN THE SAUCE

## We have a problem

https://www.lsc.gov/what-legal-aid/client-success-stories

## Plan of action

1. Get the stories from the website into a text format we can work with (Webscraping)
2. Clean the messy text and analyze it (Natural Language Processing)
3. Visualize it (Wordcloud-ing)

## Step 1: Webscraping

```{r webscraping, include = TRUE, echo = TRUE, warning = FALSE, class.source = 'jumbotron', font.family = 'Calibri'}
# Navigate to Client Stories Page and extract all the links
page <- read_html("https://www.lsc.gov/what-legal-aid/client-success-stories") %>% html_nodes("a") %>% html_attr('href')

# Take only the links for client stories (not any on the header or footer)
urls <- page[68:185] %>% unique()
urls <- paste0("https://lsc.gov", urls)

# Write a function to scrape only the text of the client story from each link
scrape <- function(x) {
  story <- read_html(x)
  stories <- html_nodes(story, "div.field.field-name-body.field-type-text-with-summary.field-label-hidden.view-mode-full") %>% html_text()
}

# Apply the function to all links
stories <- lapply (urls, scrape)

# Let's look at the first story
print(head(stories, 1))
```

## Step 2: Natural Language Processing

```{r NLP, include = TRUE, echo = TRUE, warning = FALSE, class.source = 'jumbotron', font.family = 'Calibri'}
# Remove punctuation, numbers, and uppercase letters from stories
corpus <- Corpus(VectorSource(stories)) %>% tm_map(removePunctuation) %>% tm_map(removeNumbers) %>% tm_map(tolower)

# Remove stopwords and strip whitespace
corpus <- tm_map(corpus, removeWords, stopwords("english"))
corpus <- tm_map(corpus, stripWhitespace)

# Calculate the frequency of each word in the client stories
dtm <- DocumentTermMatrix(corpus)

# Let's look at the least frequent words
frequency <- sort(colSums(as.matrix(dtm)), decreasing=TRUE)
tail(frequency, 10)
```

## Step 3.1: Visualization

```{r wordcloud, echo=TRUE, fig.height=10, fig.width=10, warning=FALSE, include=TRUE, class.source = 'jumbotron'}
# Create a wordcloud of the words by frequency
wordcloud(names(frequency), frequency, max.words = 50)
```
<img src="/assets/images/bw-wordcloud.png" alt="bw wordcloud" style="height:140px;">
## Step 3.2: If you want to get crazy

``` {r wordloud color, echo=TRUE, fig.height=10, fig.width=10, warning=FALSE, include=TRUE, class.source = 'jumbotron', font.family = 'Calibri'}
# Create a prettier wordcloud
layout(matrix(c(1, 2), nrow=2), heights=c(1, 4))
par(mar=rep(0, 4))
plot.new()
text(x=0.5, y=0.5, "Client Stories Frequency Wordcloud")
wordcloud(names(frequency), frequency,
          min.freq = 1,
          max.words = 250,
          random.order = FALSE,
          rot.per = 0.30,
          main = "Title",
          colors = brewer.pal(8, "Dark2"))
```
<img src="/assets/images/color_wordcloud.png" alt="color wordcloud" style="height:140px;">

## Key takeaways

- I solved a problem like a data scientist!
- Maybe I'll try it again sometime
