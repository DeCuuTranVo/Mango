<h1> Mango MicroService - Online Shopping Application </h1>

![C#](https://img.shields.io/badge/c%23-%23239120.svg?style=for-the-badge&logo=csharp&logoColor=white)
![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/css3-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E)
![Bootstrap](https://img.shields.io/badge/bootstrap-%238511FA.svg?style=for-the-badge&logo=bootstrap&logoColor=white)
![.Net](https://img.shields.io/badge/.NET-5C2D91?style=for-the-badge&logo=.net&logoColor=white)
![MicrosoftSQLServer](https://img.shields.io/badge/Microsoft%20SQL%20Server-CC2927?style=for-the-badge&logo=microsoft%20sql%20server&logoColor=white)
![Windows](https://img.shields.io/badge/Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white)
![Visual Studio](https://img.shields.io/badge/Visual%20Studio-5C2D91.svg?style=for-the-badge&logo=visual-studio&logoColor=white)
![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white)
![Udemy](https://img.shields.io/badge/Udemy-A435F0?style=for-the-badge&logo=Udemy&logoColor=white)

<h2> 1. Project Description </h2>
This app is a web app that serves the purpose of online purchasing goods.

<h2> 2. System design and main elements </h2>
<h3> 2.1. Tech stack</h3>

```
    Tech stack:
    ├── Database: Microsoft SQL Server
    └── Web Development: 
        ├── Front-end: HTML, CSS, JavaScript, Bootstrap, ASP.NET Core MVC 
        ├── Back-end: C#, ASP.NET Web API, Entity Framework Core, ASP.NET Identity Core
        └── Third-party libraries: Stripe
```

<h3> 2.2. Design Pattern: Model - View - Template</h3>
<h3> 2.3. Architecture: MicroService Architecture </h3>
<h3> 2.3. Project Structure </h3>

<pre>
<b>Mango </b>
├── <b>FrontEnd </b>
│   └── <b>Mango.Web </b>
│       ├── <b>Controllers </b>     
│       │   ├── AuthControllers.cs
│       │   ├── CartControllers.cs
│       │   ├── CouponControllers.cs
│       │   ├── HomeControllers.cs
│       │   ├── OrderControllers.cs
│       │   └── ProductControllers.cs
│       ├── <b>Models </b>       
│       │   ├── CartDetailsDto.cs
│       │   ├── CartDto.cs
│       │   ├── CartHeaderDto.cs
│       │   ├── CouponDto.cs
│       │   ├── ErrorViewModel.cs
│       │   ├── LoginRequestDto.cs
│       │   ├── LoginResponseDto.cs
│       │   ├── OrderDetailsDto.cs
│       │   ├── OrderHeaderDto.cs
│       │   ├── ProductDto.cs
│       │   ├── RequestDto.cs
│       │   ├── ResponseDto.cs
│       │   ├── StripeRequestDto.cs
│       │   └── UserDto.cs
│       ├── <b>Utility </b>       
│       │   ├── AllowedExtensionsAttribute.cs
│       │   ├── MaxFileSizeAttribute.cs
│       │   └── SD.cs
│       ├── <b>Services </b>  
│       │   ├── <b>IService </b>       
│       │   │   ├── IAuthService.cs
│       │   │   ├── IBaseService.cs
│       │   │   ├── ICartService.cs
│       │   │   ├── ICouponService.cs
│       │   │   ├── IOrderService.cs
│       │   │   ├── IProductService.cs
│       │   │   └── ITokenProvider.cs
│       │   └── <b>Service </b>         
│       │       ├── AuthService.cs
│       │       ├── BaseService.cs
│       │       ├── CartService.cs
│       │       ├── CouponService.cs
│       │       ├── OrderService.cs
│       │       ├── ProductService.cs
│       │       └── TokenProvider.cs
│       ├── <b>Views </b>    
│       │   ├── <b>Auth </b>   
│       │   │   ├── Login.cshtml
│       │   │   └── Register.cshtml 
│       │   ├── <b>Cart </b>    
│       │   │   ├── CartIndex.cshtml
│       │   │   ├── Checkout.cshtml
│       │   │   └── Confirmation.cshtml
│       │   ├── <b>Coupon </b>    
│       │   │   ├── CouponCreate.cshtml
│       │   │   ├── CouponDelete.cshtml
│       │   │   └── CouponIndex.cshtml
│       │   ├── <b>Home </b>   
│       │   │   ├── Index.cshtml
│       │   │   ├── Privacy.cshtml
│       │   │   └── ProductDetails.cshtml
│       │   ├── <b>Order </b>    
│       │   │   ├── OrderDetail.cshtml
│       │   │   └── OrderIndex.cshtml
│       │   ├── <b>Product </b>    
│       │   │   ├── ProductCreate.cshtml
│       │   │   ├── ProductDelete.cshtml
│       │   │   ├── ProductEdit.cshtml
│       │   │   └── ProductIndex.cshtml
│       │   └── <b>Shared </b>    
│       │       ├── Error.cshtml
│       │       └── _Layout.cshtml
│       ├── appsettings.json
│       ├── appsettings.Production.json
│       └── Program.cs
├── <b>Gateway </b>
│   └── <b>Mango.GatewaySolution </b>
│       ├── <b>Extensions </b>    
│       │   └── WebApplicationBuilderExtensions.cs
│       ├── appsettings.json
│       ├── ocelot.json
│       ├── ocelot.Production.json
│       └── Program.cs
├── <b>Integration </b>
│   └── <b>Mango.MessageBus </b>
│       ├── IMessageBus.cs
│       └── MessageBus.cs
├── <b>Services </b>
│   ├── <b>Mango.Services.AuthAPI </b>
│   │   ├── <b>Controllers </b>     
│   |   │   └── AuthAPIController.cs
│   |   ├── <b>Data </b>     
│   |   │   └── AppDbContext.cs
│   |   ├── <b>Models </b>       
│   |   │   ├── <b>Dto </b>   
│   |   │   │   ├── LoginRequestDto.cs
│   |   │   │   ├── LoginResponseDto.cs
│   |   │   │   ├── RegisterationRequestDto.cs
│   |   │   │   ├── ResponseDto.cs  
│   |   │   │   └── UserDto.cs
│   |   │   ├── ApplicationUser.cs
│   |   │   └── JwtOptions.cs
│   |   ├── <b>Service </b>     
│   |   │   ├── <b>IService </b>   
│   |   │   │   ├── IAuthService.cs
│   |   │   │   └── IJwtTokenGenerator.cs
│   |   │   ├── AuthService.cs
│   |   │   └── JwtTokenGenerator.cs
│   |   ├── appsettings.json
│   |   ├── appsettings.Production.json
│   |   └── Program.cs
│   ├── <b>Mango.Services.CouponAPI </b>
│   │   ├── <b>Controllers </b>     
│   |   │   └── CouponAPIController.cs
│   |   ├── <b>Data </b>     
│   |   │   └── AppDbContext.cs
│   |   ├── <b>Extensions </b>    
│   |   │   └── WebApplicationBuilderExtensions.cs
│   |   ├── <b>Models </b>       
│   |   │   ├── <b>Dto </b>   
│   |   │   │   ├── CouponDto.cs
│   |   │   │   └── ResponseDto.cs  
│   |   │   └── Coupon.cs
│   |   ├── <b>Service </b>     
│   |   │   ├── <b>IService </b>   
│   |   │   │   ├── IAuthService.cs
│   |   │   │   └── IJwtTokenGenerator.cs
│   |   │   ├── AuthService.cs
│   |   │   └── JwtTokenGenerator.cs
│   |   ├── MappingConfig.cs
│   |   ├── appsettings.json
│   |   ├── appsettings.Production.json
│   |   └── Program.cs
│   ├── <b>Mango.Services.EmailAPI </b>
│   |   ├── <b>Data </b>     
│   |   │   └── AppDbContext.cs
│   |   ├── <b>Extensions </b>    
│   |   │   └── WebApplicationBuilderExtensions.cs
│   |   ├── <b>Models </b>       
│   |   │   ├── <b>Dto </b>   
│   |   │   │   ├── CartDetailsDto.cs
│   |   │   │   ├── CartDto.cs
│   |   │   │   ├── CartHeaderDto.cs
│   |   │   │   └── ProductDto.cs
│   |   │   └── EmailLogger.cs
│   |   ├── <b>Message </b>    
│   |   │   └── RewardsMessage.cs
│   |   ├── <b>Messaging </b>   
│   |   │   ├── AzureServiceBusConsumer.cs 
│   |   │   └── IAzureServiceBusConsumer.cs
│   |   ├── <b>Service </b>     
│   |   │   ├── EmailService.cs
│   |   │   └── IEmailService.cs
│   |   ├── appsettings.json
│   |   ├── appsettings.Production.json
│   |   └── Program.cs
│   ├── <b>Mango.Services.OrderAPI </b>
│   │   ├── <b>Controllers </b>     
│   |   │   └── OrderAPIController.cs
│   |   ├── <b>Data </b>     
│   |   │   └── AppDbContext.cs
│   |   ├── <b>Extensions </b>    
│   |   │   └── WebApplicationBuilderExtensions.cs
│   |   ├── <b>Models </b>       
│   |   │   ├── <b>Dto </b>   
│   |   │   │   ├── CartDetailsDto.cs
│   |   │   │   ├── CartDto.cs
│   |   │   │   ├── CartHeaderDto.cs
│   |   │   │   ├── OrderDetailsDto.cs
│   |   │   │   ├── OrderHeaderDto.cs
│   |   │   │   ├── ProductDto.cs
│   |   │   │   ├── ResponseDto.cs
│   |   │   │   ├── RewardsDto.cs
│   |   │   │   └── StripeRequestDto.cs
│   |   │   ├── OrderDetails.cs
│   |   │   └── OrderHeader.cs
│   |   ├── <b>Service </b>     
│   |   │   ├── <b>IService </b>   
│   |   │   │   └── IProductService.cs
│   |   │   └── ProductService.cs
│   |   ├── <b>Utility </b>       
│   |   │   ├── BackendApiAuthenticationHttpClientHandler.cs
│   |   │   └── SD.cs
│   |   ├── MappingConfig.cs
│   |   ├── appsettings.json
│   |   ├── appsettings.Production.json
│   |   └── Program.cs
    

