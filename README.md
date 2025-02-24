# nothofagus algorithm

## Idea

Initially wanted to use TikTok's open source algorithm, but after delving throught their repo it seems they've intentionally made it almost impossible to reuse thanks to their confusing and incomplete READMEs. So, I've decided to instead create my own algorithm. How hard could that be...

## Features

- **open-source:** this repo will remain open-source and public
- **customisable:** users will be able to literally fine-tune their own algorithms using controls built into the nothofagus website
- **simple:** this algorithm will remain simple for now as my main specialty is software, NOT machine learning (however, contributions are welcome!). It will use the [Implicit](https://benfred.github.io/implicit/index.html) package, and process user likes, views, time watched and reports to create an engagement score for each user interaction with a video, and then use all user interactions to suggest new videos.

## Architecture

### When to train?

- Could wait for notification that external metadata database has been updated
- Could send GET requests periodically, only get new data if timestamp updated

### Recommending videos

Very fast model, with recommendations displaying almost immediately. The only thing that takes a while is training the database - likely greatly accelerated by GPU however, haven't tested yet.
