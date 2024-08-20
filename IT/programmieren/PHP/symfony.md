# Symfony Version 5

Create new webapp

&> symfony new symfony6 --version="6.4.*" --webapp

## Controller
A controller is the PHP function you write that builds the page. You take the incoming request information and use it to create a Symfony Response object, which can hold HTML content, a JSON string or even a binary file like an image or PDF.

$> symfony console make:controller TestController

## Routes
Show all routes

$> php bin/console debug:router

Use annotations

$> composer require doctrine/annotations



## Templates 
Rendering a template

$> composer require twig
