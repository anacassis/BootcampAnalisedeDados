## Análise Univariada

Códigos de consulta para Análise Univariada 

#### Primeiro importamos os pacotes que serão utilizados 

> library('readr')
#### Coleta e visualização dos dados do arquivo proposto
> dados_cliente <- read.csv("./clientes.csv",sep=";")

> head(dados_cliente)

![Sem título](https://user-images.githubusercontent.com/97900395/151893721-952f181b-1f39-4909-811d-7529e7f96186.png)

#### Vizualização da estrutura dos dados 
> str(dados_cliente)

![estrutura](https://user-images.githubusercontent.com/97900395/151894201-e8c12232-dba0-41dd-9d59-306ddc9cbd4a.png)


#### Visualizando as ultimas linhas da tabela
> tail(dados_cliente)


#### Definição de Grau de instrução tratada como Ordinal 
> levels(dados_cliente$Grau.Instrução)

> 'Doutorado' 'Fundamental' 'Médio' 'Mestrado' 'Superior'

### Análise univariada de variáveis qualitativas nominais
#### Tabela de frequencia : Estado Civil 

*Frequência absoluta*

>fa <- table(dados_cliente$Estado.civil)
>fa

> casado solteiro

>   20      16 


*Frequência relativa*

>fr2 <- prop.table(fa)
>fr2

>casado  solteiro

>0.5555556 0.4444444 

*Frequência percentual*

>fpct <- prop.table(fa)*100
>fpct

> casado solteiro 

>55.55556 44.44444 

*Informando casas Decimais*

>round(fpct,digit=2)
 
>casado solteiro 

>55.56    44.44 

*Visualizando a Moda* (Valor que mais aparece na tabela)

>names(fa)[which.max(fa)]

>'casado'

#### Visualização dos dados Estado Civil

>barplot(fa,main = "Frequência absoluta",xlab = "Estado Civil",ylab = "Quantidade")

![Estado Civil](https://user-images.githubusercontent.com/97900395/151895835-56e40be6-209f-487e-ba72-0f43ec2f2e30.png)


>pie(main = "Frequência relativa percentual",fpct,labels=as.character(round(fpct,digits = 2)))


![Grafico pizza](https://user-images.githubusercontent.com/97900395/151895837-36730e45-f2d8-47ed-87b2-1c33b15e7dd7.png)
