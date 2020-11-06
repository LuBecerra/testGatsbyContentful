# testGatsbyContentful

Instalar nuevo sitio Gatsby (Blog starter) 
gatsby new [SITE_DIRECTORY] https://github.com/gatsbyjs/gatsby-starter-blog
cd [SITE_DIRECTORY]
gatsby develop 

Plugin de conexión a contentful
npm install gatsby-source-contentful

Agregar datos en gatsby-config.js dentro de dependencia de plugins
  (*)accessToken en .env -> instalar desde consola 
     npm install dotenv
     crear archivo .env en root del proyecto
       en .env colocar Content Delivery API Key
       CONTENTFUL_ACCESS_TOKEN=[ACCESS_TOKEN]
       en gatsby-config.js
         // Declare dotenv
         const dotenv = require('dotenv')
         // Check that we are on develop enviroment
         if (process.env.NODE_ENV !== 'production'){
           dotenv.config()
         }

en config-gatsby.js:
{
  resolve: 'gatsby-source-contentful',
  options: {
    spaceId: '[SPACE_ID]'
    accessToken: process.env.CONTENTFUL_ACCESS_TOKEN
  }
}

Probar conexión a datos con Graphql
 (*) npm install gatsby-source-filesystem

gatsby develop
localhost:8000/___graphql
