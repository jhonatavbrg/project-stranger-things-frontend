# Habilidades

Nesse projeto, você será capaz de:
  - Publicar aplicações através do `Heroku`;
  - Visualizar logs das suas aplicações publicadas;
  - Monitorar suas aplicações publicadas;
  - Utilizar variáveis de ambiente dentro do `Heroku`;
  - Instalar, utilizar e aproveitar os principais recursos do `PM2`;
  - Fazer deploy no `Heroku` aproveitando recursos de um process manager.

---

### Frontend

O frontend consiste em um projeto simples utilizando React.

Trata-se de um frontend bem simples que vai se comunicar com a nossa API. Ele possui as seguintes funcionalidades:

- Uma tabela para exibição da resposta da nossa API;

- Um campo de pesquisa para filtro de **nome**;

- Botões de navegação para paginação;

- Um botão para ativar o modo `Mundo Invertido` no frontend.

Todas essas funcionalidades estão implementadas no componente `StrangerThings`.

---

#### Modo `upside down` - Frontend

Assim como no backend, o frontend também possui um modo "Mundo Invertido". Esse modo é ativado e desativado com o botão "Mudar de Realidade".

A ideia é a seguinte: inicialmente, o frontend possui uma imagem de background e utiliza o service instanciado com a configuração contida na variável `strangerThingsConfig`. Ao ativar o Mundo Invertido, a imagem de background é alterada e passamos a utilizar o serviço instanciado com a configuração `upsideDownConfig`.

Desse modo, ao "alternar entre os universos", vamos realizar chamadas a API's diferentes.

No exemplo pré-programado, em um dos "universos", chamamos um serviço na porta `3002` e o outro serviço na porta `3003`. Exploraremos esse comportamento durante o projeto.

---

# Requisitos do projeto

### Frontend

#### 7 - Verifica as variáveis de ambiente do frontend

Altere o frontend para utilizar variáveis de ambiente para controlar as **URLs** e **Timeouts** de comunicação com a API.

Perceba que o código está esperando por duas **APIs**. Uma para o modo `upside-down` e a outra para o modo normal.

O nome das variáveis deve ser o seguinte:

- Para seu back-end hawkins:
  - REACT_APP_HAWKINS_URL para a URL;
  - REACT_APP_HAWKINS_TIMEOUT para o timeout;

- Para seu back-end UPSIDEDOWN:
  - REACT_APP_UPSIDEDOWN_URL para a URL;
  - REACT_APP_UPSIDEDOWN_TIMEOUT para o timeout;

#### 8 - Verifica se foi feito o deploy do frontend no Heroku

**IMPORTANTE**: Assim como no backend, a variável de ambiente GITHUB_USER

deverá ser criada com o seu usuário do github.

Faça o deploy do front-end:

   1. Crie um app do Heroku com o front-end. Não é necessário a criação do `Procfile` aqui. Vamos deixar o Heroku utilizar as configurações padrões. No momento de criar o app do Heroku, utilize o `buildpack` descrito abaixo, em **Dicas**.

   2. O nome do seu app no heroku deve ser seu nome de usuário do github seguido de "-ft". Por exemplo, se o seu usuário do github for "student", o nome do seu app será "student-ft" e a url ***precisar ser*** https://student-ft.herokuapp.com/.

   2. Configure as variáveis de ambiente do app para apontar para as API's publicadas.

   3. Faça o deploy com o git.

**Dicas**:

Para publicar seu frontend React, utilize o buildpack [mars/create-react-app](https://elements.heroku.com/buildpacks/mars/create-react-app-buildpack).

Lembre-se de que é possível testar o comportamento definindo as variáveis de ambiente em sua máquina. Você pode fazê-las apontar tanto para o backend rodando localmente em sua máquina, quanto para as APIs já publicadas nos requisitos anteriores.

### Bônus

#### 9 - Verifica os multi-ambientes e modo de desenvolvimento.

Utilize a estratégia de multi-ambientes no frontend. Para isso:

   - Renomeie o *remote* atual para `development`;

   - Refaça o deploy com um item no frontend que identifique o layout como rodando em modo de "desenvolvimento". Esse tag item **deve** conter o texto "Em desenvolvimento"

   - Crie um novo app no heroku cujo nome deve ser seu nome de usuário do github seguido de "-pd". Por exemplo, se o seu usuário do github for "student", o nome do seu app será "student-pd" e a url ***precisar ser*** https://student-pd.herokuapp.com/.

   - Lembre-se que a boa prática para essa situação é criar uma variável de ambiente para controlar esse comportamento, configurando-a para ter um valor diferente em cada um dos ambientes.
