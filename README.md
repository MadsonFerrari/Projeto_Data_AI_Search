
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




