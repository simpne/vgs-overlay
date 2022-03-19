# Preliminary Guide

Software necessario:
* Windows 10+
* [Node](https://nodejs.org/dist/v17.7.2/node-v17.7.2-x64.msi "Node.js")
* [Python3](https://www.python.org/downloads/release/python-3103/ "Python 3")
* [Visual Studio](https://visualstudio.microsoft.com/it/ "Visual Studio Community")

***N.B. (basta la versione community e includere il necessario per build di applicazioni C++ Desktop per Windows).***

## Guida per installazione ambiente di sviluppo

*Eseguire tutte le istruzioni da qui in avanti dal terminale di Visual Studio.*

1. Installare Visual Studio (Includere il carico di lavoro "Sviluppo desktop con C++").
2. Installare Python3
3. Assicurarsi che npm e python siano raggiungibili da cmd o Powershell (nel caso riavviare).
4. Eseguire le seguenti istruzioni:
    1. `npm config set msvs_version 2022`.
    2. `cd client`.
    3. `npm link ../electron-overlay`, nel caso di errore -> `npm update --force`.
    5. `npm link ../node-ovhook`.
    6. `npm i`.
    7. `npm run compile:electron`.
    8. `npm run build`.
    9. `npm run start`.

## Struttura del progetto

### client

questa cartella contiene l`applicazione Electron, il fulcro della nostra applicazione. In particolare la sotto-cartella dist contiene (e dovrà contenere) i file HTML necessari per far funzionare la nostra applicazione.

### electron-overlay e node-ovhook

sono moduli .dll necessari per la creazione di un nuovo componente Node.js in Windows, sono fondamentali per il funzionamento dell`applicazione (teoricamente non vanno toccati una volta buildati, ma sarà da controllare).

### game-overlay

è il modulo di node.js vero e proprio, che permette di disegnare l'overlay. 

