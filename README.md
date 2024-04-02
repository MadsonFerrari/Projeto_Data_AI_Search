
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


Clique no botão + Criar um recurso , pesquise Azure AI Search e crie um recurso Azure AI Search com as seguintes configurações:

![Imagem1](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_1.PNG)

- Assinatura : sua assinatura do Azure .
- Grupo de recursos : Selecione ou crie um grupo de recursos com um nome exclusivo .
- Nome do serviço : um nome exclusivo .
- Localização : Escolha EASTUS.
- Nível de preços : Escolha Free se estiver disponível ou Standard S0

Selecione Review + create e depois de ver a resposta Validation Success , selecione Create .

![Imagem2](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_2.PNG)

Após a conclusão da implantação, selecione Ir para o recurso . Na página de visão geral do Azure AI Search, você pode adicionar índices, importar dados e pesquisar índices criados.

![Imagem3](https://github.com/MadsonFerrari/Projeto_Data_AI_Search/blob/main/Telas/Tela_3.PNG)

## Passo 2 - Criar a conta de armazenamento 

Retorne à página inicial do portal do Azure e selecione o botão + Criar um recurso .

Procure conta de armazenamento e crie um recurso de conta de armazenamento com as seguintes configurações:

- Assinatura : sua assinatura do Azure .
- Grupo de recursos : O mesmo grupo de recursos que os recursos do Azure AI Search e dos serviços Azure AI .
- Nome da conta de armazenamento : um nome exclusivo .
- Localização : Escolha EAST US .
- Padrão de desempenho
- Redundância : armazenamento localmente redundante (LRS)

Clique em Revisar e em Criar . Aguarde a conclusão da implantação e vá para o recurso implantado.

Na conta de Armazenamento do Azure que você criou, no painel de menu esquerdo, selecione Configuração (em Configurações ).
Altere a configuração de Permitir acesso anônimo de Blob para Habilitado e selecione Salvar .
