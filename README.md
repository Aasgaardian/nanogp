# nanogp

Access Google Photos from nanogallery2.

Since february 9, 2017, Google Photos can no more be accessed without account owner's explicit authorization.
Permanent authorization is only possible for server side applications.

nanoGP is a PHP application which delivers Google Photos content to nanogallery2 on your web pages.


## Pre-requisites:
Web server with PHP version > 5.2


## Installation
- Create a folder named `nanogp` on your web server.
- Copy the content of the `dist` folder in this folder.

## Configuration
Settings are defined in `admin/config.php`:

```
  $cfg_client_id = 'yyy';
  $cfg_client_secret = 'zzz';
  $cfg_application_name = 'nanogallery2gp';
```
`cfg_client_id` and `cfg_client_secret` can be obtained from the Google developers console.

## Enable Google API
Create and configure a new projet.

1. Open page: https://console.developers.google.com
2. Create a new project named `nanogallery2gp`
<img src="img/google_api_console1.jpg?raw=true" alt="step 1" style="max-width:400px;"/>
  
<img src="img/google_api_console2.jpg?raw=true" alt="step 2" style="max-width:400px;"/>

3. Create a consent screen
Select your email address
Define the "product namaeshown to user": "nanogallery2gp"
Others fields are optional
<img src="img/google_api_console3.jpg?raw=true" alt="step 3" style="max-width:400px;"/>
  
4. Create a `credential` kind `OAuth Client ID`
Application type: "Web application"
Name: "nanogallery2gp"
<img src="img/google_api_console4.jpg?raw=true" alt="step 4" style="max-width:400px;"/>
  
Define the authorized redirect URLs: enter the full path to your `autorize.php`
<img src="img/google_api_console5.jpg?raw=true" alt="step 5" style="max-width:400px;"/>

And you get your personal and confidential `Client ID` and `client secret`
<img src="img/google_api_console6.jpg?raw=true" alt="step 6" style="max-width:400px;"/>

## Security
The `admin` folder should only be accessible to your PHP applications.
