### Spark Installation

#### 1\) Installation of spark :

Initially, you need  to Install the Laravel Spark, For the installation of Laravel spark, Please follow the official guide, the link for which is provided below

[https://spark.laravel.com/docs/4.0/installation](https://spark.laravel.com/docs/4.0/installation). 

#### 2\) Applying the Josh skin:

After completing the installation of laravel spark, follow the below steps to apply the josh skin

1. Remove node modules by running the following commands in your project root folder `rm -rf node_modules`
2. Extract the  files from the provided zip file.
3. copy all the files into your spark installation folder/directory.
4. Run `yarn install`
5. Run `npm run dev` or `npm run production` or `npm run watch` as per your requirement.
6. once, all the above steps are performed you will get a new look for your default spark website.

#### Note:

Eventhough you can run `npm install` we suggest  you to run `yarn install` since the package contains `yarn.lock` file which lets you get the exact version of packages that we have used.

currently,  we are providing support for spark version ** v4.0.8 **
