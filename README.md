<h1 style="text-align: center"> WhatsApp API Multi Dispositivos</h1>
<p style="text-align: center">
<a href="#"><img title="skynet" src="https://img.shields.io/badge/whatsapp api nodejs Multi Dispositivos-black?style=for-the-badge" alt=""></a>
</p>
<p style="text-align: center">
<a href="https://github.com/salman0ansari/whatsapp-api-nodejs"><img title="Followers" src="https://img.shields.io/github/followers/andersonsouzabass?color=black&style=flat-square" alt=""></a>
<a href="https://github.com/salman0ansari/whatsapp-api-nodejs"><img title="Stars" src="https://img.shields.io/github/stars/andersonsouzabass/whatsapp-api-nodejs?color=black&style=flat-square" alt=""></a>
<a href="https://github.com/andersonsouzabass/whatsapp-api-nodejs/network/members"><img title="Forks" src="https://img.shields.io/github/forks/andersonsouzabass/whatsapp-api-nodejs?color=black&style=flat-square" alt=""></a>

---

Uma implementação do [Baileys](https://github.com/adiwajshing/Baileys/) como um serviço de API RESTful simples com suporte a vários dispositivos, basta baixar, instalar e começar a usar, simples assim.

# Libraries Utilizadas

-   [Baileys](https://github.com/adiwajshing/Baileys/)
-   [Express](https://github.com/expressjs/express)

# Instalação
1. Instale o docker e o docker-compose
2. Instale o yarn
3. Baixe ou clone este repositório.
4. Entre no diretório do projeto.
5. Execute `yarn install` para instalar as dependências.
6. Copie `.env.example` para `.env` e defina as variáveis de ambiente.

# Docker Compose

1. Siga o procedimento de instalação
2. Atualize .env, encontre o trecho abaixo e defina desta maneira
```
MONGODB_ENABLED=true
MONGODB_URL=mongodb://mongodb:27017/whatsapp_api
```

3. Defina seu `TOKEN=` com a sua senha personalizada, aqui é definida a senha de acesso para a sua API.
4. Executar o comando abaixo:

```
docker-compose up -d
```

# Configuração

Edite variáveis de ambiente em `.env`

```a
Importante: Você deve definir TOKEN= como uma string aleatória para proteger a rota.
```

```env
# ==================================
# SECURITY CONFIGURATION
# ==================================
TOKEN=RANDOM_STRING_HERE
```

# Uso

1. `Desenvolvimento:` Execute `yarn dev`
2. `Produção:` Execute `yarn start`

## Gere instância básica usando chave aleatória

Para gerar uma chave de instância
Usando a rota:

```bash
curl --location --request GET 'localhost:3333/instance/init' \
--data-raw ''
```

Response:

```json
{
    "error": false,
    "message": "Initializing successfull",
    "key": "d7e2abff-3ac8-44a9-a738-1b28e0fca8a5"
}
```

## Gere instância personalizada com chave personalizada e webhook personalizado

Para gerar uma instância personalizada
Usando a rota:

```bash
curl --location --request GET 'localhost:3333/instance/init?key=CUSTOM_INSTANCE_KEY_HERE&webhook=true&webhookUrl=https://webhook.site/d7114704-97f6-4562-9a47-dcf66b07266d' \
--data-raw ''
```

Response:

```json
{
    "error": false,
    "message": "Initializing successfull",
    "key": "CUSTOM_INSTANCE_KEY_HERE"
}
```

# Usando a chave

Salve o valor da `chave` da resposta. Em seguida, use esse valor para chamar todas as rotas.

## Postman Docs

Todas as rotas estão disponíveis como uma postman collection.

-   https://documenter.getpostman.com/view/12514774/UVsPQkBq

## QR Code

Visite [http://localhost:3333/instance/qr?key=INSTANCE_KEY_HERE](http://localhost:3333/instance/qr?key=INSTANCE_KEY_HERE) para visualizar o QR Code e digitalizar com o seu dispositivo. Se você demorar muito para escanear o QR Code, será necessário atualizar a página.

## Enviar Mensagem

```sh
# /message/text?key=INSTANCE_KEY_HERE&id=PHONE-NUMBER-WITH-COUNTRY-CODE&message=MESSAGE

curl --location --request POST 'localhost:3333/message/text?key=INSTANCE_KEY_HERE' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'id=919999999999' \
--data-urlencode 'message=Hello World'
```

Veja todas as rotas aqui [src/api/routes](https://github.com/andersonsouzabass/api_whatsapp/tree/main/src/api/routes)

# Nota

Não posso garantir ou ser responsabilizado se você for bloqueado ou banido ao usar este software. O WhatsApp não permite que bots usem métodos não oficiais em sua plataforma, portanto, isso não deve ser considerado totalmente seguro.

# Legal
- Este código não é de forma alguma afiliado, autorizado, mantido, patrocinado ou endossado pela WA (WhatsApp) ou por qualquer uma de suas afiliadas ou subsidiárias.
- O site oficial do WhatsApp pode ser encontrado em https://whatsapp.com. "WhatsApp", bem como nomes, marcas, emblemas e imagens relacionados, são marcas registradas de seus respectivos proprietários.
- Este é um software independente e não oficial Use por sua conta e risco.
- Não faça spam com isso.
