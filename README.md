# dev_Maven_Commons

Bibliotecas Java compartilhadas pelos serviços da Sebratel, publicadas no GitHub Packages
(`https://maven.pkg.github.com/Sebratel/dev_Maven_Commons`). Herdam de `br.com.sebratel:sebratel-java-parent`.

| Artefato | Para quê |
|---|---|
| `common-web` | Envelope de resposta/erro (`ApiResponse`, `ApiError`), `GlobalExceptionHandler`, Jackson |
| `common-security` | Validador do JWT do Google (issuer + domínio), `GetToken`, `JwtInformation` |
| `common-elleven` | Cliente Elleven (WebClient, token, `@TokenRetry`) usado por massivas e splitters |

> **Estado: esqueleto.** Cada módulo só tem o `package-info`; o código vem do monólito (`dev_SpringBoot_APIGateway`) quando
> cada serviço for extraído. Não publicar versão estável antes de haver código real.

## Uso num serviço
```xml
<dependency>
    <groupId>br.com.sebratel</groupId>
    <artifactId>common-web</artifactId>
    <version>0.1.0</version>
</dependency>
```
Com o repositório `https://maven.pkg.github.com/Sebratel/dev_Maven_Commons` declarado em `<repositories>` e um servidor `github` no `settings.xml`.

## Publicar
Criar uma Release com a tag `vX.Y.Z`. O workflow `publish.yml` ajusta a versão de todos os módulos e faz `deploy`.
Semver: **MAJOR** para mudança incompatível em classe pública; **MINOR** para classe/recurso novo; **PATCH** para correção.

## Regras do repositório
`main` só recebe PR com 1 aprovação e `ci-ok` verde; Conventional Commits.
