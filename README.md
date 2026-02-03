# Late .NET SDK

Official .NET client library for the [Late API](https://docs.getlate.dev) - Schedule and manage social media posts across multiple platforms.

## Requirements

- .NET 8.0 or later

## Installation

```bash
dotnet add package Late
```

Or via Package Manager:

```powershell
Install-Package Late
```

## Quick Start

```csharp
using Late.Api;
using Late.Client;
using Late.Model;

var config = new Configuration
{
    ApiKey = new Dictionary<string, string> { { "Authorization", "Bearer YOUR_API_KEY" } }
};

// List accounts
var accountsApi = new AccountsApi(config);
var accounts = await accountsApi.ListAccountsAsync();
Console.WriteLine(accounts);

// Create a post
var postsApi = new PostsApi(config);
var post = await postsApi.CreatePostAsync(new CreatePostRequest
{
    Content = "Hello from .NET!",
    Platforms = new List<Platform>
    {
        new Platform { PlatformName = "twitter", AccountId = "acc_123" }
    },
    PublishNow = true
});
```

## Documentation

- [API Reference](https://docs.getlate.dev/api-reference)
- [Getting Started Guide](https://docs.getlate.dev/quickstart)

## License

MIT
