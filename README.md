# Reconstrução 3D com COLMAP

Este projeto tem como objetivo realizar a reconstrução 3D de um ambiente ou objeto a partir de múltiplas imagens, utilizando a ferramenta COLMAP.

Demonstrar o uso de técnicas de Structure-from-Motion (SfM) para gerar modelos 3D a partir de fotos comuns, com aplicação em áreas como:

- Engenharia
- Patrimônio histórico
- Realidade aumentada
- Games e VFX

##  Ferramentas Utilizadas

- [COLMAP](https://colmap.github.io/) — Software de reconstrução 3D
- Git + GitHub — Controle de versão e backup do projeto
- Git LFS (opcional) — Para lidar com arquivos grandes

## 📁 Estrutura do Projeto
construcao3d/
├── imagens/
├── sparse/0/
├── README.md
├── .gitignore


## 🧪 Etapas do Processo

1. **Extração de características**
   ```bash
   colmap feature_extractor --database_path construcao3d/database.db --image_path construcao3d/imagens

2. **Matching de Imagens**
    ```bash
    colmap exhaustive_matcher --database_path construcao3d/database.db

3. **Reconstrução esparsa (SfM)**
    ```bash
    colmap mapper --database_path construcao3d/database.db --image_path construcao3d/imagens --output_path construcao3d/sparse

4. **Visualização do modelo**
    ```bash
    colmap model_viewer --path construcao3d/sparse/0

**⚠️ Observações**
O arquivo database.db não está incluído neste repositório por ser muito grande. Você deve gerá-lo localmente.
A pasta dense/ também não está incluída devido ao seu tamanho.



