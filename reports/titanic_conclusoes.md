# Titanic Dataset — Conclusões da Análise

Este ficheiro resume as principais conclusões retiradas dos exercícios feitos com o dataset do Titanic.  

## Limpeza de Dados
- As colunas `age`, `deck` e `embark_town` tinham **valores nulos**.  
  - Para `age`, os valores foram preenchidos com a **mediana**, por ser mais robusta.  
  - Para `deck`, foi criada uma categoria adicional chamada **`'Unknown'`**.
  - Para `embark_town`, os valores foram substituidos por **`'Unknown'`**.

---

## Relações Familiares
- A coluna `sibsp` representa o número de **irmãos/cônjuges** a bordo.  
- A coluna `parch` representa o número de **pais/filhos** a bordo.  
- Foi criada a coluna `family_size = sibsp + parch + 1`.  
- A partir dela, foi gerada a coluna `is_alone`:  
  - `"Yes"` → passageiro sozinho (`family_size == 1`).  
  - `"No"` → passageiro acompanhado.  

---

## Preço dos Bilhetes (`fare`)
- O preço médio pago variou bastante entre classes e sexos:  
  - Passageiros de **1ª classe** pagaram muito mais que os de 2ª e 3ª classe.  
  - Mulheres pagaram em média **mais caro que homens** em todas as classes.  

---

## Outras Observações
- O método `df.describe()` mostrou estatísticas descritivas até à coluna `fare`, já que colunas categóricas não são incluídas por defeito.  
- O uso de `df.query()` facilita filtros como `age > 50` em alternativa a indexação booleana.  
- Foi possível selecionar colunas específicas (ex.: `name`, `age`, `fare`) apenas para passageiros do sexo feminino.  

---