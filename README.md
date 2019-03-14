# LoggingApp01

A .NET Core 2.2 MVC web app with CRUD functionality (create, retrieve, update, delete). The database will be created when the app is launched from Visual Studio; it is stored in the local Cosmos DB emulator.

Install the Cosmos DB emulator. Download and install info is available here:
https://docs.microsoft.com/en-us/azure/cosmos-db/local-emulator#installation

In Visual Studio create a new Project:
File > New Project > ASP.NET Core web app > Then select version Core 2.2. & "Web App(M-V-C)".

When the project is created and open:

Add the Nuget package Microsoft.Azure.DocumentDB.Core to the project.

In DocumentDBRepository.cs at the Project level. (Change the values of the 4 readonly strings at the top of file as necessary).
Add my Item.cs to the Models folder.
Add my .cshtml files to the Views/Home/ folder:-
	Create.cshtml, Delete.cshtml, Details.cshtml, Edit.cshtml, Index.cshtml, Privacy.cshtml.

Add this line to the end of the Configure method in Startup.cs, where Item is ths name of the file just added to the Models folder:-
DocumentDBRepository<Models.Item>.Initialize();

Replace the Index action in HomeController.cs with this:-
public async Task<IActionResult> Index()
        {
            var items = await DocumentDBRepository<Item>.GetItemsAsync(d => !d.Completed);
            return View(items);
        }
