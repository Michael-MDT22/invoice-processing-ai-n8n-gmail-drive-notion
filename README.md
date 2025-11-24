Processamento Automático de Faturas com IA + n8n + Gmail + Google Drive + Notion

Automação inteligente que recebe faturas enviadas por e-mail, identifica automaticamente se o documento é uma fatura, extrai informações importantes usando IA e organiza tudo no Notion e no Google Drive — sem intervenção humana.

Este projeto demonstra como integrar IA + automação + APIs + ferramentas de produtividade para criar um fluxo empresarial completo.

🔍 Visão Geral

Este sistema:

✔ Monitora sua caixa do Gmail
✔ Baixa anexos PDF automaticamente
✔ Envia os arquivos para uma pasta do Google Drive
✔ Extrai o texto da fatura usando o n8n
✔ Usa IA para confirmar se o documento é uma fatura
✔ Se for fatura, extrai automaticamente:

Nome da fatura

Nome da empresa

Valor total

Lista de itens detalhados
✔ Salva tudo no Notion em duas bases:

📌 Faturas (dados principais)

📌 Itens da fatura (linha por linha)
✔ Se NÃO for uma fatura → o arquivo é excluído do Drive
✔ 100% automatizado end-to-end

🧠 Arquitetura do Sistema

Fluxo completo:

[Gmail Trigger]
⬇ recebe e-mails com PDFs
[n8n]
⬇ baixa anexos
[Google Drive]
⬇ salva arquivo
[n8n]
⬇ extrai texto do PDF
[IA Verifica]
⬇ “é fatura?” (sim/não)
✔ Se SIM:
 ⬇ IA extrai JSON com todos os dados
 ⬇ salva no Notion
 ⬇ salva os itens individualmente
❌ Se NÃO:
 ⬇ arquivo é excluído

🔧 Tecnologias Utilizadas
Tecnologia	Função
n8n	Automação do fluxo inteiro
Gmail API	Monitoramento e download de anexos
Google Drive	Armazenamento de PDFs
Notion API	Registro e organização dos dados
OpenAI	Classificação + Extração estruturada via IA
Extract PDF	Extração de texto
JavaScript Nodes	Organização e separação de dados
📂 Funcionalidades do Projeto
✔ 1. Detecção Automática de Faturas

IA verifica se o PDF é realmente uma fatura
(“sim” / “não”, sem alucinação)

✔ 2. Extração Estruturada com IA

A IA extrai JSON contendo:

invoice_name

company_name

total_invoice_amount

line_items[] (descrição + valor)

✔ 3. Armazenamento Automático

Os dados vão diretamente para:

📌 Notion – Banco de Dados Principal
📌 Notion – Banco de Dados dos Itens
📌 Google Drive – Arquivos organizados

✔ 4. Limpeza Automática

Se o documento não for fatura, ele é excluído da pasta.

📝 Fluxo no n8n (Explicação Simples)

O workflow contém:

Gmail Trigger – monitora a caixa de entrada

Split/Loop – percorre anexos

Upload para Drive

Download para análise

Extract from File – extrai texto

Classificação via IA

IF – separa fatura / não fatura

Se SIM:

Extrair JSON via IA

Salvar no Notion (dados principais)

Salvar cada item no Notion (linha por linha)

Se NÃO:

Deletar arquivo no Drive

🧪 Demonstração Real (Vídeo)

🎥 Veja o fluxo funcionando na prática:
➡ https://www.linkedin.com/feed/update/urn:li:activity:7383664079158255616/

📁 Estrutura Recomendada do Repositório
📦 invoice-processing-ai-n8n-gmail-drive-notion
│
├── README.md
├── workflow.json             ← fluxo real exportado do n8n
│
├── /docs
│     ├── print.png           ← imagem do workflow (screenshot)
│     └── documentos-exemplo.pdf (opcional)
│
└── /scripts
      └── (caso use algum JS custom)


📌 Você pode colocar o print do seu fluxograma dentro da pasta /docs.

🔑 Variáveis de Ambiente Necessárias

O fluxo utiliza credenciais configuradas no n8n, como:

GMAIL_OAUTH2
GOOGLE_DRIVE_OAUTH2
NOTION_API_KEY
OPENAI_API_KEY


Se quiser criar um arquivo .env.example, use:

OPENAI_API_KEY=xxxxx
NOTION_API_KEY=xxxxx

▶️ Como Executar o Projeto
1. Importe o workflow

n8n → Settings → Workflows → Import

2. Configure suas credenciais

Gmail OAuth

Google Drive OAuth

Notion

OpenAI

3. Ajuste os IDs das tabelas do Notion

Eles estão dentro do workflow nos nós correspondentes.

4. Execute

A automação roda 100% sozinha.

🚀 Resultados e Impacto

✔ Recebimento automático de faturas
✔ Classificação inteligente
✔ Extração precisa
✔ Organização automática
✔ Zero intervenção humana
✔ Redução de erros
✔ Economia de tempo empresarial real

👨‍💻 Autor

MICHAEL DOUGLAS TEOFILO
Especialista em Automação com IA e n8n

🔗 LinkedIn: https://www.linkedin.com/in/michael-douglas-automacao-ia/

🎥 Vídeo: https://www.linkedin.com/feed/update/urn:li:activity:7383664079158255616/
