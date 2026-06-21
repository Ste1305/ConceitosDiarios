# **Dia 21 de Junho 2026**

# Java
- **Exercicio 1 sobre encapsulamento e classes**: o texto do exercicio é o seguinte:

Escreva um código onde controlamos as funções de um carro, ele deve ter as seguintes funções:
- Ligar o carro;
- Desligar o carro;
- Acelerar;
- Diminuir velocidade;
- Virar para esquerda/direita
- Verificar velocidade;
- Trocar a marcha

Siga as seguintes regras na implementação:
- Quando o carro for criado ele deve começar desligado, em ponto morto e com sua velocidade em 0.
- O carro desligado não pode realizar nenhuma função.
- Quando o carro for acelerado ele deve incrementar 1km em sua velocidade (pode chegar no máximo a 120km).
- Quando diminuir a velocidade do carro ele deve decrementar 1 km de sua velocidade (pode chegar no minimo a 0km).
- O carro deve possuir 6 marchas, não deve ser permitido pular uma marcha no carro.
- A velocidade do carro deve respeitar os seguintes limites para cada velocidade:
    - Se o carro estiver na marcha 0 (ponto morto) ele não pode acelerar.
    - Se estiver na 1ª marcha sua velocidade pode estar entre 0km e 20km.
    - Se estiver na 2ª marcha sua velocidade pode estar entre 21km e 40km.
    - Se estiver na 3ª marcha sua velocidade pode estar entre 41km e 60km.
    - Se estiver na 4ª marcha sua velocidade pode estar entre 61km e 80km.
    - Se estiver na 5ª marcha sua velocidade pode estar entre 81km e 100km.
    - Se estiver na 6ª marcha sua velocidade pode estar entre 101km e 120km.

- O carro podera ser desligado se estiver em ponto morto (marcha 0) e sua velocidade em 0 km.
- O carro só pode virar para esquerda/direita se sua velocidade for de no mínimi 1km e no máximo 40km.

Aqui o link GitHub do exercicio que desenvolvi [exercicio Car](https://github.com/Ste1305/Java_Exercicios/tree/main/Car).

# Linux (Ubuntu 26.04)
- **Configurações de Rede**: para poder usar comandos sobre configuração de rede, precisa instalar o pacote *net-tools*: `sudo apt install net-tools`.
    - `sudo ifconfig`: permite as configurações basica de uma rede, como endereco IP e máscara de rede; permite visualizar o *loopback* (na interface `lo`), que indica como apontar a nossa propria maquina, mesmo quando a interface de rede esteja inativa.
        - `sudo ifconfig up` / `sudo ifconfig down`: liga ou desliga a interface de rede.
        - Para alterar o valor do IP ou da máscara de rede: `sudo ifconfig *nome rede* *novo valor IP* netmask *novo valor máscara rede*`.
    - `sudo route`: visualizar e/ou estabelecer novas rotas.
        - `sudo route add -net *novo endereço IP* netmask *novo valor máscara subrede* dev *nome da interface*`: adiciona uma nova rota colocando na ordem o IP novo, netmask seguido do valor da máscara, dev seguido do nome da interface.
    - `sudo nmap`: scaneia as portas abertas na máquina-alvo e indica porque estão abertas (*Port scan*). A realização desse Prt scan é considerado um ataque de invasão preliminar, então utilize só em maquinas onde você atua.
        - `sudo apt install nmap` para instalar o pacote nmap.
        - `sudo nmap --allports -sV`: `--allports` scaneia TODAS as portas; `-sV` indica respetivamente o serviço que está escutando na porta aberta e a versão dele.

