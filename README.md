README: Organizador de Dados de Bairros (Python/OpenPyxl)
Este script Python foi desenvolvido para automatizar a separação de dados de uma planilha base (Excel) em múltiplas abas, organizando as informações por critério de Bairro.

🚀 Funcionalidade Principal
O script lê uma planilha Excel que contém uma lista de dados (como cadastros, alunos, clientes, etc.) e distribui cada linha para uma aba específica do arquivo, baseando-se no valor presente na coluna designada como "Bairro".

⚙️ Como Funciona o Código
Carregamento: O script carrega o arquivo Bairros.xlsx e acessa a aba principal, denominada "Base_Dados".

Iteração: Percorre todas as linhas da "Base_Dados", começando após o cabeçalho.

Identificação do Bairro: Para cada linha, extrai o nome do bairro na coluna 3 (C).

Criação de Abas:

Verifica se uma aba com o nome do bairro já existe no arquivo.

Se não existir, cria uma nova aba com o nome do bairro.

Adiciona um cabeçalho fixo (Data de Nascimento, Nome, Bairro) na primeira linha (A1, B1, C1) da nova aba.

Transferência de Dados: Copia os valores das colunas 1, 2 e 3 da linha atual da "Base_Dados" e anexa-os na próxima linha vazia da aba correspondente ao bairro.

Salvamento: Ao final do processo, o script salva as alterações em um novo arquivo chamado Bairros_Separados.xlsx, mantendo o arquivo original intacto.

🧩 Estrutura do Código
Função / Bloco	Descrição
criar_aba(bairro, arquivo_bairros)	Responsável por verificar a existência da aba e criar uma nova (com cabeçalho) se necessário.
transferir_informacoes_aba(...)	Responsável por copiar os dados da linha da Base_Dados para a próxima linha disponível da aba de destino (do bairro).
Bloco Principal	Contém o for loop que itera sobre as linhas da base, extrai o bairro, chama as funções de criação/transferência e, por fim, salva o arquivo.

Exportar para Sheets

🛠️ Requisitos
Python 3.x

Biblioteca openpyxl: Utilizada para ler e escrever em arquivos Excel (.xlsx).

Instalação: pip install openpyxl

📝 Configuração do Excel
Para que o script funcione corretamente, a planilha Bairros.xlsx deve:

Conter uma aba chamada Base_Dados.

Ter a informação do Bairro na Coluna C (3).

A Linha 1 da Base_Dados é tratada como cabeçalho e não é processada.

🔑 Uso (Exemplo de Execução)
O script deve ser executado no mesmo diretório onde o arquivo Bairros.xlsx está localizado:

Bash

# Executa o script Python (assumindo que o nome do arquivo é 'desafio.py')
py desafio.py 
Saída Esperada no Terminal:

Total de linhas a percorrer na Base de Dados: 11
