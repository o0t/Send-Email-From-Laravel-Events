
## Event 

- User Registered
- User Deleted 
- POST Published 
- User Subscribed 


--------------------------------------------------------------------------------------------

Listener :

[ 
  Listener => "listens for events that occur in your application" 
]

-> POST Published (event)
   -> notify all users (listener)
   -> notify admin about the post (listener)
   
--------------------------------------------------------------------------------------------

# Start 

 - install laravel
 - create auth 
```bash
	  	1 - composer require laravel/ui --dev
		2 - npm install
		3 - npm run dev
		4 - php artisan ui:auth
		5 - php artisan migrate
```
### Create system POST [ Form - model - migrations ] 

### Create event 
```bash
	php artisan make:event PostCreated
```
### Page PostController.php

![image](https://user-images.githubusercontent.com/94997828/193459316-fbbd59f8-0d0c-4176-8364-babbb374058b.png)

### Create listener 

```bash
	php artisan make:listener NotifyUser --event=PostCreated
```


### Providers -> EventServiceProvider.php


![image](https://user-images.githubusercontent.com/94997828/193642469-7ca89589-c8b3-4746-81af-26c5f151fba6.png)


### Events -> PostCreated.php 

![image](https://user-images.githubusercontent.com/94997828/193642804-22f5f770-5060-4010-b428-e4df8b408267.png)


###  Listeners -> NotifyUser.php

![image](https://user-images.githubusercontent.com/94997828/193643389-9f1ee9c0-777a-44d7-bde1-28ed55609b73.png)

### Create UserMail

```bash
	php artisan make:mail UserMail
```

![image](https://user-images.githubusercontent.com/94997828/193643620-a3fdcf66-31d7-437e-8a50-5eef3638711a.png)


### Sing in For Emails
- (https://mailtrap.io/)

### .env
```bash
	MAIL_MAILER=test
	MAIL_HOST=test
	MAIL_PORT=test
	MAIL_USERNAME=test
	MAIL_PASSWORD=test
	MAIL_ENCRYPTION=tls
	MAIL_FROM_ADDRESS=test@test.com
```

### Save .env

```bash
	 php artisan config:cache
```

### Mail -> UserMail.php  And Create Page Mail in view 

![image](https://user-images.githubusercontent.com/94997828/193644537-46688ff5-ca87-4d0b-9853-fc3be34a2260.png)


### in page you created in view Folder UserMail.blade.php
#### This is in page and in mail massage 
```bash
		<br><h1>Mail User </h1>
		<br><b>Post title : {{$post['title']}}</b>
		<br><b>username : {{$post['username']}}</b> 
```

# Event is Done .. 

------------------------------------------------------------------------------------------------


# Start Listener

```bash
	php artisan queue:table
```

### in .env 

```bash
	QUEUE_CONNECTION=database 
```

### Save And Uplode Table 

```bash
	 php artisan config:cache
	 php artisan migrate
```

### Mail -> UserMail.php

![image](https://user-images.githubusercontent.com/94997828/193646080-2a81d280-9408-4ded-a3cc-bef2cc5e2140.png)


---------------------------------------------------------------------------------

# Start Send Code this 

```bash
	php artisan queue:listen
```

-------------------------------------------------------------------------------------

# Good luck , and run this 🧠

