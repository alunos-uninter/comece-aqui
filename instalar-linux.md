# Instalação do Linux: Virtual Machine e Docker

Este guia fornece instruções detalhadas sobre como instalar o Linux.

## 1. Instalando o Linux em uma Máquina Virtual (VM)

### Requisitos:
- **VirtualBox** ou **VMware** instalado no seu sistema
- **Imagem ISO** da distribuição Linux desejada (Ubuntu, Debian, Fedora, etc.)

### Passos:
1. **Baixar a ISO**
   - Acesse o site oficial da distribuição Linux desejada e baixe a imagem ISO.

2. **Criar uma nova VM**
   - Abra o **VirtualBox** ou **VMware** e clique em "Criar Nova Máquina".
   - Escolha um nome e selecione o tipo de sistema operacional (**Linux**) e a versão correspondente à sua ISO.

3. **Configurar a VM**
   - **Memória RAM**: Recomenda-se pelo menos **2GB** para um desempenho razoável.
   - **Disco rígido**: Escolha **criar um novo disco virtual** e aloque pelo menos **20GB**.
   - **Configuração de CPU**: Recomenda-se pelo menos **2 núcleos** para uma experiência fluida.

4. **Montar a ISO e iniciar a VM**
   - Vá até as configurações da VM e adicione a **ISO baixada** ao drive de CD/DVD.
   - Inicie a VM e siga as instruções do instalador para configurar o Linux.

5. **Finalizar a instalação**
   - Após a instalação, remova a **ISO** do drive virtual e reinicie a VM.

---

## 2. Instalando o Linux em um contêiner Docker

### Requisitos:
- **Docker** instalado no seu sistema
- Acesso ao terminal

### Instalando o Docker:
#### Ubuntu/Debian:
```sh
sudo apt update
sudo apt install docker.io -y
sudo systemctl enable --now docker
```

#### macOS:
- Baixe o **Docker Desktop**: https://www.docker.com/products/docker-desktop/

#### Windows:
- Baixe e instale o **Docker Desktop**: https://www.docker.com/products/docker-desktop/

### Criando um contêiner Linux
Para rodar um contêiner com Ubuntu:
```sh
docker run -it ubuntu /bin/bash
```

Para rodar um contêiner com Debian:
```sh
docker run -it debian /bin/bash
```

### Acessando um contêiner já criado
Para listar os contêineres em execução:
```sh
docker ps
```

Para listar todos os contêineres (inclusive os parados):
```sh
docker ps -a
```

Para entrar em um contêiner ativo:
```sh
docker exec -it <CONTAINER_ID> /bin/bash
```

Para parar um contêiner:
```sh
docker stop <CONTAINER_ID>
```

Para remover um contêiner:
```sh
docker rm <CONTAINER_ID>
```

### Criando um contêiner Linux persistente
Se quiser criar um contêiner e manter os dados mesmo após sair:
```sh
docker run -it --name meu_linux -v $(pwd)/dados:/dados ubuntu /bin/bash
```
Isso criará um contêiner chamado `meu_linux` com uma pasta compartilhada chamada `dados`.

### Conclusão
Agora você pode rodar o Linux tanto em uma Máquina Virtual quanto em um contêiner Docker, dependendo da sua necessidade.
- **VM**: Melhor para rodar aplicações gráficas ou ter uma experiência completa do sistema.
- **Docker**: Ideal para testes rápidos e ambientes de desenvolvimento isolados.

Se tiver dúvidas ou precisar de mais informações, consulte a documentação oficial do [VirtualBox](https://www.virtualbox.org/) e do [Docker](https://docs.docker.com/).

