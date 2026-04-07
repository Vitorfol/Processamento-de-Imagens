# Cronograma: PI (Atividade 1 + Revisão)

## Visão Geral (4 Dias + 1 Backup)

| Dia | Foco Teórico | Questões da Prática |
| :--- | :--- | :--- |
| **01** | Intensidade e Brilho | Q2 (Gama) e Q4abc (Negativo/Intervalo) |
| **02** | Geometria e Bits | Q4def (Espelhamentos), Q5 (Mosaico) e Q6 (Quantização) |
| **03** | Filtros e Ruído | Q1 (Esboço) e Q3 (Combinação de Imagens) |
| **04** | Documentação | Relatório Final (PDF), Insights e Gráficos |

---

## Detalhamento por Bloco

### Dia 01: O Pixel como Escalar
* **Teoria Requisito:** Representação Digital (Aulas 1, 2) e Transformações de Intensidade (Aulas 7, 8).
* **Justificativa:** Você precisa dominar a manipulação de valores individuais antes de mexer na estrutura da imagem.
* **Ação (Q2):** Converter para float $[0, 1]$, aplicar $B = A^{(1/\gamma)}$ e voltar para $[0, 255]$. 
* **Ação (Q4abc):** Implementar o negativo ($255 - p$) e o mapeamento para o intervalo $[100, 200]$. 

### Dia 02: O Pixel como Coordenada (Matrizes)
* **Teoria Requisito:** Relacionamentos entre Elementos (Aula 4) e Prática de Manipulação (Aula 6).
* **Justificativa:** Como você é de CS, esse bloco é focado em lógica de índices e fatiamento de arrays (Slicing).
* **Ação (Q4def)** 
* **Ação (Q5):** Criar o mosaico $4 \times 4$ movendo blocos da imagem original para as novas posições da grade. 
* **Ação (Q6):** Reduzir a profundidade de bits (Quantização) para ver o efeito de falsos contornos.

### Dia 03: Vizinhança e Convolução
* **Teoria Requisito:** Ruído (Aula 3) e Filtragem Espacial (Aulas 12, 13).
* **Justificativa:** Implementar filtros manualmente exige entender como o pixel central interage com os vizinhos.
* **Ação (Q1):** Criar o efeito de esboço. Passo crítico: dividir a imagem original pela versão com Blur Gaussiano ($21 \times 21$). 
* **Ação (Q3):** Média ponderada entre Imagem A e B (Ex: $0.5 \cdot A + 0.5 \cdot B$). 

---

## Guia de Conteúdo para o Relatório (Insights)

1.  **Na Quantização (Q6):** "Ao reduzir para 2 níveis (1 bit), a imagem perde toda a informação de textura, mantendo apenas a silhueta (binarização)." 
2.  **Na Correção Gama (Q2):** "Valores de $\gamma > 1$ expandem as baixas intensidades, tornando a imagem mais clara e revelando detalhes em áreas de sombra." 
3.  **No Esboço (Q1):** "A divisão pela imagem borrada atua como um filtro de realce de bordas, pois elimina as frequências baixas (áreas lisas) e mantém as altas frequências (contornos)." 

---

## Lembretes de Ouro (Regras da Atividade)
* **Proibido:** Usar funções prontas do OpenCV para as transformações (ex: `cv2.threshold`, `cv2.flip` ou `cv2.GaussianBlur` para o resultado final). 
* **Obrigatório:** Usar imagens do seu **tema de trabalho final**. Não use as imagens de exemplo do PDF! 
* **Formato:** O código pode ser Script ou Notebook, mas a entrega é um **PDF organizado** no Classroom. 