# Base16 Solarized Scheme

A more accurate [Solarized][] color scheme for [Base16][].

TODO: screenshots

## Usage

TODO: usage

## Rationale

The official "solarized" scheme [arzg/base16-solarized-scheme][arzg] does not faithfully represent Ethan Schoonover's theme. For example, the website [clearly shows][usage] the dark theme using base0 (`#839496`) for body text, but arzg's repository uses base1 (`#93a1a1`). This repository fixes this and other issues.

It's very easy to get confused because both Base16 and Solarized use 16 colors with similar names:

- Base16 uses eight monotones (base00 through base07) and eight accents (base08 through base0F).

- Solarized uses eight monotones (base03, base02, base01, base00, base0, base1, base2, base3) and eight acccents (yellow, orange, red, magenta, violet, blue, cyan, green).

> **Note**: In the following, I use "emphasized" to mean brighter in dark themes, darker in light themes; and "de-emphasized" to mean the opposite.

Here are the eight Solarized monotones and their [intended uses][usage]:

| Base | Dark                  | Light                 |
| ---: | --------------------- | --------------------- |
|   03 | background            | inverse background    |
|   02 | emphasized background |                       |
|   01 | comments              | emphasized text       |
|   00 |                       | text                  |
|    0 | text                  |                       |
|    1 | emphasized text       | comments              |
|    2 |                       | emphasized background |
|    3 | inverse background    | background            |

And here are the eight Base16 monotones and their [intended uses][styling]:

| Base | Meaning               |
| ---: | --------------------- |
|   00 | background            |
|   01 | emphasized background |
|   02 | selection background  |
|   03 | comments              |
|   04 | de-emphasized text    |
|   05 | text                  |
|   06 | emphasized text       |
|   07 | inverse background    |

In [arzg/base16-solarized-scheme][arzg], the monotones are mapped like this:

| Base16 | Base16 meaning        | Sol. Dark | Sol. Light | Solarized meaning     |
| -----: | --------------------- | --------: | ---------: | --------------------- |
|     00 | background            |        03 |          3 | background            |
|     01 | emphasized background |        02 |          2 | emphasized background |
|     02 | selection background  |        01 |          1 | comments              |
|     03 | comments              |        00 |          0 |                       |
|     04 | de-emphasized text    |         0 |         00 | text                  |
|     05 | text                  |         1 |         01 | emphasized text       |
|     06 | emphasized text       |         2 |         02 |                       |
|     07 | inverse background    |         3 |         03 | inverse background    |

While this is a nice one-to-one mapping, it has problems. The color it uses for regular text is actually intended by Solarized for emphasized text; and for emphasized text, it uses a harsh shade not intended for text at all. This mapping effectively increases the theme's contrast.

This repository instead maps the monotones like this:

| Base16 | Base16 meaning        | Sol. Dark | Sol. Light | Solarized meaning     |
| -----: | --------------------- | --------: | ---------: | --------------------- |
|     00 | background            |        03 |          3 | background            |
|     01 | emphasized background |        02 |          2 | emphasized background |
|     02 | selection background  |        02 |          2 | emphasized background |
|     03 | comments              |        01 |          1 | comments              |
|     04 | de-emphasized text    |        00 |          0 |                       |
|     05 | text                  |         0 |         00 | text                  |
|     06 | emphasized text       |         1 |         01 | emphasized text       |
|     07 | inverse background    |         3 |         03 | inverse background    |

This accurately matches up the monotones by their intended meaning in each framework, at the cost of using the same color for Base16's base01 and base02 (since Solarized lacks a shade in between "emphasized background" and "comments").


[Solarized]: https://ethanschoonover.com/solarized/
[usage]: https://ethanschoonover.com/solarized#usage-development
[Base16]: https://github.com/chriskempson/base16
[styling]: https://github.com/chriskempson/base16/blob/master/styling.md
[arzg]: https://github.com/arzg/base16-solarized-scheme
