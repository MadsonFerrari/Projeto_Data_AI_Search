
# Madson Ferrari

Olá pessoal, eu sou Madson Ferrari, Engenheiro eletricista, pós graduado em Mecatrônica pela UFRJ e entusiasta pela área de informática, programação e Innovation

## Você pode me encontrar aqui:

[![Perfil DIO](https://img.shields.io/badge/-Meu%20Perfil%20na%20DIO-0077B5?style=for-the-badge&logo=gitbook&logoColor=white)](https://www.dio.me/users/madson_ferrari)

[![LinkedIn](https://img.shields.io/badge/-LinkedIn-000?style=for-the-badge&logo=linkedin&logoColor=30A3DC)](https://www.linkedin.com/in/MadsonFerrari/)

[![Youtube](https://img.shields.io/badge/YouTube-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://www.youtube.com/@MadsonFerrari)

# Explorando um índice no Azure Search Index (UI)


- A primeira etapa foi assitir ao módulo de Document Intelligence do curso da DIO dentro do bootcamp AI-900

## Neste passo-a-passo vou te mostrar como explorar um índice no Azure Search Index.

Este exemplo está no on leraning do Azure e você pode acessar a versão original [aqui](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/11-ai-search.html)

Vamos imaginar que você trabalha para a Fourth Coffee, uma rede nacional de cafés. Você foi solicitado a ajudar a criar uma solução de mineração de conhecimento que facilite a busca de insights sobre as experiências dos clientes. Você decide criar um índice do Azure AI Search usando dados extraídos de avaliações de clientes.

Neste laboratório você irá:

- Criar recursos do Azure
- Extrair dados de uma fonte de dados
- Enriqueça os dados com habilidades de IA
- Utilize o indexador do Azure no portal do Azure
- Consulte seu índice de pesquisa
- Revise os resultados salvos em uma Loja de conhecimento

## Recursos do Azure necessários

A solução que você criará para o Fourth Coffee requer os seguintes recursos na sua assinatura do Azure:

- Um recurso do Azure AI Search , que gerenciará a indexação e a consulta.
- Um recurso de serviços de IA do Azure , que fornece serviços de IA para habilidades que sua solução de pesquisa pode usar para enriquecer os dados na fonte de dados com insights gerados por IA.

Nota Os recursos do Azure AI Search e dos serviços Azure AI devem estar no mesmo local!

- Uma conta de armazenamento com contêineres de blobs, que armazenará documentos brutos e outras coleções de tabelas, objetos ou arquivos.

## Passo 1 - Criando um recurso no Azure AI Search

Entre no portal do [Azure](https://portal.azure.com/#home)

![Imagem0](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_0.PNG)

Clique no botão + Criar um recurso , pesquise Azure AI Search (ou clique em + para ver mais recursos) e crie um recurso Azure AI Search com as seguintes configurações:

![Imagem0_1](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_0_1.PNG)

Vai aparecer a tela de criação do recurso do AI Search.

![Imagem0_2](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_0_2.PNG)

- Assinatura : sua assinatura do Azure .
- Grupo de recursos : Selecione ou crie um grupo de recursos com um nome exclusivo .
- Nome do serviço : um nome exclusivo .
- Localização : Escolha EAST US2.
- Nível de preços : Escolha Basic

Selecione Review + create e depois de ver a resposta Validation Success , selecione Create .

![Imagem0_3](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_0_3.PNG)

Aqui você pode ver a tela depois do Deploy do recurso do AI Search

![Imagem0_4](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_0_4.PNG)

Após a conclusão da implantação, selecione Ir para o recurso . Na página de visão geral do Azure AI Search, você pode adicionar índices, importar dados e pesquisar índices criados.

## Passo 2 - Criar um recurso de serviços de IA do Azure

Você precisará provisionar um recurso de serviços de IA do Azure que esteja no mesmo local que seu recurso do Azure AI Search. Sua solução de pesquisa usará esse recurso para enriquecer os dados no armazenamento de dados com insights gerados por IA.

Retorne à página inicial do portal do Azure. Clique no botão ＋Criar um recurso e pesquise os serviços de IA do Azure. Selecione criar um plano de serviços de IA do Azure 

![Imagem1](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1.PNG)

Você será levado a uma página para criar um recurso de serviços de IA do Azure. Configure-o com as seguintes configurações:

- Assinatura : sua assinatura do Azure .
- Grupo de recursos : O mesmo grupo de recursos que seu recurso do Azure AI Search .
- Região : o mesmo local do recurso do Azure AI Search .
- Nome : Um nome exclusivo .
- Nível de preços : Padrão S0

- Ao marcar esta caixa, confirmo que li e compreendi todos os termos abaixo : Selecionado

Selecione Revisar + criar . 

![Imagem1](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_1.PNG)

Depois de ver a resposta Validation Passed , selecione Create .

Aguarde a conclusão da implantação e visualize os detalhes da implantação.

![Imagem1](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_2.PNG)

## Passo 3 - Criar a conta de armazenamento 

Click em Home e Retorne à página inicial do portal do Azure e selecione o botão + Criar um recurso .

Procure conta de armazenamento e crie um recurso de conta de armazenamento

![Imagem0](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_3.PNG)

![Imagem0](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_4.PNG)


Use as as seguintes configurações:

- Assinatura : sua assinatura do Azure .
- Grupo de recursos : O mesmo grupo de recursos que os recursos do Azure AI Search e dos serviços Azure AI .
- Nome da conta de armazenamento : um nome exclusivo .
- Localização : Escolha EAST US2 .
- Padrão de desempenho
- Redundância : armazenamento localmente redundante (LRS)

OBS: O nome da conta deve ser exclusivo, por tanto este que eu usei não estará disponível

![Imagem0](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_5.PNG)

![Imagem0](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_6.PNG)

Clique em Revisar e em Criar . Aguarde a conclusão da implantação e vá para o recurso implantado clicando em *Go to resource*.

![Imagem0](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_7.PNG)

Tela do recurso de Storage

![Imagem0](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_8.PNG)

Na conta de Armazenamento do Azure que você criou (tela acima), role no painel de menu esquerdo e selecione Configuração.

![Imagem0](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_9.png)

Altere a configuração de Permitir acesso anônimo de Blob para Habilitado e selecione Salvar .

![Imagem0](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_10.png)

## Passo 4 - Carregar documentos para o armazenamento do Azure

Vamos agora trazer arquivos para oos nossos Containers. Que são como Gavetas num armário

- Secione no lasto esquerdo ***Containers***

![Imagem0](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_11.png)

- Vamos adicionar um container.

- Selecione + Contêiner . Um painel do seu lado direito é aberto.

Insira as seguintes configurações e clique em Criar :
Nome : coffeereviews
Nível de acesso público : Container (acesso de leitura anônimo para containers e blobs)
Avançado : sem alterações .

![Imagem12](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_12.png)

- E clique em CREATE para criar o container

![Image13](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_13.png)

Em uma nova guia do navegador, baixe as avaliações de café compactadas em https://aka.ms/mslearn-coffee-reviews e extraia os arquivos para a pasta de avaliações (reviews) no seu computador.

![Imagem14](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_14.png)

- Agora vamos carregar as avaliações para dentro do nosso container.
- No portal do Azure, selecione o contêiner do cofeereview que você acabou de criar.

![Imagem15](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_15.png)

- No contêiner, selecione Carregar (*Upload*).

![Imagem16](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_16.png)

- Clique na caixa de escolha de arquivos e selecione todos os arquivos de reviews salvos e clique em **carregar** (*Upload*)  

![Imagem17](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_17.png)

- Os arquivos irão aparecer no container

![Imagem18](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_18.png)

Agora já criamos todos os recursos e o container está com dados, vamos partir para a verificação destes reviews

- Clique na caixa superior e escolha o AI Search

![Imagem19](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_19.png)
 
- Clique no nosso recurso criado anteriormente no AI Search para abrir o mesmo.

![Imagem20](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_20.PNG)

- Agora clique em importar dados (*Import Data*), para importar o container criado

![Imagem21](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_21.PNG) 

- Na página Conectar-se aos seus dados , na lista Fonte de Dados , selecione Azure Blob Storage .

![Imagem21](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_22.PNG)

Vai abrir a tela de conexão de dados

![Imagem23](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_23.PNG)

Preencha os detalhes do armazenamento de dados com os seguintes valores:

- Data Source: Azure Blob Storage
- Data source name: coffee-customer-data
- Data to extract: Content and metadata
- Parsing mode: Default
- Connection string: *Selecione *Choose an existing connection*. Selecione a sua conta de storage, selecione o container *coffeereviews*, e então clique Select.

![Imagem24](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_24.PNG)

Continue preenchendo os dados restantes conforme abaixo:

- Managed identity authentication: None
- Container name: Esta escolha é colocada automaticamente após escolher a conexão.
- Blob folder: Deixe em branco.
- Description: Reviews for Fourth Coffee shops.

Sua tela deve ficar parecida com esta.

![Imagem25](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_25.PNG)

Selecione *Next: Add cognitive skills (Optional)* (Próximo: Adicionar habilidades cognitivas (opcional)) .

Na secção **Attach Cognitive Services** , selecione o seu recurso de serviços Azure AI.

![Imagem26](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_26.PNG)

Minmize a aba de **Attach Cognitive Services**

Na seção **Add enrichments** :
- Altere o **Skillset name** para **coffee-skillset** .
- Marque a caixa de seleção **Habilitar OCR e mesclar todo o texto no campo merged_content** 
- Certifique-se de que **Source data field** esteja configurado como **merged_content** .
- Altere o nível de granularidade de enriquecimento para Páginas (blocos de 5.000 caracteres) .
- Não selecione Habilitar enriquecimento incremental

E selecione os Enrichments conforme marcado na figura abaixo.

![Imagem27](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_27.PNG)

Abra a guia de **Save enrichments to a knowledge store** e escolha:

- Image projections
- Documents
- Pages
- Key phrases
- Entities
- Image details
- Image references

Nota: Se aparecer uma mensagem de **Connection Storage** quando você clicar em **Image Projections**, então escolha **Choose a existing Connection** e selecione a sua **storage account** e o **container** criados anteriormente e clique **Select**

Selecione Azure blob projections: **Document** 
A caixa do Container Name vai aparecer já escrita com o container. Não altere este nome.

![Imagem28](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_28.PNG)

Clique **Next: Customize target index**. Escolha o Index name para **coffee-index**.

Confirme que **Key** está com a opção **metadata_storage_path**. Deixe o **Suggester name** em branco e **Search mode** auto preenchido.

Reveja os ajustes padrões do campo de **index fields**. Selecione **filterable** para todos os campos que já estiverem marcados por padrão.

Veja a figura abaixo para conferir

![Imagem29](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_29.PNG)

Selecione **Next: Create an indexer**.

Troque o **Indexer name** para **coffee-indexer**.

Deixe o **Schedule** marcado como **Once**.

![Imagem30](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_30.PNG)

Expanda o **Advanced options**. Certifique que a opção **Base-64 Encode Keys** está selecionada, pois as chaves de codificação podem tornar o índice mais eficiente.

![Imagem31](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_31.PNG)

Selecione **Submit** para criar a fonte de dados, o conjunto de habilidades, o índice e o indexador. O indexador é executado automaticamente e executa o pipeline de indexação, que:
- Extrai os campos de metadados do documento e o conteúdo da fonte de dados.
- Executa o conjunto de habilidades cognitivas para gerar campos mais enriquecidos.
- Mapeia os campos extraídos para o índice.

Volte à página de recursos do Azure AI Search. No painel esquerdo, em **Search Management** , selecione **Indexers** 

![Imagem32](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_32.PNG)

Selecione o **coffee-indexer** recém-criado.

![Imagem33](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_33.PNG)

Espere um minuto e selecione ↻ Atualize até que o **Status** indique sucesso.

Vericando se a cadeia está ON

![Imagem34](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_34.PNG)

Aqui fazemos uma pesquisa por Chicago. Role a tela para ver o resultados

![Image35](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_35.PNG)

## Fazendo a pesquisa em JSON

- Clicando na opção de JSON, podemos usar o editor de Query com o seguinte código e ao clicar Search resulta em todos os documentos da base de dados

![Imagem36](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_36.PNG)

- Agora vamos filtrar por sentimento. No campo do editor de consultas JSON , copie e cole:
```
{
 "search": "sentiment:'negative'",
 "count": true
}
```
Podemos ver que resulta em duas avaliações negativas conforme a tela abaixo:

![Imagem37](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_37.PNG)

## Revise o armazenamento de conhecimento

Vamos ver o poder do armazenamento de conhecimento em ação. Ao executar o assistente Importar dados , você também criou um armazenamento de conhecimento. Dentro do armazenamento de conhecimento, você encontrará os dados enriquecidos extraídos pelas habilidades de IA que persistem na forma de projeções e tabelas.

- No portal do Azure, navegue de volta para a sua conta de armazenamento do Azure.

![Imagem38](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_38.PNG)

- No painel do menu esquerdo, selecione **Containers** . Selecione o contêiner de **knowledge-store** .

![Imagem39](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_39.PNG)

![Imagem40](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_40.PNG)

- Selecione qualquer um dos itens e clique no arquivo objectprojection.json .

![Imagem41](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_41.PNG)

- Selecione Editar para ver o JSON produzido para um dos documentos do seu armazenamento de dados do Azure.

![Imagem42](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_42.PNG)

- Selecione a localização atual do blob de armazenamento no canto superior esquerdo da tela para retornar à conta de armazenamento Containers .

- Em Containers , selecione o contêiner coffee-skillset-image-projection . Selecione qualquer um dos itens.

![Imagem43](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_43.PNG)

- Selecione qualquer um dos arquivos .jpg . Selecione Editar para ver a imagem armazenada no documento. Observe como todas as imagens dos documentos são armazenadas desta forma.

![Imagem42](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_44.PNG)

Selecione a localização atual do blob de armazenamento no canto superior esquerdo da tela para retornar à conta de armazenamento Containers .

Selecione **Storage Browser** no painel esquerdo e selecione Tabelas . Há uma tabela para cada entidade no índice. Selecione a tabela coffeeSkillsetKeyPhrases .

![Imagem45](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1_45.PNG)

Observe as frases-chave que o armazenamento de conhecimento conseguiu capturar do conteúdo das avaliações. Muitos dos campos são chaves, portanto você pode vincular as tabelas como um banco de dados relacional. O último campo mostra as frases-chave que foram extraídas pelo conjunto de habilidades.

# Limpeza do sistema.

Faça a limpeza e exclusão dos recursos criados para evitar cobranças

## Conclusão e Insights

As ferramentas de AI do Azure são muito funcionais e conseguem automatizar tarefas que seriam praticamente impossíveis de se fazer manualmente, pois demandariam muito tempo e teriam uma taxa de erro muito alta se executada manualmente.


