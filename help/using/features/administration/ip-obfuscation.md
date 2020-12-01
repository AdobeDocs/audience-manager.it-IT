---
description: La vostra azienda potrebbe voler offuscare l’indirizzo IP in molti paesi a causa delle normative globali sulla privacy. Audience Manager consente di offuscare gli indirizzi IP dei visitatori su base globale o paese per paese.
seo-description: La vostra azienda potrebbe voler offuscare l’indirizzo IP in molti paesi a causa delle normative globali sulla privacy. Audience Manager consente di offuscare gli indirizzi IP dei visitatori su base globale o paese per paese.
solution: Audience Manager
title: Offuscamento dell’indirizzo IP
feature: Data Governance and Privacy
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 22%

---


# Offuscamento dell’indirizzo IP {#ip-obfuscation}

Utilizzate questa funzione per oscurare gli indirizzi IP raccolti in  Audience Manager.

## Panoramica e metodologia {#overview-and-methodology}

La vostra azienda potrebbe voler offuscare l’indirizzo IP in molti paesi a causa delle normative globali sulla privacy. Audience Manager consente di offuscare gli indirizzi IP dei visitatori su base globale o paese per paese.

### Metodo di offuscamento IP

In base ai principi di &quot;Privacy By Design&quot;, Adobe Audience Manager consente ai clienti di abilitare l&#39;offuscamento IP dall&#39;interfaccia utente, sia a livello globale in tutte le aree geografiche sia per paesi specifici. Quando si attiva questa impostazione, l&#39;ultimo ottetto (l&#39;ultima parte) dell&#39;indirizzo IP viene eliminato immediatamente quando l&#39;indirizzo IP viene assimilato  Audience Manager.  Audience Manager scarta questa parte dell&#39;indirizzo IP prima dell&#39;elaborazione (inclusa la prima di qualsiasi ricerca geografica facoltativa o registrazione dell&#39;indirizzo IP). Ad esempio:

* Prima dell&#39;offuscamento: `255.255.255.255`
* Dopo l&#39;offuscamento: `255.255.255.0`

Vedi anche, Raccolta di indirizzi IP e offuscamento di indirizzi IP nella nostra sezione [Privacy dei dati](/help/using/overview/data-security-and-privacy/data-privacy.md).

## Requisiti di offuscamento indirizzo IP {#ip-obfuscation-requirements}

L&#39;offuscamento dell&#39;indirizzo IP è disponibile solo per  account amministratore di Audience Manager. Per informazioni su come assegnare privilegi di amministratore a un utente, vedere [Creazione di utenti](/help/using/features/administration/administration-overview.md#create-users).

>[!NOTE]
>
> A causa dell&#39;elevato volume di dati elaborati dal  Audience Manager, le modifiche dell&#39;offuscamento IP possono richiedere fino a 4 ore per entrare in vigore, dal momento in cui aggiornate le impostazioni.

## Configurare l&#39;offuscamento degli indirizzi IP {#configure-ip-obfuscation}

Seguite i passaggi indicati di seguito per configurare l&#39;offuscamento degli indirizzi IP.

1. Accedete  Audience Manager con un account amministratore e andate a **Amministrazione > Privacy**.
2. Scegliere il tipo di offuscamento IP che si desidera utilizzare.
   1. **Oscurate tutti gli indirizzi IP:** selezionate questa opzione per fare in modo che  Audience Manager offuschi l&#39;ultimo ottetto di tutti gli indirizzi IP del visitatore, indipendentemente dalla regione di origine.
   2. **Indirizzi IP offuscati per specifici paesi:** selezionate questa opzione per fare in modo che  Audience Manager offuschi l&#39;ultimo ottetto di indirizzi IP visitatore per specifici paesi. Utilizzare il campo **Elenco di paesi** o il campo **Cerca** corrispondente per individuare i paesi per cui abilitare l&#39;offuscamento IP, quindi fare clic sull&#39;icona + per aggiungerli all&#39;elenco **Selezionato per offuscamento**. Dopo aver aggiunto tutti i paesi richiesti all&#39;elenco **Selezionato per l&#39;offuscamento**, fare clic su **Salva**.

![](assets/ip-obfuscation.png)

## Disattiva offuscamento indirizzo IP {#disable-ip-obfuscation}

Per disabilitare l&#39;offuscamento globale degli indirizzi IP, passare a **Amministrazione > Privacy**, selezionare **Non offuscare gli indirizzi IP** e fare clic su **Salva**.

Per disabilitare l&#39;offuscamento dell&#39;indirizzo IP per specifici paesi, individuare i paesi nell&#39;elenco **Selezionati per l&#39;offuscamento**, quindi fare clic sulla relativa icona **X** corrispondente. Fare clic su **Save** al termine.

## Concetti correlati {#related-concepts}

* [Privacy dei dati](/help/using/overview/data-security-and-privacy/data-privacy.md)
* Video sull&#39;offuscamento dell&#39;indirizzo IP
>[!VIDEO](https://video.tv.adobe.com/v/27218/)

