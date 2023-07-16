# BasicoRSTUDIO
Comandos Básicos de carregamento, limpeza e grafico de arquivo CSV

Subindo Arquivo:
```{r}
install.packages("openxlsx") # Instalando Biblioteca para leitura de arquivo.
library(openxlsx) # Carregando

capiao<- read.csv(file.choose(),header = T,sep = ';')
capiao

```
# Explorando Dados
```{r}
head(capiao,10) # 10 Primeiros Registros.
str(capiao)# Extrutura do topico.
summary(capiao)# Resumo estatistico.
```

# Limpeza dos Dados
```{r}
is.na(capiao) # Verificando valores nulos.

```
# Criação de Gráfico
```{r}
install.packages('ggplot2')
library(ggplot2)

grafico <- ggplot(capiao, aes(x = Comarca, fill = UF)) +
  geom_bar(position = "dodge") +
  labs(x = "Processos", y = "Contagem", fill = "UF") +
  ggtitle("Gráfico de Processos por UF e Comarca") +
  theme(legend.position = "bottom")

print(grafico)
```


