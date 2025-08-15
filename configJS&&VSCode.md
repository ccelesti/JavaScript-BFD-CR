# 📚 Configuração e Execução de JavaScript no VS Code  
**Data:** 13/08  
**Turma:** 33 PE - C1 Back-End JavaScript – Semana 2  

---

## 1️⃣ Instalar o Node.js  
1. Acesse: [download node.js](https://nodejs.org/en/download/current)  
2. Baixe a opção **Windows Installer (.msi)**.  
3. Siga o processo de instalação com as opções padrão.  
4. Após instalar, feche e abra novamente o **VS Code** ou outra IDE de sua preferência.

---

## 2️⃣ Criar e configurar seu primeiro projeto  
No **VS Code**:  
1. Abra a pasta onde deseja criar seu projeto (**File → Open Folder**).  
2. Abra o terminal interno (**Ctrl + Shift + `**).  
3. No terminal, execute:
   ```bash
   npm init -y             # cria o package.json
   npm install prompt-sync # instala a biblioteca para ler entrada do usuário no console de forma síncrona

---

## 3️⃣ Possível erro: “UnauthorizedAccess / execução de scripts desabilitada”

Mensagem de erro:

```O arquivo C:\Program Files\nodejs\npm.ps1 não pode ser carregado porque a execução de scripts foi desabilitada neste sistema.```

Causa: O PowerShell bloqueia a execução de scripts por padrão.

Solução temporária:
No terminal do VS Code, execute:

`Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass`


Depois, repita:

`npm install prompt-sync`

💡 Essa alteração vale apenas enquanto o terminal estiver aberto. Ao fechar o VS Code, a configuração volta ao normal.

---

## 4️⃣ Criando seu código JavaScript

Crie um arquivo com extensão .js (ex.: app.js).

Na primeira linha do arquivo, adicione:

```js const prompt = require('prompt-sync')();```

Escreva o restante do seu código normalmente.

---

## 5️⃣ Executando o código

Para rodar o programa, use no terminal:

`node .` 📌 Não esqueça de colocar o ponto (.)

⚠️ Para evitar erros de execução em um código recentemente alterado, ative o salvamento automático no VS Code: 
`Arquivo → Salvamento Automático`

---

## 6️⃣ Erros comuns e soluções

| Erro                                         | Causa                                                                        | Como resolver                                                                                       |
| -------------------------------------------- | ---------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| **UnauthorizedAccess / PSSecurityException** | PowerShell bloqueia scripts (`npm.ps1`).                                     | Rodar `Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass`.                                 |
| **Executar no painel errado**                | Tentou rodar o comando no **Painel de Saída** ao invés do **Terminal**.      | Abrir o **Terminal** (Ctrl+Shift+\`).                                                               |
| **MODULE\_NOT\_FOUND**                       | Esqueceu de instalar ou importar um módulo.                                  | Verificar se rodou `npm install nome-do-modulo` e se incluiu `require('nome-do-modulo')` no código. |
| **Erro ao rodar `node .`**                   | O arquivo principal não é `index.js` ou não está definido no `package.json`. | Rodar `node nomeDoArquivo.js` diretamente.                                                          |

---

