# Alterando nome do roteador

Considere o seguinte cenário:

<img width="495" height="305" alt="image" src="https://github.com/user-attachments/assets/eaeaecfa-2ec0-4630-9e05-36da0270cbb5" />

Veja que na Interface ```GigabitEthernet 0/0``` deverá conter o IP ```192.168.2.1```.
Para configurar esta Interface, iremos ingressar na Interface de Linha de Comando (CLI) do roteador:

<img width="871" height="888" alt="image" src="https://github.com/user-attachments/assets/265ba504-cb1f-41a0-a63d-a218f0e6c2f9" />

Onde somos indagados se queremos ingressar no diálogo de configuração. Nossa resposta, será ```yes```.

Para tornar mais personalizável, irei editar o nome do roteador, onde para isto será necessário ingressar em modo adiministrador, usando o comando ```enable```, e em seguida o ```configure terminal```, que ingressa nas configurações do rotedor. Veja um registro deste ponto:

<img width="852" height="846" alt="image" src="https://github.com/user-attachments/assets/54780fcc-da43-4fa2-8dce-7eb0ba59d49d" />

Agora, iremos utilizar o comando para definir o nome do nosso roteador:

<img width="865" height="853" alt="image" src="https://github.com/user-attachments/assets/1beff0ce-ab6a-4373-aae3-d5e1ff82b3cc" />


# Configurando Interface 0/0

Para configurar a Interface de Rede, é importante lembrar que sempre deveremos estar no modo administrador [enable] e nas configurações do roteador [conf t], estando neste ponto, devemos definir qual interface de rede iremos configurar, já que para o roteador escolhido para a prática possui três interfaces, 0/0 ; 0/1 e 0/2. Para isto, iniciaremos com o seguinte comando:
```
interface gigabitEthernet <interface desejada>
```

Para configurar o IPv4, utilizaremos:
```
ip address <ip desejado> <mascara em decimal> [metrica]
```

Em seguida para aplicar a configuração de IPv4, é necessário rodar o seguinte comando:
```
no shutdown
```

Para a configuração de IPv6, é necessário inicialmente habilitar o roteamento IPv6 usando o comando:
```
ipv6 unicast-routing
```

Em seguida segue o comando de configuração semelhante ao do IPv4, mudando apenas o início:
```
ipv6 address <ip desejado>/<mascara em decimal> [metrica]
```

E a aplicação do mesmo, usando:
```
no shutdown
```

Veja um exemplo da configuração dos dois IP's para a Interface 0/0:

<img width="871" height="558" alt="image" src="https://github.com/user-attachments/assets/67d2c0fe-3034-4923-b337-4feab3a2930f" />

Para verificar se realmente a interface está com os IP's indicados, utilizaremos o seguinte comando seguinte para verificar os IPv4:
```
do show ip interface brief
```

E o seguinte para IPv6:
```
do show ipv6 interface brief
```

Veja no nosso exemplo, como se comportam estes comandos para visualização das configurações de IP's da Interface:

<img width="870" height="594" alt="image" src="https://github.com/user-attachments/assets/620be6ca-98c3-4e07-83ef-b566f9b4ea7e" />

