# Laravel|PHP|MySQL workflow in Docker

- **Repository:**
	- A docker-compose workflow for local Laravel development.
- **Stack:** Laravel, PHP, MySQL.
- **Services:** Nginx, MySQL, NPM.
- **Year:** 2020.

A pretty simplified docker-compose workflow that sets up a LEMP network of containers for local Laravel development.

## Step 1. Clone the repository.

Browse your projects location and run:

```bash
git clone https://github.com/diegoulloao/laravel-docker-startpoint.git project-name
```

## Step 2. Add Laravel files.

First add your entire Laravel project to the `src` folder or browse in and run:

```
laravel new
```

## Step 3. Run the service.

Run:

```
docker-compose up --build
```

Open up your browser of choice to [http://localhost:8080](http://localhost:8080) and you should see your Laravel app running as intended. **Your Laravel app needs to be in the src directory first before bringing the containers up, otherwise the artisan container will not build, as it's missing the appropriate file.**

---

**New:** Three new containers have been added that handle Composer, NPM, and Artisan commands without having to have these platforms installed on your local computer. Use the following command templates from your project root, modifiying them to fit your particular use case:

- `docker-compose run --rm composer update`
- `docker-compose run --rm npm run dev`
- `docker-compose run --rm artisan migrate`

Containers created and their ports (if used) are as follows:

- **nginx** - `:8080`
- **mysql** - `:3306`
- **php** - `:9000`
- **npm**
- **composer**
- **artisan**

**DB_HOST** must be **Gateway IP** from the mysql container. You can get it by running `docker inspect`.

--

Forked from https://github.com/aschmelyun/docker-compose-laravel

**@aschmelyun · @diegoulloao · 2020**
