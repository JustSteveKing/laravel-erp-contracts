# Laravel ERP Contracts

This repository is a package aimed to provide a set of PHP Interfaces for module development in Laravel ERP, allowing modules to remain consistent.

# Installer Contract

This is how you implement the installer contract:

```php
<?php

declare(strict_types=1);

namespace Acme;

use JustSteveKing\Laravel\ERPContracts\Module\InstallerContract;

class ModuleInstaller implements InstallerContract
{
    public function __construct(
        private Module $module,
    ) {}
    
    public function install() : void
    {
        $this->module->runSomething();
    }
}
```
When we are installing your module we will do our best to instantiate the installer script using dependency injection, so please ensure that your installer script is instantiable. We then call the install method, which is your opportunity to perform any installation actions that you require.
