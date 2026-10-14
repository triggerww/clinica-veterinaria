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
    Pessoa <|-- Tutor
    Pessoa <|-- Veterinario
    Pessoa <|-- Recepcionista

    class Pessoa {
        -cpf: String
        -nome: String
        -dataNascimento: String
        +getCpf(): String
        +getNome(): String
        +getDataNascimento(): String
    }

    class Tutor {
        -contato: String
        +getAnimais(): Pet[]
    }

    class Veterinario {
        -idVet: String
        +getIdVet(): String
    }

    class Recepcionista {
        -idRec: String
        +getIdRec(): String
    }

    class Pet {
        -id: int
        -nome: String
        -raca: String
        -idade: int
        +getId(): int
        +getDono(): Tutor
        +getRaca(): String
        +getNome(): String
        +getIdade(): int
    }

    class Exame {
        -id: int
        -descricao: String
        +getId(): int
        +getDescricao(): String
    }

    Tutor --> Pet
    Pet --> Exame
    Veterinario --> Exame
```
