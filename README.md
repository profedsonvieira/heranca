# 🐾 Sistema de Herança Completa em Python

Este projeto demonstra os principais conceitos de **Programação Orientada a Objetos (POO)** em Python, utilizando exemplos de animais domésticos para ilustrar:

* ✅ Classes e Objetos
* ✅ Herança Simples
* ✅ Herança Múltipla
* ✅ Sobrescrita de Métodos (Override)
* ✅ Polimorfismo
* ✅ Encadeamento com `super()`

---

## 📂 Estrutura do Projeto

```python
Animal
├── Cachorro
│   └── CachorroDomestico
└── Gato

AnimalDomestico
└── CachorroDomestico
```

---

# 🚀 Conceitos Demonstrados

## 1️⃣ Classe Base: `Animal`

A classe `Animal` representa qualquer animal genérico e fornece atributos e comportamentos básicos.

### Atributos

| Atributo | Descrição                    |
| -------- | ---------------------------- |
| nome     | Nome do animal               |
| idade    | Idade do animal              |
| vivo     | Indica se o animal está vivo |

### Métodos

```python
respirar()
comer(alimento)
morrer()
__str__()
```

### Exemplo

```python
animal = Animal("Generic", 2)

print(animal.respirar())
print(animal.comer("grama"))
```

---

## 2️⃣ Herança Simples: `Cachorro`

A classe `Cachorro` herda de `Animal`, reutilizando seus atributos e métodos.

```python
class Cachorro(Animal):
```

### Novos atributos

```python
raca
feliz
```

### Novos métodos

```python
latir()
brincar()
```

### Sobrescrita de método

O método `comer()` foi redefinido:

```python
def comer(self, alimento):
```

Isso permite que cachorros tenham um comportamento específico ao se alimentar.

### Exemplo

```python
rex = Cachorro("Rex", 3, "Labrador")

print(rex.latir())
print(rex.comer("ração"))
```

---

## 3️⃣ Herança Simples: `Gato`

A classe `Gato` também herda de `Animal`.

```python
class Gato(Animal):
```

### Novos atributos

```python
cor
fome
```

### Novos métodos

```python
miar()
ronronar()
dormir()
```

### Sobrescrita

O método `comer()` é personalizado para gatos.

```python
def comer(self, alimento):
```

### Exemplo

```python
felix = Gato("Felix", 2, "preto")

print(felix.miar())
print(felix.ronronar())
```

---

## 4️⃣ Classe Independente: `AnimalDomestico`

Representa características de um animal que possui dono.

### Atributos

```python
dono
vacinas
```

### Métodos

```python
vacinar(vacina)
listar_vacinas()
```

### Exemplo

```python
pet.vacinar("raiva")
```

---

## 5️⃣ Herança Múltipla: `CachorroDomestico`

A classe herda simultaneamente de:

```python
Cachorro
AnimalDomestico
```

```python
class CachorroDomestico(Cachorro, AnimalDomestico):
```

Isso significa que o objeto possui:

### De `Animal`

* respirar()
* morrer()
* nome
* idade

### De `Cachorro`

* latir()
* brincar()
* raça

### De `AnimalDomestico`

* vacinar()
* listar_vacinas()
* dono

### Exemplo

```python
buddy = CachorroDomestico(
    "Buddy",
    1,
    "Golden",
    "João"
)

print(buddy.latir())
print(buddy.vacinar("raiva"))
```

---

# 🔄 Polimorfismo

O polimorfismo permite tratar diferentes objetos da mesma forma.

No exemplo:

```python
animais = [rex, felix, buddy]

for animal in animais:
    print(animal.comer("comida"))
```

Cada objeto responde ao método `comer()` de maneira diferente:

| Classe            | Comportamento                     |
| ----------------- | --------------------------------- |
| Cachorro          | Recusa comida diferente de ração  |
| Gato              | Come elegantemente                |
| CachorroDomestico | Herda o comportamento do cachorro |

---

# 🧠 Uso do `super()`

O projeto utiliza `super()` para reutilizar a implementação da classe pai.

Exemplo:

```python
super().__init__(nome, idade)
```

Isso evita duplicação de código e melhora a manutenção.

Também é utilizado em:

```python
super().__str__()
```

---

# ▶️ Como Executar

### Clone ou baixe o projeto

```bash
git clone <repositorio>
```

### Execute o arquivo

```bash
python heranca_completa.py
```

---

# 📌 Saída Esperada

```text
=== ANIMAL BASE ===
Generic (2 anos) - Vivo

=== CACHORRO (Herança Simples) ===
Rex (3 anos) - Vivo - Raça: Labrador

=== GATO (Herança Simples) ===
Felix (2 anos) - Vivo - Cor: preto

=== CACHORRO DOMÉSTICO (Herança Múltipla) ===
Buddy (1 anos) - Vivo - Raça: Golden - Dono: João

=== POLIMORFISMO ===
Rex: Rex recusou comida e quer ração!
Felix: Felix comeu comida elegantemente
Buddy: Buddy recusou comida e quer ração!
```

---

# 🎯 Objetivo Educacional

Este projeto foi desenvolvido para praticar e compreender:

* Programação Orientada a Objetos (POO)
* Herança Simples
* Herança Múltipla
* Encapsulamento básico
* Polimorfismo
* Sobrescrita de métodos
* Reutilização de código com `super()`

É um excelente exemplo para estudantes iniciantes e intermediários em Python que desejam consolidar conceitos fundamentais de orientação a objetos.

---

## 👨‍💻 Autor

Projeto educacional para estudo de **Herança e Polimorfismo em Python**.
