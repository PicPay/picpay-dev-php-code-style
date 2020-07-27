# picpay-dev-php-code-style
Estilo de código PHP para projetos do PicPay usando [PHP_CodeSniffer Standards Composer Installer Plugin](https://github.com/Dealerdirect/phpcodesniffer-composer-installer)


# Como usar

1 - Adicione no composer.json 

```json
"require-dev": {
     "picpay/picpay-dev-php-code-style": "1.0.*"
},
"repositories": [
        {
            "type": "vcs",
            "url": "https://github.com/PicPay/picpay-dev-php-code-style.git"
        }
]        
```

2 - Crie um arquivo codesize.xml na raiz do projeto

```xml
<?xml version="1.0"?>
<ruleset>
    <arg name="basepath" value="."/>
    <arg name="extensions" value="php"/>
    <arg name="parallel" value="45"/>
    <arg name="cache" value=".phpcs-cache"/>
    <arg name="colors"/>

    <!-- Para ignorar -->
    <arg value="nps"/>

    <file>src</file>
    <file>tests</file>

    <rule ref="PicPay"/>
    <!-- Alguma regra customizada do seu projeto -->

</ruleset>
```
3 - Veja se foi instalado corretamente
```
./vendor/bin/phpcs -i
```


![image](https://user-images.githubusercontent.com/18670067/88567067-59ebcf80-d00d-11ea-8fcb-eec1140e5c70.png)
