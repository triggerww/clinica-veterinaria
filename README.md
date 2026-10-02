# Clínica Veterinária
Trabalho de final da matéria de Engenharia de Software. [2° Semestre/2026]

### Prototipo
Prototipo no Figma: [Aqui](https://www.figma.com/design/0kAb3nbGc9SY4zAAa7lrjq/Clinica-Veterinaria?t=4Qsj4DI84pijXLV3-1)

### Diagrama UML
```Mermaid
flowchart TD
    cliente["Cliente"]
    veterinario["Veterinário"]

    %% Ações
    subgraph Sistema
        cadastro-pet["Cadastra pet"]
        cadastro-tutor["Cadastra o tutor"]
        agenda["Agenda a consulta"]
    end

    %% Relacionamentos
    cliente -- "Leva pet" --> veterinario
    veterinario --> cadastro-tutor --> cadastro-pet
```

[![](https://mermaid.ink/img/pako:eNptUsFOg0AQ_ZXNJN6gKRQWysGkaY96UeNB8TDCFIiwS5alVpt-jCe_wC_oj7lAMW0jBzLvzWPm8XZ3kMiUIIJ1Kd-THJVmD6tYxYKZJykLEpqeY1gOVQwvY29DmlQhUBXS9B8HdPgy8CgahVdXbHH4PvxQMzJN-5oprHN2XzSaKhz5fiWm2Ggl7Zp0t3eAyAw8WX6m1K2W6lQrWU9d6DEjkaLRLfqCIUukaNpS44nQdC6831GJSSEFViYA2VxEw2ybxXBDm6NDg69Po_knrV5ybv6c6gYdPYAFmSpSiLRqyYKKVIUdhF03NgadU2UOJTKlorTd2imqNzuRZff3sdib72sUT1JW4wgl2yyHaI1lY1Bbp6hpVaA5j-qPVSYFUkvZCg2RE4auBZQWxuftcFX6G9NPhmgHW4hms-nEnZk3D0Mv4D634AOi0JsEDp9zL3AdHsz5fG_BZ29lOgmmLvdD33eCucennrv_BdLC0zQ?type=png)](https://mermaid.live/edit#pako:eNptUsFOg0AQ_ZXNJN6gAVoWysGkaY96UeNB8TDCFDbCbrMstdr0Yzz5BX5Bf8yFFtM2cpr35jHz9u1uIVM5QQLLSr1nJWrDHhapTiWzX1YJkoaeU5gfqhReht6aDGkhUQtl-48HtP-y8CgahFdXbLb_3v9QMzBN-1poXJXsXjSGahz4fiXm2Bit3BWZbu8BIrPwZPmZ0rRG6VOtYj11oceCZI5WN-sLhixTsmkrgydC27nwfkcVZkJJrG0AqrmIhrkuS-GG1keHFl-fRvNPWr3k3Pw51Q06egAHCi1ySIxuyYGadI0dhG03NgVTUm0vJbGlprzduDnqNzdTVXf6VO7s_yuUT0rVwwit2qKEZIlVY1G7ytHQQqC9j_qP1TYF0nPVSgOJH_PQAcqF9Xl7eCr9i-knQ7KFDSTBdDIKxuOxx-N4EvGQO_ABScxHkc-nYeRNgyAOfb5z4LO34o0iL-BhHIZ-NJ1wbxLsfgHUYNM0)


