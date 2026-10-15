# Geologic Time taught by Star Wars

Earth's 4 billion years of rock history laid along the running time of *The Empire Strikes Back*. The first rocks form at 0:00:00, the credits roll at present day, and each station on the timeline shows a moment in the history of life next to the scene playing at that point in the film. Modern humans show up one second before the credits.

Live version: https://ethandavidmagalei.com/starwars/

I made it for EPS 4 at Stanford. I did the math (in Desmos), chose the events and wrote the text.

## How it works

- `data/timeline.json` holds the explainer and the 16 stations. Each station has a geologic time (`geo`), a film timestamp (`film`), a title, and a body. `pos` places it on the track at the bottom, which is to scale: a station's distance from the left edge is its share of geologic time.
- `index.html` is the whole page: a starfield drawn on a canvas, a card for each station, arrows (or ← →, or a swipe) to travel between stations, and the scale track. `#s=5` in the address opens station 5.
- Blank lines in a body are paragraph breaks, and `[words](https://…)` is a link.

To change the timeline, edit `data/timeline.json`. A station can also take `"video": "<YouTube id>"` or `"images": [{ "src": "…", "alt": "…", "caption": "…" }]`.

## Running it

It's a static page with no build step. From this folder:

```
python3 -m http.server 8000
```

then open http://localhost:8000. (Opening `index.html` straight from disk won't load the JSON in most browsers.)

## Photos

The live version has photos at some stations. They aren't mine (they come from Sci.news, Lucasfilm and Phys.org), so they aren't in this repository.

## License

The code is MIT (see `LICENSE`). The text in `data/timeline.json` is © Ethan David Magalei, CC BY 4.0. *Star Wars* and *The Empire Strikes Back* belong to Lucasfilm; this project isn't affiliated with them and uses none of the films' logos, art or music.
