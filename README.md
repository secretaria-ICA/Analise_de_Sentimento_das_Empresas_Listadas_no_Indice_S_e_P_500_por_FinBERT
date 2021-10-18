<!-- antes de enviar a versão final, solicitamos que todos os comentários, colocados para orientação ao aluno, sejam removidos do arquivo -->

# Análise de Sentimento das Empresas Listadas no Índice S&P 500 por FinBERT

#### Aluno: [Paulo Gabriel Dantas Laque](https://github.com/paulolaque).
#### Orientador: [Felipe Borges Coelho](https://github.com/FelipeBorgesC).
---

Trabalho apresentado ao curso [BI MASTER](https://ica.puc-rio.ai/bi-master) como pré-requisito para conclusão de curso e obtenção de crédito na disciplina "Projetos de Sistemas Inteligentes de Apoio à Decisão".

- [Link para o código (parte 1) - Extração de MD&As das Empresas do S&P 500](https://github.com/paulolaque/sp500-mda-finbert-sentiment/blob/main/MD%26A.ipynb). <!-- caso não aplicável, remover esta linha -->
- [Link para o código (parte 2) - Limpeza e Análise de Sentimentos](https://github.com/paulolaque/sp500-mda-finbert-sentiment). <!-- caso não aplicável, remover esta linha -->


- Trabalhos relacionados: <!-- caso não aplicável, remover estas linhas -->
    - [MD&A Extractor](https://github.com/tzuhsial/edgar-10k-mda).
    - [FinBERT](https://github.com/yya518/FinBERT).
    

---

### Resumo

<!-- trocar o texto abaixo pelo resumo do trabalho, em português -->

O objetivo deste trabalho é criar uma forma automatizada de análisar em escala o sentimento dos documentos financeiros publicados por todas
as empresas listada no índice financeiro S&P 500. Os documentos análisados são aqueles enviados à SEC (autoridade de valores mobiliários americana) anualmente
com comentários da gestão de cada companhia sobre a performance passada e sobre as expectativas do futuro, conhecidos como a seção MD&A do arquivo 10K. 
Logo existe um documento por ano para cada empresa.
Portanto compilei os resultados em uma tabela onde cada linha é uma empresa do S&P 500 e que contém uma coluna para o documento por empresa. 
Utilizei um script de extração de MD&A já publicado e criei algumas modificações
para executar a extração em escala para todas as empresas do S&P em cada ano. Após este processo, fiz a limpeza de alguns caracteres do documento para torná-lo legível.
Então tokenizei as frases de cada documento e executei o modelo FinBERT de análise de sentimentos. 
A coluna sentimentos quando é negativo indica performance ruim, zero é neutro e positivo indica performance boa/excelente.
### Abstract <!-- Opcional! Caso não aplicável, remover esta seção -->

<!-- trocar o texto abaixo pelo resumo do trabalho, em inglês -->

The objective of this work is to create a sentiment analysis in scale of the financial documents published by all
as companies listed on the S&P 500 financial index. The analyzed documents ar ethe ones sent to the SEC (American Securities Authority) annually
with comments from each company's management on past performance and expectations for the future, known as the MD&A section of the 10K file.
There is one document per year for each company.
I compiled the results into a table where each row is an S&P 500 company and which contains a column for each document per company.
I used a previously published MD&A extraction script and created modifications
to run a scaled extraction for all S&P companies per year. 
After this process, it cleans some characters from the document to make it readable. Then tokenize as sentences from each document and ran the FinBERT sentiment analysis model.
The sentiment column when negative indicates poor performance, zero is neutral and positive indicates good / excellent performance.

### 1. Introdução

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin pulvinar nisl vestibulum tortor fringilla, eget imperdiet neque condimentum. Proin vitae augue in nulla vehicula porttitor sit amet quis sapien. Nam rutrum mollis ligula, et semper justo maximus accumsan. Integer scelerisque egestas arcu, ac laoreet odio aliquet at. Sed sed bibendum dolor. Vestibulum commodo sodales erat, ut placerat nulla vulputate eu. In hac habitasse platea dictumst. Cras interdum bibendum sapien a vehicula.

Proin feugiat nulla sem. Phasellus consequat tellus a ex aliquet, quis convallis turpis blandit. Quisque auctor condimentum justo vitae pulvinar. Donec in dictum purus. Vivamus vitae aliquam ligula, at suscipit ipsum. Quisque in dolor auctor tortor facilisis maximus. Donec dapibus leo sed tincidunt aliquam.

### 2. Modelagem

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin pulvinar nisl vestibulum tortor fringilla, eget imperdiet neque condimentum. Proin vitae augue in nulla vehicula porttitor sit amet quis sapien. Nam rutrum mollis ligula, et semper justo maximus accumsan. Integer scelerisque egestas arcu, ac laoreet odio aliquet at. Sed sed bibendum dolor. Vestibulum commodo sodales erat, ut placerat nulla vulputate eu. In hac habitasse platea dictumst. Cras interdum bibendum sapien a vehicula.

Proin feugiat nulla sem. Phasellus consequat tellus a ex aliquet, quis convallis turpis blandit. Quisque auctor condimentum justo vitae pulvinar. Donec in dictum purus. Vivamus vitae aliquam ligula, at suscipit ipsum. Quisque in dolor auctor tortor facilisis maximus. Donec dapibus leo sed tincidunt aliquam.

### 3. Resultados

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin pulvinar nisl vestibulum tortor fringilla, eget imperdiet neque condimentum. Proin vitae augue in nulla vehicula porttitor sit amet quis sapien. Nam rutrum mollis ligula, et semper justo maximus accumsan. Integer scelerisque egestas arcu, ac laoreet odio aliquet at. Sed sed bibendum dolor. Vestibulum commodo sodales erat, ut placerat nulla vulputate eu. In hac habitasse platea dictumst. Cras interdum bibendum sapien a vehicula.

Proin feugiat nulla sem. Phasellus consequat tellus a ex aliquet, quis convallis turpis blandit. Quisque auctor condimentum justo vitae pulvinar. Donec in dictum purus. Vivamus vitae aliquam ligula, at suscipit ipsum. Quisque in dolor auctor tortor facilisis maximus. Donec dapibus leo sed tincidunt aliquam.

### 4. Conclusões

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin pulvinar nisl vestibulum tortor fringilla, eget imperdiet neque condimentum. Proin vitae augue in nulla vehicula porttitor sit amet quis sapien. Nam rutrum mollis ligula, et semper justo maximus accumsan. Integer scelerisque egestas arcu, ac laoreet odio aliquet at. Sed sed bibendum dolor. Vestibulum commodo sodales erat, ut placerat nulla vulputate eu. In hac habitasse platea dictumst. Cras interdum bibendum sapien a vehicula.

Proin feugiat nulla sem. Phasellus consequat tellus a ex aliquet, quis convallis turpis blandit. Quisque auctor condimentum justo vitae pulvinar. Donec in dictum purus. Vivamus vitae aliquam ligula, at suscipit ipsum. Quisque in dolor auctor tortor facilisis maximus. Donec dapibus leo sed tincidunt aliquam.

---

Matrícula: 192.110.127

Pontifícia Universidade Católica do Rio de Janeiro

Curso de Pós Graduação *Business Intelligence Master*
