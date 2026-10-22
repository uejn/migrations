# Versión de la UEJN

Fork de [CakeDC/migrations](https://github.com/CakeDC/migrations) en la tag `2.6`, la última de
la rama 2, con lo mínimo para que corra en PHP 8. Lo usa [Croogo 2](https://github.com/uejn/croogo)
y, a través de él, [AfiGestión](https://github.com/uejn/afigestion) (uejn/afigestion#430).

El paquete se sigue llamando `cakedc/migrations`. Los tags son `2.6.0.N`.

## Cambios de la UEJN

### 2.6.0.1 (22/10/2026)

- `MigrationVersion`: `each()` (eliminada en PHP 8) por `key()`/`current()`, en los dos lugares.
- `MigrationShell`: `ob_implicit_flush()` recibe `bool`.
- Necesita `uejn/cakephp` 2.10.24.2 o más nuevo: las migraciones corren dentro de una
  transacción y en MySQL un DDL la cierra solo; con PHP 8 el `commit()` rompía.
- Los tests del plugin siguen en PHPUnit 3.7 y no se corren acá: se prueba a través de los de
  Croogo.

---

CakeDC Migrations Plugin
========================

[![Bake Status](https://secure.travis-ci.org/CakeDC/migrations.png?branch=master)](http://travis-ci.org/CakeDC/migrations)
[![Downloads](https://poser.pugx.org/CakeDC/migrations/d/total.png)](https://packagist.org/packages/CakeDC/migrations)
[![Latest Version](https://poser.pugx.org/CakeDC/migrations/v/stable.png)](https://packagist.org/packages/CakeDC/migrations)

The **Migrations** plugin enables developers to quickly and easily manage and migrate between database schema versions.

As an application is developed, changes to the database may be required, and managing that in teams can get extremely difficult. The **Migrations** plugin enables you to share and coordinate database changes in an iterative manner, removing the complexity of handling these changes.

* **Console:** The console script allows you to run migrations up and down.
* **Installation:** Migrations can also be run programmatically via an installer script.
* **ORM:** The **Migrations** plugin makes use of the *CakePHP* ORM and supports all databases provided by the framework.

This is NOT a Backup Tool
-------------------------

We highly recommend to not run the **Migrations** plugin in a production environment directly *without* doing a backup first.

However, you can make use of the ```before()``` and ```after()``` callbacks in the migration files to add logic which triggers a backup script.

Requirements
------------

* CakePHP 2.5+ (We recomment latest 2.x)
* PHP 5.3.0+ (We recommend php 7+)

Documentation
-------------

For documentation, as well as tutorials, see the [Docs](Docs/Home.md) directory of this repository.

Support
-------

For bugs and feature requests, please use the [issues](https://github.com/CakeDC/migrations/issues) section of this repository.

Commercial support is also available, [contact us](http://cakedc.com/contact) for more information.

Contributing
------------

This repository follows the [CakeDC Plugin Standard](http://cakedc.com/plugin-standard). If you'd like to contribute new features, enhancements or bug fixes to the plugin, please read our [Contribution Guidelines](http://cakedc.com/contribution-guidelines) for detailed instructions.

License
-------

Copyright 2007-2014 Cake Development Corporation (CakeDC). All rights reserved.

Licensed under the [MIT](http://www.opensource.org/licenses/mit-license.php) License. Redistributions of the source code included in this repository must retain the copyright notice found in each file.
