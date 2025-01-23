# MegaMan Boss API

## Contexto
Este projeto é uma API desenvolvida em .NET Core, com o objetivo de fornecer informações sobre os chefes ("bosses") do jogo MegaMan. A API retorna os dados no formato JSON com o seguinte modelo:

```json
{
  "Id": 1,
  "Code": "DLN/DRN-003",
  "Name": "Cutman",
  "HP": 150,
  "Picture": "https://vignette.wikia.nocookie.net/megaman/images/2/22/Cutman.png"
}
```

## Tecnologias Utilizadas
- **.NET Core 3.1**
- **Entity Framework Core 3.1.8** (para manipulação e persistência de dados)
- **Newtonsoft.Json 12.0.2** (para serialização e manipulação de JSON)
- **SQL Server** (banco de dados relacional)

## Estrutura do Projeto
O projeto segue o formato padrão de uma API ASP.NET Core:

- **Controllers:** Contém os controladores responsáveis por definir os endpoints da API.
- **Models:** Define as classes que representam os dados, como o modelo de Boss.
- **Data:** Contém o contexto do Entity Framework Core para interação com o banco de dados.

## Instalação e Configuração
1. Certifique-se de ter o **.NET Core SDK 3.1** instalado.
2. Clone o repositório para sua máquina local:
   ```bash
   git clone https://github.com/seu-repositorio/megaman-boss-api.git
   cd megaman-boss-api
   ```
3. Restaure as dependências do projeto:
   ```bash
   dotnet restore
   ```
4. Configure o banco de dados no arquivo `appsettings.json`:
   ```json
   {
     "ConnectionStrings": {
       "DefaultConnection": "Server=seu-servidor;Database=megaman-db;User Id=seu-usuario;Password=sua-senha;"
     }
   }
   ```
5. Execute as migrações para criar as tabelas do banco de dados:
   ```bash
   dotnet ef database update
   ```

## Uso
Para rodar a API localmente:
```bash
dotnet run
```
A API estará disponível em `http://localhost:5000` ou `https://localhost:5001`.

### Endpoints Disponíveis

- **GET /api/bosses**
  - Retorna a lista de todos os bosses.
- **GET /api/bosses/{id}**
  - Retorna os detalhes de um boss específico pelo ID.
- **POST /api/bosses**
  - Adiciona um novo boss. Requer um corpo JSON com os seguintes campos:
    ```json
    {
      "Code": "DLN/DRN-004",
      "Name": "Gutsman",
      "HP": 200,
      "Picture": "https://vignette.wikia.nocookie.net/megaman/images/1/1e/Gutsman.png"
    }
    ```
- **PUT /api/bosses/{id}**
  - Atualiza as informações de um boss específico.
- **DELETE /api/bosses/{id}**
  - Remove um boss pelo ID.

## Pacotes Utilizados
- **Microsoft.EntityFrameworkCore**: Para interagir com o banco de dados usando o padrão ORM.
- **Microsoft.EntityFrameworkCore.Design**: Necessário para comandos de migração e scaffolding.
- **Microsoft.EntityFrameworkCore.SqlServer**: Provedor do Entity Framework Core para SQL Server.
- **Newtonsoft.Json**: Manipulação avançada de JSON.

## Contribuição
Contribuições são bem-vindas! Sinta-se à vontade para abrir issues ou enviar pull requests.

1. Faça um fork do projeto.
2. Crie uma nova branch para suas alterações:
   ```bash
   git checkout -b minha-branch
   ```
3. Commit suas alterações:
   ```bash
   git commit -m "Descrição das alterações"
   ```
4. Envie sua branch:
   ```bash
   git push origin minha-branch
   ```
5. Abra um pull request no repositório original.

## Licença
Este projeto está licenciado sob a [MIT License](LICENSE).
