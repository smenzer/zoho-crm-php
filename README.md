**Forked from [https://github.com/tristanjahier/zoho-crm-php](https://github.com/tristanjahier/zoho-crm-php)**

# Zoho CRM API wrapper library (PHP)

This is an API wrapper library for Zoho CRM, written in PHP.

It aims to cover the whole API (every module and method), while providing a great abstraction and very easy-to-use methods.

## Requirements

- PHP : `5.5+`
- PHP cURL extension enabled

## Installation

The recommended way to install this package is through [Composer](https://getcomposer.org).

Make sure to add the VCS repository in your `composer.json` file:

```json
"repositories": [{
    "type": "vcs",
    "url": "https://github.com/smenzer/zoho-crm-php"
}]
```

Then add the package in the `require` section:

```json
"require": {
    "smenzer/zoho-crm-php": "^0.3"
}
```

## Get started

This package is currently at an early development stage. Full documentation will come when it is stable enough.

### A quick example

```php
// Create a Zoho connection
$zoho = new Zoho\Crm\Connection('MY_ZOHO_AUTH_TOKEN');

// Use its supported modules to make easy queries...
$one_lead = $zoho->leads->find('1212717324723478324');
$many_leads = $zoho->leads->findMany(['8734873457834574028', '3274736297894375750']);
$all_potentials = $zoho->potentials->all()->get();
$admins = $zoho->users->admins()->get();

// ...or build them manually
$response = $zoho->newQuery('Module', 'method', ['a_parameter' => 'blablebloblu'])->execute();
$records = $response->toEntityCollection();
```
