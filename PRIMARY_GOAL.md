# Web Engineering 2021-2022 / microservices

## Primary goal

In order to launch the services (as we did in lab2 to launch different modules) on separate terminals we are going to use the command "./gradlew :module:bootRun" :

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

At this point if we search accounts by owner at the web we obtain this results:

![Alt text](/img/accountsDashboard1.PNG?raw=true "Web accounts info dashboard")

Then we kill the service `accounts (2222)`, as we can see we can´t obtain his info but we obtain the 
info from the service `accounts (4444)`:

![Alt text](/img/2222no.PNG?raw=true "Accounts 2222 info")

![Alt text](/img/4444si.PNG?raw=true "Accounts 4444 info")

When we search accounts by owner at the web now, we obtain this results:

![Alt text](/img/accountsDashboard1.PNG?raw=true "Web accounts info dashboard")

We can retrieve information about the accounts because the registration server still has the service `accounts (4444)` available and can retrieve that info from that service.




