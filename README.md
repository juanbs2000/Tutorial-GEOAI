# Tutorial-GEOAI

1. Introdução
O presente trabalho tem como objetivo principal a identificação e o mapeamento de zonas úmidas a partir de imagens de satélite, com base na análise dos índices espectrais NDWI (Normalized Difference Water Index) e NDMI (Normalized Difference Moisture Index). A proposta está inserida no contexto do tutorial "GeoAI 12" da disciplina “Tópicos Especiais em Acústica Dinâmica e Vibrações” e visa demonstrar a utilidade de dados remotos no planejamento ambiental e territorial.

2. Metodologia
Inicialmente foi considerado o uso do software GeoAI com modelagem via inteligência artificial, mas devido à sua lentidão no processamento de dados e limitações no controle sobre os parâmetros dos índices, decidiu-se adotar o Sentinel Hub EO Browser, uma plataforma ágil que permite o download de bandas espectrais específicas (B03, B08, B11) dos satélites Sentinel-2.

Com essas bandas, foram calculados dois índices:

NDWI = (B03 - B08) / (B03 + B08) → utilizado para identificar corpos d'água.

NDMI = (B08 - B11) / (B08 + B11) → utilizado para identificar umidade do solo e vegetação.

A seguir, foi desenvolvido um script em Python (Google Colab) para:

Processar os arquivos .tiff das bandas;

Calcular os índices NDWI e NDMI;

Aplicar uma classificação de cores para destacar:

Azul escuro: água (NDWI > 0.2),

Azul médio e claro: níveis intermediários de NDWI,

Verde escuro a claro: níveis graduais de umidade (NDMI),

Branco: zonas secas;

Gerar uma imagem RGB resultante;

Calcular o percentual de cobertura para cada classe de solo.

3. Resultados
O algoritmo gerou uma imagem final que permite distinguir claramente:

Corpos d’água, como rios e lagos;

Zonas de alta umidade, como várzeas ou regiões de vegetação densa;

Áreas secas, como solos urbanizados ou arenosos.

Além disso, foi obtida uma estatística com os percentuais de cada tipo de cobertura identificada na região analisada.

4. Ferramentas Utilizadas
Sentinel Hub EO Browser – para o download das bandas espectrais e pré-visualização dos índices;

Python (Google Colab) – para o processamento das imagens e geração da classificação;

GitHub – para armazenamento do código, relatório e resultados.

5. Conclusão
A metodologia proposta mostrou-se eficaz e flexível para o mapeamento de zonas úmidas. A distinção entre água pura e áreas com diferentes níveis de umidade permitiu uma análise ambiental detalhada da paisagem. O uso de índices combinados, aliado à visualização em cores e ao cálculo de porcentagens, oferece uma ferramenta poderosa de apoio à tomada de decisão em projetos de gestão ambiental, urbanização e uso do solo.
