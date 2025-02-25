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
- Only train once a day
- Train once certain number of new videos added

### Recommending videos

Very fast model, with recommendations displaying almost immediately. The only thing that takes a while is training the database - likely greatly accelerated by GPU however, haven't tested yet.

Something especially helpful about this Python library is that the user's inputs can be updated and their data recalculated without needing to retrain the entire model. It's probably best to send an update of the user interactions every 3-5 videos or so to ensure the model remains accurate for each user.
