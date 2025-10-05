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

4-Após ver os resultados da query(pergunta) resolvi pedir o ip público, só que apara o DNS autoritativo (10.201.100.243)

5- apos usar o comando "dig @10.201.100.243 givemetheflag.com", o resultado aparece mais rápido do que o esperado ( em menos de 5 minutos kk)

6- A Flag estava numa query TXT (onde os ADMs do DNS fazem comentários em texto puro entre si)
Flag: "flag{0767ccd06e79853318f25aeb08ff83e2}".

Aprendizado: sempre estude a base antes de focar em algo mais técnico (CTFs). Eu fiz isso e o resulto ficopu claro, um CTF que no passado eu nem consegui fazer terminado em menos de 5 minutos e com somente 2 linhas de comandos.

Recomendação: Recomendo para quem está se aventurando no mundo do DNS(simples se souber a base, e divertido quando se completa).


