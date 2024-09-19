# Tarana

## Description

This is a basic client for the Tarana API. It uses the EasySwagger library, but contains the Tarana swagger JSON file.

## Usage

### Environment variables

You can specify parameters in the constructor, but if any are left out, these environment variables will be used instead.

TARANA_API_TOKEN - Authentication token for API

TARANA_HOST - URL of server API

### Instantiate

Create an instance of the Tarana object.

```
$tarana = new Ocolin\Tarana\Tarana();
```

#### Parameters

$host: Name of the Tarana host server. If null, will use .env field.

$api_key: Authentication token for server. If null, will use .env field.

$api_file: Path to Swagger JSON file. If null, will use included file.

$local: If true, it will try to load .env file in root directory.

### Making a call

```
$output = $tarana->path( 
    path: '/v1/network/regions',
    data: [ 'count' => '10' ]
);
```

#### Parameters

$path: REQUIRED - Swagger call path, including named parameters.

$data: Array of parameters name/values to use for URI path or body.

$method: HTTP method. Defaults to GET.