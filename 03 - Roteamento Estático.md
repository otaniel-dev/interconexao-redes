# Cenário considerado

<img width="1900" height="876" alt="image" src="https://github.com/user-attachments/assets/e862f421-71dd-411a-a6c6-887197501090" />

# Tabela de Roteamento de R1

| IP (Rede) | Máscara | Gateway/Next Hop | Interface | Métrica |
|----------------|---------|------------------|-----------|---------|
| 192.168.1.0    | /24     | 192.168.1.1      | 0/0      | 0     |
| 192.168.2.0    | /24     | 10.0.0.2      | 0/1      | 1     |
| 192.168.3.0    | /24     | 10.0.0.6      | 0/2      | 1     |

Para configurar a rota do roteador R1 para acessar a rede ```192.168.2.0/24``` precisamos habilitar o modo administrador usando:
```
enable
```

Em seguida, ingressar no modo de configuração do roteador:
```
configure terminal
```

Para configurar uma rota estática, considerando a tabela de roteamento acima, usaremos:
```
ip route <rede> <mascara_em_decimal> <proximo_salto>
```
