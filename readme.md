# Get up and running
Clone repository, install and build
```
git clone https://github.com/klementj/directus.git
pnpm install
pnpm build
```

1. add .env file to /api. Use env.example
```
cp api/.env.example api/.env
```

2. run postgress DB from docker 
```
docker compose up postgress -d
```

3. Initialize database
```
pnpm --filter api cli bootstrap
```

4. Run api
```
pnpm --filter api dev
```

5. In another terminal run the app
```
pnpm --filter app dev
```

## Start developing an extension

1. Change directory to appropriate extension category. If developing an interfaces
```
cd api/extensions/interfaces
```
2. Create extensions
```
npx create-directus-extension@latest
```
Follow the guide to create extension

3. Go into `package.json` and change output of the scripts dev option to
```
"dev": "directus-extension build --type interface --input src/index.js --output index.js --watch --no-minify ",
```

Directus will look for plugin in the root of extensions directory. So we change output from dist/index.js to index.

4. Go and check that directus can see the extension


## To Do
* Setup global development database
