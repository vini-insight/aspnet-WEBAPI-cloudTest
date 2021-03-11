# SQLserverEFcoreMVC
SQLserverEFcoreMVC

    https://github.com/Clavico/CursoDigitalOne
    https://github.com/Clavico/CursoDigitalOne/tree/master/CursoTest


remover pacotes:

    dotnet remove package <PACKAGE_NAME>


  dotnet new xunit

- PASSO: adicionar referencias dos projetos que serão incluidos nos testes. essas referencias podem ser adicionadas por linhas de comando. mas também pode ser feita a cola do seguinte código no .csproj:

  <ItemGroup>
    <ProjectReference Include="..\SQLserverEFcoreMVC\SQLserverEFcoreMVC.csproj" />
    <ProjectReference Include="..\ASP NET API cloud\ASP NET API cloud.csproj" />
  </ItemGroup>


- PASSO: adicionar dependências:

    dotnet add package Moq --version 4.13.1

    dotnet add package Microsoft.EntityFrameworkCore.Tools --version 3.1.1

    dotnet add package Microsoft.EntityFrameworkCore.SqlServer --version 3.1.1


- PASSO: 

precisa modificar a classe de contexto do projeto de referencia MVC

MODIFICAR PROPRIEDADE:

    public DbSet<Categoria> Categorias { get; set; }

PARA
    
    public virtual DbSet<Categoria> Categorias { get; set; }


ADICIONAR O MÉTODO:

    public virtual void SetModified(object entity)
    {
        Entry(entity).State = EntityState.Modified;
    }


OU FAZER ASSIM:

https://entityframework.net/knowledge-base/20471927/how-to-fake-dbcontext-entry-method-in-entity-framework-with-repository-pattern




PARA RODAR OS TETES NO CONSOLE INSIRA O COMANDO:

  dotnet test

AGUARDE OS RESULTADOS:

