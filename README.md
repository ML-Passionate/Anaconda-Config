Configuração do Anaconda e do ambiente Python

# Configurações do Anaconda 
 
## 1) Lista as configurações do Anaconda

conda config --show

## 2) Listar todas as versões de python instaladas no anaconda

conda search "^python$"

# Configurações de um ambiente

## 1) Lista as configurações do ambiente ativo

conda info

## 2) Descobrir a versão de python do ambiente ativo

python --version

## 3) Lista os pacotes do ambiente ativo

conda info --envs

## 4) Atualizar ou mudar a versão do Python no ambiente ativo 

Nota. Não usar 3.10.10 (3.10 ele instala a mais nova).

conda install python=3.10

## 5)  Descobrir a versão de python, sem ativar o ambiente

conda list -n meu_env python

## 6) Mudar a versão do Python em um ambiente ativo, ou não

conda activate meu_env
conda install python=3.10

## 7) Como instalar um pacote no ambiente ativo

conda install numpy pandas

## 8) como deletar um pacote do ambiente ativo

conda remove numpy

## 9) Como atualizar os pacotes do ambiente ativo

conda update --all

# Gerenciamento de ambientes

## 1) Listar todos os ambientes Conda disponíveis (base é o default)

conda env list

## 2) Criar um ambiente com pacotes

conda create -n meu_env python=3.8 numpy pandas
conda activate meu_env

## 3) Ativar um ambiente

conda activate meu_env

## 4) Remover um ambiente

conda remove --name meu_env --all

## 5) O ambiente base é automaticamente ativado, para desativar que ele seja automaticamente ativado

conda config --set auto_activate_base False

## 6) Ativar automaticamente um ambiente ao abrir o terminal

echo conda activate meu_env >> %USERPROFILE%\Documents\conda_auto.bat

Pressione Win + R, digite regedit e pressione Enter.

Navegue até:

HKEY_CURRENT_USER\Software\Microsoft\Command Processor

Clique com o botão direito em Command Processor > Novo > Valor da String.

Nomeie como AutoRun e defina o valor como:

%USERPROFILE%\Documents\conda_auto.bat
Agora, sempre que abrir o cmd, o ambiente será ativado automaticamente.

## 7) Definir um ambiente como padrão dentro do Conda

conda config --set env_prompt "({name}) "
conda config --set auto_activate_base False
echo "conda activate meu_env" >> %USERPROFILE%\.condarc

# Compartilhando ambientes

Quando usar environment.yml?
https://github.com/ML-Passionate/Anaconda-Config/blob/main/environment.yml

Para compartilhar um ambiente entre equipes.
Para garantir que um ambiente seja recriado com as mesmas versões de pacotes.
Para documentar as dependências de um projeto.

## 1) Criando um ambiente a partir de um arquivo enviroment.yml

conda env create -f environment.yml

## 2) Exportando a configuranção de um ambiente para enviroment.yml

conda env export > C:\Draft\environment.yml 

## 3) Atualizar um arquivo enviroment.yml

conda env update --file environment.yml --prune

