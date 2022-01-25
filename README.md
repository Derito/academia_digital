# Projecto Academia_digital da DIO 
> Serve como base de estudo do Sping e da API Rest.
## Inovações ao projecto
Ao rodar o projecto original o spring roda, carrega não dá erro nem gera tabelas.
### Para resolver a situação usei:
> Adição da automação na criação de tabelas no banco PostgreSQL usando ***flyway***.
1. Inserção das pastas db/migration requeridas pelo flyway.
2. Adição do script das tabelas na pasta migration.
3. Uso da Anotação @Builder nas entidades e,
4. ### Dependência adicionada ao projecto original
```
<dependency>
    <groupId>org.flywaydb</groupId>
    <artifactId>flyway-core</artifactId>
    <version>8.4.2</version>
</dependency>
```
5. Configuração no application.yml
```
 flyway:
    baselineOnMigrate: true
    check-location: true
    locations:
      classpath: db/migration
    schemas: public
    enabled: true
```
