# Enunciado · DR2-TP3

## Introdução

Este Teste de Performance avalia sua capacidade de gerenciar aplicativos, pacotes, containers e sistemas de inicialização no Linux utilizando exclusivamente a linha de comando, relacionando conceitos fundamentais de sistemas operacionais com práticas profissionais reais em ambientes Linux.

Siga cuidadosamente as instruções de cada exercício e capture screenshots após a execução de cada tarefa, pois eles servirão como evidência objetiva do seu trabalho.

Além dos screenshots, ao final deste Teste de Performance, você deverá gravar um vídeo com duração entre 4 e 6 minutos, no qual deverá:

- Explicar, com suas próprias palavras, o que foi realizado em cada conjunto de exercícios
- Demonstrar no terminal os principais comandos utilizados
- Comentar brevemente a finalidade de cada comando no contexto do gerenciamento de serviços, pacotes e containers em sistemas Linux

## Exercício 1 · Programas, comandos e executáveis no Linux

**Contexto.** Em sistemas Linux, aplicações podem se manifestar como comandos internos do shell, scripts interpretados ou binários compilados. Diferenciar esses elementos é essencial para compreender como o sistema operacional localiza, carrega e executa programas, impactando diretamente tarefas de automação, depuração, empacotamento e segurança.

1. Selecione três comandos disponíveis no sistema
2. Utilize which para localizar o caminho associado a cada comando
3. Utilize type para identificar se cada comando é interno do shell, alias ou binário externo
4. Utilize file sobre o executável identificado
5. Registre comandos executados e conclusões técnicas em um arquivo de texto

## Exercício 2 · Estado global do sistema após a inicialização

**Contexto.** Após o boot, o Linux mantém informações detalhadas sobre o estado global do sistema e dos serviços ativos. A inspeção desse estado é prática comum em diagnóstico e validação de ambientes produtivos.

1. Execute systemctl status
2. Identifique serviços ativos e serviços inativos
3. Registre evidências relevantes observadas na saída do comando

## Exercício 3 · Análise cronológica do processo de boot

**Contexto.** Os logs do boot descrevem, em ordem temporal, como o sistema operacional foi inicializado e quais serviços foram acionados. Essa análise permite compreender dependências e identificar possíveis falhas de inicialização.

1. Utilize journalctl -b para acessar os logs do boot atual
2. Filtre mensagens relacionadas ao systemd ou a serviços essenciais
3. Registre os trechos relevantes e os comandos utilizados

## Exercício 4 · Inspeção do boot loader

**Contexto.** Em sistemas baseados em UEFI, o boot loader faz parte da cadeia crítica de inicialização. Sua inspeção permite compreender como o kernel foi carregado e quais configurações estão ativas.

1. Execute bootctl status
2. Identifique informações sobre o loader e o kernel utilizado
3. Registre as principais evidências observadas

## Exercício 5 · Inspeção detalhada de serviços com systemd

**Contexto.** O systemd fornece um modelo unificado para gerenciamento de serviços. A inspeção detalhada de serviços é essencial para administração e diagnóstico de sistemas Linux.

1. Escolha um serviço disponível no sistema
2. Utilize systemctl status <serviço>
3. Identifique PID, estado atual e logs recentes
4. Registre as informações obtidas

## Exercício 6 · Controle do ciclo de vida de serviços

**Contexto.** Além da inspeção, o administrador precisa controlar o ciclo de vida de serviços, iniciando, interrompendo ou reiniciando processos conforme alterações de configuração ou manutenção.

1. Escolha um serviço não crítico
2. Utilize systemctl start e systemctl stop
3. Utilize systemctl restart
4. Registre os efeitos observados em cada etapa

## Exercício 7 · Configuração de inicialização automática de serviços

**Contexto.** Definir quais serviços iniciam automaticamente durante o boot impacta diretamente a disponibilidade, o desempenho e a segurança do sistema.

1. Escolha um serviço gerenciado pelo systemd
2. Utilize systemctl enable ou systemctl disable
3. Execute systemctl daemon-reload, se aplicável
4. Documente o estado final do serviço

## Exercício 8 · Gestão de pacotes e cadeia de suprimentos de software

**Contexto.** Os gerenciadores de pacotes integram a cadeia de suprimentos de software no Linux, controlando origem, dependências e versões das aplicações instaladas.

1. Utilize apt search ou yum search para localizar um pacote
2. Instale o pacote utilizando o gerenciador apropriado
3. Utilize apt show ou yum info para inspecionar metadados
4. Registre as informações obtidas

## Exercício 9 · Introdução prática a containers via namespaces

**Contexto.** Containers são construídos a partir de mecanismos do kernel, como namespaces. Compreender esses conceitos no sistema base é fundamental para o uso correto de tecnologias de containerização.

1. Execute lsns para visualizar namespaces ativos
2. Relacione namespaces a processos em execução
3. Registre observações técnicas

## Exercício 10 · Uso de cgroups e controle de recursos

**Contexto.** O controle de recursos é base conceitual do isolamento promovido por containers. O systemd expõe essas informações por meio de ferramentas específicas.

1. Execute systemd-cgtop
2. Observe o uso de CPU e memória por grupos de controle
3. Registre evidências relevantes

## Exercício 11 · Manipulação avançada de arquivos com o editor vi

**Contexto.** Em ambientes profissionais Linux, especialmente servidores e sistemas sem interface gráfica, o editor vi/vim é utilizado para edição rápida e precisa de arquivos de configuração, scripts e definições de serviços. O uso eficiente do vi depende do domínio de seus modos de operação, atalhos padrão e comandos de automação, permitindo modificações seguras mesmo em arquivos extensos. Este exercício avalia o uso consciente do vi como ferramenta profissional, indo além da simples inserção de texto.

1. Crie um arquivo chamado config_vi.txt utilizando exclusivamente o editor vi ou vim
2. No modo normal, navegue pelo arquivo e insira pelo menos 5 linhas de texto estruturado, simulando um arquivo de configuração
3. Utilize atalhos padrão do vi para executar obrigatoriamente as seguintes ações:
   a) Inserir texto em pelo menos dois pontos distintos do arquivo utilizando comandos diferentes (i, a, o ou O)
   b) Copiar (yank) uma linha completa e colá-la em outra posição do arquivo
   c) Apagar uma linha inteira utilizando comando de modo normal
   d) Desfazer e refazer uma alteração (undo e redo)
4. Utilize um comando de busca (/) para localizar um termo no arquivo
5. Utilize um comando de substituição para alterar todas as ocorrências de um termo específico no arquivo
6. Salve o arquivo e saia do editor utilizando comandos explícitos do vi
7. Documente, em um arquivo chamado vi_operacoes.txt:
   - Os comandos e atalhos do vi utilizados
   - A finalidade de cada operação realizada

**Evidência em vídeo.** No vídeo de entrega do TP, apresente a execução deste exercício, mostrando a abertura do arquivo no vi ou vim; a execução dos principais comandos solicitados (inserção, cópia, remoção, busca e substituição); e o salvamento e fechamento correto do arquivo. O vídeo deve evidenciar o uso efetivo dos atalhos e comandos do vi, funcionando como comprovação prática do domínio da ferramenta.

## Exercício 12 · Construção e execução de um container Docker

**Contexto.** Containers permitem empacotar aplicações e suas dependências de forma reproduzível, sendo amplamente utilizados em pipelines modernos de desenvolvimento e deploy.

1. Crie um Dockerfile simples para uma aplicação mínima
2. Utilize docker build para gerar uma imagem
3. Execute a imagem com docker run
4. Utilize docker ps e docker images para inspecionar o ambiente
5. Registre todo o processo de forma organizada

## Entrega

1. Reúna todos os screenshots e os arquivos de evidência produzidos em um único arquivo PDF
2. Grave um vídeo entre 4 e 6 minutos, explicando e demonstrando no terminal as atividades realizadas
   - Armazene o vídeo no seu Google Drive institucional
   - Inclua o link do vídeo ao final do PDF
3. Nomeie o arquivo conforme o padrão: nome_sobrenome_DR2_TP3.PDF
4. Poste o PDF e o vídeo como resposta a este Teste de Performance no ambiente da disciplina

Os screenshots devem evidenciar claramente os comandos executados e suas respectivas saídas. O vídeo deve complementar o material escrito, funcionando como uma exposição técnica do conteúdo, demonstrando sua capacidade de gerenciar serviços, pacotes e containers em sistemas Linux.

## Orientações para defesa do trabalho em vídeo

1. Utilize uma ferramenta adequada: é preciso que apareça a tela com seu trabalho e a imagem da sua webcam (sugestões: Loom ou OBS).
2. Escolha um local adequado: ambiente calmo, sem ruídos ou distrações.
3. Webcam ligada, com boa iluminação e enquadramento centralizado.
4. Revise o vídeo: verifique se o vídeo e o áudio estão bons.
5. Salve o vídeo no Google Drive de aluno Infnet.
6. Altere as permissões de acesso para "qualquer pessoa com o link" e envie o link conforme as instruções da atividade.
