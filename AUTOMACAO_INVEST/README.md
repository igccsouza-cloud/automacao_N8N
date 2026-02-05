# 🤖 Sistema de Atendimento Inteligente - Hashtag Capital

Este repositório contém um fluxo automatizado desenvolvido no **n8n** utilizando agentes de IA (Google Gemini) para gestão de assessoria de investimentos.

## 🏢 Estrutura da Equipe de IA

O sistema utiliza uma arquitetura de **Agente Orquestrador** com sub-agentes especialistas:

1.  **Sofia (Gerente de Atendimento):** O cérebro do fluxo. Ela identifica a intenção do cliente e roteia para o especialista correto.
2.  **Arthur (Customer Success):** Focado em triagem de perfil (Proteção vs. Rentabilidade) e agendamento de reuniões.
3.  **Bia (Analista Financeira):** Responsável por consultas de boletos, status de pagamentos e segunda via.
4.  **Leo (Analista Técnico):** O braço educacional, tirando dúvidas sobre conceitos de mercado (SELIC, CDB, FIIs, etc.).

## 🛠️ Tecnologias Utilizadas

* **n8n:** Orquestração de workflow low-code.
* **Google Gemini (1.5 Flash):** Modelos de linguagem para processamento natural.
* **Telegram API:** Interface de comunicação com o usuário final.
* **PostgreSQL/Supabase (Opcional):** Para memória e histórico de chat.

## 🚀 Como Importar

1.  Faça o download do arquivo `workflow.json` deste repositório.
2.  No seu n8n, clique em **Workflows > Import from File**.
3.  Configure as suas credenciais para:
    * Telegram Bot API
    * Google Gemini API
4.  Certifique-se de que os nós de ferramentas (Tools) estão conectados aos sub-agentes correspondentes.

## ⚠️ Notas de Configuração

* **Modo de Texto:** O sistema está configurado para responder apenas em texto simples (sem Markdown), garantindo compatibilidade total com o bot do Telegram sem erros de formatação.
* **Resets:** Implementamos uma lógica de `##RESET##` para que os agentes devolvam a bola para a Sofia caso recebam um assunto fora de sua especialidade.