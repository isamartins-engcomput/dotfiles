# ⚙️ Dotfiles Factory

Bem-vinda à **Factory** definitiva do meu ambiente de desenvolvimento.

Este repositório armazena e gerencia as configurações cruciais do meu sistema operacional (Debian 13 Trixie + KDE Plasma 6). Utilizando o gerenciador de symlinks GNU Stow, qualquer novo hardware se transforma instantaneamente em uma **Object instance** perfeitamente replicada do meu ecossistema ideal para engenharia e programação.

## 🚀 Pré-requisitos

Antes de iniciar a restauração, certifique-se de que o novo sistema possui os pacotes fundamentais instalados:

```bash
sudo apt update
sudo apt install git stow
```

## 📦 Instanciando o Ambiente (Instalação)

Para importar essas configurações para uma nova máquina, siga as etapas abaixo. A clonagem é feita via HTTPS para manter o fluxo de trabalho ágil e direto, dispensando a configuração de chaves de terceiros.

**1. Clone o repositório para o diretório raiz do seu usuário:**

```bash
git clone [https://github.com/isamartins-engcomput/dotfiles.git](https://github.com/isamartins-engcomput/dotfiles.git) ~/dotfiles
cd ~/dotfiles
```

**2. Invoque o Stow para gerar os links simbólicos:**
O Stow vai ler cada diretório isolado aqui dentro e injetar os atalhos invisíveis (symlinks) diretamente no diretório pai (`~/`). Para o sistema, é como se os arquivos estivessem no lugar padrão.

```bash
stow bash
stow git
stow kde
```

> **Aviso de Conflito:** Se o sistema recém-instalado já tiver criado um arquivo padrão (como um `~/.bashrc` limpo), o Stow abortará a operação para evitar sobrescrever dados. Se isso acontecer, basta excluir o arquivo original (`rm ~/.bashrc`) e rodar o comando do Stow novamente.

## 🛠️ Manutenção e Atualizações

Sempre que uma otimização for feita no ambiente de desenvolvimento, o fluxo para imortalizar a alteração na nuvem é simples:

1. O symlink garante que editar o arquivo no sistema já é editar o arquivo no repositório.
2. Navegue até a pasta da Factory:

```bash
   cd ~/dotfiles
```

3. Registre e envie a mudança:

```bash
   git add .
   git commit -m "feat: atualização de aliases e tema"
   git push
```

---

*Manutenção da infraestrutura por Isadora Martins.*
