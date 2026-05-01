# 📖 Hyperion Tweaks - Wiki Oficial

Bem-vindo à documentação técnica do **Hyperion Tweaks**. Este guia explica o funcionamento interno da ferramenta, as categorias de modificação e as melhores práticas de uso.

---

## 📑 Sumário
1. [Introdução](#introdução)
2. [Arquitetura de Modificação](#arquitetura-de-modificação)
3. [Categorias de Tweaks](#categorias-de-tweaks)
4. [Guia de Uso (Passo a Passo)](#guia-de-uso)
5. [Segurança e Pontos de Restauração](#segurança)

---

## 1. Introdução <a name="introdução"></a>
O Hyperion Tweaks não é apenas um "limpador" de arquivos. É uma ferramenta de **ajuste fino de kernel e registros**, projetada para alinhar o comportamento do Windows com as necessidades de aplicações de tempo real (Jogos Competitivos).

---

## 2. Arquitetura de Modificação <a name="arquitetura-de-modificação"></a>
A ferramenta opera em três níveis principais:

*   **Registry Level (Regedit):** Modifica chaves de configuração que o Windows não expõe na interface comum (GUI).
*   **Service Management:** Desativa o agendamento de tarefas e serviços que geram picos de uso de CPU (*spikes*).
*   **Command Line Execution:** Utiliza comandos via `PowerShell` e `CMD` para reconfigurar subsistemas como a rede e o gerenciamento de energia.

---

## 3. Categorias de Tweaks <a name="categorias-de-tweaks"></a>

### ⚡ Performance de Processamento (CPU)
*   **Core Unparking:** O Windows costuma "adormecer" núcleos da CPU para economizar energia. Nós forçamos o estado ativo para eliminar a latência de ativação do núcleo.
*   **Win32PrioritySeparation:** Ajustamos o *quantum* (tempo de atenção) da CPU para dar prioridade máxima a aplicações em primeiro plano (o seu jogo).

### 🖱️ Redução de Latência (Input Lag)
*   **Disable Pointer Precision:** Remove a aceleração do mouse nativa do Windows no registro, garantindo precisão 1:1.
*   **Keyboard DataQueueSize:** Reduz o tamanho da fila de dados do teclado para que os comandos sejam processados mais rapidamente pelo processador.

### 🌐 Otimização de Rede
*   **TCP No Delay:** Desabilita o algoritmo de Nagle, enviando pacotes de rede imediatamente, reduzindo o jitter e estabilizando o ping.
*   **Network Throttling Index:** Remove o limite que o Windows impõe ao tráfego de rede quando o processador está sob carga pesada.

---

## 4. Guia de Uso <a name="guia-de-uso"></a>

### Passo 01: Preparação
Antes de qualquer alteração, feche todos os programas abertos e navegadores. O Hyperion precisa de acesso exclusivo a certas chaves de registro.

### Passo 02: Criação de Backup
1. Vá até a aba de **Segurança/Backup**.
2. Clique em **Criar Ponto de Restauração**.
3. Aguarde a confirmação do sistema.

### Passo 03: Aplicação dos Tweaks
Recomendamos aplicar as modificações por seções:
1. Aplique os tweaks de **Sistema**.
2. Reinicie o computador.
3. Aplique os tweaks de **Rede**.
4. Reinicie novamente.
> **Dica:** Aplicar tudo de uma vez dificulta a identificação de qual modificação trouxe o melhor benefício para o seu hardware específico.

---

## 5. Segurança <a name="segurança"></a>

### Como reverter uma modificação?
Se você sentir que o sistema ficou instável ou se algum software de trabalho (ex: Adobe Premiere, AutoCAD) parou de funcionar corretamente:
1. Abra o **Hyperion Tweaks**.
2. Vá em **Restauração**.
3. Selecione o ponto criado anteriormente e clique em **Restaurar**.

### Logs de Erro
A ferramenta gera logs em `%APPDATA%/HyperionTweaks/logs`. Caso encontre um erro ao aplicar um tweak, anexe esse arquivo ao abrir uma *Issue* no GitHub.

---

## 🛠️ Tecnologias Utilizadas
*   **Frontend:** React + Tailwind CSS
*   **Backend:** Rust (Tauri Framework)
*   **Ícones:** Lucide React
*   **Target:** Windows 10/11 (x64)

---
*Documentação atualizada em: Maio de 2026*
