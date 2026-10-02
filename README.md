# Clínica Veterinária
Trabalho de final da matéria de Engenharia de Software. [2° Semestre/2026]

### Prototipo
Prototipo no Figma: [Aqui](https://www.figma.com/design/0kAb3nbGc9SY4zAAa7lrjq/Clinica-Veterinaria?t=4Qsj4DI84pijXLV3-1)

## Diagrama UML

### Diagrama de caso de uso:
```Mermaid
flowchart TD
    cliente["Cliente"]
    recepcionista["Recepcionista "]
    vet["Veterinário"]

    %% Ações
    subgraph Sistema
        pet["Cadastra pet"]
        tutor["Cadastra o tutor"]
        consulta["Agenda a consulta"]
        examina["Examina pet"]
        diagnostico["Da diagnóstico"]
        cobra["Cobra o valor da consulta $$"]
    end

    %% Relacionamentos
    cliente -- "Leva pet na veterinaria" --> recepcionista --> tutor --> pet
    recepcionista --> consulta

    cliente -- "Entrega pet" --> vet --> examina --> diagnostico
```

[![](https://mermaid.ink/img/pako:eNptU0tu2zAQvQpBJDvZsD6WZC0CBHZ27SYtumjVxUSayAQkUqAo163hw3TVAxQ9gS-WIWW5ihNuOPPmzUdvxAMvVIk848-1-lFsQRv2eZPrXDI6RS1QGvyW8_Vg5fz7GNNYYFsIJUVngBiPU59NiDs0FP6CBrWQp99aqHNwJNzesvvTn9M_7Eak658qDe2WfaJi2MCI29O6cmsooTMarDvpZY_pjdJTihqgK1qhZNfXbvT7CmUJDC7YFRX30AhpmQ-D9U7XUkAlVWdEoYi3gQE4_XXIm9ZP2lZb25vG20GtNCv_92c3N5MUGu5KrkeswUoNDS1FdVfrYrMZ6f8Bd25ORuPuBvFBC_o0Ct-93p5DnEbOsh_33pJd8CLRZKJXfR-k0VidJXIp1N3dZxmdPZFrWol7vNKi5JnRPXq8Qd2AdfnBxnNuttjQT5iRqbHs97NC1XazuTxSagvyq1LNmK1VX2159gx1R17flmBwQ301NBdUk7io16qXhmeRH6Qex1KQEh-HV-Eeh6vMswPf8yxYzMMgDcMoXaRhtIp9j__kWZzMo2XkR0kYpmmc-Kujx3-5URbzJPCDOA5XyzhM4lW6PL4AQjYd2Q?type=png)](https://mermaid.live/edit#pako:eNptU0tu2zAQvQoxSHayEcX6xFoUCOzs2k1adNGqi4k0kQlIpDCiXLeGD9NVD1D0BL5YSMpyFTfccObNm4_eiHsodEmQwXOtvxcbZCM-rXPOlbCnqCUpQ19zWA1WDt_GGFNBbSG1kp1By3ic-mJC3JKx4c9kiKU6_mKpT8GRcH0t7o-_j3-pG5Guf6oY2434aItRgyPuTuvLrbDEzjA6d9LLHdMbzVOKHqALWqFV19d-9PuKVIkCz9gFlXbYSOWYD4P1RtdSYqV0Z2ShLW-NA3D845H_Wj-xq7Zytx1vi7VmUf7rL66uJil2uAu5HqlGJzU2dim6u1iXmM2s_u9p6-cUdtztID6ytJ9mw-9eb88jXiNvuY97a8k-eJZoMtGrvg_KMFUniXyK7e7vk4zensg1rQQBVCxLyAz3FEBD3KBzYe_iOZgNNfYnzKzJVPa7WaFrt9lcHWxqi-qL1s2YzbqvNpA9Y91Zr29LNLS2fRmbM8pWXOKV7pWBLApvogColFaJD8Or8I_DV4ZsDzvIZmE8T9IwSZfRMkmTOFykAfyALI7nURyFaXoXJ1EUL8JDAD_9MDfz9Da8TZLFMk4WabK8iw8ve08eQQ)


