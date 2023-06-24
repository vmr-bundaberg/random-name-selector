# Random Name Selector

This is installed as:
* https://www.vmrbundabergfishingclassic.com.au/juniors.html
* https://www.vmrbundabergfishingclassic.com.au/seniors.html

This makes it easier for non-technical users to utilise by opening one tab for seniors and one for juniors.

## Build Instructions

This project is built using Vite + Vue 3 + TypeScript template. You can run this project by executing these commands.

```bash
npm install # Install dependencies

vite build # Production build (more reliable)

npm run dev # For development
npm run build # For production build (as per original developer)

```

MacOS installation:

```bash
brew install npm vite
```

Debian installation:

```bash
apt install npm; npm install vite
```

## Installation Instructions

Copy `dist/index.html` to both `juniors.html` and `seniors.html` (the same code can be used for both).

Copy the contents of `dist/assets` to the `assets` directory in the website.

**Note:** The file names include checksums and so change. You should delete the old versions when updating.
