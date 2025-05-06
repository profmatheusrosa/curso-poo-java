
# Abstração em Java

## 📌 O que é Abstração?

**Abstração** é um dos pilares da Programação Orientada a Objetos (POO) e tem como objetivo **esconder os detalhes de implementação** e **expor apenas as funcionalidades essenciais** de um objeto.

Assim como usamos um carro sem conhecer todos os detalhes do seu motor, na programação usamos a abstração para trabalhar com objetos sem nos preocupar com como exatamente eles fazem o que fazem.

---

## 🎯 Benefícios da Abstração

- **Facilita a manutenção** do código.
- **Aumenta a reutilização** de código.
- **Reduz o acoplamento** entre as classes.
- **Melhora a legibilidade** e a organização.

---

## 🔧 Como aplicar Abstração em Java?

Em Java, usamos principalmente:

- **Classes abstratas**
- **Interfaces**

---

## 🧱 Classes Abstratas

Uma classe abstrata é aquela que **não pode ser instanciada diretamente** e pode conter **métodos abstratos** (sem corpo) e **métodos concretos** (com implementação).

### Sintaxe:
```java
abstract class Animal {
    abstract void emitirSom(); // método abstrato

    void dormir() {
        System.out.println("Dormindo...");
    }
}
```

Uma subclasse deve **implementar** os métodos abstratos da superclasse:

```java
class Cachorro extends Animal {
    @Override
    void emitirSom() {
        System.out.println("Latindo...");
    }
}
```

---

## 🧩 Interfaces

Uma **interface** define um **contrato** que uma classe deve seguir. Todos os métodos de uma interface são **abstratos por padrão** (em versões antigas do Java).

### Sintaxe:
```java
interface Controlavel {
    void ligar();
    void desligar();
}
```

Implementação em uma classe:

```java
class Computador implements Controlavel {
    public void ligar() {
        System.out.println("Computador ligado");
    }

    public void desligar() {
        System.out.println("Computador desligado");
    }
}
```

---

## 🤔 Quando usar cada um?

| Recurso         | Quando usar                                                                 |
|-----------------|------------------------------------------------------------------------------|
| Classe Abstrata | Quando há uma **relação hierárquica clara** e algum comportamento comum      |
| Interface       | Quando se deseja **garantir um contrato** sem se preocupar com herança       |

---

## 🧠 Exemplo Prático

Imagine um sistema bancário. Podemos abstrair uma conta bancária como:

```java
abstract class Conta {
    String numero;
    double saldo;

    void depositar(double valor) {
        saldo += valor;
    }

    abstract void sacar(double valor);
}
```

Cada tipo de conta (poupança, corrente) implementa o saque de maneira diferente:

```java
class ContaCorrente extends Conta {
    @Override
    void sacar(double valor) {
        saldo -= valor + 0.10; // tarifa
    }
}
```

---

## ✅ Conclusão

- Abstração permite focar **no que o objeto faz** e não **em como ele faz**.
- Use **classes abstratas** quando há código comum entre subclasses.
- Use **interfaces** para definir contratos que múltiplas classes podem implementar, mesmo que não estejam relacionadas.

---

[🔙 Voltar ao Sumário](#abstração-em-java)
