# Desafio Técnico - Full Stack Junior

## Candidato
  *Nome:* Allex Thiago Santos Rosa
  <br/>
  *Linkedin:* https://www.linkedin.com/in/allexthiagosantosrosa/
  <br/>
  *GitHub:* https://github.com/AllexThiagoSR/
  <br/>
  *Telefone(WhatsApp):* (99) 99127-3808
  <br/>
  *Email:* allexthiagodev@gmail.com

## Tecnologias Utilizadas
  - TypeScript
  - Tailwind Css
  - Nextjs

## O que é preciso para rodar a aplicação localmente?

  - Git
  - Node

## Como rodar a aplicação localmente?

  Clonar esse repositório na sua máquina

  ```bash
  $ git clone https://github.com/AllexThiagoSR/fullstack-junior-1
  ```

  Mudar para a branch main se não estiver nela ainda

  ```bash
  $ git checkout main
  ```

  Entrar na pasta <b>*my-app*</b>

  ```bash
  $ cd my-app
  ```

  Instalar as dependências do app

  ```bash
  $ npm install
  ```

  Rodar a aplicação em desenvolvimento
  ```bash
  $ npm run dev
  ```

  ou

  Rodar como se estivesse em produção
  ```bash
  $ npm run build
  $ npm run start
  ```

  Pronto! Agora a aplicação está rodando na porta 3000 do localhost, basta acessar http://localhost:3000 no seu navegador

# Frontend

### Hero Section escolhida

<img width="100%" align="center" src="./hero-section.png" />

### 

# Backend

  URL base: http://localhost:3000/api/

### Secret

  Todas as rotas tem uma verificação de secret que caso não seja informado ou informado o secret incorreto seré enviado a seguinte resposta
  ```json
  {
    "message": "You don't have access to this route."
  }
  ```

## Obter todos os trabalhos

### Requisição

  `GET /jobs`

    http://localhost:3000/api/jobs

    headers: {
      "secret": "string"
    }

    query: {
      "level": "string | undefined"
    }

### Resposta - 200 - OK
  Caso a requisição seja feita corretamente
  ```json
  [
    {
      "id": 1,
      "job": "Full Stack Developer",
      "level": "Junior",
      "status": "open"
    },
    {
      "id": 2,
      "job": "Frontend Developer",
      "level": "Junior",
      "status": "closed"
    },
    {
      "id": 3,
      "job": "Backend Developer",
      "level": "Junior",
      "status": "closed"
    },
    {
      "id": 4,
      "job": "Full Stack Developer",
      "level": "Senior",
      "status": "closed"
    }
  ]
  ```

## Obter um trabalho pelo seu ID

### Requisição

  `GET /jobs/:id`

    http://localhost:3000/api/jobs/1

    headers: {
      "secret": "string"
    }

### Resposta - 200 - OK
  Caso a requisição seja feita corretamente
  ```json
  {
    "id": 1,
    "job": "Full Stack Developer",
    "level": "Junior",
    "status": "open"
  }
  ```

### Resposta - 404 - NOT FOUND
  Caso o trabalho com o id informado não exista
  ```json
  {
    "message": "Job not found."
  }
  ```

## Aplicar-se a uma posição

### Requisição

  `POST /jobs/submit`

    http://localhost:3000/api/jobs/submit

    headers: {
      "secret": "string"
    }

    body: {
      "name": "string",
      "age": "number",
      "phone": "string",
      "state":"string",
      "city": "string"
    }

### Resposta - 200 - OK
  Caso a requisição seja feita corretamente
  ```json
  {
    "message": "Thank you for your application, Applicant Name"
  }
  ```

### Resposta - 400 - BAD REQUEST
  Caso algum campo não tenha sido preenchido ou preenchido com um valor inválido será enviada uma mensagem relacionada ao campo que está faltando ou incorreto, caso não seja enviado nada a seguinte resposta será retornada:
  ```json
  {
    "message": "No fields sent."
  }
  ```
  
