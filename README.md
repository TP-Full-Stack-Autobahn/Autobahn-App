![alt text](https://avatars.githubusercontent.com/u/118977085?s=200&v=4)

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

### What we are going to do (installation summary) :

1. Install and run Docker Desktop
2. Setup express api proxy service (Autobahn-Proxy)
3. Setup symfony api service (Autobahn-User)
4. Setup and publish react library UI (Autobahn-UI)
5. Setup front website and run it in local (Autobahn)

<br>
<br>
<br>

### 1. Install and run Docker Desktop

Go to docker website and install the latest version of Docker Desktop

https://www.docker.com/products/docker-desktop/

At the root of the project :

Setup Docker images

```bash
  docker compose build
```

And builds, (re)creates, starts, and attaches to containers for a service with this following command :

```bash
  docker compose up
```

<br>
<br>
<br>

### 2. Setup express api proxy service (Autobahn-Proxy)

Go in project folder and run this following command :

#### Install

```bash
  npm i
```

<br>
<br>
<br>

### 3. Setup symfony api service (Autobahn-User)

#### Configuration

Modify .env file and complete it the following informations :

- hostname : db
- port : 3306
- user : admin
- password : admin

To modify the database information, refer to the `docker-compose.yml` file

#### Install

To install the user service, go to the user container console. There are two ways to do it :

```bash
docker-compose exec user bash
```

OR with Docker desktop by going to the `Containers` tab, in the `service-user`. Click on the 3 dots (show container actions) and select `Open in terminal`

When you are there, enter the following commands :

```bash
composer i
```

```bash
php bin/console doctrine:migrations:migrate
```

```bash
php bin/console doctrine:fixtures:load
```

```bash
php bin/console lexik:jwt:generate-keypair
```

<br>
<br>
<br>

### 4. Setup and publish react library UI (Autobahn-UI)

Go in project folder and run this following command :

#### Install

```bash
npm i 
```

```bash
npm run build
```

Optionnal (test library in web browser) :

```bash
npm run storybook
```

### Build and deploy in local

Install `yalc` module in global package

```bash
npm i yalc -g
```

```bash
npm run yalc:build
```

<br>
<br>
<br>

### 5. Setup front website and run it in local (Autobahn)

Go in project folder and run this following command :

#### Install

```bash
npm i 
```

Then, install library locally :

```bash
yalc link autobahn-ui
```

Finally, start the server :

```bash
npm run dev
```

Credentials to login as admin :
- id : admin@gmail.com
- password : admin
