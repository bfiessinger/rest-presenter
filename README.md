<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://www.codelabx.ltd/assets/images/xtend-packages/rest-presenter/rest-presenter-banner-dark.png">
  <img alt="XtendLaravel" src="https://www.codelabx.ltd/assets/images/xtend-packages/rest-presenter/rest-presenter-banner-light.png">
</picture>

[![Latest Version on Packagist](https://img.shields.io/packagist/v/xtend-packages/rest-presenter.svg?style=flat-square)](https://packagist.org/packages/xtend-packages/rest-presenter)
[![PHP from Packagist](https://img.shields.io/packagist/php-v/xtend-packages/rest-presenter)](https://packagist.org/packages/xtend-packages/rest-presenter)
[![GitHub Tests Action Status](https://img.shields.io/github/actions/workflow/status/xtend-packages/rest-presenter/tests.yml?label=tests)](https://github.com/xtend-packages/rest-presenter/actions/workflows/tests.yml)
[![GitHub Code Style Action Status](https://img.shields.io/github/actions/workflow/status/xtend-packages/rest-presenter/code-styling.yml?label=code%20style)](https://github.com/xtend-packages/rest-presenter/actions/workflows/code-styling.yml)
[![GitHub Code Style Action Status](https://img.shields.io/github/actions/workflow/status/xtend-packages/rest-presenter/phpstan.yml?label=static%20analysis)](https://github.com/xtend-packages/rest-presenter/actions/workflows/phpstan.yml)
[![Total Downloads](https://img.shields.io/packagist/dt/xtend-packages/rest-presenter.svg?style=flat-square)](https://packagist.org/packages/xtend-packages/rest-presenter)
[![GitHub Sponsors](https://img.shields.io/github/sponsors/adam-code-labx)](https://github.com/sponsors/adam-code-labx)
[![GitHub License](https://img.shields.io/github/license/xtend-packages/rest-presenter)](https://github.com/xtend-packages/rest-presenter/blob/main/LICENSE.md)

# RESTPresenter

RESTPresenter simplifies Laravel API development by providing a lightweight package that seamlessly integrates with Laravel API Resources and Spatie's powerful Data objects.

## Starter Kits
Our initial release includes the following Starter Kits to jumpstart your development:
- [Breeze Auth Starter Kit](https://github.com/xtend-packages/rest-presenter/discussions/categories/general) (Will be replaced soon by Sanctum Auth Kit)
- [Lunar API Starter Kit](https://github.com/xtend-packages/rest-presenter/discussions/categories/lunar-starter-kit) 
- [Filament API Starter Kit](https://github.com/xtend-packages/rest-presenter/discussions/categories/filament-starter-kit) 

## Key Features

- Effortless REST API creation with Laravel API Resources.
- Simplified data transformation using our Presenter layer.
- Built-in example filters and presenters for rapid API development.
- Testing support to ensure reliability and stability.
- Automating API creation from resources in Filament.
- TypeScript auto-generation for API resource DTOs.

## Planned Features
- Release of Sponsorware API Kits for comprehensive API integration.
- Customisable kits providing a solid foundation for API development.
- Future open-sourcing of full kits upon reaching sponsorship milestones.

more to follow soon...

## What Makes This Package Unique?
RESTPresenter is more than just a CRUD generator. It offers:
- A Presenter layer for easy data transformation without modifying API resources.
- Compliance with standard features like OpenAPI, RESTful CRUD, filtering/pagination.
- Better business logic and direct access to required data for requests.
- Everything is extendable and customisable to fit your project's needs.
- API Kits to jumpstart your development with pre-built features and resources.

## Roadmap
Check out our [Roadmap](https://github.com/orgs/xtend-packages/projects/1/views/1) for upcoming features and improvements. Feel free to open an issue for suggestions or feature requests. We'll soon be launching our Discord for collaborative discussions.
Meanwhile start a discussion on GitHub to share your thoughts and ideas.

## Requirements

- PHP ^8.2
- Laravel 10+

## Installation

You can install the package via composer:

```bash
composer require xtend-packages/rest-presenter
```

After installation, the package sets up default Breeze auth scaffolding along with the users resource. You can access the register endpoint at api/v1/auth/register using API clients like Insomnia.

## Setup
Customize RESTPresenter for your project with our setup command:

```bash
php artisan rest-presenter:setup
```
Select the Starter Kits to use during setup to configure the package according to your needs. The command also publishes the configuration file rest-presenter.php to your config directory and automatically registers the RESTPresenterServiceProvider.

## So What Are Presenters?
Presenters are simply a way to transform data before it's sent to the client. They allow you to modify the data in any way you want, without modifying the API resources. This is especially useful when you need to transform data in a specific way for a particular endpoint before sending it to the client.

To use a presenter, simply add the header property `X-REST-PRESENTER: PresenterName` to your request. RESTPresenter will automatically apply the presenter to the data before sending it to the client.
Presenters can be used with collections and single resources. They can also be used with nested resources, allowing you to transform data at any level of the response.

## Usage

### Video Tutorials
https://rest-presenter.com\
Coming soon...

### Generate Resources (Prompts)
To generate a new resource, use the following command:

```bash
php artisan rest-presenter:make-resource
```
This command will guide you through creating a new resource. Prompts will allow you to automatically generate presenters, filters, data, and set up your resource ready to use. All model relationships and fields are automatically detected throughout the prompt process. Additionally, we provide a custom option for most prompts to generate without auto-detection.

### Generate Resources (Blueprint)
Coming soon, leveraging the outstanding capabilities of [Laravel Blueprint](https://blueprint.laravelshift.com/)

### Registering Kits

To register a kit, add it to the starterKits array in the register method of the RESTPresenterServiceProvider. For example:

```php
namespace App\Providers;

use Illuminate\Support\ServiceProvider;
use XtendPackages\RESTPresenter\Facades\RESTPresenter;
use XtendPackages\RESTPresenter\StarterKits\Auth\Breeze\BreezeApiKitServiceProvider;

class RESTPresenterServiceProvider extends ServiceProvider
{
    public function register(): void
    {
        RESTPresenter::register($this->app)
            ->starterKits([
                BreezeApiKitServiceProvider::class,
            ]);
    }
}
```

### Configuration

Configure RESTPresenter in the `config/rest-presenter.php` file to customize the package according to your project requirements.

## API Endpoints
Users can import this collection into their Insomnia application to quickly access and test the endpoints provided by RESTPresenter. This file is located [here](https://raw.githubusercontent.com/xtend-packages/rest-presenter/main/resources/insomnia/rest-presenter-Insomnia_2024-04-07.json)

## Testing

RESTPresenter includes a comprehensive testing suite to ensure your API's reliability and stability. Test generators will soon be added to facilitate testing when creating new resources.

## Contributing

See [CONTRIBUTING](CONTRIBUTING) for details on how to contribute to RESTPresenter.

## License

RESTPresenter is open-source software licensed under the [MIT License](LICENSE)
