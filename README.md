# design-patterns-GoF
# Oque são padrões de projeto

São **soluções elegantes para problemas conhecidos** recorrentes no desenvolvimento de softwares que foram utilizados e testados no passado e continuam relevantes nos dias atuais
Foram catalogados e popularizados pelo livro **"Padrões de projeto - Soluções reutilizáveis de software orientado a objetos"** (os padrões da "GoF", de 1994/95 - por Erich Gamma, Richard Helm, Ralpha Johnson, Jon Vlissides) Gang of Four

# São divididos em 3 categorias: 
**de criação (creational)**, que visam abstrair o processo de como objetos são criados na aplicação;
**estruturais(structural)**, que lidam com a composição de classes e objetos;
**comportamentais(behavioural)**, que caracterizam como as classes e objetos interagem e distribuem responsabilidades na aplicação

São **APENAS SUGESTÕES** de software que podem ser aplicadas a qualquer linguagem de programação

De criação  (**creational**)
- Abstract factory
- Factory Method
- Builder
- Prototype
- Singleton
Estrutural (**structural**)
- Adapter
- Bridge
- Composite
- Decorator
- Façade
- Flyweight
- Proxy
Comportamental (**behavioural**)
- Interpreter
- Template method
- Chain of responsibility
- Iterator
- Command
- Mediator
- Memento
- Observer
- State
- Strategy
- Visitor
Vamos usar TypeScript

# Benefícios e problemas

**O que é bom:**
- Você não precisa reinventar a roda
- Padrões universais facilitam o entendimento do seu projeto
- Evita refatoração desnecessária
- Ajuda na reutilização do código (conceito DRY - Don't repeat youself)
- Abstrai e nomeia partes particulares do projeto
- Ajuda na aplicação dos principios do design orientado a objetos (SOLID)
- Facilitam a criação de testes unitários

**O que é ruim:**
- Alguns padrões podem ser complexos até que você os compreenda
- Muito código para atingir um objetivo simples
- Podem trazer otimizações prematuras para o seu código (YAGNI - You Ain't Gonna Need It)
- Se usados incorretamente, podem atrapalhar ao invés de ajudar