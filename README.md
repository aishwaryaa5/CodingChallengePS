# CodingChallengePS
This exercise requires Node.js installed, which you can download from here: https://nodejs.org/ - I recommend the LTS version, 18.18, but other versions should be fine too.
It also requires Visual Studio 2022 - you can download the Community edition for free here: https://visualstudio.microsoft.com/downloads/  - with at least the "ASP.NET and web development" and "Node.js development" workloads installed. If you already had Visual Studio 2022 installed, I recommend first checking that it has been updated to at least version 17.7


1. Project setup 
In Visual Studio, click “Create a new project” and search for “webapi” - two templates titled "ASP.NET Core Web API" should appear, use the C# one
On the next screen give it a name
On the screen after that, select:
Framework: .NET 6.0 LTS
Authentication type: None
disable HTTPS (makes it easier to test locally)
enable “Use controllers”
enable “Enable OpenAPI support”
enable “Do not use top-level statements”
With the solution from step 1 open, click File -> New -> Project and search for “react”. Select “Standalone JavaScript React Project” (or use the TypeScript one if you’d really prefer)
On the next screen make sure Solution is set to “Add to solution”
On the screen after that, please leave “Add integration for Empty ASP.NET Web API project” turned OFF, even though it may seem that it would help
Click Project -> “Configure Startup Projects”, set it to “Multiple startup projects” and set both projects to have their Action “Start”.


2. REST Server (C#)
The “ASP.NET Core Web API” template includes some sample code that generates a fake weather forecast – you are encouraged to use this as an example when writing your own code, and then delete the files “WeatherForecast” and “WeatherForecastController” when you are done.
Running the project from Visual Studio will open a browser with the “Swagger UI”, which can be helpful for testing. The “/WeatherForecast” path shown there is the URL path to the API endpoint which has its code in the WeatherForecastController file. If, for example, the test server is running on port 5102 (it will probably be something different in your case), with the Swagger UI at http://localhost:5102/swagger/index.html then the raw REST API endpoint can be accessed at http://localhost:5102/WeatherForecast 
Create a new public class called Score, with 2 public properties: string Name, and int Points.
Create a new controller class called ScoresController
Define a string array with the values “Homer”, “Marge”, “Bart”, “Lisa”, “Maggie”, “Abe”
Make the API controller output an array of Score objects, using the string array above to populate the Name field, and setting each Points to a random integer


3. React app
Edit the code in App.jsx so that it loads the data from the REST API and displays it in a table.
If you are not familiar with React or need a refresher, there is a quick start guide at https://react.dev/learn
You will likely want to use both the effects hook https://react.dev/reference/react/useEffect and the JavaScript “fetch” method to read in the data when the page first loads
Add onClick events to the table column headings (you might want to render them as buttons, but you don’t have to), so that when clicked, it sorts the table by that column. If clicked again when already sorting by that column, reverse the sort order.
Add some CSS of your own and/or either Bootstrap or Tailwind to make it look pretty, but don’t spend too long on it
