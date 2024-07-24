# Hands-on demo of GitHub Copilot with Visual Studio


*Main outline*

1. Start the .NET application by clicking on the play button.	 
1. Run the current solution, test the search feature 
1. Using Copilot, learn how the current solution works 
1. Use Copilot to improve the Search End Point code 
1. Use Copilot to learn for a better way to test an Endpoint 
1. Run the current solution, test the search feature in the solution.  

> [!NOTE] 
> A project is contained within a solution. Despite its name, a solution isn't an "answer." It's simply a container for one or more related projects, along with build information, Visual Studio window settings, and any miscellaneous files that aren't associated with a particular project. 


## Verify the problem

- Open the solution in [src/00 demo/eShopLite.sln](/../../src/00 demo/eShopLite.sln)
- Run the solution by clicking on the play button
- Open the browser in Visual Studio and make a search for a product
- Stop the application, the search should take close to 11 seconds to complete

## Use Copilot to understand where the problem is

- In VS2022, ask Copilot to explain the code in the solution:  

```bash 
show me the endpoints in the solution  
``` 

GitHub Copilot should give a general response, not useful. 

Switch the prompt to Focus this in the current solution using `#solution`: 

```bash 
show me the endpoints in the #solution  
``` 

Analyze the Copilot response and ask to explain the data class `productDataContext.cs` . You can use inline-chat or use plain chat for this:

```bash 
/explain the code in #productDataContext.cs  
``` 

- (optional) Ask how many sample products are added to the local test DB 

```bash 
how many sample products are added while initializing the DB?  
``` 

## Fix the problem

In order to show the elapsed time for the Search process, edit the file [.\src\00 demo\Store \Components\Pages\Search.razor] and uncomment the following code: 

```csharp
@* Uncomment this to show the elapsed time *@ 

@* <p class="mark">Elapsed Time: [@elapsedTime]</p> *@ 
```

This should show the total elapsed time in the Search Window. 

- Test again and take a note of the elapsed time. In the current demo is ~11 seconds. Use Copilot to improve the Search End Point 
- Back to the SEARCH Endpoint, select the search code between the Stopwatch start/stop and ask copilot to optimize the code using Entity Framework Functions. Suggested prompt: 

```bash 
/optimize this code, use EF Functions and like for the search. Also use the search criteria from the parameters 
``` 

This is the original code:

```csharp 

var stopwatch = new Stopwatch(); stopwatch.Start(); 

List<Product> products = new List<Product>(); var name = ""; 

for (int i = 0; i < db.Product.Count(); i++) 
{ 
    var product = db.Product.ToArray()[i]; 
    name = product.Name; 
    if (name.Contains(search, StringComparison.InvariantCultureIgnoreCase)) { 
        products.Add(product); } 
} 

stopwatch.Stop();
``` 

  

The new code should look like this 


```csharp 

List<Product> products = await db.Product 

.Where(p => EF.Functions.Like(p.Name, $"%{search}%")) 

.ToListAsync();  

``` 

  

Run the search again. It should be faster. 

> [!NOTE] 
> In the test video the search process went down from 11 seconds to 0.2 seconds. 


## Test the Endpoint

Use Copilot to find a better way to test an Endpoint 

Let's figure out a better way to test an endpoint. Ask Copilot Chat using `/askvs` slash command:

```bash 
/askvs how can I test an http endpoint in a C# WebAPI project directly in Visual Studio?  
``` 
  
V2 if the previous demo doesn't work, test the following prompt: 

```bash 
/askvs how can I test an http endpoint in a C# WebAPI project directly in Visual Studio? Can I use the file.http in the project? 
``` 

Read the answer, it explains how to use a file.http in Visual Studio 2022. 
Edit the file [products.http] and add the following lines :

```bash 
GET {{HostAddress}}/api/Product/search/Camping Accept: application/json 
``` 

Run just the [Products] project and test the endpoint from [products.http].

- Show the elapsed time from the http response window. 
