<!-- antes de enviar a versão final, solicitamos que todos os comentários, colocados para orientação ao aluno, sejam removidos do arquivo -->

# Análise de Sentimento das Empresas Listadas no Índice S&P 500 por FinBERT

#### Aluno: [Paulo Gabriel Dantas Laque](https://github.com/paulolaque).
#### Orientador: [Felipe Borges Coelho](https://github.com/FelipeBorgesC).
---

Trabalho apresentado ao curso [BI MASTER](https://ica.puc-rio.ai/bi-master) como pré-requisito para conclusão de curso e obtenção de crédito na disciplina "Projetos de Sistemas Inteligentes de Apoio à Decisão".

- [Link para o código (parte 1) - Extração de MD&As das Empresas do S&P 500](https://github.com/paulolaque/sp500-mda-finbert-sentiment/blob/main/MD%26A.ipynb). <!-- caso não aplicável, remover esta linha --> 
 Carregar no notebook o arquivo edgar_v3.py e sp500.csv
- [Link para o código (parte 2) - Limpeza e Análise de Sentimentos](https://github.com/paulolaque/sp500-mda-finbert-sentiment/blob/main/Limpeza%20e%20%20An%C3%A1lise%20FinBERT.ipynb). <!-- caso não aplicável, remover esta linha --> 
- [Link para o código (parte 3) - Análise dos Resultados](https://github.com/paulolaque/sp500-mda-finbert-sentiment/blob/main/Regress%C3%A3o_Sentimento.ipynb). <!-- caso não aplicável, remover esta linha --> Carregar com o graphs.py
- [Link para o resultado](https://github.com/paulolaque/sp500-mda-finbert-sentiment/blob/main/Regress%C3%A3o_Sentimento.ipynb)


- Trabalhos relacionados: <!-- caso não aplicável, remover estas linhas -->
    - [MD&A Extractor](https://github.com/tzuhsial/edgar-10k-mda).
    - [Github FinBERT](https://github.com/yya518/FinBERT).
    - [Paper FinBERT](https://arxiv.org/abs/1908.10063)
    

---

### Resumo

<!-- trocar o texto abaixo pelo resumo do trabalho, em português -->

O objetivo deste trabalho é criar uma forma automatizada de análisar em escala o sentimento dos documentos financeiros publicados por todas
as empresas listada no índice financeiro S&P 500. Os documentos análisados são aqueles enviados à SEC (autoridade de valores mobiliários americana) anualmente
com comentários da gestão de cada companhia sobre a performance passada e sobre as expectativas do futuro, conhecidos como a seção MD&A do arquivo 10K. 
Compilei os resultados em uma tabela onde cada linha é uma empresa do S&P 500 e que contém uma coluna para o documento por empresa. 
Os documentos foram analisádos pelo modelo FinBERT afim de se obter as notas de sentimentos.
Os resultados indicam baixa capacidade de previsibilidade da resposta do mercado aos releases, sendo estes relatórios apresentados com sentimentos mais otimistas do que o mercado em todos os anos analisados. Apenas o ano de 2019 que apresentou relevância estatística na previsibilidade de retornos contra os sentimentos apresentados nos demonstrativos.

### Abstract <!-- Opcional! Caso não aplicável, remover esta seção -->

<!-- trocar o texto abaixo pelo resumo do trabalho, em inglês -->

The objective of this work is to create an automated way to analyze in scale the sentiment of the financial documents published by all
companies listed on the S&P 500 financial index. The documents analyzed are those submitted to the SEC (US Securities Authority) annually
with comments from each company's management on past performance and expectations for the future, known as the MD&A section of the 10K file.
I compiled the results into a table where each row is an S&P 500 company and which contains a column for the document per company.
Those documents were analysed under FinBERT model in order to return a sentiment score.
The results indicate low predictability of the market's response to releases, and these reports are presented with more optimistic feelings than the market in all the years analyzed. Only the year 2019 showed statistical relevance in predicting returns against the sentiments presented in the statements.

### 1. Introdução

O objetivo deste trabalho é criar uma forma automatizada de análisar em escala o sentimento dos resultados apresentados pelas empresas listadas no índice financeiro S&P 500. Os documentos análisados são aqueles enviados à SEC (autoridade de valores mobiliários americana) anualmente
com comentários da gestão de cada companhia sobre a performance passada e sobre as expectativas do futuro, conhecidos como a seção MD&A do arquivo 10K. 


### 2. Modelagem

Foram extraidos os textos das demonstrações financeiras de todas as empresas listadas no índice financeiro entre os anos 2015-2019. Totalizando aproximadamente 2500 documentos.
Compilei os resultados em uma tabela (results.csv) onde cada linha é uma empresa do S&P 500 e que contém uma coluna para o documento por empresa. 
Utilizei um script de extração de MD&A já publicado e criei algumas modificações para executar a extração em escala para todas as empresas do S&P em cada ano. Após este processo, fiz a limpeza de alguns caracteres do documento para torná-lo legível.
Então tokenizei as frases de cada documento e executei o modelo FinBERT de análise de sentimentos para cada frase, computando no final, a média de sentimentos descontados frases cujo sentimento foi nulo por empresa e por ano, resultando na coluna sentimentos.
A coluna sentimentos quando é negativo indica performance ruim, zero é neutro e positivo indica performance boa/excelente.

### 3. Resultados

A extração obteve resultados satifatórios sendo possivel extrair os releases de todas as empresas. Porém o sentimento não se demonstrou um bom preditor da valorização de mercado em relação a divulgação dos documentos, sendo que apenas no ano de 2019 foi possível ter esse sentimento como preditor estatísticamente significante à 5%. Vimos que exitem fortes indicios autoregressivos visto que exite alta correlação entre os sentimentos passados mais próximos.

### 4. Conclusões

Não encontramos evidências de predição no modelo atual, sendo dos cinco anos analisados apenas 2019 houve poder preditivo do modelo.
Sugiro para próximos estudos a criação de métodos de distinção entre palavras que se referem ao passado e ao futuro para distinguir comentários de resultados realizados contra previsões (guidance) da gestão da companhia. Outra possível melhoria se daria pela retirada de disclosures de riscos, pois estes mostram cenários possíveis mas que não necessáriamente foram realizados, portanto punindo empresas de setores com exigências legais altas nos disclosures como a aéreo-espacial. Próximos estudos também podem explorar mais exautivamente o componente autoregressivo dos sentimentos das demonstrações financeiras com modelos mais complexos.

---

Matrícula: 192.110.127

Pontifícia Universidade Católica do Rio de Janeiro

Curso de Pós Graduação *Business Intelligence Master*
