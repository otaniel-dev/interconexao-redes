# Configurando rede interfaces de rede
.
Inicialmente é necessário habilitar o encaminhamento de IPv4 para que seja possível utiulizar o IPv4 nas nossas máquinas, para isto, iremos ingressar no arquivo de configurações do sistema usando o camando:
```
nano /etc/sysctl.conf
```
Neste arquivo encontraremos o seguinte registro:
<img width="799" height="597" alt="image" src="https://github.com/user-attachments/assets/bc76ce4a-1abf-44ac-ad99-b71af3fee159" />

Aqui, iremos descomentar [remover o '#'] na opção ```net.ipv4.ip_forward=1```, deixando o arquivo assim:
<img width="798" height="598" alt="image" src="https://github.com/user-attachments/assets/07d5b7b5-43d4-4d3b-b7c5-92bcab77fcf1" />

Após permitir o encaminhamento IPv4, iremos configurar nossas interfaces de rede, para isto iremos ingressar no arquivo de configuração de interfaces usando o comando:
```
nano /etc/network/interfaces
```
Onde encontraremos isto:
<img width="797" height="598" alt="image" src="https://github.com/user-attachments/assets/555cf01c-3a7f-45ed-8fc1-00d203229fc7" />

Neste ponto, iremos configurar para o Cenário 1, o Roteador 2 que é o mais completo, servindo de exemplo para os demais. Para isto precisamos inserir as interfaces no loopback desta maneira:
<img width="637" height="248" alt="image" src="https://github.com/user-attachments/assets/27b2a459-cd61-4042-812d-7ed3d6d14cbe" />

Veja que adicionei: enp0s3, enp0s8 e enp0s9

Após adicionar o nome das interfaces iremos confiugurá-las de acordo com a prática, usando o IP 192.168.2.1 e a Máscara 255.255.255.0 para a primeira interface, deixando-a assim:
<img width="755" height="599" alt="image" src="https://github.com/user-attachments/assets/78669983-f00a-4fea-8ab9-fa98c3eecdb5" />

Veja que mudamos de ```dhcp``` para ```static``` e adicionamos o campo ```address``` com o ip em seguida e o campo ```netmask``` com o endereço da máscara em seguida. 

Para as outras duas interfaces faremos o mesmo:
<img width="753" height="601" alt="image" src="https://github.com/user-attachments/assets/49dadb4d-fdb3-494b-a366-e74ba9761b96" />

Ao concluir, salvamos o arquivo.

Após configurar os endereços e interfaces, é necessário reiniciar as interfaces. Para verificarmos quais interfaces estão ativas usamos o comando
```
ip -c -br add
```
As que estiverem com ```UP``` estão ativas. As que estão em ```DOWN``` estão inativas.

Para todas, iremos reinicar para garantir, usando os comandos:
```
ifdown enp0s3
ifup enp0s3
```

```
ifdown enp0s8
ifup enp0s8
```

```
ifdown enp0s9
ifup enp0s9
```

Após reiniciá-las, podemos verificar que os ips já foram atribuidos corretamente:
<img width="752" height="121" alt="image" src="https://github.com/user-attachments/assets/90857b04-2eeb-4733-80ca-d323816ff673" />
