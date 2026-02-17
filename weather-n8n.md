# 🌦️ Telegram Weather Chatbot — n8n Workflow

![n8n](https://img.shields.io/badge/n8n-workflow-orange)
![Telegram](https://img.shields.io/badge/Telegram-Bot-blue)
![OpenWeather](https://img.shields.io/badge/OpenWeather-API-yellow)
![License](https://img.shields.io/badge/license-MIT-green)

Chatbot integrado ao **Telegram** que fornece informações climáticas em tempo real utilizando a **OpenWeather API**, orquestrado através de um workflow no **n8n** com suporte a IA para interpretação de mensagens.

---

# 📌 Visão Geral

O usuário envia uma mensagem para o bot no Telegram contendo o nome de uma cidade.

O workflow:

1. Recebe a mensagem
2. Usa IA para normalizar cidade / estado / país
3. Consulta a OpenWeather API
4. Gera resposta amigável com temperatura atual
5. Retorna ao usuário no Telegram

---

# 🧠 Componentes de IA

O workflow utiliza dois modelos de linguagem configurados:

* Google Gemini
* OpenAI (fallback)

Funções da IA:

✅ Normalizar entrada do usuário
✅ Extrair cidade corretamente
✅ Gerar resposta amigável

---

# 📦 Arquivo do Workflow

O workflow está disponível no repositório:

```
workflow-chatbot-telegram.json
```

---

# ⚙️ Pré-requisitos

* n8n instalado e funcional
* Acesso à internet
* Credenciais configuradas no n8n:

  * Telegram Bot
  * OpenWeather API
  * (Opcional) Credencial de IA

---

# 📥 Importando o Workflow no n8n

1. Acesse o n8n
2. Menu **Workflows**
3. Clique em **Import**
4. Selecione o arquivo:

```
workflow-chatbot-telegram.json
```
# 🔐 Configuração das Credenciais no n8n

## 🤖 Telegram Credential

Nome esperado da credencial:

```
TELEGRAM_TOKEN
```

Tipo:

```
Telegram API
```

Configurar:

* Bot Token

---

## 🌦️ OpenWeather Credential

Nome esperado:

```
OPENWEATHER_API_KEY
```

Tipo:

```
HTTP Query Auth
```

Configuração:

| Campo | Valor       |
| ----- | ----------- |
| Name  | appid       |
| Value | SUA_API_KEY |


---

## 🧠 Credenciais de IA (Opcional)

O workflow suporta:

* Google Gemini
* OpenAI

Caso não configure ambos, apenas um já funciona.

---

# ▶️ Executando o Chatbot

### 1️⃣ Ativar Workflow

Abrir workflow e clicar em:

```
Activate
```

---

### 2️⃣ Testar no Telegram

Enviar mensagem para o bot:

```
Porto Alegre, RS
```

ou

```
Clima São Paulo
```

---

# ✅ Resposta Esperada

Exemplo:

```
A temperatura atual em Porto Alegre é 28°C.
```

---

# ❌ Tratamento de Erros

Se a cidade não for encontrada:

```
Olá, cidade não encontrada!!
Informe uma cidade e estado válido!
EX: Porto Alegre, RS
```

---

# 👨‍💻 Autor

Marcos Barth.
