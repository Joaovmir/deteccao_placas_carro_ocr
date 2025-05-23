# Detecção e OCR de Placas de Carro 🚗🔍

[![Python](https://img.shields.io/badge/python-3.8%2B-blue.svg)](https://www.python.org/)

Este repositório apresenta um pipeline completo para **detecção de placas de carro em imagens** e extração automática do texto via **OCR (Reconhecimento Óptico de Caracteres)**, usando Python e bibliotecas modernas de visão computacional.

---

## 🌟 Motivação

Reconhecer automaticamente placas de veículos tem aplicações importantes em segurança, controle de acesso, monitoramento de frotas e automação de processos. Este projeto demonstra uma abordagem prática e replicável para detecção e leitura de placas usando imagens reais, podendo ser expandido para vídeos ou integrado a sistemas maiores.

---

## 🎯 Objetivos do Projeto

- Detectar regiões de placas de carro em imagens utilizando técnicas de visão computacional.
- Aplicar OCR para extrair automaticamente o texto das placas.
- Avaliar a precisão do reconhecimento e os desafios em imagens reais.
- Disponibilizar um **notebook interativo** para facilitar testes e adaptações.

---

## 🗂️ Etapas do Projeto

1. **Carregamento das imagens de placas e outros exemplos** (pasta `imagens/`)
2. **Pré-processamento das imagens** (filtros, binarização, remoção de ruído)
3. **Detecção de regiões candidatas a placas** (métodos clássicos: segmentação, contornos, morfologia, etc.)
4. **Aplicação de OCR** com Tesseract ou similar para leitura do texto
5. **Exibição e avaliação dos resultados**: texto extraído e bounding boxes
6. **Testes em imagens com e sem placas, para avaliar falsos positivos**

---

## 📚 Tecnologias Utilizadas

- [Python 3.8+](https://www.python.org/)
- [OpenCV](https://opencv.org/) — Processamento de imagens
- [Pytesseract](https://pypi.org/project/pytesseract/) — Wrapper Python para Tesseract OCR
- [Matplotlib](https://matplotlib.org/) — Visualização
- (Adicione outras bibliotecas se utilizadas no notebook)

---

## ⚡ Como Rodar o Projeto

### 1. Clone o repositório

```bash
git clone https://github.com/Joaovmir/deteccao_placas_carro_ocr.git
cd deteccao_placas_carro_ocr
```

### 2. Instale as dependências

```bash
pip install opencv-python pytesseract matplotlib
```

> **Obs:** Para usar o Tesseract, é necessário instalar o executável no seu sistema.
>
> * [Guia de instalação Tesseract](https://github.com/tesseract-ocr/tesseract)

No Windows, adicione o caminho do executável (`tesseract.exe`) ao PATH ou configure manualmente no notebook.

### 3. Estrutura das Imagens

A pasta `imagens/` deve conter:

* `placa_carro1.png`
* `placa_carro2.jpg`
* `placa_carro3.jpg`
* `trecho_livro.png`

### 4. Execute o notebook

Abra e execute o arquivo `deteccao_placas_carro_ocr.ipynb` em seu ambiente Jupyter, VS Code ou Colab.

---

## 💡 Exemplos de Análises e Resultados

### Carregamento de Imagem

```python
import cv2
import matplotlib.pyplot as plt

img = cv2.imread('imagens/placa_carro1.png')
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
plt.imshow(img_rgb)
plt.axis('off')
plt.show()
```

### Detecção da Placa

```python
# Pré-processamento e detecção usando OpenCV
# (Trechos exatos de código variam conforme o notebook)

# Exemplo: Encontrar contornos e filtrar possíveis placas
```

### Extração do Texto

```python
import pytesseract

placa = pytesseract.image_to_string(img_placa, config='--psm 8')
print("Texto reconhecido:", placa)
```

### Resultado Esperado

* Exibição da imagem original, região da placa detectada e texto extraído.
* Avaliação dos resultados em diferentes imagens (com e sem placa).

---

## 📁 Estrutura do Projeto

```
deteccao_placas_carro_ocr/
├── deteccao_placas_carro_ocr.ipynb
├── imagens/
│   ├── placa_carro1.png
│   ├── placa_carro2.jpg
│   ├── placa_carro3.jpg
│   └── trecho_livro.png
├── README.md
```

---

## 🔎 Limitações e Possíveis Expansões

* Sensibilidade a iluminação, ângulos e qualidade das imagens.
* Possibilidade de aprimorar com modelos de deep learning para detecção.
* Adaptação para processar vídeos em tempo real.
* Testar diferentes configurações do Tesseract e augmentação dos dados.

```

Se quiser adicionar prints dos resultados, detalhar as técnicas de pré-processamento ou exemplos de resultados do OCR, só pedir!
```

