# Scenescoop

Scenescoop is a tool to get similar semantic scenes from a pair of videos. Basically, you input a video and get a scene that has a similar meaning in another video.

This project is inspired by [Thingscoop](https://github.com/agermanidis/thingscoop) made by [@agermanidis](https://github.com/agermanidis).

![description](static/imgs/img.png)

## How it works

Scenescoop uses the [im2text](https://github.com/tensorflow/models/tree/master/research/im2txt) tensorflow model on a frame by frame basis over the input and transfer video. It then uses [Spacy](https://spacy.io/) to  average the word vectors in a sentence and [Annoy](https://github.com/spotify/annoy) to create an index for fast nearest-neighbor lookup. (based on [@aparrish](https://github.com/aparrish) [Plot to poem](https://github.com/aparrish/plot-to-poem/blob/master/plot-to-poem.ipynb))

## Usage

Get the pretrained model from [here](https://drive.google.com/open?id=1tSTzD21qXXOiXlfgJllgXNZ9lREy6yij).

You can run Scenescoop in two ways:

1) Get frames and run model over video
```
python scenescoop.py --video videos/moonrisekingdom.mp4 --name moonrisekingdom
```

2) Transform a video
```
python scenescoop.py --input_data transcripts/street.json --input_seconds 0,5 --transform_src videos/her.avi --transform_data transcripts/her.json
```

## Web App

![description](static/imgs/demo.gif)

To run the app:
```
python server.py
```

To develop:
```
cd static
yarn watch
```

## Mobile App

Soon

## License

MIT