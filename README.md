# Clínica Veterinária
Trabalho de final da matéria de Engenharia de Software. [2° Semestre/2026]

### Prototipo
Prototipo no Figma: [Aqui](https://www.figma.com/design/0kAb3nbGc9SY4zAAa7lrjq/Clinica-Veterinaria?t=4Qsj4DI84pijXLV3-1)

## Diagramas UML

### Diagrama de caso de uso:
```Mermaid
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

[![](https://mermaid.ink/img/pako:eNqFU0tu2zAQvQpBJDvbsCRHkrUIENjpqkWLJOiiVRcTaSITkEiBolw3hg9TdJEDFD2BL9YhbbmyEqDccD5vPnwz3PJM5cgT_lSq79kKtGEPy1SnktHJSoHS4NeUP7RG6ZR_6zwaM6wzoaRoDJD_rq-zHnCNhtyf0aAWcv9TC3V0doDLS3azf9n_waazNO1joaFesXtKhhV0dntql24BOTRGg1V7tewxttE-RB1MA1imZNOWrvWbAmUODE62ARQ3UAlpkbcH6Y2quYBCqsaITBFuCQfD_rezDLCqRm2zvYNn9tHK9Ppf6lV_jw60sDe9YQ2l0iz_1yS7uBiE1FDYiE90_Q9ODx6M4A5LsOODigaumsECsPGYZvoe1-7tjChYHwYKWhBd5L4-3whncbw7yRL21uI454n2XkdndW-l0VgcaXchVN3dx9E4uTeCLotjmo0nlOMeWU2lRQO0CWxyjj-2QUy_rn_teLV2PuKFFjlPjG5xxCvUFViVb21Mys0KK0x5QqLGvN2MM1XavUvljkJrkF-UqrpordpixZMnKBvS2joHg0vqSEN1smoaE-qFaqXhiX_lX4045oI4_XD4se7jusw82fINT-JoEsWBF0dxGPredD4b8R888eJJ7AVxEPhBGM5nQRDuRvzZ9TKdxOF0FvmRP43nYeR73u4vXMRQTA?type=png)](https://mermaid.live/edit#pako:eNqFU0tu2zAQvQpBJDvbsCRXkrUIENjpqkWLJOiiVRcTaSITkEiBolw3Rg5TdNEDFD2BL9YhZbmyEqDccD5vPnwz3PNM5cgT_liqb9kGtGH361SnktHJSoHS4JeU37dG6ZR_7T0aM6wzoaRoDJD_dqizAXCLhtyf0KAW8vBDC3V09oDLS3Z9-HX4g01vadqHQkO9YXeUDCvo7fbULt0KcmiMBqsOatljbKNDiOpMI1imZNOWrvXrAmUODE62ERR3UAlpkTed9ErVXEAhVWNEpgi3hs5w-O0sI6yqUdtsb-GJfbAyvf6netHfgwOt7E1v2EKpNMv_NckuLkYhNRQ24iNd_4PTg0cjuMUS7PigooGrZrQAbDqlmb7DrXs7Iwq23UBBC6KL3FfnG-EsjncnWcJeWxznPNE-6Ois7o00Gosj7S6Eqrv7OBonD0bQZ3FMs-mMctwhq6m0aIA2gc3O8cc2iOmX9a8cr5299_ad9jqf8EKLnCdGtzjhFeoKrMr3LoqbDVaY8oREjXm7m2aqtBuZymcKrUF-Vqrqo7Vqiw1PHqFsSGvrHAyuqVcN1cmqaYCoV6qVhif-G9-bcMwFsf2--8vuS7vMPNnzHU_iaBbFgRdHcRj63ny5mPDvPPHiWewFcRD4QRguF0EQPk_4k-tlPovD-SLyI38eL8PI97znv8EaV-g)

### Diagrama de classes
```Mermaid
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

[![](https://mermaid.ink/img/pako:eNqdVN1KwzAUfpVyrhS70ena1dw6BS8UEfFCenNYzmqgTUaaynTseXwQX8yTanXdKmwGSpPznZ8v30mygpmRBAJmBVbVVGFuscxspgMejS14qJ2xwao1-jG4uLsSQeWs0nnHrk1JvYBEh73AzGiHzvRiqFWJqhLBHblN4CQnxwyOjvuiPHjLNP5Gp8xlF137SXfnXHZr30qKQGnX3ZrRTL9RqWO3-PGOh6mkJEraqeA5X0vPuAeYcnUP7dT34L2n8F-Zrj2Zraodkb4OxmDQtqcr3iM54rRoldkScbaYHyTLP9vd09DLJZa0R0vJ-_VyfMHCWBHMC4P796gp-zf9R5_Tw52sHfqbYv4K3oM0pdrIzQ9CyK2SIJytKYSSLF8tXsLK58nAPRMHguCpJVkv-WIyqwwyvebQBeonY8o22po6fwYxx6LiVb3g203fb8ePC2lJ9sLU2oGYxNEoBJKKD8zN93vjf01iECtYghjFoyG7JcnZaZRG0SQN4RXE6XiYxlGcjM_jJEniaLwO4a1hEg3TSbz-BEBTbzg?type=png)](https://mermaid.live/edit#pako:eNqdVFFPwjAQ_ivLPWkchAljrK-iCQ8aYgwPZi8XeswmrCVdZ1DC7_GH-Me8TlEGI1GbLGvv6919_a7XDcyNJBAwX2JZjhXmFovMZjrgUduCh8oZG2x2Rj86V9MbEZTOKp037NoU1ApIdNgKzI126EwrhloVqEoRTMntAxc5OWZwdt7m5cE7pnEaHTOXY3TrJ82Tc9qDcyspAqVd82hGM_1apYbd4vsb_k0lJVHSUQbPeSI94xZgzNk9dJTfg_eewn9lmngyB1kbIn1ejE5nV56meDNyxGHRKnMg4ny1-JMs_yx3S0Gv11jQL0pKfl8rx2dcGiuCxdLg72tUpz1Nf-ZjergRtUF_X8wfwVuQOtXOc_-DEHKrJAhnKwqhIMutxUvY-DgZuCdiRxA8tSSrNTcms8og01t2XaF-NKbYeVtT5U8gFrgseVWtuLvp6-343kJakr0ylXYgkkHaC4Gk4gtz-_Xe-F8dGMQG1iCiftqNe9Ew7SeXcTyK00EILyAu4-4o7sXDKBpE6TBJkv42hNeaS687SuLtByMjb74)
