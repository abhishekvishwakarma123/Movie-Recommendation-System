# Movix

Movix is a movie and TV discovery app built with React and Vite. Browse trending, popular, and top-rated titles, search the catalog, explore movies or TV shows by genre, and open a detail page with cast, videos, similar titles, and recommendations.

Catalog data and artwork are provided by [The Movie Database (TMDB)](https://www.themoviedb.org/).

## Features

- Home page with trending, popular, and top-rated titles
- Search for movies and TV shows
- Explore titles by media type
- Genre labels and rating indicators
- Detail pages with cast, trailers/videos, similar titles, and recommendations
- Responsive layout with lazy-loaded artwork
- Client-side routing with React Router
- Shared application state with Redux Toolkit

## Technology

- React 18
- Vite 4
- React Router
- Redux Toolkit and React Redux
- Axios
- Sass/SCSS
- TMDB API
- Auth0 React SDK wrapper

## Requirements

- Node.js 18 or later
- npm
- A TMDB API Read Access Token

## Getting Started

1. Install dependencies:

	```bash
	npm install
	```

2. Create a `.env` file in the project root and add your TMDB Read Access Token:

	```env
	VITE_APP_TMDB_TOKEN=your_tmdb_read_access_token
	```

	Do not commit `.env` or share your token publicly. Vite exposes variables prefixed with `VITE_` to browser code, so use a TMDB read-only token intended for client-side use.

3. Start the development server:

	```bash
	npm run dev
	```

4. Open the local URL printed by Vite, usually `http://localhost:5173/`.

## Available Scripts

| Command | Description |
| --- | --- |
| `npm run dev` | Start the Vite development server |
| `npm run build` | Create a production build in `dist/` |
| `npm run preview` | Preview the production build locally |

## Application Routes

| Route | Page |
| --- | --- |
| `/` | Home and featured title lists |
| `/movie/:id` | Movie details |
| `/tv/:id` | TV show details |
| `/search/:query` | Search results |
| `/explore/:mediaType` | Explore movies or TV shows |
| `*` | Not found page |

## Project Structure

```text
movierecomendation-main/
|-- index.html                 # Vite HTML entry point
|-- logic.txt                  # Project notes
|-- package.json               # Scripts and dependencies
|-- package-lock.json          # Locked npm dependency versions
|-- vite.config.js             # Vite configuration
|-- .gitignore                 # Ignored files, including .env and node_modules
|-- public/
|   `-- movix-logo.png         # Public logo asset
`-- src/
	 |-- App.jsx                # App routes and initial TMDB data loading
	 |-- App.css                # App-level styles
	 |-- index.scss             # Global styles
	 |-- mixins.scss            # Shared Sass mixins
	 |-- main.jsx               # React, Redux, and Auth0 entry point
	 |-- assets/
	 |   |-- avatar.png
	 |   |-- logo5.png
	 |   |-- no-poster.png
	 |   `-- no-results.png
	 |-- components/
	 |   |-- carousel/          # Horizontal content carousel
	 |   |-- circleRating/      # Rating indicator
	 |   |-- contentWrapper/    # Shared content layout wrapper
	 |   |-- footer/            # Site footer
	 |   |-- genres/            # Genre labels
	 |   |-- header/            # Navigation and search
	 |   |-- lazyLoadImage/     # Lazy-loaded image component
	 |   |-- movieCard/         # Movie and TV item card
	 |   |-- spinner/           # Loading indicator
	 |   |-- switchTabs/        # Tab switcher
	 |   `-- videoPopup/        # Video player popup
	 |-- hooks/
	 |   `-- useFetch.jsx       # Data-fetching hook
	 |-- pages/
	 |   |-- 404/               # Not found page
	 |   |-- details/           # Movie and TV detail page
	 |   |   |-- carousels/     # Similar titles and recommendations
	 |   |   |-- cast/          # Cast list
	 |   |   |-- detailsBanner/ # Main detail banner
	 |   |   `-- videosSection/ # Videos and trailers
	 |   |-- explore/           # Browse by media type
	 |   |-- home/              # Home page
	 |   |   |-- heroBanner/    # Featured title banner
	 |   |   |-- popular/       # Popular titles
	 |   |   |-- recommend/     # Recommendation section
	 |   |   |-- topRated/      # Top-rated titles
	 |   |   `-- trending/      # Trending titles
	 |   `-- searchResult/      # Search results page
	 |-- store/
	 |   |-- homeSlice.js       # Home data and API configuration state
	 |   `-- store.js           # Redux store
	 `-- utils/
		  `-- api.js             # TMDB API client
```

## Configuration Notes

- The TMDB token is read from `VITE_APP_TMDB_TOKEN` in `src/utils/api.js`.
- Auth0 is currently wrapped around the app in `src/main.jsx`. The Auth0 domain and client ID are configured there; replace them with your own Auth0 application settings when using a different tenant.
- `.env` is excluded by `.gitignore` and should remain local.

## Build

Create and preview a production build:

```bash
npm run build
npm run preview
```
