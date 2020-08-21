## install global npx
`sudo npm install -g npx`

## create new project
`npx create-nuxt-app <project-name>`

## add css loader
`npm install --save-dev pug@2.0.3 pug-plain-loader coffeescript coffee-loader node-sass sass-loader`

## run dev in external IP 
`npm install --save-dev cross-env`
`"dev": "cross-env NUXT_HOST=0.0.0.0 NUXT_PORT=3333 nuxt"`

## Buid
`npm run build`

## Start server
`npm run start`

## Generate static file
`npm run generate`
