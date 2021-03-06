# Modelo de API .NET Core + DDD

O **modelo.api.net** é um projeto open source, escrito em .Net Core. À partir dele, é possível ter uma arquitetura simplificada baseando-se no DDD (Design Domain Driven).

O projeto foi agrupado da seguinte maneira:

- **Modelo.Application** - Http Request, Http Response 
- **Modelo.Domain** - Definição de entidades; Definição de contratos
- **Modelo.Infra.Data** - Camada de Infraestrutura - Dados de contexto do banco de dados; Mapeamento de entidades
- **Modelo.Infra.CrossCutting** - Camada de Infraestrutura - Recursos técnicos genéricos utilizados por todas as camadas; Envio de mensagem; Injeção de dependências; Envio de e-mails;

## Tecnologias  implementadas

* FluentValidation.AspNetCore
* Microsoft.EntityFrameworkCore.Design
* Microsoft.EntityFrameworkCore.Tools
* Pomelo.EntityFrameworkCore.MySql
* MySqlConnector

## Configurações

### Modificar Context

Neste repositório foi utilizado como exemplo o banco MySQL. Atualmente é necessário alterar o arquivo `MySqlContext.cs` informando os dados de conexão com o servidor.

### Criar tabela User

```database
CREATE TABLE `User` ( `Id` INT NOT NULL , `Cpf` VARCHAR(255) NOT NULL , `BirthDate` DATE NOT NULL , `Name` VARCHAR(255) NOT NULL );
```

### Incluir usuário inicial

```database
INSERT INTO `User` (`Id`, `Cpf`, `BirthDate`, `Name`) VALUES ('1', '01569347603', '1989-06-30', 'vinicius');
```

## Referências

- [Projeto original](https://github.com/alex250195/Modelo.Api)
- [Uma nova arquitetura em .Net Core baseada em DDD](https://medium.com/@alexalvess/criando-uma-api-em-net-core-baseado-na-arquitetura-ddd-2c6a409c686)
- [Namespace Naming Guidelines](https://docs.microsoft.com/en-us/previous-versions/dotnet/netframework-1.1/893ke618%28v=vs.71%29?redirectedfrom=MSDN)
- [Common Web Application Architectures](https://docs.microsoft.com/en-us/dotnet/architecture/modern-web-apps-azure/common-web-application-architectures)
- [CrossCutting](https://pt.stackoverflow.com/questions/82976/oque-%C3%A9-cross-cutting-e-qual-sua-rela%C3%A7%C3%A3o-com-aspect-oriented-programming-aop)
