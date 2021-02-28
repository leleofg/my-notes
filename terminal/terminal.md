Comandos linux:

```
ls = lista todas as pastas/diretórios e arquivos do diretório atual
ls -l ou ls --long = lista todas as pastas/diretórios com mais informações
ls -l -h = lista todas as pastas/diretórios com mais informações e formata o tamanho da pasta, se tiver um numero grande de bytes
no comando anterior, ele muda pra M nesse agora. Ex: 48707058 fica 48M. -h é um comnando pra deixar mais humano a resposta
ls -a ou ls --all = mostra todos os arquivos, inclusive os ocultos
lscpu ou vá até a raiz dos comandos e rode: cat proc/cpuinfo = para mostrar informações da sua cpu
cd = mudar de diretórios(change directory)
cd .. = volta um diretório
cat arquivo = mostra o conteúdo do arquivo no terminal
pwd = mostra o diretório que estou atualmente
cd ~ = vou direto para meu usuário
mkdir nomeDaPasta = criar diretório(make directory)
touch nomeDoArquivo = criar arquivo
```

Como matar um processo no linux:

```
sudo kill -9 $(sudo lsof -t -i:4000)
```