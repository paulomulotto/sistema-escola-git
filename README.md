feature -> develop -> main -> release
# Configuração Inicial
- Crie um repositório público no GitHub chamado sistema-escola-git
- Clone o repositório no seu computador seguindo as instruções do GitHub
- Crie uma branch local chamada develop


## Base Escola
- Crie uma branch chamada feature/base_escola
- Na branch feature/base_escola, adicione o arquivo escola.py com o código:
```
class Escola:
    def __init__(self, nome):
        self.nome = nome
```
- Faça o commit do arquivo escola.py
- git commit -m "ENH: Criação da classe das escolas"
- Envie as alterações da branch feature/base_escola e realize o merge com a branch develop

## Base Alunos
- Crie uma branch chamada feature/base_aluno
- Na branch feature/base_aluno, adicione o arquivo aluno.py com o código:
```
class Aluno:
    def __init__(self, nome, cpf):
        self.nome = nome
        self.cpf = cpf
```
- Faça o commit do arquivo escola.py: 
```
git add aluno.py && git commit -m "ENH: Criação da classe dos alunos"
```
- Envie as alterações da branch feature/base_aluno e realize o merge com a branch develop

## Base Alunos
- Crie uma branch chamada feature/base_professor
- Na branch feature/base_professor, adicione o arquivo professor.py com o código:
```
class Professor:
    def __init__(self, nome, cpf):
        self.nome = nome
        self.cpf = cpf
```
- Faça o commit do arquivo professor.py: 
```
git add professor.py && git commit -m "ENH: Criação da classe dos professores"
```
- Envie as alterações da branch feature/base_professor e NÃO realize o merge com a branch develop


## Nova Release
- Faça o merge da branch develop com a branch main
- Crie a release RLS: v1.0.0 com a TAG v1.0.0
- Para baixar a tag para seu computador, utilize ```git fetch --all --tags```

## Implementando a conexão entre escola e aluno
- Crie uma nova branch a partir da main chamada feature/conexao_escola_aluno

- Altere o código de escola.py para:
```
class Escola:
    def __init__(self, nome):
        self.nome = nome
        self.alunos = []
```

- Altere o código de aluno.py para:
```
class Aluno:
    def __init__(self, nome, cpf, escola):
        self.nome = nomee # erro intencional
        self.cpf = cpf
        self.escola.append(self)
```
- Leve para a branch develop a nova feature
```
git add professor.py aluno.py && git commit -m "ENH: Conexão entre as classes Aluno e Escola - com erro"
```


## ATENÇÃO: Branches desatualizadas
- Com a criação da release a classe Aluno e Escola fazem parte do código de produção, logo as features que estavam em desenvolvimento devem baixar os novos códigos e considerar que eles fazem parte do código atual
- Atualize a branch feature/base_professor com o que foi implementado na main
- Faça o merge da branch com a branch develop


## Crie uma nova release 
- RLS: v1.1.0 (nova subversão com novas funcionalidades e elementos)

## Corrija o erro
- Crie uma branch chamada hotfix/atribuicao-nome-aluno
- Utilizando o comando git revert, vamos reverter o commit inteiro com a descrição "Conexão entre as classes Aluno e Escola - com erro"



Anexo:
https://pandas.pydata.org/docs/development/contributing.html#committing-your-code

https://github.com/pandas-dev/pandas

TAG
git checkout v0.0.1

git reset --hard v0.0.1




Anexo 2: Exemplos commit
[Pull Request] - https://github.com/pandas-dev/pandas/pull/50682
[Issue] - https://github.com/pandas-dev/pandas/issues/50342
