# Gridsome Tailwing Tutorial


### 1. Tworzę projekt
```
gridsome create my-gridsome-site
```


### 2. Dodaję Tailwind

1. Instaluję Tailwind
```
npm install tailwindcss
```

2. Instaluję Post CSS
```
npm i -D @fullhuman/postcss-purgecss
```

3. Tworzę *main.css* w */src* a w nim dodaję:
```
@tailwind base;

@tailwind components;

@tailwind utilities;
```

4. Na górze *main.js* dodaję mój nowy css
```
// Import global styles
require('~/main.css')
```

5. Generuję *tailwind.config.js* komendą
```
npx tailwind init
```
Wypełniam *tailwind.config.js* tym:
```
module.exports = {
    theme: {
        extend: {}
    },
    variants: {},
    plugins: []
}
```

6. Następnie do *gridsome.config.js* dodaję tailwind i pureCSS

```
const tailwind = require('tailwindcss')
const purgecss = require('@fullhuman/postcss-purgecss')

const postcssPlugins = [
  tailwind(),
]

if (process.env.NODE_ENV === 'production') postcssPlugins.push(purgecss(require('./purgecss.config.js')))

module.exports = {
    siteName: 'Gridsome',
    plugins: [],
    css: {
        loaderOptions: {
            postcss: {
                plugins: postcssPlugins,
            },
        },
    },
}
```

7. Tworzę w root plik *purgecss.config.js* a wnim :
```
module.exports = {
    content: [
        './src/**/*.vue',
        './src/**/*.js',
        './src/**/*.jsx',
        './src/**/*.html',
        './src/**/*.pug',
        './src/**/*.md',
    ],
    whitelist: [
        'body',
        'html',
        'img',
        'a',
        'g-image',
        'g-image--lazy',
        'g-image--loaded',
    ],
    extractors: [
        {
            extractor: content => content.match(/[A-z0-9-:\\/]+/g),
            extensions: ['vue', 'js', 'jsx', 'md', 'html', 'pug'],
        },
    ],
}
```


### 3. Logo + Card
Robię kartę
*tracking-wider* to letter-spacing
*h-3* to wysokość
*text-sm* pomniejszenie rozmiaru tekstu


### 4. Responsive - drobne zmiany
*max-w-md* maksymalna szerokość diva - bardzo użyteczne
*mx-auto*  wyśrodkuje diva na viewport
*sm:* od sm do xl przejmie zadany parametr, zawsze leci w górę (sm | md | lg | xl)

### 5. Responsive zmiana układu przy zmianie viewport

Aby uzyskać efekt, że zdjęcie i tekst układają się pozimo na lg:  
1. Tworzę div wrapper dla flexa
2. na dole dodaję nowy div ze zdjęciem który będzie widoczny
tylko na lg i ukrywam na lg ten górny div ze zdjęciem.  
*hidden lg:block* ukrywa div na wszystkim oprócz lg


### 6. Hover, Focus Active
Hover i focus dodajemy normalnie. Aby zmienić active dodajemy w *tailwind.config.js* opcję w *variants*:
```
// wymieniam wszystkie, w tej kolejności.
backgroundColor: ['responsive', 'hover', 'focus', 'active'],
```

Żeby nadać wygląd tylko dla jednej rozdzielczości, kombinacja:
```
md:hover:bg-gray-600
```

w *variants* mogę zmieniać też inne parametry: opacity, border, text-color, itp...






