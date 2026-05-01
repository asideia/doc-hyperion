# 📑 Perguntas Frequentes (FAQ) - Hyperion Tweaks

Bem-vindo à central de ajuda do **Hyperion Tweaks**. Este documento foi criado para explicar de forma detalhada como as ferramentas funcionam, os riscos envolvidos e como obter o máximo de performance do seu sistema.

---

## 🛠️ 1. Conceitos Gerais

### O que é o Hyperion Tweaks?
O Hyperion Tweaks é uma suite de ferramentas desenvolvida para reduzir a latência (input lag), estabilizar o frame time e remover processos desnecessários do Windows que consomem recursos de hardware (CPU/RAM). Ele atua diretamente em registros do sistema, serviços e planos de energia.

### O uso do app pode banir em jogos (Anti-Cheats)?
**Não.** O Hyperion Tweaks não realiza "code injection" em processos de jogos. Ele modifica as configurações do Windows e do hardware. Softwares de Anti-Cheat (como Vanguard, EAC ou BattlEye) monitoram a memória do jogo, enquanto o Hyperion atua na camada do sistema operacional.

---

## 🚀 2. Performance e Otimização

### Como a redução de processos ajuda nos FPS?
O Windows por padrão mantém centenas de serviços ativos (telemetria, buscas, mapas, impressoras). Cada serviço consome ciclos da CPU. Ao desativar o que é irrelevante para jogos, a CPU fica livre para processar os dados do motor gráfico do jogo com mais rapidez.

### O que é o "Input Lag" e como o app o reduz?
Input lag é o tempo entre você clicar no mouse e a ação aparecer na tela. O Hyperion reduz isso através de:
* **Interrupt Moderation:** Ajusta como a CPU lida com sinais de periféricos.
* **FSO (Fullscreen Optimizations):** Desativa camadas de interface do Windows que criam delay sobre o jogo.

### O app faz Overclock?
O Hyperion **não** altera frequências de clock ou voltagens. Ele realiza o que chamamos de "Software Optimization". Ele garante que o hardware que você já tem trabalhe da forma mais eficiente possível dentro das especificações de fábrica.

---

## 📋 3. Funcionalidades Específicas

### Planos de Energia Customizados
* **High Performance vs. Hyperion Power:** Enquanto o plano de alto desempenho do Windows é genérico, o nosso força os núcleos da CPU a permanecerem em "unparked state", evitando quedas bruscas de clock durante o gameplay.

### Limpeza de Temporários
* **Por que limpar?** Arquivos de cache e logs antigos podem causar lentidão na leitura de disco. O Hyperion limpa as pastas `%temp%`, `prefetch` e logs de erro automaticamente para manter o sistema "leve".

### Otimização de Rede
* **Nagle's Algorithm:** O Hyperion desativa esse algoritmo que agrupa pequenos pacotes de dados antes de enviar. Para navegação é bom, mas para jogos cria latência (ping alto). Desativá-lo faz com que cada comando seja enviado instantaneamente.

---

## ⚠️ 4. Segurança e Reversão

### O que devo fazer antes de aplicar um Tweak?
**Sempre crie um Ponto de Restauração do Sistema.** Embora o Hyperion seja seguro, cada configuração de hardware reage de uma forma. Ter um ponto de restauração garante que você possa voltar ao estado original em segundos.

### Posso reverter as alterações?
Sim. O Hyperion foi projetado para ser modular. Se você sentir que uma função específica (como desativar o Windows Defender) não é ideal para o seu uso diário, você pode reativá-la através da interface do app.

### O Windows Defender detectou o app como ameaça. E agora?
Isso é um **Falso Positivo**. Como o app altera chaves de registro (`Regedit`) e serviços do sistema para otimização, alguns antivírus interpretam essas ações como "suspeitas". Recomendamos adicionar a pasta do Hyperion às exclusões do seu antivírus.

---

## 🖥️ 5. Suporte Técnico

### Meu Windows parou de atualizar após o uso. Por quê?
Alguns perfis de otimização extrema desativam o **Windows Update** para evitar que o sistema instale drivers genéricos por cima dos seus drivers de performance. Se precisar atualizar, basta reativar o serviço no painel de serviços do Hyperion.

### O app não abre ou fecha sozinho.
Certifique-se de que:
1. Você está executando o app como **Administrador**.
2. O **WebView2 Runtime** está instalado (necessário para a interface Tauri).
3. Seu Windows é versão 10 ou 11 (64-bits).

---

## 🤝 Contribuição e Erros
Encontrou um erro ou tem uma sugestão de otimização?
* Abra uma **Issue** aqui no GitHub.
* Entre no nosso **Discord** para suporte em tempo real.

---
> **Aviso Legal:** O uso dessas ferramentas é de responsabilidade do usuário. Embora testadas, modificações no sistema operacional podem variar de desempenho dependendo da versão do hardware.
