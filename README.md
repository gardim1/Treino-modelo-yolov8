# Projeto de Treinamento YOLOv8 para Detecção de Carros de Fórmula E

<img src="https://miro.medium.com/v2/resize:fit:720/format:webp/1*J-xFM5IGIsRwBvpDXbqjJQ.png" alt="Logo Formula E" width="1000"/>

## Descrição do Projeto

Este projeto foi desenvolvido para treinar um modelo YOLOv8 voltado à detecção de carros de Fórmula E em vídeos ou imagens. Utilizando um dataset personalizado hospedado no Roboflow, o treinamento é realizado diretamente no Google Colab, aproveitando o poder de processamento da GPU.

## Funcionalidades

- **Treinamento do YOLOv8**: Treinamento de um modelo YOLOv8 usando um dataset de imagens de carros de Fórmula E.
- **Validação e Previsões**: Valida o modelo treinado e realiza previsões em imagens de teste.
- **Visualização de Resultados**: Exibe gráficos como a matriz de confusão e resultados de validação para análise de performance.

## Como o Código Funciona

1. **Verificação da GPU**: Verifica se há uma GPU NVIDIA disponível para realizar o treinamento com maior eficiência.
2. **Instalação de Dependências**: Instala a versão necessária da biblioteca Ultralytics (YOLOv8) e outras dependências como o Roboflow para gerenciamento de datasets.
3. **Download do Dataset**: O dataset "fecars", relacionado a carros de Fórmula E, é baixado automaticamente do Roboflow, facilitando a configuração do ambiente.
4. **Treinamento do Modelo**: O YOLOv8 é treinado usando o dataset, com 100 epochs e gráficos para monitoramento do progresso.
5. **Validação e Teste**: Após o treinamento, o modelo é validado com um conjunto de dados de teste, gerando previsões visuais e métricas de desempenho.
6. **Visualização de Resultados**: Imagens de exemplo, como a matriz de confusão e previsões sobre as imagens de validação, são exibidas para análise.

## Requisitos

- **Google Colab** (ou ambiente similar com suporte a GPUs)
- **Bibliotecas**:
  - `ultralytics==8.0.196`
  - `roboflow`
  - `opencv-python`

## Como Executar

1. Clone este repositório ou copie o código para um ambiente Colab.
2. Certifique-se de ter configurado uma GPU nas configurações do Colab.
3. Execute as células do notebook para instalar as dependências, baixar o dataset, e iniciar o treinamento do modelo YOLOv8.

### Comandos Principais:

- **Instalação do YOLOv8**:
  ```bash
  !pip install ultralytics==8.0.196
  ```
- **Baixar Dataset do Roboflow**:
  ```bash
  !pip install roboflow
  ```
- **Validação do Modelo**:
  ```bash
  !yolo task=detect mode=val model={HOME}/runs/detect/train2/weights/best.pt data={dataset.location}/data.yaml
  ```
- **Previsões**:
  ```bash
  !yolo task=detect mode=predict model={HOME}/runs/detect/train2/weights/best.pt conf=0.65 source={dataset.location}/test/images save=True

## Visualização de Resultados

Após o treinamento e a validação, você pode visualizar os resultados diretamente no Colab. Aqui estão os principais arquivos de resultado gerados:

1. **Matriz de Confusão**:
   ```bash
   Image(filename=f'{HOME}/runs/detect/train/confusion_matrix.png', width=600)
2. **Resultados do Treinamento, incluindo métricas como precisão, recall, etc**:
   ```bash
   Image(filename=f'{HOME}/runs/detect/train/results.png', width=600)
3. **Predições no Batch de Validação**:
   ```bash
   Image(filename=f'{HOME}/runs/detect/train/val_batch0_pred.jpg', width=600)
4. **Previsões em Imagens de Teste**:
   ```bash
   Image(filename=image_path, width=600)
## Conclusão

Este projeto oferece uma abordagem prática para treinar um modelo YOLOv8 para detectar carros de Fórmula E, fornecendo todas as etapas necessárias, desde a configuração do ambiente até a visualização dos resultados. Ao final do processo, o modelo estará apto a realizar detecções precisas em vídeos ou imagens, exibindo as bounding boxes e os resultados esperados para análise.

<img src="https://store.fiaformulae.com/on/demandware.static/-/Sites-navigation-catalog-FE-S9/default/dw8427c471/LogosTeams/LogoMahindra2.png" alt="Logo Mahindra" width="300"/><img src="https://avatars.githubusercontent.com/u/79948663?s=200&v=4" alt="Logo FIAP" width="200"/>





