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

[![](https://mermaid.ink/img/pako:eNptUsFugkAQ_ZXNJN7UIOKCHJoYPbaXtumhpYcpjEICu2ZZrK3xY3rqF_QL_LEOIA2actjMe_Nm5jG7B4h1QhDCOtfvcYrGisdVZCIl-IvzjJSllwiWbRTBa5fbkSWTKTSZ5vxTi05fDM-iTjgYiMXp-_RDZceU1dvG4DYVD1lpqcCOb0ZigqU1erQlW89tIQqGveEXSltZbfpaLRrqSo8bUgmybtEEAkWsVVnlFntCzlx5v6cc40wrLHgBurxajRiNRAS3tDs7ZHzTX80_22okl-YvqbrR2QMMYWOyBEJrKhpCQabAGsKhbhuBTangSwk5NJRU-1Gs8_rHI3Xk0i2qZ62LrtroapNCuMa8ZFRtE7S0ypCvovhjDS-AzFJXykI4CQI5BEoytnjXvpLmsTSdITzAHsLp1Bm7Uz5lEHi-nHHBB4SBN_Ynci49351Ify7nxyF8Nlacse-4chbMZhN_7knHc4-_e-zRaQ?type=png)](https://mermaid.live/edit#pako:eNptUsFOg0AQ_ZXNJN6gKRQWysGkaY96UeNB8TDCFIiwS5alVpt-jCe_wC_oj7lAMW0jBzLvzWPm8XZ3kMiUIIJ1Kd-THJVmD6tYxYKZJykLEpqeY1gOVQwvY29DmlQhUBXS9B8HdPgy8CgahVdXbHH4PvxQMzJN-5oprHN2XzSaKhz5fiWm2Ggl7Zp0t3eAyAw8WX6m1K2W6lQrWU9d6DEjkaLRLfqCIUukaNpS44nQdC6831GJSSEFViYA2VxEw2ybxXBDm6NDg69Po_knrV5ybv6c6gYdPYAFmSpSiLRqyYKKVIUdhF03NgadU2UOJTKlorTd2imqNzuRZff3sdib72sUT1JW4wgl2yyHaI1lY1Bbp6hpVaA5j-qPVSYFUkvZCg2RE4auBZQWxuftcFX6G9NPhmgHW4hms-nEnZk3D0Mv4D634AOi0JsEDp9zL3AdHsz5fG_BZ29lOgmmLvdD33eCucennrv_BdLC0zQ)


