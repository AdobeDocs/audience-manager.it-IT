---
description: La vostra azienda potrebbe voler offuscare l’indirizzo IP in molti paesi a causa delle normative globali sulla privacy. Audience Manager consente di offuscare gli indirizzi IP dei visitatori su base globale o paese per paese.
seo-description: La vostra azienda potrebbe voler offuscare l’indirizzo IP in molti paesi a causa delle normative globali sulla privacy. Audience Manager consente di offuscare gli indirizzi IP dei visitatori su base globale o paese per paese.
solution: Audience Manager
title: Offuscamento dell’indirizzo IP
feature: Governance dei dati e privacy
exl-id: 8c976d1e-f4ba-4892-bd68-d4e74bdb4d9b
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 22%

---

# Offuscamento dell’indirizzo IP {#ip-obfuscation}

Utilizza questa funzione per offuscare gli indirizzi IP raccolti nell’Audience Manager.

## Panoramica e metodologia {#overview-and-methodology}

La vostra azienda potrebbe voler offuscare l’indirizzo IP in molti paesi a causa delle normative globali sulla privacy. Audience Manager consente di offuscare gli indirizzi IP dei visitatori su base globale o paese per paese.

### Metodologia di offuscamento dell’IP

Seguendo i principi di &quot;Privacy By Design&quot;, Adobe Audience Manager consente ai clienti di abilitare l’offuscamento dell’IP dall’interfaccia utente, sia a livello globale in tutte le aree geografiche che per specifici paesi. Quando abiliti questa impostazione, l’ultimo ottetto (l’ultima parte) dell’indirizzo IP viene eliminato immediatamente quando l’indirizzo IP viene acquisito nell’Audience Manager. L’Audience Manager elimina questa parte dell’indirizzo IP prima dell’elaborazione (incluso prima di qualsiasi ricerca geografica facoltativa o registrazione dell’indirizzo IP). Ad esempio:

* Prima dell&#39;offuscamento: `255.255.255.255`
* Dopo l&#39;offuscamento: `255.255.255.0`

Vedi anche Raccolta di indirizzi IP e offuscamento di indirizzi IP nella nostra [sezione Privacy dei dati](/help/using/overview/data-security-and-privacy/data-privacy.md).

## Requisiti di offuscamento dell’indirizzo IP {#ip-obfuscation-requirements}

L’offuscamento dell’indirizzo IP è disponibile solo per gli account amministratore di Audience Manager. Per informazioni su come assegnare privilegi di amministratore a un utente, consulta [Creare utenti](/help/using/features/administration/administration-overview.md#create-users) .

>[!NOTE]
>
> A causa del grande volume di dati elaborati dall’Audience Manager, le modifiche all’offuscamento dell’IP possono richiedere fino a 4 ore per entrare in vigore, dal momento in cui aggiorni le impostazioni.

## Configura offuscamento dell&#39;indirizzo IP {#configure-ip-obfuscation}

Segui i passaggi riportati di seguito per configurare l’offuscamento dell’indirizzo IP.

1. Accedi ad Audience Manager con un account amministratore e vai a **Amministrazione > Privacy**.
2. Scegli il tipo di offuscamento IP che desideri utilizzare.
   1. **Offusca tutti gli indirizzi IP:**  seleziona questa opzione per far sì che l’Audience Manager offuschi l’ultimo ottetto di tutti gli indirizzi IP del visitatore, indipendentemente dalla regione da cui provengono.
   2. **Offusca gli indirizzi IP per paesi specifici:**  seleziona questa opzione per far sì che l’Audience Manager offuschi l’ultimo ottetto degli indirizzi IP del visitatore per paesi specifici. Utilizza il campo **Elenco di paesi** o il corrispondente campo **Ricerca** per trovare i paesi per cui abilitare l&#39;offuscamento dell&#39;IP, quindi fai clic sull&#39;icona + per aggiungerli all&#39;elenco **Selezionati per offuscamento**. Dopo aver aggiunto tutti i paesi richiesti all&#39;elenco **Selezionati per offuscamento**, fai clic su **Salva**.

![](assets/ip-obfuscation.png)

## Disabilita offuscamento indirizzo IP {#disable-ip-obfuscation}

Per disabilitare l&#39;offuscamento dell&#39;indirizzo IP a livello globale, vai a **Amministrazione > Privacy**, seleziona **Non offuscare gli indirizzi IP** e fai clic su **Salva**.

Per disabilitare l&#39;offuscamento dell&#39;indirizzo IP per paesi specifici, individua i paesi nell&#39;elenco **Selezionati per offuscamento**, quindi fai clic sulla relativa icona **X**. Al termine, fai clic su **Salva**.

## Concetti correlati {#related-concepts}

* [Privacy dei dati](/help/using/overview/data-security-and-privacy/data-privacy.md)
* Video dimostrativo sull&#39;offuscamento dell&#39;indirizzo IP
>[!VIDEO](https://video.tv.adobe.com/v/27218/)
