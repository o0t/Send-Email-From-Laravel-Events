
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



