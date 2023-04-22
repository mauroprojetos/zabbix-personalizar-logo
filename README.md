# Zabbix - Módulo de Personalização de Logotipo
Este repositório contém um módulo para personalizar e renomear sua instalação de front-end do Zabbix.

# Como usar
# Passo 1: Baixe o arquivo de configuração
Baixe o arquivo brand.conf.php e salve-o na pasta do Zabbix FrontEnd, geralmente localizado em /usr/share/zabbix/local/conf/.

# Passo 2: Faça upload do logotipo
Faça upload do logotipo desejado usando a ferramenta de upload de imagens do Zabbix. Para fazer isso, siga estas etapas:

Faça login no Zabbix como administrador
Vá para "Administração" > "Geral" > "Imagens"
Faça upload da imagem desejada
Depois de concluir o upload, copie o caminho da URL da imagem. Geralmente, ele será parecido com o exemplo abaixo:

```
/imgstore.php?iconid=233

```
# Passo 3: Edite o arquivo de configuração
Edite o arquivo brand.conf.php e defina as seguintes variáveis de acordo com as informações da sua instalação:

```php
<?php
$brand = [
    'BRAND_LOGO' => '/imgstore.php?iconid=233',
    'BRAND_LOGO_SIDEBAR' => '/imgstore.php?iconid=235',
    'BRAND_LOGO_SIDEBAR_COMPACT' => '/imgstore.php?iconid=234',
    'BRAND_FOOTER' => '©NOC',
    'BRAND_HELP_URL' => 'https://www.example.com/help/'
];
```
Você pode personalizar as variáveis conforme suas necessidades. Por exemplo, se quiser ocultar os links para as páginas de Suporte Zabbix e Integrações Zabbix, basta remover as seguintes linhas:

```php
'BRAND_LOGO_SIDEBAR' => '/imgstore.php?iconid=235',
'BRAND_LOGO_SIDEBAR_COMPACT' => '/imgstore.php?iconid=234',
```
# Passo 4: Salve o arquivo de configuração
Salve o arquivo brand.conf.php após fazer as alterações.

# Passo 5: Reinicie o serviço do Zabbix
Reinicie o serviço do Zabbix para que as alterações entrem em vigor.

# Contribuindo
Se você tiver alguma sugestão ou encontrar algum problema, sinta-se à vontade para abrir uma issue neste repositório.

Licença
Este projeto é licenciado sob a licença MIT.
