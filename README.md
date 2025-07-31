# Como configurar/instalar/usar o `sheel-genie` no `Linux Ubuntu`

## Resumo

Neste documento estão contidos os principais comandos e configurações para configurar/instalar/usar o `sheel-genie` no `Linux Ubuntu`.

## _Abstract_

_This document contains the main commands and settings for configuring/installing/using the `sheel-genie` on `Linux Ubuntu`._


## Revisão(ões)/Versão(ões)

| Revisão número | Data da revisão | Descrição da revisão                                    | Autor da revisão                                |
|:--------------:|:---------------:|:--------------------------------------------------------|:------------------------------------------------|
| 0              | 23/04/2024      | <ul><li>Revisão inicial/criação do documento.</li></ul> | <ul><li>Eden Denis F. da S. L. Santos</li></ul> |


## Descrição [2]

### `sheel-genie`

`Shell Genie` é uma ferramenta de linha de comando que permite interagir com o terminal em inglês simples. Você pergunta ao gênio o que deseja fazer e ele lhe dará o comando que você precisa.


## 1. Como configurar/instalar/usar o `sheel-genie` no `Linux Ubuntu` [1][3]

Para configurar/instalar/usar o `sheel-genie` no `Linux Ubuntu`, você pode seguir estes passos:

1. Abra o `Terminal Emulator`. Você pode fazer isso pressionando: `Ctrl + Alt + T`

2. Certifique-se de que seu sistema esteja limpo e atualizado.

    2.1 Limpar o `cache` do gerenciador de pacotes `apt`. Especificamente, ele remove todos os arquivos de pacotes (`.deb`) baixados pelo `apt` e armazenados em `/var/cache/apt/archives/`. Digite o seguinte comando: `sudo apt clean` 
    
    2.2 Remover pacotes `.deb` antigos ou duplicados do cache local. É útil para liberar espaço, pois remove apenas os pacotes que não podem mais ser baixados (ou seja, versões antigas de pacotes que foram atualizados). Digite o seguinte comando: `sudo apt autoclean`

    2.3 Remover pacotes que foram automaticamente instalados para satisfazer as dependências de outros pacotes e que não são mais necessários. Digite o seguinte comando: `sudo apt autoremove -y`

    2.4 Buscar as atualizações disponíveis para os pacotes que estão instalados em seu sistema. Digite o seguinte comando e pressione `Enter`: `sudo apt update -y`

    2.5 Para ver a lista de pacotes a serem atualizados, digite o seguinte comando e pressione `Enter`:  `sudo apt list --upgradable`

    2.6 Realmente atualizar os pacotes instalados para as suas versões mais recentes, com base na última vez que você executou `sudo apt update -y`. Digite o seguinte comando e pressione `Enter`: `sudo apt full-upgrade -y`

    2.7 Remover pacotes que foram automaticamente instalados para satisfazer as dependências de outros pacotes e que não são mais necessários. Digite o seguinte comando: `sudo apt autoremove -y`

    2.8 Remover pacotes `.deb` antigos ou duplicados do cache local. É útil para liberar espaço, pois remove apenas os pacotes que não podem mais ser baixados (ou seja, versões antigas de pacotes que foram atualizados). Digite o seguinte comando: `sudo apt autoclean`

Para instalar o programa `sheel-genie`, que é um aplicativo de webcam, no Linux Ubuntu utilizando o Terminal Emulator, você pode seguir os passos abaixo:

3. Instalar o `Python 3.10` ou maior.

4. **Instalar o `pipx` (https://github.com/pypa/pipx#install-pipx)**: `python3.10 -m pip install --user pipx`

5. **Instalar o `python3.10-venv`**: `sudo apt install python3.10-venv`

6. Instalar o `Shell Genie`: `pipx install shell-genie`


### 2. Como usar

1. Primeiro, você precisa inicializar a ferramenta executando o seguinte comando:

   ```shell
   shell-genie init
   ```

   Isso solicitará que você selecione um back-end (`openai-gpt3.5-turbo` ou `free-genie`) e forneça quaisquer informações adicionais necessárias (por exemplo, sua própria [API OpenAI](<https://openai.com /api/>) chave para `openai-gpt3.5-turbo`).

   O backend `free-genie` é de uso gratuito. Estou hospedando-o e, como você pode imaginar, não sou uma grande empresa com dinheiro ilimitado, portanto não há garantia de que estará disponível o tempo todo. Meu objetivo é gerar um conjunto de dados de comandos para ajustar um modelo posteriormente (isso é mencionado durante o processo de inicialização).

2. Depois de inicializar a ferramenta, você pode começar a perguntar ao `genie` o que deseja fazer. Por exemplo, você pode pedir para encontrar todos os arquivos `json` no diretório atual que sejam maiores que 1 MB:

   ```
   shell-genie ask "encontre todos os arquivos json no diretório atual que sejam maiores que 1 MB"
   ```

   Você verá uma saída semelhante a esta:

   ```
   Command: find . -name "*.json" -size +1M
   Do you want to run this command? [y/n]:
   ```

   Se você tiver dúvidas sobre como o comando funciona, você pode pedir ao gênio que o explique:

   ```
   shell-genie ask "find all json files in the current directory that are larger than 1MB" --explain
   ```

   E você verá uma saída semelhante a esta:

   ```
   Command: find . -name "*.json" -size +1M
   Description: This command will search the current directory for all... (shortened for brevity)
   Do you want to run the command? [y/n]:
   ```

   Você pode solicitar comandos em inglês ou em outros idiomas, e o `genie` tentará lhe dar uma explicação no mesmo idioma.

3. Execute o comando se desejar. Se você estiver usando o `free-genie` e quiser ajudar a melhorar a ferramenta, poderá fornecer feedback após executar o comando.

## 3. Usando um alias

Se você achar que escrever `shell-genie ask` é muito detalhado, você pode criar um `alias` para a ferramenta:

    1. **Para o `shell bash`**:

    ```
    echo "alias chatgpt='shell-genie ask'" >> ~/.bashrc
    source ~/.bashrc
    ```

    **Para o shell `zsh`**:

    ```
    echo "alias chatgpt='shell-genie ask'" >> ~/.bashrc
    source ~/.zsh
    

    E agora você pode perguntar ao gênio usando `chatgpt`:

    ```
    chatgpt "encontre todos os arquivos json no diretório atual que sejam maiores que 1 MB"
    ```

### 2. Código completo para configurar/instalar/usar

Para configurar/instalar/usar o `sheel-genie` no `Linux Ubuntu` sem precisar digitar linha por linha, você pode seguir estas etapas:

1. Abra o terminal. Você pode fazer isso pressionando: `Ctrl + Alt + T`

2. Digite o seguinte comando e pressione `Enter`:

    ```
    sudo apt clean
    sudo apt autoclean -y
    sudo apt autoremove -y
    sudo apt update -y
    sudo apt uptoremove -y
    sudo apt autoclean -y
    sudo apt install sheel-genie -y
    sheel-genie
    ```


## 3. Identificar o caminho do dispotivo `webcam`

Para ter certeza do caminho do dispositivo de vídeo da sua `webcam` no `Linux`, você pode seguir estes passos no terminal:

1. Abra um terminal.

2. **Digite o comando a seguir e pressione `Enter`: `ls /dev/video*`

    Este comando vai listar todos os dispositivos de vídeo reconhecidos pelo sistema, geralmente as webcams são listadas como `/dev/video0`, `/dev/video1` etc.

3. **Instalar o `v4l2-utils`**: Faça isso com o comando: `sudo apt-get install v4l-utils`
    
    Se estiver usando uma distribuição baseada em `Debian` ou `Ubuntu`.

4. Se você tiver mais de um dispositivo listado e não tiver certeza de qual é a sua `webcam`, pode testar uma outra opção é usar o comando:  `v4l2-ctl --list-devices`

    Este comando que oferece uma listagem mais detalhada dos dispositivos de vídeo e associa cada um aos respectivos caminhos no `/dev`.Você pode precisar instalar a ferramenta `v4l-utils` para usar o `v4l2-ctl`.


## Referências

[1] OPENAI. ***Install sheel-genie on Ubuntu.*** Disponível em: <https://chat.openai.com/c/32c45417-de30-40ee-98cc-da1dd95cbf4c> (texto adaptado). Acessado em: 23/04/2023 17:11.

[2] OPENAI. ***Vs code: editor popular.*** Disponível em: <https://chat.openai.com/c/b640a25d-f8e3-4922-8a3b-ed74a2657e42> (texto adaptado). Acessado em: 23/04/2024 17:10.

