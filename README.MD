<table align="center">
    <tr>
        <td align="center" width="25%">
            <img src="https://vignette.wikia.nocookie.net/megaman/images/2/22/Cutman.png" alt="Megaman" >
        </td>
        <td align="center" width="75%">
          
# Megaman API

<br/>
<br/>

<sup><b>(MEGA-MAN-ROBOTS)</b></sup></sub>

<br/>
<br/>
          
[![Latest release](https://img.shields.io/github/v/release/felipeAguiarCode/MegaApiDotnetCore)](https://github.com/MegaApiDotnetCore/releases/latest)

</table>

<p align="center">
  Megaman API é uma aplicação backend desenvolvida em .NET Core, cujo objetivo é listar os dados e status dos bosses do jogo Megaman, retornando as informações no formato JSON. 
  A API pode ser usada para fornecer dados sobre os robots/bosses para outros sistemas ou frontends.
  <br />
</p>

<p align="center">
  A API utiliza a arquitetura **RESTful**, é construída com **.NET Core 3.1** e suporta operações básicas como listagem, consulta e envio de dados de bosses.
  <br>
  Mais detalhes sobre como usar a API estão disponíveis na seção **Uso** abaixo.
</p>

<p align="center">
<br/>
<img src="./_docs/assets/carbon.png"/>
</p>

## Uso

Para rodar essa API localmente, siga os passos abaixo:

1. Clone o repositório para sua máquina local.
2. Abra o projeto no **Visual Studio** ou **Visual Studio Code**.
3. Restaure as dependências do projeto executando o comando:

   ```bash
   dotnet restore
   ```

4. Caso seja necessário configurar o banco de dados, crie e aplique as migrações executando:

   ```bash
   dotnet ef migrations add InitialCreate
   dotnet ef database update
   ```

5. Para rodar a aplicação, execute o seguinte comando:

   ```bash
   dotnet run
   ```

6. A API estará disponível em `http://localhost:5000` ou o endereço configurado para sua aplicação.

## Endpoints

Aqui estão os endpoints disponíveis para consumir a API:

<table align="center">
    <thead>
        <tr>
            <th>Metodo</th>
            <th>Endpoint</th>
            <th>Descrição</th>
            <th>Exemplo de Resposta</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>GET</td>
            <td>/api/v1/robots</td>
            <td>Retorna uma lista de todos os robots/bosses.</td>
            <td>
                ```json
                [
                  {
                    "Id": 1,
                    "Code": "DLN/DRN-003",
                    "Name": "Cutman",
                    "HP": 150,
                    "Picture": "https://vignette.wikia.nocookie.net/megaman/images/2/22/Cutman.png"
                  }
                ]
                ```
            </td>
        </tr>
        <tr>
            <td>GET</td>
            <td>/api/v1/robots/{id}</td>
            <td>Retorna os detalhes de um boss específico baseado no `id`.</td>
            <td>
                ```json
                {
                  "Id": 1,
                  "Code": "DLN/DRN-003",
                  "Name": "Cutman",
                  "HP": 150,
                  "Picture": "https://vignette.wikia.nocookie.net/megaman/images/2/22/Cutman.png"
                }
                ```
            </td>
        </tr>
        <tr>
            <td>POST</td>
            <td>/api/v1/robots</td>
            <td>Endpoint para enviar dados de um novo robot (funcionalidade a ser implementada).</td>
            <td>
                ```json
                {
                  "message": "Robot enviado com sucesso"
                }
                ```
            </td>
        </tr>
    </tbody>
</table>

## Técnicas Utilizadas

O projeto utiliza as seguintes tecnologias e abordagens:

<table align="center">
    <thead>
        <tr>
            <th>Técnica</th>
            <th>Descrição</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>.NET Core 3.1</td>
            <td>Framework utilizado para desenvolver a API, proporcionando uma plataforma rápida, moderna e robusta.</td>
        </tr>
        <tr>
            <td>Entity Framework Core</td>
            <td>ORM utilizado para realizar operações no banco de dados de forma eficiente e simplificada.</td>
        </tr>
        <tr>
            <td>RESTful API</td>
            <td>Arquitetura de comunicação entre sistemas, baseada em recursos, onde os dados são manipulados através de operações HTTP (GET, POST, PUT, DELETE).</td>
        </tr>
        <tr>
            <td>JSON</td>
            <td>Formato de dados utilizado para a comunicação entre cliente e servidor, tornando a integração fácil e ágil.</td>
        </tr>
        <tr>
            <td>Swagger</td>
            <td>Utilizado para gerar uma documentação interativa da API, facilitando o teste e consumo pelos desenvolvedores.</td>
        </tr>
    </tbody>
</table>

## Dependências

Este projeto utiliza as seguintes dependências, que são essenciais para seu funcionamento:

<table align="center">
    <thead>
        <tr>
            <th>Dependência</th>
            <th>Descrição</th>
            <th>Link</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>[Microsoft.EntityFrameworkCore](https://docs.microsoft.com/en-us/ef/core/)</td>
            <td>ORM para interação com o banco de dados relacional.</td>
            <td><a href="https://docs.microsoft.com/en-us/ef/core/">Link</a></td>
        </tr>
        <tr>
            <td>[Microsoft.EntityFrameworkCore.Design](https://docs.microsoft.com/en-us/ef/core/cli/dbcontext-creation)</td>
            <td>Ferramentas de design para o Entity Framework Core, necessárias para a criação de migrações.</td>
            <td><a href="https://docs.microsoft.com/en-us/ef/core/cli/dbcontext-creation">Link</a></td>
        </tr>
        <tr>
            <td>[Microsoft.EntityFrameworkCore.SqlServer](https://docs.microsoft.com/en-us/ef/core/providers/sql-server/)</td>
            <td>Provedor SQL Server para o Entity Framework Core.</td>
            <td><a href="https://docs.microsoft.com/en-us/ef/core/providers/sql-server/">Link</a></td>
        </tr>
        <tr>
            <td>[Newtonsoft.Json](https://www.newtonsoft.com/json)</td>
            <td>Biblioteca para serialização e desserialização de JSON em .NET.</td>
            <td><a href="https://www.newtonsoft.com/json">Link</a></td>
        </tr>
    </tbody>
</table>

## Estrutura do Projeto

A estrutura de pastas do projeto é organizada da seguinte maneira:

```plaintext
.vs
.vscode
bin
Controllers
Database
middlewares
Models
obj
Properties
Services
appsettings.Development.json
appsettings.json
global.json
MegamanApi.csproj
MegamanApi.sln
Program.cs
Startup.cs
```

### Descrição das Pastas:
- **.vs** e **.vscode**: Pastas criadas pelo Visual Studio e VS Code, respectivamente, para armazenar configurações do ambiente de desenvolvimento.
- **bin**: Diretório onde os arquivos compilados da aplicação são armazenados.
- **Controllers**: Contém os controladores que gerenciam os endpoints da API.
- **Database**: Diretório onde as interações com o banco de dados, como migrações, estão localizadas.
- **middlewares**: Contém middlewares que processam as requisições e respostas da API.
- **Models**: Contém as classes de modelo que representam a estrutura dos dados dos robots (bosses).
- **obj**: Diretório gerado durante o processo de compilação, contendo arquivos temporários.
- **Properties**: Contém arquivos de configuração relacionados ao projeto.
- **Services**: Contém a lógica de negócios e serviços para manipulação de robots.
- **appsettings.Development.json** e **appsettings.json**: Arquivos de configuração para diferentes ambientes de execução.
- **global.json**: Arquivo de configuração que especifica a versão do SDK do .NET Core.
- **MegamanApi.csproj**: Arquivo do projeto que define as dependências e configurações.
- **MegamanApi.sln**: Arquivo de solução que organiza o projeto no Visual Studio.
- **Program.cs**: Arquivo de entrada da aplicação.
- **Startup.cs**: Arquivo de configuração que define os serviços e o pipeline HTTP da aplicação.

## Arquitetura

```🌐
src
├── 📂 Controllers      [Routes for endpoints]
├── 📂 Models           [Database models]
├── 📂 Services         [Business rules]
├── 📂 Middlewares      [Intermediate functions between the HTTP request and the final server response]
├── 📂 Database         [Structures related to the database]
│   ├── 📂 DTOs             [Input Models and View Models (Data Transfer Objects)]
│   ├── 📂 EntityFramework  [Files related to the ORM Entity Framework]
│   │     ├── 📂 Context         [Entity context settings]
│   │     ├── 📂 Migrations      [Migrations for database updates]
│   ├── 📂 Repositories     [Repository pattern]
```

## Licença

Este software está licenciado sob a [MIT License](LICENSE).

⌨️ Obrigado Felipe Aguiar da DIO
<br/> 
[GitHub do Felipe - Criador desta API](https://github.com/felipeAguiarCode)