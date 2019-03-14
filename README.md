# LoggingApp01

A .NET Core 2.2 MVC web app with CRUD functionality (create, retrieve, update, delete). It's an update of the "quickstart" app that you can download from within the Cosmos DB emulator which is a Core 1.0 app.



Install the Cosmos DB emulator. Download and install info is available here:
https://docs.microsoft.com/en-us/azure/cosmos-db/local-emulator#installation
Don't create anything in the emulator; the app does that when launched.

In Visual Studio create a new Project:

File > New Project > ASP.NET Core web app > Then select version Core 2.2. & "Web App(M-V-C)".

When the project is created and open:

Add the Nuget package Microsoft.Azure.DocumentDB.Core to the project.

Modify the Item class (in the Models folder) to suit your application.

Modify the .cshtml files (in the Views/Home/ folder) to suit your application.

The four configuration strings towards the top of the DocumentDBRepository class should not need to be changed because all Cosmos emulators use the same endpoint and access keys, but you'll need to change the DatabaseId and CollectionId if you want to give your database or collection a different name.
