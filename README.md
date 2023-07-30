# Coffee Shop

Coffee Shop is an engaging portfolio website powered by Stripe, offering a delightful online shopping experience for coffee enthusiasts, where they can explore and purchase a variety of quality coffee products.

## To run API and client in development:

1. Make sure you are in the project root directory.

2. Install dependencies:
   `npm run install:all`

3. Create `.env` file based on `example.env`, but replace `<bracket values>` with your values.

- Make sure `NODE_ENV` is set to `"development"`
- You can leave `COFFEE_ESHOP_NO_ADMIN_PROD_MEDIA` as an empty string (`""`)
- Use Stripe test key
- Use localhost for `COFFEE_ESHOP_NO_ADMIN_CLIENT_URL`

4. Run:
   `npm run start:all`

## To deploy API for production:

1. Make sure you are in the project root directory.

2. Install dependencies:
   `npm run install:api`

3. Set variables on your server based on `example.env` with your own production variables, e.g., in the default `~/.bashrc` or your custom `~/.bashrc.d` directory.

- Make sure `NODE_ENV` is set to `"production"`
- Rename the default `COFFEE_ESHOP_NO_ADMIN_MONGO_URL="mongodb://localhost:27017/coffeeEshopHardcodedDev"`.
- Set `COFFEE_ESHOP_NO_ADMIN_PROD_MEDIA` to an absolute path of media directory on your server.
- Use Stripe production key
- Use production URL for `COFFEE_ESHOP_NO_ADMIN_CLIENT_URL`

4. Navigate to the project's root directory.

5. Rename and move the `api` directory to a desired location, e.g. `mv ./api ~/apis/coffee-eshop-hardcoded-api`.

6. Start the API using PM2: `NODE_ENV=production pm2 start YOUR_API_DIRECTORY/server.js --name YOUR_PM2_APP_NAME`, e.g. `NODE_ENV=production pm2 start ./coffee-eshop-hardcoded-api/server.js --name coffee-eshop-hardcoded-api`.

## To deploy client for production:

1. Make sure you are in the project root directory.

2. Install dependencies:
   `npm run install:client`

3. Navigate to `client` subdirectory using the command `cd ./client`.

4. To set the homepage, use the command `json -I -f package.json -e "this.homepage=\"<YourHomepageHere>\""`. If the website is located in the root location, you can set it as the current directory with `json -I -f package.json -e "this.homepage=\".\""`. For websites in sublocations, specify the full URL like `json -I -f package.json -e "this.homepage=\"https://example.com/apps/coffee-eshop\""`.

5. Build with these react environment variables, e.g.:
   `REACT_APP_API_URL="https://example.com/api" REACT_APP_MEDIA_URL="https://example.com/media" npm run build`.

6. After the previously ran build command, you can rename and move the resulting `client/build` directory to a desired location (e.g., somewhere in `/usr/share/nginx`).
