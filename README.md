<div align="center">
  <img
    src="https://res.cloudinary.com/dgeeyohmv/image/upload/v1721158568/o0xyba5nos2wzxrpbohu.png"
    alt="Logo do VTEX Runner"
    width="141"
    height="47"
  />

  <h3>Figma Tokens</h3>

  <p>Integração entre design e código</p>

</div>

## Sobre
O Figma Tokens é uma aplicação que permite que todos os padrões criados dentro do Figma sejam exportados como código com facilidade sem a necessidade de ter conhecimentos em programação.
* O profissional UX/UI que estiver criando as interfaces, consegue enviar uma nova versão dos tokens do Design System apenas com um clique.
* A aplicação consiste no uso do plugin do Figma [Design Tokens](https://www.figma.com/community/plugin/888356646278934516/design-tokens) e o [Style Dictionary](https://amzn.github.io/style-dictionary/#/), onde o Plugin exporta um arquivo de configurações de projeto no Figma em JSON e o Style Dictionary converte para o formato mais adequado conforme a necessidade do usuário.

> [!CAUTION]
> Esse projeto é uma demonstração de uma implementação que você pode fazer em seu projeto, sendo necessário instalar as dependências e realizar configurações de acordo com sua necessidade no seu projeto original.

> [!IMPORTANT]
> Este projeto requer Node.js^16 ou superior e npm.
> ```$ npm -v && node -v```

## Como utilizar
1. Criação do token de acesso do Github:
- [Acessar as configurações do seu Github](https://github.com/settings/tokens):
  > `` Settings > Developer Settings > Personal access tokens ↓ Tokens (classic) ``
- [Criação do token de acesso do Github](https://github.com/settings/personal-access-tokens/new):
  > `` Generate new token ↓ Generate new token(classic) ``
  - Dentro da tela de criação de tokens, você deve preencher da seguinte forma:
    - Note: (Nome do Token, pode ser "Figma Token"
    - Expiration: No expiration (Pode váriar conforme seu projeto)
    - Select scopes: Atenção nessa configuração, pois ela pode váriar conforme a visibilidade do seu repositório
       - Se o seu repositório for público, marque apenas a opção "public repo"
       - Se o seu repositório for privado, marque a opção "repo"

2. Configurações do plugin Design Tokens dentro do Figma:
- Preenchimento dos campos:
  - O campo de "Server url" vai utilizar o seu nome de usuário e o nome do repositório
    - ``https://api.github.com/repos/{user}/{repo}/dispatches``
  - O campo "Acess Token" vai ser o token criado no passo anterior.
  - Inserir uma mensagem de "commit" e enviar
    
![Plugin](https://res.cloudinary.com/dgeeyohmv/image/upload/v1721177774/s9dmeuswtsn5fod29k44.gif)

4. Após a realização desses passos e clicar em "Save export", o plugin envia um evento chamado `update-tokens` e um body JSON com os tokens, acionando o evento de dispatch onde o workflow vai lidar com o build das novas alterações.

## Licença
Este projeto está licenciado sob Creative Commons Attribution-NonCommercial (CC BY-NC). Você é livre para usá-lo, desde que seja para fins não comerciais e o crédito seja dado ao criador.

<p align="center">feito por <a href="https://github.com/zmatezz">zmatezz</a></p>
