### Install laravel

Create a new Laravel project inside a `tmp` folder

```bash
docker-compose run --rm backend composer create-project --prefer-dist laravel/laravel tmp "8.*"
```

Move files to `backend` working directory and remove tmp folder

```bash
docker-compose run --rm backend sh -c "mv -n tmp/.* ./ && mv tmp/* ./ && rm -Rf tmp"
```

Update `.env` with the database configuration. Mind `DB_HOST`. it should equal `mysql` instead of 127.0.0.1


### Install Vite

Create a new Vite project

```bash
docker-compose run --rm frontend sh -c "npm init @vitejs/app tmp"
```

Move files to `frontend` working directory and remove tmp folder

```bash
docker-compose run --rm frontend sh -c "mv -n tmp/.* ./ && mv tmp/* ./ && rm -Rf tmp"
```

Install dependencies

```bash
docker-compose run --rm frontend sh -c "npm install"
```