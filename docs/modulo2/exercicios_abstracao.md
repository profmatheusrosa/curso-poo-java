
# 🧪 Exercícios Práticos - Abstração em Java

## 📘 Cenário

Você foi contratado para desenvolver uma aplicação simples de gerenciamento de veículos. O sistema deve permitir representar diferentes tipos de veículos e suas formas de ligar e abastecer. Para isso, você deverá aplicar **abstração** utilizando classes abstratas e interfaces.

---

## 🔨 Exemplo de Estrutura Inicial

```java
abstract class Veiculo {
    String modelo;
    int ano;

    Veiculo(String modelo, int ano) {
        this.modelo = modelo;
        this.ano = ano;
    }

    abstract void ligar();

    void exibirInfo() {
        System.out.println(modelo + " - " + ano);
    }
}
```

Crie as seguintes classes concretas:

```java
class Carro extends Veiculo {
    Carro(String modelo, int ano) {
        super(modelo, ano);
    }

    @Override
    void ligar() {
        System.out.println("Carro ligado com chave.");
    }
}

class Moto extends Veiculo {
    Moto(String modelo, int ano) {
        super(modelo, ano);
    }

    @Override
    void ligar() {
        System.out.println("Moto ligada com botão.");
    }
}
```

---

## 🧩 Interface Abastecivel

Crie uma interface chamada `Abastecivel` com os métodos:

```java
interface Abastecivel {
    void abastecerGasolina();
    void abastecerAlcool();
}
```

Implemente essa interface nas classes `Carro` e `Moto`.

---

## 🧠 Desafios

1. Crie uma classe `Garagem` que receba uma lista de veículos e os ligue automaticamente.
2. Adicione um método na interface que permita verificar o tipo de combustível atual do veículo.
3. Implemente uma nova classe `Caminhao` com comportamento diferente ao ligar e abastecer.

---

## ✅ Objetivo

Esses exercícios ajudam a reforçar os conceitos de:
- Classes abstratas e métodos abstratos.
- Interfaces e implementação de contratos.
- Polimorfismo e reutilização de código.
