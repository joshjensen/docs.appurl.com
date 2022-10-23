## Official AppURL API

### About

The AppURL API gives you access to the engine powering our Smart URLs. We have built a powerful, easy-to-use tool that will make it unbelievably fast to create smart URLs at scale.

Our API is based on the latest microservice architecture. As a result, we can handle URL generation requests at scale. If you have any questions please don't hesitate to contact us at support@appurl.io

The AppURL API requires an API key / access token. To get your access token, visit [AppURL API Access](https://appurl.io/j2ME7Zna0n).

### Javascript

We have a convenient API wrapper if you use Javascript for your project. You can find it here [NPM](https://www.npmjs.com/package/appurl)

### Usage:

Remember, an API key provided by AppURL is required. To get your access token check out [AppURL API Access](https://appurl.io/j2ME7Zna0n).

**Example:**

```
curl --location --request POST 'https://api.appurl.io/share' \
--header 'Content-Type: application/json' \
--header 'x-api-key: API-TOKEN' \
--data-raw '{
    "props": {
      "appName": "Google",
      "fallbackUrl": "https://google.com",
    }
  }'
```

## Additional Features

Because the AppURL API is protected by an API key, which you are responsible for, we are able to offer more access.

### Image Upload

The AppURL API also accept image uploads. This allows for very specific control of how your link preview looks when shared across a variety of mobile devices and apps.

To use the image upload you must BASE64 encode your image, then pass that string as image property. Here is an example.

**Example:**

```
curl --location --request POST 'https://api.appurl.io/share' \
--header 'Content-Type: application/json' \
--header 'x-api-key: API-TOKEN' \
--data-raw '{
    "image": "iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAQAAAC1HAwCAAAAC0lEQVR42mNk+A8AAQUBAScY42YAAAAASUVORK5CYII=",
    "props": {
      "appName": "Test App Name",
      "fallbackUrl": "https://google.com",
    }
  }'
```

The code above will upload the image at set it as your preview image. This is extremely handy for sharing.

### Optional Properties

Optional properties are one more way you have complete control over your AppURL. The third optional argument of the shorten function is an object containing a very specific list of settings for your AppURL allowing you to control every aspect of it's functionality.

**Properties**

```
    'appName'
    'fallbackUrl'
    'iosIphoneAppUrl'
    'iosIphoneFallbackUrl'
    'iosIpadFallbackUrl'
    'iosIpadAppUrl'
    'androidAppPackage'
    'androidAppScheme'
    'androidFallbackUrl'
    'windowsPhoneAppUrl'
    'windowsPhoneFallbackUrl'
    'blackberryFallbackUrl'
    'clickSendUsername'
    'clickSendApiKey'
    'googleAnalyticId'
    'ogDescription'
    'ogImageUrl'
```

This example would upload the custom preview image and set the redirect landing page title to "My App" and the share preview description to "This is my amazing app!".

**Example:**

```
curl --location --request POST 'https://api.appurl.io/share' \
--header 'Content-Type: application/json' \
--header 'x-api-key: API-TOKEN' \
--data-raw '{
    "image": "iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAQAAAC1HAwCAAAAC0lEQVR42mNk+A8AAQUBAScY42YAAAAASUVORK5CYII=",
    "props": {
      "appName": "Test App Name",
      "fallbackUrl": "https://google.com",
      "ogDescription": "Test app description"
    }
  }'
```

## Contact us

We are proud of the products we are making! If you have any questions please don't hesitate to reach out to [AppURL Support](mailto:support@appurl.io).
