# DDD - Modelagem Tática e Patterns: Desafio Order Repository

Neste desafio, trabalha-se o _pattern_ **Repository**:

- Conforme Vaughn Vernon: "De um modo geral, existe uma relação de um-para-um entre um tipo Agregado e um Repositório". No caso deste desafio, lidamos com o Agregado _Order_.

- Como evitar o acoplamento com a implementação do Repositório e, ainda assim, fazer com que o Domínio tenha controle sobre esse Repositório? Através de interfaces. Se aproxima à idéia de adaptadores na _Arquitetura Hexagonal_. Neste caso, definimos a interface _RepositoryInterface_ como um adaptador;

- _RepositoryInterface_ representa um Repositório genérico, onde são definidos métodos de _create_, _update_, _find_ e _findAll_. Mas, eventualmente, cada Agregado pode ter necessidades específicas. Assim, é criada a interface _OrderRepositoryInterface_, estendendo de _RepositoryInterface_;

- Este desafio, consiste, portanto, em:

  - Implementar os métodos definidos por _OrderRepositoryInterface_;

  - A implementação compreende também na criação dos testes automatizados (com _Jest_).

> N.T. 1: Linguagem de programação para este desafio: _TypeScript_.
> N.T. 2: A solução envolve também definir uma nova camada responsável por conversar com o mundo externo, isto é, através de conexões externas ao Domínio. Essa camada que chamamos de _Infrastructure_ conta com a definição de classes representando o mapeamento objeto-relacional (com _Sequelize_) em relação a _OrderModel_ e _OrderItemModel_. E também a definição da classe _OrderRepository_ - responsável por implementar os métodos definidos na interface de Domínio.

```
/src/infrastructure/repository/order.repository.spec.ts
/src/infrastructure/repository/order.repository.ts
```
