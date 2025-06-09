# Hola Adri

Homepage for the browser with custom bookmarks made with Vue and Tailwind.

It has keyboard shortcuts: left and right arrows for navigating between the two views and numbers to navigate through the sections.

Made by [Adri.info](https://adri.info)

## Screenshots

Home
![Home](screenshots/home.png 'Home')

Work
![Work](screenshots/work.png 'Work')

## Customize

### Data

Two data files in `/src/data` with fields `title`, `url`, `img`:

- `homeData.js`: contains 'press', 'tv', 'podcasts', 'games', 'music'
- `workData.js` contains 'front', 'back', 'others', 'youtube', 'courses', 'tools'

### Colors

Replace hex colors in `base.css`, :

```
  --background: #ffffff;
  --primary: #2f343f;
  --primary-light: #868ea1;
  --primary-opposite: #d0cbc0;
  --secondary: #d3d3d3;
```

### Images

3 .ai files in `/src/illustrator`:

- `restricted.ai` for centered square logos
- `withbg.ai` for rectangle logos with bg
- `youtube.ai` for small logos with full image

Images must be saved in `/src/assets/logos/avif/` with _.avif_ format

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Compile and Minify for Production

```sh
npm run build
```
