# Base de Conhecimento - Suporte Técnico e Help Desk

Esta central de conhecimento reúne procedimentos operacionais padrão (POPs) e guias de resolução de problemas (troubleshooting) para analistas de suporte de Nível 1 e Nível 2. O objetivo é padronizar atendimentos e agilizar o tempo de resposta (SLA).

---

## 1. Diagnóstico de Rede Local e Conectividade

Quando o usuário relatar que está "sem internet" ou sem acesso aos sistemas internos, siga o roteiro de comandos abaixo no Prompt de Comando (CMD):

1. **Verificar as configurações de IP da máquina:**
```cmd
ipconfig /all

```

*O que analisar:* Verifique se o adaptador de rede recebeu um IP válido da rede local ou se está com o IP padrão de falha (169.254.x.x).

2. **Testar a comunicação com o roteador (Gateway Padrão):**

```cmd
ping [endereco_do_gateway]

```

*O que analisar:* Se houver perda de pacotes, o problema está no cabo, switch ou conexão física do usuário.

3. **Testar a resolução de nomes (DNS):**

```cmd
nslookup google.com

```

*O que analisar:* Se o comando falhar, a máquina não está conseguindo traduzir os endereços web. Execute a limpeza de cache.

---

## 2. Procedimento para Liberação de Espaço em Disco (Windows)

Procedimento seguro para estações de trabalho que apresentam lentidão ou travamentos devido ao esgotamento do armazenamento principal (Disco C:):

1. Feche todos os navegadores e sistemas abertos pelo usuário.
2. Pressione as teclas `Windows + R`, digite `cleanmgr` e pressione Enter.
3. Selecione a unidade `C:` e clique em **Limpar arquivos do sistema**.
4. Marque as opções: *Arquivos de Log*, *Arquivos Temporários de Internet*, *Instalações anteriores do Windows* (se houver) e *Miniaturas*.
5. Clique em OK e confirme a exclusão.

---

## 3. Guia de Troubleshooting: VPN Corporativa

Se o usuário relatar falha ao conectar na rede corporativa em Home Office:

1. **Confirmação de Conectividade:** Certifique-se de que a internet residencial do usuário está funcionando normalmente acessando qualquer site de testes.
2. **Reinicialização do Serviço:** Abra o menu de Serviços do Windows (`services.msc`) e verifique se o serviço relacionado ao cliente VPN (ex: FortiClient, Cisco AnyConnect) está em execução. Se necessário, clique com o botão direito e selecione "Reiniciar".
3. **Verificação de Credenciais:** Confirme se a conta do usuário não foi bloqueada no Active Directory (AD) devido a excesso de tentativas incorretas.
