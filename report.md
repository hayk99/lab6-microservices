# Laboratory 6 - Microservices
Author: Hayk Kocharyan - 757715

## Running one instance of each service.
In first place we are going to run the registration service, next we wil run accounts and web service from diferent terminals. Each of this services will be run with:
``` 
# service = [ web | accounts | registration ]
gradle :service:bootRun 
```

* Registration service on port 1111.
![port 1111](screenshots/gradle_registration.png)
* Accounts service on port 2222.
![port 2222](screenshots/gradle_accounts.png)
* Web service on port 3333.
![port 3333](screenshots/gradle_web.png)
* Eureka dashboard
![eureka dashboard](screenshots/eureka.png)


## Running another accounts instance.
First of all we must change port number in applications.yml file for accounts module and the run the new instance with 
```
gradle :accounts:bootRun
```
![port 4444](screenshots/gradle_accounts2.png)

![eureka 2 accoutns](screenshots/eureka_2.png)


## -   What happens when you kill the microservice  `accounts (2222)`  and do requests to  `web`?  Can the web service provide information about the accounts again? Why?

First we are goint to kill the service wth `Ctrl + c`.
![eureka accounts 2222 down](screenshots/status_down.png)

Now we are going to check if the web service can provide accounts functionality.

* First check.
![eureka accounts 2222 down](screenshots/web_ok_after_down.png)
* Second check.
![eureka accounts 2222 down](screenshots/web_ok_after_down_2.png)

This is happening because we have another accounts service running on port 4444.




