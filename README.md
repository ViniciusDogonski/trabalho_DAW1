
---

# Configuração do Projeto Nest.js e Vue.js

Este guia fornece instruções passo a passo para configurar um projeto usando o Nest.js para o back-end e o Vue.js para o front-end. As instruções são divididas em várias etapas para facilitar a configuração.

## Passo 1: Preparação Inicial

1. Crie uma pasta para o projeto e navegue até ela pelo terminal:

```bash
mkdir Projeto-Nest
cd Projeto-Nest
```

2. Atualize os pacotes do sistema (opcional, mas recomendado):

```bash
sudo apt update
sudo apt upgrade
```

3. Instale o Volta para gerenciar versões do Node.js:

```bash
curl https://get.volta.sh | bash
export VOLTA_HOME="$HOME/.volta"
export PATH="$VOLTA_HOME/bin:$PATH"
```

4. Verifique a instalação do Volta:

```bash
volta --version
```

5. Instale a versão LTS mais recente do Node.js:

```bash
volta install node
```

6. Verifique a instalação do Node.js:

```bash
node -v
```

7. Instale o npm (Node Package Manager):

```bash
npm -v
```

8. Configure o ambiente virtual do projeto:

```bash
volta pin node@18.17.1
volta pin npm@9.6.7
```

## Passo 2: Configuração do Back-End com NestJS

1. Instale o Nest CLI globalmente:

```bash
npm install -g @nestjs/cli
```

2. Crie um novo projeto NestJS:

```bash
nest new backend
```

3. Navegue para a pasta do projeto:

```bash
cd backend
```

## Passo 3: Configuração do Banco de Dados MongoDB

1. Baixe e instale o MongoDB Community Server para o seu sistema operacional.

2. Verifique a versão do Linux:

```bash
lsb-release -a
```

3. Inicie o serviço do MongoDB:

```bash
sudo systemctl start mongod
```

4. Baixe e instale a interface gráfica MongoDB Compass.

5. Abra o MongoDB Compass e configure a URI de acesso ao banco de dados.

6. No arquivo app.module.ts do NestJS, configure a conexão com o MongoDB:

```typescript
import { Module } from '@nestjs/common';
import { MongooseModule } from '@nestjs/mongoose';

@Module({
  imports: [
    MongooseModule.forRoot('mongodb://localhost:port/nome-do-banco-de-dados', {
      useNewUrlParser: true,
      useUnifiedTopology: true,
    }),
    // Outros módulos
  ],
  controllers: [],
  providers: [],
})
export class AppModule {}
```

## Passo 4: Configuração do Front-End com Vue.js

1. Volte para o diretório principal do projeto:

```bash
cd ..
```

2. Instale o Vue CLI globalmente:

```bash
npm install -g @vue/cli
```

3. Crie um novo projeto Vue.js:

```bash
vue create frontend
```

## Passo 5: Integração entre Back-End e Front-End

1. Navegue para a pasta do projeto Vue.js:

```bash
cd frontend
```

2. Instale o pacote axios para fazer solicitações HTTP ao back-end:

```bash
npm install axios
```

3. Crie chamadas de API no Vue.js para se comunicar com o servidor NestJS.

## Passo 6: Execução dos Projetos

1. Inicie o servidor NestJS:

```bash
npm run start:dev
```

2. Inicie o servidor de desenvolvimento Vue.js:

```bash
npm run serve
```

Agora, o back-end do NestJS estará rodando em um servidor local e o front-end Vue.js será servido em outro servidor. Lembre-se de que essa é uma configuração básica e você pode ajustá-la conforme necessário ao desenvolver seu projeto.

---
