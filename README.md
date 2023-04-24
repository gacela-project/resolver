# Gacela Resolver

<p align="center">
  <a href="https://github.com/gacela-project/container/actions">
    <img src="https://github.com/gacela-project/container/workflows/CI/badge.svg" alt="GitHub Build Status">
  </a>
  <a href="https://scrutinizer-ci.com/g/gacela-project/container/?branch=main">
    <img src="https://scrutinizer-ci.com/g/gacela-project/container/badges/quality-score.png?b=main" alt="Scrutinizer Code Quality">
  </a>
  <a href="https://scrutinizer-ci.com/g/gacela-project/container/?branch=main">
    <img src="https://scrutinizer-ci.com/g/gacela-project/container/badges/coverage.png?b=main" alt="Scrutinizer Code Coverage">
  </a>
  <a href="https://shepherd.dev/github/gacela-project/container">
    <img src="https://shepherd.dev/github/gacela-project/container/coverage.svg" alt="Psalm Type-coverage Status">
  </a>
  <a href="https://github.com/gacela-project/container/blob/master/LICENSE">
    <img src="https://img.shields.io/badge/License-MIT-green.svg" alt="MIT Software License">
  </a>
</p>

## Installation

```bash
composer require gacela-project/container
```

## Usage

You can define a map between an interface and the concrete class that you want to create (or use) when that interface is found during the process of auto-wiring via its constructor. For example:

### Container

Get (create) an instance by class name.

```php
$bindings = [
  AbstractString::class => StringClass::class),
  ClassInterface::class => new ConcreteClass(/* args */)),
  ComplexInterface::class => new class() implements Foo {/** logic */}),
  FromCallable::class => fn() => new StringClass('From callable')),
];

$container = new Container($bindings);

$instance = $container->get(YourClass::class);
```

### Example

A usage example in the Gacela Framework: [AbstractClassResolver](https://github.com/gacela-project/gacela/blob/main/src/Framework/ClassResolver/AbstractClassResolver.php#L142)

