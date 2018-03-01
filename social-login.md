# Social Login

We provide the social login for Facebook, Gmail and LinkedIn. For that we have to provide id, secret key and callback url in the .env file.

## **For Facebook**, register your app [here](https://developers.facebook.com/apps)  then click on settings on sidenav.

* From the basic settings you will be able to    access your `API key` and `API secret`.
* Also, click the Add Platform button below the settings configuration. Select **Website** in the platform dialog then    enter the    website    URL, in our case it is [\( http://demo.joshadmin.com/](http://clean.lorvent.in/~~]%28http://clean.lorvent.in/) \)
* Set the App Domains    to your site url, privacy policy and terms of    service url \([http://demo.joshadmin.com\](http://clean.lorvent.in%29%29\) \) and choose    the category    as Business then save the settings.
* Then Click on App Review tab    -&gt;Choose Yes For Make Your Site Public.
* Now Click the Add Product tab on    settings    from sidenav and add the facebook login.
* Next Click on Facebook Login -&gt;Client    OAuth Settings Section select yes    for all except Use Strict Mode    For Redirect    URLS.    and    Enter Valid OAtuth Redirect URLS\([http://demo.joshadmin.com/facebook/callback/](http://clean.lorvent.in/auth/facebook/callback/) \)choose **yes **for login from devices.
  then save.

**Note: **The values of **FACEBOOK\_ID**, **FACEBOOK\_SECRET** and **FACEBOOK\_URL** should be set in your .env file. The    **FACEBOOK\_URL**     in this case will be \([http://demo.joshadmin.com/facebook/callback \)](http://clean.lorvent.in/auth/facebook/callback~~]%28http://clean.lorvent.in/auth/facebook/callback):

# For Google, Creating a Google API Console project and clientID

Before you can integrate Google Sign-In into your website, you must have a Google API Console project. In the project, you    create a    client ID, which you need to call the sign-in    API.

To create a Google API Console project and client ID, follow    these steps:

* Go to the [Google    API    Console](https://console.developers.google.com/project/_/apiui/apis/library).
* From the project    drop-down, select an existing    [project](https://support.google.com/cloud/answer/6158853) ,    or create a new one by selecting **Create a new project**.
* In the sidebar under "APIs & Services",    select **Credentials**, then select the **OAuth consent screen **tab.

       `a).Choose An Email    Address, specify a Product Name and press save.`

* In the Credentials tab, Select the Create Credentials drop-down list and choose OAuth client ID.

* Under **Application type**, select **Web application**.

  ```
       Register    the origins from which your app is allowed    to access the Google    APIs, as    follows.    An origin is a unique    

    combination    of protocol, hostname, and port.
  ```

* In the **Authorized JavaScript origins** field, enter the origin for your app. You can enter multiple origins to allow for your app    to run on different protocols, domains, or subdomains. You cannot use wildcards. In the example below, the second    URL could be a production URL.

> ```
> http://localhost:8080
>
> https://myproductionurl.example.com
> ```

```
      The Authorised Redirect URI require a value. Press the create button.
```

* From the resulting OAuth client dialog box, copy the client id. The Client Id lets your app access enabled Google APIs.

# For LinkedIn, Please Follow The Steps

To connect your Auth0 app to    LinkedIn, you will need to generate a **Client ID** and **Client Secret **into your Auth0 settings, and enable the connection.

## Log into    the developer portal

Login to    the [LinkedIn Developer portal](https://developer.linkedin.com/)    and    click **My    Apps**:

![](/assets/one.jpeg)

## Create your app

Click the Create Application button.

![](/assets/two.jpeg)

## Complete information about your app

For the Website URL field    enter the following URL:

[https://YOUR\_AUTH0\_DOMAIN](https://YOUR_AUTH0_DOMAIN)    \([http://demo.joshadmin.com](http://clean.dev)\) Then complete all the required fields on the form. Click **Submit**.

![](/assets/three.jpeg)

### Enter Redirect URL

Enter the following URL in the    Authorized Redirect URLs field and click Add:

```
https://YOUR\_AUTH0\_DOMAIN/login/callback    ( http://demo.joshadmin.com/linkedin/callback)
```

Next click on **Update **button.

![](/assets/four.jpeg)

### Get your Client ID and Client Secret

On the same page you will be able to see your **Client ID** and **Client Secret **under the **Authentication Keys** section:

![](/assets/five.jpeg)

## Copy your Client Id and Client Secret into Auth0

Login to    the [Connections    &gt; Social    section of the Auth0 Dashboard](https://manage.auth0.com/#/connections/social).

Select the LinkedIn connection to access its **Settings** page.

Copy the **Client Id **into the **API Key **section and **Client Secret **into the **Secret Key** section.

Enable any desired permissions and attributes then click **SAVE**.

![](/assets/six.jpeg)

## Enable the Connection

Go to the **Apps** tab of the    LinkedIn connection on Auth0 and select each    of your existing Auth0 apps for which you want to enable this connection:

![](/assets/seven.jpeg)

## Test your app

Go back    to the [Connections &gt;    Social](https://manage.auth0.com/#/connections/social) section of the    Auth0 dashboard.

A **TRY **icon will now be displayed next to the LinkedIn logo:

![](/assets/eight.jpeg)

Click **TRY**.

You    will    see    the    LinkedIn Authorize screen, click **Allow**    to finish    creating    the    connection.

![](/assets/nine.jpeg)

If you have configured everything correctly, you will    see    the **It works!!! **page:

![](/assets/ten.jpeg)

## Access LinkedIn API

Once you successfully authenticate a user, LinkedIn includes an    [access token](https://auth0.com/docs/tokens/access-token) in the user profile it returns to Auth0.

You    can    then use this token to call their API.

In order to get a LinkedIn access token, you have to retrieve the full user's profile,    using the Auth0 Management    API,    and    extract    the access token from the response. For detailed steps refer to [Call an Identity Provider API](https://auth0.com/docs/connections/calling-an-external-idp-api).

Once you have the token you can call the API, following    LinkedIn's documentation.

