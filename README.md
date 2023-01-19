# Autobahn-App
Project Fromscratch by :
Groupe :
- HOCHET Dylan
- MENDEL Quentin
- HEROLD Alexis


## Getting Started

Git clone project with submodules, paste and run the following command :

```bash
git clone --recurse-submodules https://github.com/TP-Full-Stack-Autobahn/Autobahn-App.git
```

1. Install proxy packages service from project
2. Build images and run docker container with Mysql Database
3. Configure symfony API service from project
4. Configure and publish react libray from project
5. Configure front website service from project

### Setup express api proxy service (Autobahn-Proxy)

Go in project folder and run this following command :

#### Install


```bash
  npm run i || install
```


### Setup docker container

Build docker images

```bash
  docker compose build
```

And builds, (re)creates, starts, and attaches to containers for a service with this following command :

```bash
  docker compose up
```

### Setup symfony api service (Autobahn-User)


#### Configuration

- Create .env and complete it

To know :

- hostname : db
- port : 3306
- user/password refer to docker-composer-.yml


#### Install

In service console, run this following commands :

```bash
composer install
```

```bash
php bin/console doctrine:migrations:migrate || symfony doctrine:migrations:migrate
```

```bash
php bin/console doctrine:fixtures:load || symfony doctrine:fixtures:load
```

```bash
php bin/console lexik:jwt:generate-keypair
```


### Setup and publish react library UI (Autobahn-UI)

Go in project folder and run this following command :


#### Install

```bash
npm install || npm i 
```

```bash
npm run build
```

Optionnal (test library in web browser):
```bash
npm run storybook
```


### Build and deploy in local

(Need 'yalc' module in global package)

```bash
npm run yalc:build
```


### Setup front website in local (Autobahn)

Go in project folder and run this following command :

#### Install

```bash
npm install || npm i 
```

Then, install local library :
```bash
yalc link autobahn-ui
```

Finally, start the server :
```bash
npm run dev
```
