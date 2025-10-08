# Desafios-Do-Tryhackme
Lugar dos meus CTFs completos ou em desenvolvimento.

## 04/10/25

CTF/Teoria: "DNS in Detail"

Relato: Comecei a fazer este CTF para melhorar a minha base de DNS.
Agora que tenho um pouco mais de noção sobre DNS, acho que já posso ir para o meu 1° CTF mais realista ("Dig Dug") que é focado em DNS também.
No começo eu estava meui confuso em como começar a participar de CTFs, ams quando vi que era simples (base teórica + prática) eu perdi esse receio.
No "DNS in Detail", eu aprendi muitom sobre como um DNS funciona(server autoritativos, intermediários TLD...) que são a base de tudo no DNS.

Recomendação: Eu recomendo o "DNS in detail" pra quem está começando a se interessar sobre DNS ( o CTF é simples, direto e muito explciativo) 10/10!


## 05/10/25

CTF: "Dig Dug"
Site alvo: "givemetheflag.com"

Objetivo: Encontrar uma FLAG no meio dos servidores DNS autoritativos(os chefes).

Descrição: "Oooh, turns out, this MACHINE_IP machine is also a DNS server! If we could dig into it, I am sure we could find some interesting records! But... it seems weird, this only responds to a special type of request for a givemetheflag.com domain?".
Ferramenta: dig(Domain Information Groper).

Relato: A 1° coisa que eu fiz ao iniciar a máquina do tryhackme(Hack-the-box) foi usar o comando "whoami" que mostra qual é o meu usuário no pc.

2- Reler a descrição do desafio(muito importânte, o objetivo fica claro quando se entende o que deve fazer).

3- Abrir o terminal e executar um comando padrão do dig (dig givemetheflag.com). Esse comando pede ao DNS qual é o ip público de um domínio(site).

4-Após ver os resultados da query(pergunta) resolvi pedir o ip público para o DNS autoritativo (10.201.100.243)

5- apos usar o comando "dig @10.201.100.243 givemetheflag.com", o resultado aparece mais rápido do que o esperado ( em menos de 5 minutos kk)

6- A Flag estava numa query TXT (onde os ADMs do DNS fazem comentários em texto puro entre si)
Flag: "flag{0767ccd06e79853318f25aeb08ff83e2}".

Aprendizado: sempre estude a base antes de focar em algo mais técnico (CTFs). Eu fiz isso e o resulto ficou claro: Um CTF que no passado eu nem conseguia resolver, terminado em menos de 5 minutos e com somente 2 linhas de comandos.

Recomendação: Recomendo para quem está se aventurando no mundo do DNS(simples se souber a base, e divertido quando se completa).

## 07/10/25
 Estudo: "DIG" e "WHOIS"
 
 Objetivo: Apreder recon passivo(sem contato direto com o alvo, só informações públicas).

 Relato: Usei o whois paara ver informações do site do Tryhackme.com. 
 no começo, eu tive muita dificuldade por conta das perguntas estarem em inglês(a tradução automática não é muito boa), mas mesmo assim, eu consegui       aprender um pouco sobre o que usar da saída do "whois" (criação, servidor NS, registro/compradores do domínio etc).
 
 Recon Passivo: A ordem que eu vou usar daqui pra frente nesses recons de domínios e DNS é essa:
 
 1°- "WHOIS" para ver os registros do domínio(criador, registro/comprador,expiração,NS...)
 
 2°- "DIG" para o recon de DNS (A,AAAA,MX,NS,SOA,TXT, AXFR...)
 
 Aprendizado: Como foi meu 1° contato com o "whois", ainda tem muita coisa para apreder, mas nada que muita prática e teoría não resolva.

## 08/10/25

 CFT/teoría: "Passive Reconnaissance"

 Estudos: Reconhecimento passivo(sem contato direto com o alvo).

 Objetivo: Entender como funciona o recon passivo e quais ferramentas usar.

 ferramentas: "DIG", "WHOIS", "Shodan.io", "DNSDumpster"

 1- Foi a parte da introdução ( o CTF explicando o que iriamos usar e fazer).
 2- Explicando a diferença de recon passivo e ativo.

   Passive Recon: Consiste em buscar infomações públicas do alvo (sites, subdomínios telefones, emails)
   Ex: "Um atacante analizando a base inimiga de longe" (sem contato direto, ou seja, passive recon)
   
   Ferramentas: 
   
   1- "WHOIS": Ferramenta de consluta de domínio (não é de DNS). pega infos públicas de um site, por exemplo: NS, datas de criaão e expiração do site,              registros de quem comprou/ dono do site e quem é dono do endereço dele (URL).

   2- "DNSDumpster" : Ferramenta de descoberta de subdomínios(infos públicas, porem escondidas) ex: admim.site.com, help.site.com (tudo antes do                "site.com" é um subdomínio).

   3- "Shodan.io": Ferramnta de consulta de dispositivos na rede. ele tenta se conectar em um site e tenta pegar todas suas infos públicas.
       Com isso ele descobre:
       
   .Endereço IP
   .empresa de hospedagem
   .localização geográfica
   .tipo de servidor e versão

   Active Recon: Consiste em buscar informações privadas de um alvo.
   EX: "O atacante checando a fechadura da base inimiga. Se ela estiver fraca, pode ser uma possível falha ou vulnerabilidade"
   
   Ferramentas:
   
   1- "Nmap": chegando minusiosamente a fechadura, se diver algo aberto...

   2- "Hydra": Essa fechadura está meio fraca... vou ver se consigo quebrar ela na força bruta.

   Apredizado: Aprendi um pouco sobre o "WHOIS", "Shodan.io" E DNSDmpster, asm acho que desses 3 aí, eu só vou usar o "WHOIS" e talvéz o "DNSDumpster"      (ainda não vejo muita funcionalidade pra eles no momento).

   Relato: Eu demorei 2 dias pra fazer este CTF teórico (não pela dificuldade,mas por falta de tempo).
   


