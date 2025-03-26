# JUinit Test e Coverage

## O que é JUnit?

JUnit é um framework de teste para a linguagem Java, amplamente utilizado para escrever e executar testes unitários. Ele faz parte do ecossistema de desenvolvimento de software e é essencial para a prática de TDD (Test-Driven Development).

### Características principais:

- Open-source: Gratuito e de código aberto;
- Anotações: Usa anotações para definir testes (@Test, @Before, etc.);
- Assertions: Fornece métodos para verificar resultados (assertEquals, assertTrue, etc.);
- Integração: Compatível com IDEs e ferramentas de build (Eclipse, IntelliJ, Maven, Gradle);

### Anotações mais comuns no JUnit

1. @Test : Indica que o método é um teste;
2. @Before	Método executado antes de cada teste (setup);
3. @After	Método executado após cada teste (cleanup);
4. @BeforeClass	Método estático executado uma vez antes de todos os testes;
5. @AfterClass	Método estático executado uma vez após todos os testes;
6. @Ignore	Ignora o teste;
7. @Test(expected=Exception.class)	Espera que o teste lance uma exceção específica;
8. @Test(timeout=100)	Falha se o teste demorar mais que 100ms;

### Exemplo de Teste

```
import org.junit.Test;
import static org.junit.Assert.*;

public class CalculadoraTest {
    
    @Test
    public void testSoma() {
        Calculadora calc = new Calculadora();
        int resultado = calc.soma(2, 3);
        assertEquals(5, resultado);
    }
    
    @Test
    public void testDivisao() {
        Calculadora calc = new Calculadora();
        double resultado = calc.divide(10, 2);
        assertEquals(5.0, resultado, 0.0001); // delta para comparação de doubles
    }

    //Teste de excessão, definindo o Tipo de excessão que é esperada.
    @Test(expected = IllegalArgumentException.class)
    public void testDivisaoPorZero() {
        Calculadora calc = new Calculadora();
        calc.divide(10, 0);
    }
}
```
## O que é Code Coverage (Cobertura de Código)?

Code Coverage é uma métrica que mede quanto do seu código fonte está sendo exercitado pelos testes. Ela ajuda a identificar:
- Partes do código que não estão sendo testadas;
- Casos de teste que podem estar faltando;
- Código morto (que nunca é executado);

### Tipos comuns de cobertura:
- Cobertura de Linhas: Porcentagem de linhas executadas;
- Cobertura de Branches: Porcentagem de ramificações (if/else, switch) testadas;
- Cobertura de Métodos: Porcentagem de métodos chamados;
- Cobertura de Instruções: Porcentagem de instruções bytecode executadas;

### Ferramentas para medir cobertura

As ferramentas mais populares para Java são:
- JaCoCo: Integrado com Maven, Gradle e IDEs;
- Cobertura: Alternativa mais antiga;
- Emma: Outra alternativa;

### Exemplo com JaCoCo no Maven
Adicione ao seu pom.xml:

```
<plugin>
    <groupId>org.jacoco</groupId>
    <artifactId>jacoco-maven-plugin</artifactId>
    <version>0.8.7</version>
    <executions>
        <execution>
            <goals>
                <goal>prepare-agent</goal>
            </goals>
        </execution>
        <execution>
            <id>report</id>
            <phase>test</phase>
            <goals>
                <goal>report</goal>
            </goals>
        </execution>
    </executions>
</plugin>
```

Execute os testes com cobertura:

```
mvn clean test
```

O relatório será gerado em `target/site/jacoco/index.html`

### Boas práticas para testes e cobertura
1. Nomes descritivos: Nomeie os testes de forma clara (test[Metodo][Cenario][ResultadoEsperado]);
2. Teste um conceito por teste: Cada teste deve verificar apenas uma coisa;
3. AAA Pattern: Arrange (preparar), Act (agir), Assert (verificar);
4. Cobertura razoável: Almeje 70-80% como meta inicial, 100% em código crítico;
5. Teste comportamentos, não implementações: Foque no que o código faz, não em como faz;
6. Evite testes frágeis: Não dependa de detalhes de implementação que podem mudar;

### Interpretando relatórios de cobertura
Um relatório típico mostra:
- Cobertura total por pacote/classe/método;
- Linhas cobertas (verde) e não cobertas (vermelho);
- Branches cobertos e não cobertos;

**Exemplo de meta**: "Nossa classe StringUtils tem 100% de cobertura de linhas e 85% de branches porque não testamos todos os casos de entrada possívels para o método capitalize."

### Dicas avançadas
1. Testes parametrizados: Use @ParameterizedTest para testar múltiplos valores;
2. Mocking: Use Mockito para simular dependências;
3. Testes de integração: Separe testes unitários rápidos de testes de integração mais lentos;
4. CI/CD: Execute testes e cobertura em seu pipeline de integração contínua;

**Lembre-se**: alta cobertura não significa bons testes. É possível ter 100% de cobertura com testes inúteis. O importante é testar os comportamentos e casos de uso significativos.
