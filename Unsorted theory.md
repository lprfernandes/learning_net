## DTOs - Data Transfer Objects
Alternative to the Domain models to not expose models to the controllers or to the views neither as arg nor return type. Normally they have 2 parts, the request and response:

    //example of a method taking in a dto request and returning dto response
    public CountryResponse AddCountry(CountryAddRequest? countryAddRequest)
    {
        ...
    }

    //example of a dto class
    public class CountryAddRequest
    {
        public string? CountryName {get;set;}
    }
    //notice that it doesn't have id property. The id will be generated automatically inside the domain class.

There will be always a necessity of transforming the requests to domain objects (to be stored in the db), so it's best practice to create a method to do that in the dto request class. 

    public Country ToCountry()
    {
        return new Country() {CountryName = CountryName};
    }

And then there's the necessity of transforming domain objects to responses. To not mess with the domain class where we could put a transform method, we will add an extension class to the request file, create an extension method, extending the domain class with the method ToCountryResponse().

    public class CountryResponse
    {
        ...
    }
    public static class CountryExtensions
    {
        public static CountryResponse ToCountryResponse(this Country country)
        {
            return new CountryResponse 
            { 
                CountryId = country.CountryId, 
                CountryName = country.CountryName
            };
        }
    }

## TDD - Test Driven Development
After the signatures of the interfaces are done. We're not going to implement the services. We'll test it first and then we'll analyze the requirements and build from there. The functionality follows the requirement.

1. Create the serviceTest class on a test project.
2. On that class' constructor, instantiate the field interface with a new class of the testing target class.
3. Create a service class and implement the interface but leave it with the not implemented exception.
4. On the serviceTest class write in comments the test cases and their expected returns. Add a region for each method we'll test.
5. Start with the first comment and create the first method signature. Add the tag [Fact]. In the name of the method, follow the convention [MethodName]_[Scenario]_[Expected Result], and inside the method create an AAA comment structure (Arrange, Act, Assert)

    public void AddCountry_IfCountryAddRequestIsNull_ThrowArgumentNullException()
    {
        AAA
    }

6. If the assert is of type throw, use the Assert.Throws<\T>, and add the Act code inside a lambda into the assert

    //Arrange
    CountryAddRequest? request = null
    
    //Assert
    Assert.Throws<\ArgumentNullException>(()=>{
        
        //Act
        _countriesService.AddCountry(request);
    });

7. After finishing all the test methods, they're supposed to all fail. Now is where we start to work on the implementation.

## Assert class methods to know

    Assert.Throw
    Assert.True
    Assert.Empty
    Assert.Null

## Model Validation from the service
To validate a model from a service, we can:

    ValidationContext validationContext = new ValidationContext(personAddRequest);
    List<ValidationResult> validationResults = new List<ValidationResult>();

    bool isValid = Validator.TryValidateObject(personAddRequest, validationContext,
    validationResults, true);

## ITestOutputHelper
To see the actual values when the cases are passed or failed or to print in the test details summary window. 
Inject it in a constructor of a service test class.

    private readonly ITestOutputHelper _testOutputHelper;

    public PersonsServiceTest(ITestOutputHelper testOutputHelper)
    { 
        _testOutputHelper = testOutputHelper; 
    }

    //to call it
    _testOutputHelper.WriteLine("Just line console");


## Controller Routing Annotation

We can annotate the controller with the route path. By doing so, the action methods can have only the action path portion of the url.

    [Route("Persons")]
    public class MyController
    {
        [Route("Create")]
        public IActionResult Create()
        {

        }
    } 

In case we want the routes with the same names of the controller and the action methods we can pass only the route tokens on the annotations.
    
    [Route("[Controller]")]
    public class MyController
    {
        [Route("[Action]")]
        public IActionResult Create()
        {

        }
    } 

This way, the controller and the action routes will always have the same names of the classes/methods themselves.