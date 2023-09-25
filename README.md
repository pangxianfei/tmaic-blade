# Think-Blade 8.x
thinkphp 8.0 blade 视图渲染驱动  
blade版本: v9.52.15 

## Installation
```
composer require tmaic/blade
```

#### view.php
```php
<?php
[
    // 模板引擎类型
    'type'         => 'blade',
    // 默认模板渲染规则 1 解析为小写+下划线 2 全部转换小写 3 保持操作方法
    'auto_rule'    => 1,
    // 模板目录名
    'view_dir_name'=> 'view',
    // 模板后缀
    'view_suffix'  => 'blade.php',
    // 模板文件名分隔符
    'view_depr'    => DIRECTORY_SEPARATOR,
    // 编译缓存
    'tpl_cache'     => true,
];
```


### auth 支持 (自行实现并绑定到以下命名)
- app->bind('auth', concrete::class)
  - auth->check(): bool
  - auth->guest(): bool
- app->bind('auth.gate', concrete::class)
  - auth->check($abilities, $arguments): bool
  - auth->denies($abilities, $arguments): bool
  - auth->any($abilities, $arguments): bool

