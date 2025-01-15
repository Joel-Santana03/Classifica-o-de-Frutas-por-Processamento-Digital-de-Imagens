# Classificação de Frutas por Processamento Digital de Imagens

## **Descrição**
Este projeto implementa um pipeline completo de processamento digital de imagens para classificação de frutas. Utilizando técnicas de pré-processamento, segmentação, extração de características e aprendizado de máquina, o objetivo é classificar imagens de frutas isoladas (como maçãs, bananas e laranjas) com precisão.
O projeto foi desenvolvido como parte do trabalho prático da disciplina **Processamento Digital de Imagens (TAD0018)** da **Universidade Federal do Rio Grande do Norte**.

---

## **Objetivo**
Consolidar os conceitos estudados na disciplina por meio do desenvolvimento de um sistema automatizado para classificação de objetos visuais, seguindo todas as etapas do pipeline de processamento de imagens, desde a aquisição até a classificação.

---

## **Arquitetura do Projeto**
O projeto está dividido nas seguintes etapas:

1. **Aquisição de Imagens**:
   - Protocolo definido para capturar imagens coloridas de frutas (uma por imagem) em fundo branco.
   - 10 imagens capturadas por classe (maçã, banana e laranja), totalizando 30 imagens iniciais.

2. **Pré-processamento**:
   - Conversão para escala de cinza.
   - Redução de ruído usando filtro Gaussiano.
   - Realce de contraste com CLAHE.
   - Geração de imagens aumentadas (data augmentation), multiplicando a base em 3 vezes.

3. **Segmentação e Representação**:
   - Segmentação baseada em limiarização (Otsu).
   - Geração de duas bases de dados:
     - **Base de Representação:** Contendo assinaturas de contorno normalizadas.
     - **Base de Descrição:** Incluindo descritores geométricos (área, perímetro, circularidade, etc.) e momentos de Hu.

4. **Classificação**:
   - Uso do modelo k-NN com 7 vizinhos para classificar as frutas em ambas as bases.
   - Avaliação por meio de matriz de confusão e relatório de classificação.

---

## **Resultados**
- **Base de Representação**:
  - Acurácia: **73%**.
  - Melhor desempenho para frutas com formas distintivas (`banana`).
- **Base de Descrição**:
  - Acurácia: **60%**.
  - Desempenho inferior, especialmente ao classificar `maçã` e `laranja`.

---

## **Como Executar o Projeto**

### **Pré-requisitos**
- Python 3.8 ou superior.
- Bibliotecas necessárias:
  - `numpy`
  - `opencv-python`
  - `matplotlib`
  - `pandas`
  - `scikit-learn`
  - `seaborn`

Instale as dependências com:
```bash
pip install -r requirements.txt
```

### **Passos para Execução**
1. Clone este repositório:
   ```bash
   git clone <url-do-repositorio>
   cd <nome-do-repositorio>
   ```

2. Certifique-se de que as imagens estejam organizadas no diretório apropriado:
   ```
   /processed_database
       /banana
       /laranja
       /maca
   ```

3. Execute o pipeline de classificação:
   ```bash
   python main.py
   ```

4. Os resultados das classificações estarão disponíveis no console e como matrizes de confusão plotadas graficamente.

---

## **Estrutura de Arquivos**
```plaintext
├── processed_database/         # Diretório com as imagens pré-processadas
├── representation_base.csv     # Base de dados de representação (assinaturas)
├── description_base.csv        # Base de dados de descrição (descritores geométricos)
├── main.py                     # Código principal do projeto
├── README.md                   # Este arquivo
└── requirements.txt            # Bibliotecas necessárias
```

---

## **Possíveis Melhorias**
1. Incluir descritores de textura (ex.: LBP ou Haralick) para enriquecer a base de descrição.
2. Usar algoritmos mais sofisticados, como SVM ou redes neurais, para melhorar a classificação.
3. Implementar a normalização de código de cadeia para garantir invariância à rotação.

---

## **Autores**
- Joel Santana
- Lucas Lopes

---

## **Licença**
Este projeto é parte de um trabalho acadêmico e está licenciado sob a [MIT License](LICENSE).

---

Se precisar de ajustes ou adicionar mais detalhes, como links ou exemplos de saída, posso ajudar!
