![GitHub repo size](https://img.shields.io/github/repo-size/iuricode/README-template?style=for-the-badge)
![GitHub forks](https://img.shields.io/github/forks/iuricode/README-template?style=for-the-badge)
![Bitbucket open issues](https://img.shields.io/bitbucket/issues/iuricode/README-template?style=for-the-badge)

# SQL Modelagem banco de dados ResiliaData

Este projeto consiste na criação de um banco de dados de relações empresariais, utilizando a linguagem SQL. O banco de dados é composto pelas seguintes tabelas:

* **Empresas:** armazena informações sobre as empresas, como nome, CNPJ, endereço e telefone.
* **Colaboradores:** armazena informações sobre os colaboradores, como nome, cargo, email, disponibilidade.
* **Tecnologias:** armazena informações sobre as tecnologias utilizadas pelas empresas, como nome, versão e status.
* **Registros:** armazena a relação entre as empresas e as tecnologias, indicando quais tecnologias são utilizadas por cada empresa, assim como a permissão e a área a qual ela se aplica.

## Requisitos

Para executar este projeto, é necessário ter instalado o MySQL e o xampp tendo acesso ao PHPMyAdmin.

## Instruções de instalação

1. Clone o repositório do GitHub:
   ```
   https://github.com/IsabelaAthayde/modelagem-pi-mod3.git
   ```
3. Importe o arquivo `projetoResiliadata.sql` no PHPMyAdmin:
   ```
   Import -> Selecione o arquivo projetoResiliadata.sql -> Clique em "Importar"
   ```

Exemplos de consultas SQL
A seguir, são apresentados alguns exemplos de consultas SQL que podem ser utilizadas para consultar o banco de dados:

* **Listar todas as empresas:**
```sql
SELECT * FROM empresa;
```

* **Listar todos os colaboradores:**

```sql
SELECT * FROM colaborador;
```

* **Listar todas tecnologias:**

```sql
SELECT * FROM tecnologia;
```

* **Listar todos os registros:**

```sql
SELECT * FROM registro;
```

* **Recuperar todas as tecnologias, por área:**
  
```sql
SELECT tecnologia.nome, registro.area
FROM tecnologia
INNER JOIN registro
ON tecnologia.id_tec = registro.id_tec
ORDER BY registro.area;

```

* **Recuperar todos os colaboradores das empresas:**

```sql
SELECT colaborador.nome, colaborador.cargo, empresa.nome
FROM colaborador
INNER JOIN empresa
ON colaborador.id_empresa = empresa.id_empresa;

```

* **Recuperar todas as tecnologias que uma empresa parceira está utilizando:**

```sql
SELECT registro.area, tecnologia.nome, tecnologia.versao
FROM registro
INNER JOIN tecnologia
ON registro.id_tec = tecnologia.id_tec
WHERE registro.id_empresa = 1;
```

# 🤝 Colaboradores

Agradecemos às seguintes pessoas que contribuíram para este projeto:

<table>
  <tr>
    
    <td align="center">
      <a href="https://github.com/IsabelaAthayde">
        <img src="https://avatars.githubusercontent.com/u/100873483?v=4" width="100px;" alt="Foto da Isabela Athayde"/><br>
        <sub>
          <b>Isabela Athayde</b>
        </sub>
      </a>
    </td>
  </tr>
</table>

## Contribuições são bem-vindas. Para contribuir, siga as seguintes instruções:

1- Realize um fork do projeto.
2- Crie uma branch com a nova feature.
3- Realize o commit das alterações.
4- Realize o push da branch para o seu fork.
5- Abra um pull request para o repositório original.

## Licença

Este projeto é licenciado sob a licença [--].
