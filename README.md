# Base de Conhecimento - Suporte Tecnico e Help Desk

Esta central de conhecimento reune procedimentos operacionais padrao (POPs) e guias de resolucao de problemas (troubleshooting) para analistas de suporte de Nivel 1 e Nivel 2. O objetivo e padronizar atendimentos e agilizar o tempo de resposta (SLA).

---

## 1. Diagnostico de Rede Local e Conectividade

Quando o usuario relatar que esta "sem internet" ou sem acesso aos sistemas internos, siga o roteiro de comandos abaixo no Prompt de Comando (CMD):

1. **Verificar as configuracoes de IP da maquina:**
   ```cmd
   ipconfig /all

```

*O que analisar:* Verifique se o adaptador de rede recebeu um IP valido da rede local ou se esta com o IP padrao de falha (169.254.x.x).

2. **Testar a comunicacao com o roteador (Gateway Padrao):**
```cmd
ping [endereco_do_gateway]

```


*O que analisar:* Se houver perda de pacotes, o problema esta no cabo, switch ou conexao fisica do usuario.
3. **Testar a resolucao de nomes (DNS):**
```cmd
nslookup google.com

```


*O que analisar:* Se o comando falhar, a maquina nao esta conseguindo traduzir os enderecos web. Execute a limpeza de cache.

---

## 2. Procedimento para Liberacao de Espaco em Disco (Windows)

Procedimento seguro para estacoes de trabalho que apresentam lentidao ou travamentos devido ao esgotamento do armazenamento principal (Disco C:):

1. Feche todos os navegadores e sistemas abertos pelo usuario.
2. Pressione as teclas `Windows + R`, digite `cleanmgr` e pressione Enter.
3. Selecione a unidade `C:` e clique em **Limpar arquivos do sistema**.
4. Marque as opcoes: *Arquivos de Log*, *Arquivos Temporarios de Internet*, *Instalacoes anteriores do Windows* (se houver) e *Miniaturas*.
5. Clique em OK e confirme a exclusao.

---

## 3. Guia de Troubleshooting: VPN Corporativa

Se o usuario relatar falha ao conectar na rede corporativa em Home Office:

1. **Confirmacao de Conectividade:** Certifique-se de que a internet residencial do usuario esta funcionando normalmente acessando qualquer site de testes.
2. **Reinicializacao do Servico:** Abra o menu de Servicos do Windows (`services.msc`) e verifique se o servico relacionado ao cliente VPN (ex: FortiClient, Cisco AnyConnect) esta em execucao. Se necessario, clique com o botao direito e selecione "Reiniciar".
3. **Verificacao de Credenciais:** Confirme se a conta do usuario nao foi bloqueada no Active Directory (AD) devido a excesso de tentativas incorretas.
