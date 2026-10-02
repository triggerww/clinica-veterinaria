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
        -animais: Lista de Pet
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
        +atenderPet(Pet: Pet) void 
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

[![](https://mermaid.ink/img/pako:eNqlVFFr2zAQ_ivinlrqBDuOHUevzQaFbpQx-jD8ckQXVxBLQZZLtpDfsx-yP7aT16xx4pZ2MwhL9-nuvvtO0g6WVhFIWK6xaRYaK4d16Uoj-Ots4mvrrRO7gzF8o-u7j1I03mlT9ezG1jQIKPQ4CCyt8ejtIIZG16gbKW5141EoEnfkj3dcVeSZysXlkHsAPzOfl9EFkzpH92HSl4DTngiglRTa-H6N1nAdnVw9u8NfP_F9cmmFis4yBM43KjAeABacPUBn-QP4JVD4V5luApmTrD2R_pyQ0ejQnr549-SJw6LT9kTE5Wb1Lln-p93oyShyzPCChwxUL8Wj1Uq80vcPW6zpDZ2nsG-wlEdcWyfFam3x7a3s0r5c5X2IGeBe1B79Y82f-zKAdKkOnscDIqicViC9aymCmhxfRV7CLsQpwT8QO4LkqSPVbvkiM6sSSrNn1w2ab9bWB29n2-oB5ArXDa_aDb8G9PTW_N3StefatsaDnKX5PAJSms_Vp6f3Kfy6wCB3sAU5SeNxUmRJFifTfFpM0yKC72yejvM0jeMkncwyRrJ9BD86KvG4mOdxPsvmSZbNikmc7n8DR6qA2A?type=png)](https://mermaid.live/edit#pako:eNqlVNtu2zAM_RWBTy3mBE7lS6bXZgMKbEMxDH0o_EJEjCsglgJZLrIF-Z59yH5slNdsceIO7WZAsMQjkoeHknawdJpAwXKNbbswWHtsKl9ZwV9vE1-64LzYHYzxm1zfvleiDd7YemC3rqFRQGPAUWDpbMDgRjG0pkHTKvHBtAGFJnFL4XjHm5oCU7m4HHOP4Cfm8zy6YFLn6D5OhhJw2hMBjFbC2DCs0Vmuo5drYPf44zu-Ti6jUdNZhsj5RkfGI8CCs0foLH8EP0cK_yrTTSRzknUg0q8TMpkc2jMU744CcVj0xp2IuNysXiXL_7QbA1lNnhle8FCR6qV4dEaLv_T93RYbekHnKe4bLeUR184rsVo7fHkr-7TPV3kXY0Z4EHVA_1jzP30ZQfpUB8_jAQnU3mhQwXeUQEOeryIvYRfjVBAeiB1B8dST7rZ8kZlVBZXds-sG7b1zzcHbu65-ALXCdcurbsOvAT29Nb-tvu_PtetsAFXKIkuAtOGD9fHpgYq_PjKoHWxBXcl0OpvnszydZUU2z-Q8ga9szqaFlGk6k1dlzki-T-BbzyWdzt8WaVEWWS5zWUpZ7n8CyfKBHw)
