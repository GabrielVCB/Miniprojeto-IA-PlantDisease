# 🌿 Classificação de Doenças em Plantas com Deep Learning e XAI

![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)
![Keras](https://img.shields.io/badge/Keras-D00000?style=for-the-badge&logo=keras&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Google Colab](https://img.shields.io/badge/Google%20Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white)

Este repositório contém o **Miniprojeto Acadêmico** desenvolvido para a disciplina de **Inteligência Artificial (2026.1)** na UNICAP. O objetivo é a classificação automatizada de doenças em folhas de plantas utilizando Redes Neurais Convolucionais (CNN) e técnicas de IA Explicável (XAI).

---

## 👥 Equipe
*   Aléx Rhikelme
*   Gabriel Vera Cruz
*   Gustavo Igor
*   Igor Leal
*   Nathan Vinicius

---

## 📖 Artigo Base
O projeto fundamenta-se no seguinte artigo científico:
> **Título:** *Improving Plant Disease Classification With Deep-Learning-Based Prediction Model Using Explainable Artificial Intelligence*  
> **Autores:** Natasha Nigar, Hafiz Muhammad Faisal, Muhammad Umer, Olukayode Oki, Manappattukunnel Lukose Joseph  
> **Periódico:** IEEE Access (Volume 12, 2024)  
> **DOI:** [10.1109/ACCESS.2024.3428553](https://doi.org/10.1109/ACCESS.2024.3428553)

---

## 🚀 Contribuição Original (Diferencial Técnico)
Como requisito para a pontuação extra do miniprojeto, implementamos as seguintes melhorias em relação ao artigo original:
1.  **Inclusão do EfficientNetB4:** Adicionamos este modelo de última geração ao benchmark para comparar o equilíbrio entre precisão e custo computacional.
2.  **Implementação de Grad-CAM:** Substituímos/Comparamos o framework LIME pelo **Grad-CAM**, permitindo uma visualização determinística das regiões da folha que ativaram a decisão da rede neural.

---

## 📊 Dataset
Utilizamos o **New Plant Diseases Dataset**, disponível no Kaggle.
*   **Total de Imagens:** ~87.000
*   **Classes:** 38 categorias (doenças e folhas saudáveis).
*   **Espécies:** 14 tipos de plantas (ex: Tomate, Batata, Maçã, Milho).
*   **Split:** 80% para treinamento, 20% para validação.

---

## 🛠️ Tecnologias e Implementação
O projeto foi desenvolvido em **Python** utilizando **TensorFlow** e **Keras**.

### Principais Passos:
1.  **Pré-processamento:** Redimensionamento para 224x224 px e Normalização.
2.  **Data Augmentation:** Rotação (±40°), deslocamento horizontal/vertical (20%), shear (20%), zoom (20%) e espelhamento horizontal.
3.  **Transfer Learning em Duas Fases:**
    - **Fase 1 (Aquecimento):** 3 épocas com base_model congelada para estabilizar a última camada.
    - **Fase 2 (Fine-tuning):** 5 épocas com base_model destravada, usando taxa de aprendizado reduzida (1e-4).
4.  **Treinamento:** Otimizador Adam, Loss Categorical Crossentropy e Regularização com Dropout (0.5).
5.  **Explicabilidade (XAI):** Geração de mapas de calor Grad-CAM para validação visual das regiões de ativação da rede neural.

---

## 📈 Resultados e XAI
A imagem abaixo demonstra o sucesso da nossa contribuição original, onde o **Grad-CAM** identifica com precisão as manchas de doenças na folha:

![Resultado Final XAI - Grad-CAM](PlantaDoente.jpeg)

---

## ⚙️ Como Executar
1. Faça o download do arquivo `MiniProjetoipynb.ipynb`[cite: 3].
2. Abra-o no **Google Colab**.
3. Ative a **GPU T4** (Ambiente de Execução > Alterar tipo de ambiente de execução).
4. Insira seu token de API do Kaggle para o download automático da base de dados.
5. Execute as células sequencialmente.

---

## 🎓 Instituição
**Universidade Católica de Pernambuco (UNICAP)**  
**Disciplina:** Inteligência Artificial (2026.1)  
**Professor:** Francisco Madeiro