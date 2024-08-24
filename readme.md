# Como usar?

Renomeio o arquivo .env.example para .env e faça as configurações no mesmo.

No arquivo docker-composer.yaml escolha uma senha/chave api para EvolutionAPI, no lugar de "EvolutionAPIKey" ou deixe assim mesmo se não se importar.

Na pasta principal rode o comando: 
```shel
docker compose up -d
```
Rode também:
```shel
composer update 
```
Acesse a página html/zap_login.php para fazer login no WhatsApp.

Agora já pode usar como desejar:
```php
<?php
require_once __DIR__ . "/bootstrap.php";
$Notify = new \App\Notify();
// envia mensagem para um número do WhatsApp
$Notify->sendZap('Sua mensagem para WhatsApp', '5511');

// Envia menagem de e-mail
$Notify->senMail('Assunto de Email', 'Conteúdo do e-mail');
```

# Correios 
Como exemplo também tem o script /crons/correios.php
Se desejar utilizá-lo importe a base sql notify.sql

Vai precisar colocar o código de rastreio na tabela "track"