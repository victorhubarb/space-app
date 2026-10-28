# Space App

A gallery of space photos built with React. You can search by title, filter by tag, mark favorites, and open any photo in a zoom modal.

**Live demo:** [space-app-ten-mocha.vercel.app](https://space-app-ten-mocha.vercel.app)

## What's inside

- **Search and tag filters together.** `App` holds the search text and the selected tag in state, and a `useEffect` recomputes the visible photos from the source list whenever either one changes.
- **Favorites.** Toggling the heart updates the gallery, and also the open modal when the same photo is showing.
- **Zoom modal.** Built on the native `<dialog>` element, with a form that closes it. The expanded view reuses the same `Imagem` component as the gallery.
- **Styled Components.** Each component owns its styles, and a global style file loads the custom font. The page background and the banner are styled with gradients and an image.
- **Static data.** Photos, tags and the "popular" list come from JSON files in `src/`, so there is no backend.

The interface is in Portuguese.

## Stack

React 18, Vite 5, Styled Components 6, deployed on Vercel.

## Run it locally

Requires Node.js 18 or newer.

```bash
git clone https://github.com/victorhubarb/space-app.git
cd space-app
npm install
npm run dev
```

Vite prints the local address, `http://localhost:5173` by default.

## Project structure

```
src/
├── App.jsx            State, filtering and layout
├── componentes/       Cabecalho, BarraLateral, Banner, Galeria (Tags, Imagem, Populares),
│                      ModalZoom, CampoTexto, Rodape, EstilosGlobais
├── fotos.json         The photo list
└── main.jsx
```

## Known gaps

- Favorites are kept in the photo list that `App` builds, and applying a search or tag filter rebuilds that list from the original data, so favorites reset when a filter changes. They also do not survive a reload. Saving them by id in `localStorage` is the fix.
- The layout uses fixed widths (a 1440 px container, 460 px cards), so it is made for desktop and is not responsive.
- The "Ver mais" button under Populares does nothing yet.
- No tests.

---

Victor Hugo Barbosa · [GitHub](https://github.com/victorhubarb) · [LinkedIn](https://www.linkedin.com/in/victorhbarbosa/)
