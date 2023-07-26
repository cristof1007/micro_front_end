# micro_front_end

Util:
single-spa Inspector
https://chrome.google.com/webstore/detail/single-spa-inspector/emldbibkihanfiaiaghebffnbahjcgcp/related

Steps:

npm install create-single-spa

npx create-single-spa
1: single-spa root config
    ? Directory for new project baseapp
    ? Select type to generate single-spa root config
    ? Which package manager do you want to use? npm
    ? Will this project use Typescript? Yes
    ? Would you like to use single-spa Layout Engine Yes
    ? Organization name (can use letters, numbers, dash or underscore) mfe-base
    
    npm install
    npm start

2: single-spa application / parcel
    ? Directory for new project mfe-react
    ? Select type to generate single-spa application / parcel
    ? Which framework do you want to use? react
    ? Which package manager do you want to use? npm
    ? Will this project use Typescript? Yes
    ? Organization name (can use letters, numbers, dash or underscore) mfe
    ? Project name (can use letters, numbers, dash or underscore) mfe-react-proyect

    npm install
    npm start

2.1 Para react en index.js del root imports agregar las librerias de react

    "react": "https://unpkg.com/react@17/umd/react.development.js",
    "react-dom" : "https://unpkg.com/react-dom@17/umd/react-dom.development.js",

3 single-spa application / parcel
    $ npx create-single-spa
    ? Directory for new project mfe-vue
    ? Select type to generate single-spa application / parcel
    ? Which framework do you want to use? vue
    ? Organization name (can use letters, numbers, dash or underscore) mfe

    npm install
    npm run serve

3.1 configurar el vue para que no utilice su empaquetador (transquilador), y definimos un empaquetador valido
Para esto, se comenta su trasnquilador por defecto que esta en la raiz/vue.config.js

    module.exports = {
        configureWebpack : {
            output: {
            libraryTarget : 'system'
            },
        },
    }

4 single-spa application / parcel = angular
    ? Directory for new project mfe-angular
    ? Select type to generate single-spa application / parcel
    ? Which framework do you want to use? angular
    ? Project name (can use letters, numbers, dash or underscore) mfe
    ? Would you like to add Angular routing? Yes
    ? Which stylesheet format would you like to use? Sass 

    The package single-spa-angular@8.1.0 will be installed and executed.
    Would you like to proceed? Yes
    ? Does your application use Angular routing? Yes
    ? What port should your project run on? 4200

    Project setup complete!
    Steps to test your Angular single-spa application:
    1. Run 'npm run serve:single-spa:mfe'
    2. Go to http://single-spa-playground.org/playground/instant-test?name=mfe&url=%2F%2Flocalhost%3A4200%2Fmain.js&framework=angular to see it working!

    npm install
    npm start

4.1 en index poner cualquier nombre al componente
    !importante: colocar el localhost:puerto/main.js
    "@mfe/mfe-angular": "//localhost:4200/main.js"