Node.js (REST API) + Vue.js/Nuxt.js (Frontend/Backend) + MySQL Boilerplate
This is a boilerplate project. The project contains Node.js REST API and frontend/backend developed by Vue.js with BootstrapVue.

API
Node.js, Express, Webpack, Express Validator, JWT, Bunyan, Promise MySQL, Node Mailer, Jest, Supertest, Nodemon
Frontend - Nuxt.js
Nuxt.js, Vue.js, Vuex, Vuelidate, BootstrapVue, Jest
Frontend - Vue.js
Vue.js, Vuex, Vue Router, Vue Draggable, Vuelidate, BootstrapVue, Jest, Cypress
Backend
Vue.js, Vuex, Vue Router, Vuelidate, BootstrapVue, Jest, Cypress
Demo
Service	Endpoint
API	https://nvm-boilerplate.chrislee.kr/api/
Frontend - Nuxt.js	https://nvm-boilerplate.chrislee.kr/frontend-nuxt/
Frontend - Vue.js	https://nvm-boilerplate.chrislee.kr/frontend-vue/
Backend	https://nvm-boilerplate.chrislee.kr/backend/
Mailhog	https://nvm-boilerplate.chrislee.kr/mailhog/                   
How to start in your local environment
$ docker-compose up -d
Once docker containers are up, then you can access services with below URL.

Service	Endpoint
API	http://localhost/api
Frontend - Nuxt.js	http://localhost/frontend-nuxt
Frontend - Vue.js	http://localhost/frontend-vue
Backend	http://localhost/backend
Mailhog	http://localhost/mailhog
MySQL	localhost:3307
There are three users in the database initially. You can use them to login Frontend/Backend.

Service	Username	Email	Password
Backend	admin	admin@boilerplate.local	123456
Backend	staff	staff@boilerplate.local	123456
Frontend	user	user@boilerplate.local	123456
API
API docker container will be launched as development mode with nodemon. However, it won't detect any changes unless uncomment volumes.

To enable live change for the API, simply uncomment following lines in docker-compose.yml

  volumes:
    - ./api:/srv
Please make sure you run npm install in the api folder.

Frontend & Backend
Currently, Frontend (Nuxt.js/Vue.js) and Backend docker container is configured to serve production mode due to the limitation of setting development environment of Vue.js in sub directory.

If you want to have Hot Reload feature, then you should launch the Frontend separately by npm run serve.

cd frontend-vue
npm run serve

# or

cd frontend-nuxt
npm run dev

# or

cd backend
npm run serve
Then access Frontend - Nuxt.js with http://localhost:3000, Frontend - Vue.js with http://localhost:8080 and Backend with http://localhost:8081 via your browser.

Mailhog
Currently, API is configured to point Mailhog to send an email. Any email sent by the API can be viewed in Mailhog web interface.

Access via your browser http://localhost/mailhog

MySQL
In the folder mysql/sql, there is a SQL file called inital.sql, which will become initial database table/rows. MySQL port is mapped to 3307.

Features
Frontend - Vue.js

User registration
Confirm user email address
Reset user password
User login/logout
Manage todo
Manage account information
Frontend - Nuxt.js

Support all features that "Frontend - Vue.js"
Server Side Render (SSR)
Backend

Staff login/logout
Staff permission management
List todo
Manage users
Manage staffs
Manage settings
CI/CD

Gitlab: .gitlab-ci.yml
Github: .github/workflows/main.yml
