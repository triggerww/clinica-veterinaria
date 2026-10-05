# Clínica Veterinária
Trabalho de final da matéria de Engenharia de Software. [2° Semestre/2026]

### Prototipo
Prototipo no Figma: [Aqui](https://www.figma.com/design/0kAb3nbGc9SY4zAAa7lrjq/Clinica-Veterinaria?t=4Qsj4DI84pijXLV3-1)

## Diagramas UML

### Diagrama de caso de uso:
```mermaid
flowchart TD
    cliente["Tutor"]
    recepcionista["Recepcionista "]
    vet["Veterinário"]

    %% Ações
    subgraph Sistema
        pet["Cadastra pet"]
        tutor["Cadastra o tutor"]
        consulta["Agenda a consulta"]
        examina["Examina pet"]
        diagnostico["Da diagnóstico"]
        opera["Faz Operação"]
        cobra["Cobra o valor da consulta $$"]
        paga["Paga valor da consulta $$"]
    end

    %% Relacionamentos
    cliente -- "Leva pet na veterinaria" --> recepcionista --> tutor --> pet
    recepcionista --> consulta

    cliente -- "Entrega pet" --> vet --> examina --> diagnostico
    opera -. "Se precisar" .-> diagnostico --> cobra
    cliente --> paga
```

### Diagrama de classes
```mermaid
classDiagram
    class Tutor {
        -CPF: string
        -nome: string
        -data: string
        -contato: string
        -animais: Pet
        +getCPF(): string
        +getNome(): string
        +getData(): string
    }

    class Pet {
        -id: int
        -dono: Tutor
        -raça: string
        -nome: string
        -idade: int
        +getId(): int
        +getDono(): Tutor
        +getRaça(): string
        +getNome(): string
        +getIdade(): int
    }

    Tutor -- Pet

    class Veterinario {
        -cpf: string
        -nome: string
        +getCPF(): string
        +getNome(): string
    }

    class Exame {
        -id: int
        -exame: string
        -valor: float
        +getId(): int
        +getExame(): string
        +getValor(): float
    }

    Veterinario -- Pet
    Veterinario -- Exame
```
