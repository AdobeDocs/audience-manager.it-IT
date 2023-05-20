---
description: La vostra azienda potrebbe voler offuscare l’indirizzo IP in molti paesi a causa delle normative globali sulla privacy. Audience Manager consente di offuscare gli indirizzi IP dei visitatori su base globale o paese per paese.
seo-description: Your company may desire to obfuscate IP address in many countries due to global privacy regulations. Audience Manager allows you to obfuscate visitor IP addresses on a global or country-by-country basis.
solution: Audience Manager
title: Offuscamento dell’indirizzo IP
feature: Data Governance & Privacy
exl-id: 8c976d1e-f4ba-4892-bd68-d4e74bdb4d9b
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 16%

---

# Offuscamento dell’indirizzo IP {#ip-obfuscation}

Utilizza questa funzione per offuscare gli indirizzi IP raccolti in Audience Manager.

## Panoramica e metodologia {#overview-and-methodology}

La vostra azienda potrebbe voler offuscare l’indirizzo IP in molti paesi a causa delle normative globali sulla privacy. Audience Manager consente di offuscare gli indirizzi IP dei visitatori su base globale o paese per paese.

### Metodologia di offuscamento dell’IP

Seguendo i principi di &quot;Privacy By Design&quot;, Adobe Audience Manager consente ai clienti di abilitare l’offuscamento dell’IP dall’interfaccia utente, sia a livello globale in tutte le aree geografiche che per specifici paesi. Quando abiliti questa impostazione, l’ultimo ottetto (l’ultima parte) dell’indirizzo IP viene eliminato immediatamente quando l’indirizzo IP viene acquisito in Audience Manager. Audience Manager elimina questa parte dell’indirizzo IP prima dell’elaborazione (incluso prima di qualsiasi ricerca geografica facoltativa o registrazione dell’indirizzo IP). Ad esempio:

* Prima dell’offuscamento: `255.255.255.255`
* Dopo offuscamento: `255.255.255.0`

Vedi anche Raccolta di indirizzi IP e offuscamento degli indirizzi IP nel nostro [Sezione Privacy dei dati](/help/using/overview/data-security-and-privacy/data-privacy.md).

## Requisiti di offuscamento degli indirizzi IP {#ip-obfuscation-requirements}

L’offuscamento dell’indirizzo IP è disponibile solo per gli account amministratore Audience Manager. Consulta [Crea utenti](/help/using/features/administration/administration-overview.md#create-users) per informazioni su come assegnare i privilegi di amministratore a un utente.

>[!NOTE]
>
> A causa dell’elevato volume di dati elaborati da Audience Manager, l’entrata in vigore delle modifiche di offuscamento dell’IP può richiedere fino a 4 ore, dal momento in cui vengono aggiornate le impostazioni.

## Configurare l’offuscamento dell’indirizzo IP {#configure-ip-obfuscation}

Per configurare l’offuscamento dell’indirizzo IP, segui la procedura riportata di seguito.

1. Accedi a Audience Manager con un account amministratore e vai a **Amministrazione > Privacy**.
2. Scegli il tipo di offuscamento dell’IP che desideri utilizzare.
   1. **Offusca tutti gli indirizzi IP:** seleziona questa opzione affinché Audience Manager offuschi l’ultimo ottetto di tutti gli indirizzi IP dei visitatori, indipendentemente dalla regione di origine.
   2. **Offusca gli indirizzi IP per specifici paesi:** seleziona questa opzione affinché Audience Manager offuschi l’ultimo ottetto degli indirizzi IP dei visitatori per paesi specifici. Utilizza il **Elenco dei paesi** o il corrispondente **Ricerca** per trovare i paesi per i quali abilitare l’offuscamento dell’IP, quindi fai clic sull’icona + per aggiungerli al **Selezionato per offuscamento** elenco. Dopo aver aggiunto tutti i paesi richiesti alla **Selezionato per offuscamento** , fare clic su **Salva**.

![](assets/ip-obfuscation.png)

## Disabilita offuscamento indirizzo IP {#disable-ip-obfuscation}

Per disabilitare l’offuscamento dell’indirizzo IP a livello globale, vai a **Amministrazione > Privacy**, seleziona **Non offuscare gli indirizzi IP** e fai clic su **Salva**.

Per disabilitare l’offuscamento degli indirizzi IP per paesi specifici, individua i paesi in **Selezionato per offuscamento** , quindi fare clic sul pulsante corrispondente **X** icona. Clic **Salva** quando hai finito.

## Concetti correlati {#related-concepts}

* [Privacy dei dati](/help/using/overview/data-security-and-privacy/data-privacy.md)
* Dimostrazione video offuscamento indirizzo IP
>[!VIDEO](https://video.tv.adobe.com/v/27218/)
