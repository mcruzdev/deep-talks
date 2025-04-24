# Migrando aplicações Spring para Quarkus

> "Quando você inventa o navio, você inventa o naufrágio."
>
> **Paul Virillo**


# Java no passado

Para os problemas de 1999 o Java tinha o J2EE, as aplicações naquela época eram aplicações monolíticas, você tinha aplicações para intranet, a internet era lenta, você não tinha um usuário que batia ou jogava o celular na parede por uma demora de 5 segundos de experiência, você não tinha milhares de dispositivos móveis circulando conectados na internet, você não tinha uma "criança de poucos anos arrastando pra cima" com um celular na mão.

# Pensamentos que guiam de certa forma guiaram o desenvolvimento de aplicações

Desde que comecei a programar eu ouvia que uma tecnologia era boa, pois ela fazia com que eu (desenvolvedor), usasse todo o meu esforço, em resolver regras de negócio, e isso faz sentido, eu sempre ouvi que era pago para resolver problemas de negócio (o usuário quer a funcionalidade e não um código que usa arquitetura X ou Y). Isso fala muita da **experiência do desenvolvedor** e o foco na **redução de tempo de entrega**, remoção da carga cognitiva e potencializar o desenvolvedor para entregar o máximo possível de valor.

Com base nesse pensamento temos o Spring Boot, Spring AOP, Quarkus DevServices, Quarkus DevUI, DevOps, Engenharia de Plataform, entre outras ferramentas e práticas.

# Microservices

Os microservics vieram para resolver problemas de pessoas, escalar times, e ele traz muitos benefícios e malefícios, sempre é um **trade-off**. É certo que na época da ascenção e hype dos microservices as pessoas já estavam pirando se a resposta de uma determinada requisição demorasse mais que 1 segundo. 

O comportamento do usuário hoje em dia pode ser medido da seguinte forma:


|Tempo|Experiência|
|---|---|
|0 a 100ms|Dopamina|
|100 a 300ms|Dopamina|
|300 a 1000ms|Dopamina|
|Depois de 1 segundo|Estresse, ansiedade e aparelhos domésticos quebrados|

Desde então, você ainda ouve muito a seguinte frase: "Vamos começar com microservices (A aplicação tem apenas 100 usuários e não sei se foi escrito um RFC/ADR para medir o possível crescimento e uma justificativa válida para começar com microservices, é apenas hype mesmo)".

O SpringBoot foi e tem sido um bom ferramental para a criação de microservices Java, não somento o SpringBoot o ecossistema Spring no geral.

# [Eras](#25-anos-de-java-modern-cloud-native-javajakarta-ee-frameworks-tips-challenges-and-trends)

## Info age

Main frames > Personal Computers > Multiple Devices > Cloud > Services

## Tiers age

One tier > Three tiers > Microservices

## Deploy ages

Yearly > Monthly > Daily > Instantly 

# Java e consumo de memória

O Java sempre teve a fama de ser uma plataforma lenta e pesada. Essa percepção foi válida por um tempo, especialmente quando comparado a outras linguagens e runtimes. No entanto, o Java evoluiu — e continua evoluindo rapidamente.

Desde a versão 8, a linguagem tem recebido melhorias importantes, especialmente no contexto de containers. Além disso, questões como tempo de inicialização e consumo de memória também vêm sendo endereçadas com bastante foco, tornando o Java cada vez mais adequado para ambientes modernos e exigentes.

## Lives:

### [Rafael Benevides - Java & Kubernetes: O Guia Para um Relacionamento Saudável](https://www.youtube.com/watch?v=Oh7X89tMe3A)

### [25 Anos de Java: Modern Cloud Native Java/Jakarta EE Frameworks: tips, challenges, and trends](https://www.youtube.com/watch?v=jEkmVX9d5CY)

### [Keeping Your Java Hot by Solving the JVM Warmup Problem](https://www.youtube.com/watch?v=G5jVGS-EJKw)


Algumas JEPs importantes:

* [JEP 220 – Modular Run-Time Images](https://openjdk.org/jeps/220)
* [JEP 282 – jlink: The Java Linker](https://openjdk.org/jeps/282)
* [JEP 310 – Application Class-Data Sharing (AppCDS)](https://openjdk.org/jeps/310)
* [JEP 318 – Epsilon: A No-Op Garbage Collector](https://openjdk.org/jeps/318)
* [JEP 341 – Default CDS Archives](https://openjdk.org/jeps/341)
* [JEP 343 – Packaging Tool (jpackage)](https://openjdk.org/jeps/343)
* [JEP 345 – NUMA-Aware Memory Allocation for G1](https://openjdk.org/jeps/345)
* [JEP 376 – ZGC: Concurrent Thread-Stack Processing](https://openjdk.org/jeps/376)
* [JEP 379 – Shenandoah: A Low-Pause-Time Garbage Collector](https://openjdk.org/jeps/379)
* [JEP 387 – Elastic Metaspace](https://openjdk.org/jeps/387)
* [JEP 447 – Prepare for Pre-Initialization](https://openjdk.org/jeps/447)
