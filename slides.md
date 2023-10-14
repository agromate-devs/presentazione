---
theme: seriph
background: https://source.unsplash.com/collection/94734566/1920x1080
class: text-center
highlighter: shiki
lineNumbers: false
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
drawings:
  persist: false
transition: slide-left
title: Welcome to Slidev
mdc: true
---

# Agromate

La serra diventa smart

---
transition: fade-out
---

# Cos'è Agromate?

Agromate è una serra smart controllabile da remoto. 

Agromate permette di controllare le piante comodamente dal telefono. 

Le piante vengono monitorate 24 ore su 24 e i dati sono disponibili sotto forma di grafico nell'applicazione Agromate

Possiamo selezione oltre 80 mila piante dal catagolo e piantarle comodamente nella nostra serra. La gestione di queste piante è totalmente automatizzata.

---
layout: default
---

# L'Agrosmart

L'Agrosmart è il cuore di Agromate, racchiude la pianta e la gestisce.

è formata da un'illuminazione realizzata attraverso striscia led RGB, un sensore di temperature e umidità DHT11, un umidificatore ad ultrasuoni, una pompa per l'acqua e una sonda per monitorare il terreno.

Tutto questo viene gestito con un ESP8266 programmato attraverso la ESP8266 FreeRTOS SDK.

---

# L'infrastruttura cloud di Agromate

L'infrastruttura cloud di Agromate è basata su AWS.

L'infrastruttura è altamente scalabile e flessibile. Utilizza database noSQL per gestire i dati(DynamoDB), broker MQTT altamente scalabile(IoT Core) e le API sono serverless ed altamente scalabili(Lambda + API Gateway).

L'autenticazione è gestita da Firebase, noi non possediamo alcun dato degli utenti.

Il broker MQTT permette di interfacciare le API con l'ESP8266 in modo che gli ultimi cambiamenti dell'utente siano sempre riportati sull'Agrosmart.

<center>
<img src="/images/aws_logo.png" width="350"/>
</center>
--- 

# L'app

L'app è scritta con Capacitor.JS e Framework7.

L'app è cross-platform e scritta con le tecnologie del web. Si integra alla perfezione con Firebase per l'autenticazione e le notifiche.

Dall'app possiamo sceglie oltre 80 mila piante, configurare i nostri Agrosmart ed infine monitorare i parametri della pianta.

<div class="grid grid-cols-5">
        <div>
          <img src="https://agromate-devs.github.io/sito-di-presentazione/dist/images/hello.png" width="120"/>
        </div>
        <div>
          <img src="https://agromate-devs.github.io/sito-di-presentazione/dist/images/esplora.png" width="120"/>
        </div>
        <div>
          <img src="https://agromate-devs.github.io/sito-di-presentazione/dist/images/marco.png" width="120"/>
        </div>
                <div>
          <img src="/images/piante.jpg" width="120"/>
        </div>
        <div>
          <img src="/images/grafici.jpg" width="120"/>
        </div>
    </div>

---
layout: two-cols
---

# L'ESP8266

L'esp8266 è il cuore dell'agrosmart.

è programmato con la ESP8266 RTOS SDK che ci permette di gestire varie operazioni contemporaneamente tra cui:

- Prendere i dati dai sensori
- Gestire la connessione al broker MQTT
- Regolare la pompa dell'acqua e l'umidificatore
- Gestire i led RGB per illuminare la serra

::right::

  <img src="https://agromate-devs.github.io/docs/assets/images/main_bb-050659258635517d45a9d39483f8f4a4.png" width="400"/>
<!-- <img src="" width="300"/> Schema dell'esp8266 -->