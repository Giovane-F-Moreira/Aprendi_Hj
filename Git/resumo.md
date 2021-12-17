# 									**GIT**:computer:

------



O Git é capaz orgazinar e re-organizar arquivos e diretorios, **versionando** suas alterações em ramificações sendo manipuladas por varias pessoas.
O Git utiliza **Hash** SHA1 para identificar qualquer mudança feita em um arquivo 

## Objetos fundamentais do Git

- **Blob** - Armazena um conjunto de caracteres de 40 digitos, o **HASH**
- **Tree**- Modelo **hieraquico** no qual o Git organiza seus **diretorios**
- **Commits** - Funciona como um ' carimbo temporal ', ele registras as modificações feitas pelo autor

## Comandos Iniciais

```
	//Configuração de usuario e email
	$ git config --global user.email "email@gmail.com"
	$ git config --global user.name nome

	//Mostra as configurações do Git
	$ git config --list	
	
	//Faz o link de um repositorio local par aum remoto
	$ git remote add origin https://github.com/usuario/repositorio.git
	$ git push -u origin main
	
	//Exibe lista de repositorios
	$ git remote -v
	
	//Inicia o repositorio locla git 
	$ git init  

	//Verifica o status do repositorio
	$ git status

	//Adiciona todas as alterações ao STAGE
	$ git add .

	//Commita o que foi adicionado anteriormente
	$ git commit -m "mensagem"

	//Envia o commit 
	$ git push
	
	//Baixa as ultimas alterações naquele repositorio 
	$ git pull origin main
	
```



## Conceitos do GIT

- **Untracked** - O Git não conhece esses arquivos
- **Tracked** - Arquivos conhecidos pelo Git
  1. **Unmodified** - Arquivos que não foram alterados - verifica-se pelo SHA1
  2. **Modified** - Arquivos modificados
  3. **Stage** - Arquivos que possuem um 'estado', esse estado é o que antecede o commit, arquivos modificados vão pro **STAGE** apos serem adicionados com comando `$ git add`, estando no **STAGE**, ele podem ir pro **COMMIT**



Caso eliminemos arquivos **Unmodified**, eles irão para os arquivos **Untracked**
Apos *commitar* os arquivos, eles passam a ser **Unmodified**, e aguardam suas novas alterações para serem *commitados* posteriomente

## O Git é um  Sistema Distribuido

- **Servidor** - repositorio remoto

- **Ambiente de desenvolvimento** - Local onde estamos desenvolvendo 

  - Diretorio de trabalho
  - Area de Staging
  - Repositorio Local

  

