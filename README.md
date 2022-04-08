## O que é?
Exemplo para gerar Coverage e Sonar "local" antes de enviar para o servidor ou fazer commit e/ou Pull Request

## Pré-requisitos
- [Docker](https://www.docker.com/products/docker-desktop)
- [Java JDK](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)
- [Sonar Scanner](https://www.nuget.org/packages/dotnet-sonarscanner/4.8.0)
- [Report Generator](https://github.com/danielpalme/ReportGenerator)

## Instalações 

### SonarQube com Docker
```
docker run -d --name sonarqube -p 9000:9000 sonarqube:9.3-community
```

### Sonar Scanner para .Net 
```
dotnet tool install --global dotnet-sonarscanner
```

### Report Generator
```
dotnet tool install -g dotnet-reportgenerator-globaltool
```

## Execução dos Testes de unidade (Unit test)
No projeto de teste instalar a seguinte dependência: 
Essa dependência será responsável de gerar o nosso code coverage
```
dotnet add package coverlet.collector
```
## Execução dos testes 
Dentro da pasta do projeto, executar o seguinte comando: <br>
OBS: após o comando dotnet test é necessário colocar o caminho do projeto que vamos executar os testes de unidade (unit tests) (deve ser aplicado para testes feitos em xUnit)
```
dotnet test Tests.Unity/{nomeDoProjectTests}.csproj --collect:"XPlat Code Coverage"
```





Foi utilizado como fonte o repositório do jailton, porém temos algumas modificações de versão
https://github.com/JailtonJunior94/dotnet-sonarqube-docker-tests
