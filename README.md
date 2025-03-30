# Anaconda-Config
 Configuração do Anaconda e do ambiente Python
 
## 1) Lista as configurações do Anaconda

conda config --show

## 2) lista as configurações do ambiente default

conda info

## 3) Listar todas as versões de python instaladas no anaconda

conda search "^python$"

## 4) Listar todos os ambientes Conda disponíveis (base é o default)

conda env list

## 5) Descobrir a versão de python do ambiente ativo

python --version

## 6) Atualizar ou mudar a versão do Python no ambiente "base". Não usar 3.10.10 (3.10 ele instala a mais nova).

conda install python=3.10

## 7) Listar todos os instalados no ambiente ativo

conda info --envs

## 8)  Descobrir a versão de python Sem ativar o ambiente

conda list -n meu_env python

## 9) Mudar a versão do Python em um ambiente existente

conda activate meu_env
conda install python=3.10

## 10) Remover um ambiente

conda remove --name meu_env --all

## 11) Criar um ambiente com pacotes essenciais

conda create -n meu_env python=3.8 numpy pandas
conda activate meu_env

## 12) O ambiente base é automaticamente ativado, para desativar que ele seja automaticamente ativado

conda config --set auto_activate_base False

## 13) Ativar automaticamente um ambiente ao abrir o terminal

echo conda activate meu_env >> %USERPROFILE%\Documents\conda_auto.bat

Pressione Win + R, digite regedit e pressione Enter.

Navegue até:

HKEY_CURRENT_USER\Software\Microsoft\Command Processor

Clique com o botão direito em Command Processor > Novo > Valor da String.

Nomeie como AutoRun e defina o valor como:

%USERPROFILE%\Documents\conda_auto.bat
Agora, sempre que abrir o cmd, o ambiente será ativado automaticamente.

## 14) Definir um ambiente como padrão dentro do Conda

conda config --set env_prompt "({name}) "
conda config --set auto_activate_base False
echo "conda activate meu_env" >> %USERPROFILE%\.condarc
