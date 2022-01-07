# Web Engineering 2021-2022 / microservices

## Primary goal

As we did in lab2, to launch the services (different modules on our project) on separate terminals we are going to use the command "./gradlew :module:bootRun" :

* **Service discovery** (`./gradlew :registration:bootRun`):
  
![Alt text](/img/registrationTerminal.PNG?raw=true "Registration service")

* **Account service** (`./gradlew :accounts:bootRun`):
  
![Alt text](/img/accountsTerminal.PNG?raw=true "Accounts service on port 2222")

* **Web service** (`./gradlew :web:bootRun`):

![Alt text](/img/webTerminal.PNG?raw=true "Web service")

At this point, the two services `accounts (2222)` and `web` are running and the service registration service has these two services registered as we can see on Eureka Dashboard `http://localhost:1111`:

![Alt text](/img/registrationDashboard.PNG?raw=true "Eureka dashboard")

In order to run a second `accounts` service instance that will use the port 4444 we need to modify the port on the file `aplication.yaml`:

![Alt text](/img/cambiosAccount.PNG?raw=true "Changes on Account (application.yaml)")

* **Account service(4444)** (`./gradlew :accounts:bootRun`):

![Alt text](/img/accountsTerminal2.PNG?raw=true "Accounts service on port 4444")

As we can see on Eureka Dashboard `http://localhost:1111`:

![Alt text](/img/registrationDashboard2.PNG?raw=true "Eureka dashboard")

* What happens when you kill the service `accounts (2222)` and do requests to `web`?  
  Can the web service provide information about the accounts again? Why?



