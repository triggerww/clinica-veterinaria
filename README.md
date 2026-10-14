# Clínica Veterinária
Trabalho de final da matéria de Engenharia de Software. [2° Semestre/2026]

### Prototipo
Prototipo no Figma: [Aqui](https://www.figma.com/design/0kAb3nbGc9SY4zAAa7lrjq/Clinica-Veterinaria?t=4Qsj4DI84pijXLV3-1)

## Diagramas UML

### Diagrama de caso de uso:
```mermaid
flowchart TD
    tutor["Tutor"]
    recepcionista["Recepcionista "]
    vet["Veterinário"]

    %% Ações
    subgraph Sistema
        pet["Cadastra pet"]
        cadtutor["Cadastra o tutor"]
        consulta["Agenda a consulta"]
        examina["Examina pet"]
        diagnostico["Da diagnóstico"]
        opera["Faz Operação"]
        receituario["Preenche receituário"]
    end

    %% Relacionamentos
    tutor -- "Leva pet na veterinaria" --> recepcionista --> cadtutor --> pet
    recepcionista --> consulta

    tutor -- "Entrega pet" --> vet --> examina --> diagnostico --> receituario
    diagnostico -. "Se precisar" .-> opera  --> receituario 
    vet -- "Devolve pet depois de todo procedimento" --> tutor
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
        +getId(): int
        +getExame(): string
    }

    Veterinario -- Pet
    Veterinario -- Exame
```
