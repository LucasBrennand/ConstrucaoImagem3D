# Reconstrução 3D com COLMAP

Este projeto tem como objetivo realizar a reconstrução 3D de um ambiente ou objeto a partir de múltiplas imagens, utilizando a ferramenta COLMAP.

Demonstrar o uso de técnicas de Structure-from-Motion (SfM) para gerar modelos 3D a partir de fotos comuns, com aplicação em áreas como:

- Engenharia
- Patrimônio histórico
- Realidade aumentada
- Games e VFX

##  Ferramentas Utilizadas

- [COLMAP](https://github.com/colmap/colmap/releases) — Software de reconstrução 3D
- Git + GitHub — Controle de versão e backup do projeto

## 📁 Estrutura do Projeto
ConstrucaoImagem3D-main/ ..
├── imagens/ ..
├── sparse/0/ ..
├── README.md ..
├── .gitignore ..


## Para a visualização do modelo do repositorio 

1. **Instale o COLMAP**<br>
    Extraia os arquivos para o seu computador (Baixe a versão CUDA somente se tiver uma GPU da NVIDIA)

2. **Baixe o ZIP do repositorio e extraia para a mesma pasta onde está salvo seu COLMAP**<br>
    Exemplo de estrutura:<br>
    COLMAP/<br>
    ├── bin/<br>
    ├── ConstrucaoImagem3D-main/<br>
    ├── plugins/<br>


3. **Abra o VSCODE e navegue até a pasta "bin" pelo terminal (CMD)**<br>
    ```bash
    cd c:\COLMAP\bin

4. **Execute o seguinte comando no terminal(CMD)**<br>
    ```bash
    colmap gui

5. **Se aparecer o erro "Could not find the Qt platform plugin "windows" ", execute esse comando antes do passo 4**<br>
    ```bash
    set QT_QPA_PLATFORM_PLUGIN_PATH=C:\COLMAP\plugins\platforms
    colmap.exe

    
## Para a reprodução do modelo
1. **Instale o COLMAP**<br>
    Extraia os arquivos para o seu computador (Baixe a versão CUDA somente se tiver uma GPU da NVIDIA)

2. **Crie uma pasta onde estiver salvo sua pasta COLMAP**<br>
 Exemplo de estrutura:<br>
    COLMAP/<br>
    ├── bin/<br>
    ├── ConstrucaoImagem3D-main/<br>
    ├── plugins/<br>


3. **Crie uma pasta chamada "imagens" dentro da pasta que foi criada**<br>
 Exemplo de estrutura:<br>
    ConstrucaoImagem3D-main/<br>
    ├── imagens/<br>


4. **Baixe um database de imagens relevantes ao projeto e coloque elas dentro da pasta "imagens"**<br>
Esse repositorio utilizou o database [THU-MVS](https://www.aoki.ecei.tohoku.ac.jp/mvs/)

5. **Abra a pasta do COLMAP no VSCODE e execute no terminal (CMD) os próximos passos**

6. **Extração de características**
   ```bash
   colmap feature_extractor --database_path construcao3d/database.db --image_path construcao3d/imagens

7. **Matching de Imagens**
    ```bash
    colmap exhaustive_matcher --database_path construcao3d/database.db

8. **Reconstrução esparsa (SfM)**
    ```bash
    colmap mapper --database_path construcao3d/database.db --image_path construcao3d/imagens --output_path construcao3d/sparse

9. **Visualização do modelo**
    ```bash
    colmap gui

10. **Se aparecer o erro "Could not find the Qt platform plugin "windows" ", execute esse comando antes do passo 9**
    ```bash
    set QT_QPA_PLATFORM_PLUGIN_PATH=C:\COLMAP\plugins\platforms
    colmap.exe

11. **Clique em importar modelo e abre a pasta de sparse/0**

**⚠️ Observações**
O arquivo database.db não está incluído neste repositório por ser muito grande. Você deve gerá-lo localmente.
A pasta dense/ também não está incluída devido ao seu tamanho.



