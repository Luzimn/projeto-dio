# projeto-dio
# Projeto DIO – Simulação de Ataques Brute Force com Kali Linux e Medusa

## 📚 Descrição do Projeto

Este projeto foi desenvolvido como parte do desafio da DIO com o objetivo de estudar técnicas de auditoria de segurança em ambientes controlados utilizando Kali Linux, Medusa e máquinas vulneráveis.

O laboratório foi criado utilizando máquinas virtuais no VirtualBox para simular cenários reais de autenticação insegura e ataques de força bruta.

⚠️ Todos os testes realizados foram executados exclusivamente em ambiente de laboratório e para fins educacionais.

---

# 🎯 Objetivos

* Compreender ataques de força bruta;
* Utilizar o Kali Linux para auditoria de segurança;
* Praticar enumeração de serviços;
* Simular ataques em FTP, SMB e aplicações web;
* Documentar processos técnicos;
* Criar um portfólio técnico no GitHub.

---

# 🖥️ Ambiente Utilizado

## Máquina Atacante

* Sistema: Kali Linux
* Ferramentas:

  * Medusa
  * Nmap
  * Hydra
  * SMBClient

## Máquina Alvo

* Sistema: Metasploitable 2
* Aplicações vulneráveis:

  * FTP
  * SMB
  * DVWA

## Virtualização

* VirtualBox
* Rede Host-Only

---

# 🌐 Configuração da Rede

As máquinas foram configuradas utilizando rede interna Host-Only para permitir comunicação entre os ambientes sem exposição externa.

## Exemplo de IPs

| Máquina          | IP            |
| ---------------- | ------------- |
| Kali Linux       | 192.168.56.10 |
| Metasploitable 2 | 192.168.56.20 |

---

# 🔍 Enumeração Inicial

Antes dos testes foi realizado reconhecimento utilizando Nmap.

## Comando utilizado

```bash
nmap -sV 192.168.56.20
```

## Objetivo

* Identificar portas abertas;
* Detectar serviços ativos;
* Descobrir possíveis vetores de ataque.

---

# 🔐 Ataque de Força Bruta em FTP

## Objetivo

Realizar testes de autenticação no serviço FTP da máquina vulnerável.

## Wordlist Utilizada

```txt
admin
user
msfadmin
root
```

## Comando Medusa

```bash
medusa -h 192.168.56.20 -u msfadmin -P senhas.txt -M ftp
```

## Resultado

O Medusa conseguiu validar credenciais fracas utilizadas no ambiente vulnerável.

---

# 🌍 Teste em Aplicação Web – DVWA

## Objetivo

Simular tentativas automatizadas de login na aplicação DVWA.

## Cenário

* DVWA configurado em nível de segurança baixo;
* Testes realizados apenas em ambiente local.

## Exemplo de Credenciais Testadas

```txt
admin:password
admin:123456
```

## Observações

Foram observadas falhas relacionadas à ausência de limitação de tentativas e senhas fracas.

---

# 🖧 Password Spraying em SMB

## Objetivo

Testar autenticação SMB utilizando uma senha comum para múltiplos usuários.

## Enumeração de Usuários

```bash
enum4linux 192.168.56.20
```

## Exemplo de Teste

```bash
medusa -h 192.168.56.20 -U usuarios.txt -p password -M smbnt
```

## Resultado

Foi possível identificar contas utilizando senhas simples.

---

# 🛡️ Medidas de Mitigação

Durante os testes foram identificadas práticas inseguras que poderiam ser mitigadas com:

* Utilização de senhas fortes;
* Política de bloqueio por tentativas;
* MFA (autenticação multifator);
* Atualização de serviços vulneráveis;
* Restrição de acesso SMB;
* Monitoramento de logs;
* Desativação de serviços desnecessários.

# 📖 Aprendizados

Durante o desenvolvimento deste laboratório foi possível compreender:

* Como ataques de força bruta funcionam;
* A importância de senhas fortes;
* Riscos de serviços mal configurados;
* Técnicas básicas de enumeração;
* Funcionamento do Medusa;
* Importância da segmentação de rede.

---

# ⚠️ Considerações Éticas

Todos os testes apresentados neste projeto foram realizados em ambiente controlado e destinado exclusivamente para fins educacionais.

Ataques em sistemas sem autorização são ilegais.

---

# 🚀 Conclusão

O projeto permitiu explorar conceitos fundamentais de segurança ofensiva e auditoria em ambientes Linux.

Além da prática técnica, o desafio reforçou a importância da documentação, organização e análise de vulnerabilidades em ambientes controlados.

---

# 👨‍💻 Autor

Projeto desenvolvido para o desafio da DIO.
