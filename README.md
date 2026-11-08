# Collie theme starter

A ready-made theme file for ColliePWA, to copy and change into your own.

The file is `collie-theme.json`. It is a theme called Petal, soft and round, and it wears the Kawaii character. It has a light half and a dark half. It uses every part of a theme file: colours, two typefaces, the shape words, a terminal palette and a character. Edit the parts you want to change and delete the parts you do not.

A second example sits in `themes/`: Fleece, which wears the Sheep character. Keep it, change it, or delete the folder.

A theme changes how the app looks and nothing else. It holds colours and a few words. It cannot run code, load a file or reach a server.

## Make your own

1. Click **Use this template** on GitHub, or clone this repository.
2. Open `collie-theme.json`. Change `id`, `name` and `author` first. The `id` must be unique. It uses lower-case letters, digits and hyphens, and it may not be the id of a theme that Collie ships (`collie`, `nightwatch`, `daylight` or `harbour`).
3. Change the colours in `light` and `dark`. Change the words in `surface`, the typefaces in `fonts`, and the `character`.
4. Check the file:

   ```sh
   collie theme check collie-theme.json themes/*.collie-theme.json
   ```

   Exit code 0 means the file passes. Exit code 1 means a rule is broken, and the check prints each cause. A contrast warning means some text is hard to read in one place. Fix it by changing the colour.

A token you leave out takes the value of the default theme, so a short file is a good file. Give both halves when you change the page colours.

The full reference lists every token, every word and every rule: https://colliepwa.dev/docs/themes

## Pick a character

A character is the figure in the header of the app. Its beads circle it, and they turn fast while an agent works. Petal picks Kawaii, and Fleece picks Sheep:

```json
"character": "kawaii"
```

The key takes one of these words. Collie may add more later.

| Word | Character |
| --- | --- |
| `collie` | Collie, the collie head in profile, in the ink of the page. The default. |
| `kawaii` | Kawaii, a round puppy face from the front, with big glossy eyes and candy pearls. |
| `kawaii-tilt` | Kawaii Tilt, the same puppy with its head tilted. |
| `pixel` | Pixel, an 8-bit collie head with square beads that hop. |
| `glass` | Glass, a collie head in profile as a leaded stained-glass panel, with jewels in the ring. |
| `glass-front` | Glass Front, the same stained glass, the head from the front. |
| `sheep` | Sheep, the sheep the collie herds: a charcoal face in cream wool, in profile. |
| `owl` | Owl, the owl that watches through the night, from the front, with huge amber eyes. |

- A file that sets `character` says `"version": 4`. Leave the key out and the header shows Collie.
- A version 4 file needs a Collie that knows characters. An older Collie refuses the whole file. To reach older Collies too, leave `character` out and say version 3.
- Each phone can pick its own character in **Settings → Appearance → Character**. That choice wins over the theme, unless it is **From the theme**.
- The app icon and the splash stay Collie under every theme.

## Try it in Collie

1. Open **Settings**, then **Appearance**. The **Theme** card is under the **Character** card.
2. Tap **Import** and choose your file. Or tap **Paste**, paste the text of the file, and tap **Read**.
3. Read the preview. It shows both halves, the shape, the terminal colours and a contrast report.
4. Tap **Try** to wear the theme for a while, or **Apply** to keep it.

Collie does not fetch a theme from a link. To use a theme from a link, open it, copy the text and paste it.

## Share it

1. Put your file at the root of a public GitHub repository, named `collie-theme.json`.
2. In the **About** box of the repository page, add the topic `colliepwa-theme`.
3. The site looks for tagged repositories once a day. It checks every theme file with the same check as the app, and it reads the name, the description and this README. A repository that passes shows up on https://colliepwa.dev/themes.

One repository can hold several themes. Put each one in `themes/`, with its id in the name. This repository does both: Petal at the root and Fleece in `themes/`, so the site lists two themes. Delete the one you do not want.

```text
themes/
  my-day.collie-theme.json
  my-night.collie-theme.json
```

The `author` field of a file is the credit the site shows.

Replace this README with a short note about your own theme. Say what it looks like and who it is for.

## Let an agent write it

Tell your coding agent to run:

```sh
collie theme --skill
```

It prints the steps and every key a theme file may use. It also tells the agent to run `collie theme check` on the result.

## Licence

MIT. See `LICENSE`.
