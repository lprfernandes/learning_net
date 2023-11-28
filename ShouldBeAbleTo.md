# .NET ShouldBeAbleTo Study Guide

This document serves as an iterative learning test for understanding and mastering .NET. The process involves attempting to answer questions, reviewing incorrect or unknown answers, and iterating until all answers can be provided confidently without consulting external sources.
The source for these are the Udemy Course here: https://www.udemy.com/course/c-sharp-oop-ultimate-guide-project-master-class/learn/lecture/20471791#overview

## Test Instructions
- Make a first attempt to answer each question to the best of your ability.
- For any questions you cannot answer or answer incorrectly, mark them for review.
- Consult sources to find the correct answers for those marked questions.
- Revisit the marked questions in subsequent study sessions until you can answer them without assistance.


## Section 2: Getting Started
1. Create an empty .NET project. What does the builder var holds? and what's its type? 
2. Create multiple launch settings profiles and experiment with them 

## Section 3: HTTP
3. Create a basic http response with run method
4. Create a custom header myKey = myValue and sent it through a request
5. Create a basic http request and respond with an html with the path of the previous request and the method
6. Create a basic http request with a valid query string and a response that print the given value of the query dict to html.
7. Describe the classes of status code. ex: 1... are informational..2...
8. Create a basic http request with a custom header kv pair and print it to html in a response.
9. In postman create a request with an AuthorizationKey = 101 kv pair header and read it in a response if auth successful send plain text "Hello", if not "Access not authorized" and add the status codes accordingly.
10. Describe the main request methods.
11. Create a post request in postman and send a query in the body. Receive the request and convert the body query into a dictionary and then respond with a value of the query.

## Section 4: Middleware
12. What's a middleware? How to create them?
13. Create a chain of 2 middleware. Pass the context from the 1st to the 2nd. 
14. Create a custom Middleware class implementing IMiddleware. Don't forget to add it to the services.
15. Create an extension method to use the middleware created above
16. Create a custom conventional middleware.
17. Whats the correct middleware order?
18. Create a branch in the middleware pipeline with the UseWhen method.

## Section 5: Routing
19. What's routing?
20. What are the 2 methods that must be called in order to activate the routing. Explain what each method does.
21. Create endpoints and pass in a lambda with an async response.  
22. What are the differences between Map,MapGet,MapPost?
23. After app.UseRouting() get the endpoint into an Endpoint object.
24. What are the possible params passed in by route
25. Create a request route and respond by printing the route params. 
26. What are route constraints? And of what kind? map a request route through map with every kind of constraint.
27. Create a custom constraint class and don't forget to register it in the services.        
28. What is the Endpoint selection order?
29. Create a wwwroot folder and enable its access. Change the name of the folder and then change the default name in the builder.

## Section 6: Controllers & IActionResult
30. What's a controller? create one with an Action method. Don't forget to AddControllers, MapControllers and on the method the attribute routing.
31. What are the responsibilities of the controllers? 
32. Create an action method that returns Content Result and Content
33. Create an action method that returns JSONResult or Json.
34. What are the 3 different types of FileResult? Create an example for each.
35. What are the different IActionResults?
36. Create a redirect to action and supply route values.

## Section 7: Model Binding and Validations
37. What's model binding? What is the priority for the model binding types?
38. Create an action that takes in args through Query model binding
39. Create an action that takes in args through Route model binding
40. Create an action that takes in form fields.
41. What model validation property annotations are possible?
42. Create your own custom validation class. It should have a default error message in case the user doesn't provide it and a min value.
43. Create your own custom validation class validating multiple fields.
44. Create a model class which implements the IValidatable
45. Create an action model in which you only wan't to bind some of the props and another where you don't want to bind some.
46. Create a post action that sends a json and another that sends an xml. Both must be recognized by the model binding.
47. Create a custom model binder.
48. Take the custom model binder and render it accessible to the whole application, so that every action that takes in that model class validates it the way you customized it.

## Section 8: Razor Views
49. Create a simple view and navigate to it in the browser.
50. Create a Razor View using razor syntax code block, if,ifelse, switch, foreach, for, string literal and comments.
51. Create a Razor View that contains a local function and a method. Call them in the view.
52. Print an unsanitized html or js in the view
53. What's ViewData? Create a key and value in the controller and print it in the view.
54. What's ViewBag? Create a key and value in the controller and print it in the view.
55. What's a strongly typed view? Create an example and access it on a view.
56. Create a strongly typed view with multiple models.
57. What's _ViewImports? Create a global one and a local one.
58. What's a shared view? Create one.

## Section 9: Layout Views
59. What's a layout view? Create one. Pass a title from each view. Make sure each view's body renders.
60. What's viewStart? Create one
61. What's dynamic Layout view? Create one
62. What are layout sections? Create one.
63. What are nested layouts? Create one.

## Section 10: Partial Views
64. What are partial views? Create one. Invoke it via html and via razor syntax.
65. What's the difference between partialAsync and RenderPartialAsync?
66. Supply a custom ViewData object to a partial from a view. 
67. Create a strongly typed partial and pass it an object of that model.
68. What's the purpose of return PartialViewResult?

## Section 11: View Components
69. What's a view component? What's the difference to a partial view? Create one and invoke through the 2 possible ways.
70. Create a strongly typed view component and pass an object from the vc class and print it in the view.
71. Create a view component with params, passing args from the parent view to the vc.
72. Create a js method in a view returning a ViewComponentResult.

## Section 12: Dependency Injection
73. What's the dependency inversion principle?
74. What's Inversion of control? And IoC container?
75. What's dependency injection? 
76. Define the 3 different service lifetimes
77. Create a service class and interface and inject it in a controller and register it as singleton.
78. Create a service class and interface and inject it in a service method.
79. What is a child (service) scope? Create one.
80. Inject a service in a view but not on the controller
81. What are the best practices when dealing with dependency injection?
82. Whats the difference between GetRequiredService and GetService.

## Section 13: Environments
83. Access the environment in the program.cs
84. Access the environment in the controller by injecting the service
85. Access the environment in the views by using a tag helper
86. Set the env of an app through cmd or powershell and run it.

## Section 14: Configuration
87. What's configuration?
88. How can we get the config inside a controller? Create an example
89. Get a section from the config, next, get the value from the 2 possible ways.
90. What's the options pattern? Create an example with the Get<\T> and another with Bind. What's the difference between them?
91. Create a configuration as a service and inject it in a controller.
92. What's the order of precedence of configuration sources?
93. What's user-secrets? Why is it used? Create one example.
94. Set environment values and run from the dotnet cli.
95. Create and read a custom config file.
96. Create and HttpClient injecting IHttpClientFactory

## Section 15: xUnit
97. Create a test project. What are the 3A's? Define each.
98. What's the tag Fact? Create one
99. Create a serviceTest and create test cases before the implementation. Create also the service, the model and the contracts and dtos.
100. Create a validation of the model from the service.
101. What's the purpose of ITestOutputHelper. Create an example. 

## Section 16: CRUD Operations
Here there are no questions but it's important to revisit the course to see how the author creates a landing page with a table where we sort by any of the columns, in asc or desc. This info is sent by the view to the action method on the controller.
He also creates a form with tag helpers 

## Section 17: Tag Helpers
102. What are tag helpers? Define the pre-defined ones.
103. What are the advantages of this approach?
104. Build a create view
105. Build an edit view
106. Build a delete view

## Section 18: EntityFrameworkCore
107. Create a functioning applicationDbContext with 2 dbSets.
108. Create a stored procedure and call it from code.
109. Create a stored procedure with parameters and call it from code.
110. Resorting to Fluent Api, specify a prop column name, its column type, its default value, if its unique values only and a check constraint of exactly 8chars on it's length.
111. Resorting to Fluent Api, specify a relationship between 2 classes. 
112. What's a navigation property? and a foreign key? If I want to include the nav prop in a linq query what must I do? Create an example.
113. Generate a pdf through Rotativa package.
114. Generate a csv through csv helper.
115. Generate an excel file through epplus.
116. Create an Excel to Db upload.

## Section 19: Unit Testing [Advanced, Moq & Repository Pattern]
117. What are the best practices of unit testing?
118. Create a mock of a dbContext
119. Use Autofixture to create randomized data.
120. Create test cases with Fluent Assertions.
121. What's the repository pattern? Create one.
122. What are the pros and cons of the repository pattern?
123. Create a mock of the repository while unit test the service layer.
124. Create a mock of the services while unit test the controller layer.
125. Create an integration test.
126. Create an integration test that tests the response DOM with Fizzler.

## Section 20: Logging and Serilog
127. What are the log levels? Log one message from each level.
128. Use ILogger inside a controller to log something.
129. Add HttpLogging in an app and add a LoggingField (like header for ex.)
130. Log a message using Serilog.
131. Create a log to a file with an hourly rolling interval.
132. Create a log to a file with a size limit.
133. Create a log which it's sink is in MSSqlServer
134. Create a log to seq sink.
135. Create a log with enrichers within Serilog.
136. Print an object with the IDiagnosticContext of Serilog.
137. Log a timing of some action with a Serilog Timing

## Section 21: Filters
138. Remember the filter pipeline and it's entry point on the middleware pipeline. What type of filters there are?
139. Create an action filter with both methods, and make assign it to an action method.
140. Pass in Action Args to the HttpContext items in the OnActionExecuting and then retrieve it in the OnActionExecuted.
141. Create an ActionFilter with args.
142. What are the scopes of the filters? Create examples.
143. How to create a custom order of filter execution?. Create one example.
144. Do the same but recurring to the IOrderedFilter interface.
145. Create an async actionFilter.
146. How can we short circuit the filter pipeline? Create an example. 
147. What's a Result Filter? Create an example.
148. Add an auth cookie at the last minute with the result filter.
149. What's a Resource Filter? Create an example. 
150. What's an Authorization Filter? Create an example. 
151. What's an Exception Filter? Create an example.
152. What's the impact of short-circuiting the various components? Explain one by one.
153. What's the IAlwaysRun Result Filter? What's it's characteristics? Create an example.
154. What's the Filter Overrides? How can I create a SkipFilter functionality?
155. What's a Service Filter? What's the difference to a TypeFilter? Create an example.
156. What's filter attribute classes? Create one example. 
157. What's IFilterFactory? Create an example where the filter class is directly instantiated inside the CreateInstance method and another where it is injected from the IoC container.

## Section 22: Error Handling
158. What's a Exception Handling middleware? What's the difference to the exception filter? Create an example. 
159. What's a Custom Exception? Create one example.
160. What's UseExceptionHandler method? Create an example passing an exceptionHandlerPathFeature to a view.
161. Create an example with UseStatusCodePagesWithRedirects

## Section 23: SOLID Principles
162. What are the solid principles? Define each of them. 
163. Explain Single Responsibility principle
164. Explain Open/Closed principle. Create one example with an alternative implementation of the class by implementing the same interface. Do the same with a child class. What is the danger of this last approach?
165. Explain Liskov Substitution principle. 
166. Explain Interface Segregation principle
167. Explain Dependency Inversion principle

## Section 24: Clean Architecture
168. What's the main goal of Clean architecture. What are its major features and benefits?
169. Create a solution with the different projects and all the necessary folders. 

## Section 25: Identity, Authorization, Security
170. What's Identity?
171. What's Identity user and Identity Role classes? Create examples deriving from them.
172. Without creating views, create a register example with a controller, action methods, with userStore and roleStore(repository pattern).
173. Do the same with login and the SignInManager.
174. Set the complexity of the password. 
175. Create and add an authorization policy.
176. Create an example implementing the return url as soon as the user logs in.
177. What's remote validation? Create an example.
178. What's conventional routing?
179. Create different user roles.
180. What's an area? Create one and the routing dependant on the role.
181. How can I restrict a controller or an action method with role based authentication?
182. Create custom authorization policies.
183. How does HTTPS work? Enable it.
184. What's XSRF? And a anti-forgery token? Implement it.

## Section 26: Asp.Net Core Web API
185. What's the difference between AddControllers and AddControllersWithViews.
186. What's does the tag attribute [ApiController] allows to do automatically?
187. Add entity framework to a webapi project.
188. What's a problem return type? And a ValidationProblem? Create one example.
189. Why would we create a custom controller based on the controllerbase class? Create one example.

## Section 27: Swagger / Open API
190. Add swagger to a project.
191. Write comments to a method and make it show in swagger.
192. What's content negotiation? Create a produces/consumes attribute to declare that the app only produces/consumes application/json
193. Create versioning of the api with urlsegmentapiversionreader. Also, create docs through SwaggerDoc for both versions.

## Section 28: Angular and CORS
194. What's CORS? How to enable it?
195. Add custom policy with headers and methods.  

## Section 29: JWT & Web API Authentication
196. Add identity to an API project.
197. What's a JWT? What are the constituent parts?
198. What claims are usually inserted into a jwt payload?
199. Create a CreateJwtToken method that given an applicationUser, creates a jwtToken an returns it in a AuthenticationResponse.
200. How can we check (server side) if the token is being included in the headers of the client app? Create that authentication check.
201. How can we add the Authorize at a global level? (not controller by controller)
202. What's a claimsPrincipal?  
203. What's a refresh token? Implement it.

## Section 30: Minimal API
203. What's minimal API? Create a project.
204. Create CRUD operations with each of the methods GET, POST, etc.
205. Create an endpoint that receives a route parameter for ex id. Add constraints to it.
206. What's a MapGroup? Create one and make it as an extension method.
207. What's the IResult? Create one example
208. Create a method that returns a ValidationProblem object.
209. What's an endpoint filter? Create one example.
210. Take the same endpoint filter and implement it on a separate file with IEndPointFilter.
