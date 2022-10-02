
## Event 

- User Registered
- User Deleted 
- POST Published 
- User Subscribed 

---------------------------------------------------------------

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
- Create system POST [ Form - model - migrations ] 

- Create event 
```bash
	php artisan make:event PostCreated
```
- Page Controller CreatePost
![image](https://user-images.githubusercontent.com/94997828/193459252-96de8821-6d55-429c-ae99-3af69bb2da26.png)
