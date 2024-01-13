 **# Deployment Instructions**

**This README outlines the steps required to deploy a Laravel project to shared hosting.**

**## 1. Edit .env File**

1. Open the `.env` file in your project's root directory.
2. Modify the following variables:

   ```
   DB_CONNECTION=mysql
   APP_NAME=appname
   APP_ENV=production
   APP_KEY=base64key (replace with your actual base64 key)
   APP_DEBUG=false
   APP_URL=https://domain.com (replace with your domain)
   DB_HOST=localhost
   DB_PORT=3306
   DB_DATABASE=dbname
   DB_USERNAME=dbuser
   DB_PASSWORD=dbuserpass
   ```

**## 2. Run Artisan Commands**

1. Open your terminal or command prompt.
2. Navigate to your project's root directory.
3. Run the following commands:

   ```bash
   php artisan key:generate
   php artisan config:cache
   php artisan config:clear
   php artisan route:cache
   php artisan serve
   ```

**## 3. Create Zip File**

1. Compress your entire project folder, including subfolders and files, into a zip archive.
2. Export your database as an `.sql` file.

**## 4. Upload Files to Hosting**

1. Access your shared hosting control panel (cPanel or DirectAdmin).
2. Upload both the zip file and the `.sql` file to your hosting account.

**## 5. Check PHP Version**

1. Ensure that the PHP version on your hosting server matches the PHP version used in your local development environment.

**## 6. Move index.php**

1. Move the `index.php` file from the `public` folder to the project's root directory.

**## 7. Modify index.php**

1. Open the `index.php` file in the project's root directory.
2. Remove the `/..` from the following lines:

   ```php
   require __DIR__.'/../vendor/autoload.php';
   $app = require_once __DIR__.'/../bootstrap/app.php';
   ```

**## 8. Move .htaccess**

1. Move the `.htaccess` file from the `public` folder to the project's root directory.

**## 9. Update Domain (if necessary)**

1. If you changed the domain in step 1, update the domain in the `.htaccess` file as well.

**## 10. Remove "/public" in Views**

1. In your Blade templates, remove any references to `/public` in paths to assets (e.g., images, CSS, JavaScript).

**## Additional Notes**

- Specific instructions may vary slightly depending on your hosting provider's control panel.
- If you encounter issues, consult your hosting provider's documentation or support.
