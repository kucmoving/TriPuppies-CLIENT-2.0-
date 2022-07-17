<h2>Introduction</h2>

[Tripuppies](https://tricli.azurewebsites.net/) is a social media for travellers and guides. This website allows users to update their personal information, search for others by specific criteria and communicate with their match(follow and message).

![image](https://user-images.githubusercontent.com/92262463/179397781-66bc7e23-fa53-4a1b-af05-a2982938d216.png)


<h2>Get started</h2>

1. Clone the project
```$ git clone https://github.com/kucmoving/TriPuppies-CLIENT-2.0-```
```$ git clone https://github.com/kucmoving/Tripuppies-API```

2. Use your tool to open the folder (Visual Studio Code or Visual Studio)

3. Create a local database(Personally i am using MicrosoftSQL 2019)
* Add a connection string to appsetting.json (in API Please change your own location code after DefaultConnection)<br>
```{
  "ConnectionStrings": {
    "DefaultConnection": "Data Source=LAPTOP-NCT36AOV\\SQLEXPRESS;Initial Catalog=ParentStudentWebAPI;Integrated Security=True;Connect Timeout=30;Encrypt=False;TrustServerCertificate=False;ApplicationIntent=ReadWrite;MultiSubnetFailover=False"
  },
```
* Add migration, update database<br>
```dotnet ef migrations add InitialCreate```
```dotnet ef database update```

4. You Should now have both frontend and backend development server running in your default browser.
* for client folder ```$ npm install``` ```$ ng serve```
* for api folder(make sure in the folder) ```$dotnet watch run```

5. API Key
* Register an account in [Cloundinary](https://cloudinary.com/)
* Input Secret key and code in AppSettings.json


<h2>Lesson Learned</h2>

Here are some elements i have learnt after this project:<br>

1. Deep dive in many to many relationship
* Many to many relationship is quite confusing when we are creating table but we can have a better naming in poco or draw a database mind map before coding, just 
like the picture below(not as same as the final product)
*Follow function is the easier one that simply linking the relationship record
*Message function is the harder one. First we should define more pocos with different data types in entity and understand that message thread is a list of message
![image](https://user-images.githubusercontent.com/92262463/179399762-07dd47ca-79a5-40d6-bb44-eef6345efd05.png)

2. Angular Component Operation
* Angular is a component framework with different files that can make the project easier to maintain. Angular is complicated because there are lots of files but developers can use the hotkeys in vs code to deal with it.
```ctrl + p (search file name), ctrl + f(search the code)``` 

3. Debugging between frontend and backend
* Debugging becomes interesting. When i faces a bug, i identify the root cause of the problem by testing api in swagger. If backend function properly, i will move to Chrome console log and network to see how the data is passing. Generally, bug happens because of variable naming, datatypes and version conflict.

4. Azure deployment
* Because the project is separtion of frontend and backend. I have to upload three parts of my project to azure and connect them together. To allow client side connect the api, we should set the cros in api app. To connect the server, we should modify the setting of firewall. It is recommand to install extension for your client app because some conflicts may happen in Azure deployment.


Future Development 
1. External Api Google map
* Receving more user information can make the application better user experience.

3. Ecommence element 
* Adding stripe.js 




