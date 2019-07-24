---
description: Descrive l'integrazione e la conformità di Audience Manager con le best practice generalmente accettate relative alle procedure di privacy e rinuncia del consumatore.
seo-description: Descrive l'integrazione e la conformità di Audience Manager con le best practice generalmente accettate relative alle procedure di privacy e rinuncia del consumatore.
seo-title: Privacy dei dati
solution: Audience Manager
title: Privacy dei dati
uuid: 865 e 7 b 4 e-fee 1-4 fa 4-8035-1595 fc 77 cd 96
translation-type: tm+mt
source-git-commit: e6dcd0a33489ae388df25a95d3ad4841030afe31

---


# Privacy dei dati{#data-privacy}

Descrive l'integrazione e la conformità di Audience Manager con le best practice generalmente accettate relative alle procedure di privacy e rinuncia del consumatore.

## Privacy dei dati {#data-privacy-center}

See the [Adobe Privacy Center](https://www.adobe.com/privacy/opt-out.html).

## Consumer Privacy Protection {#consumer-privacy-protection}

Audience Manager riconosce il patto implicito tra i consumatori e i marchi online con cui interagiscono. Entrambe le parti beneficiano dello scambio trasparente di elementi dati anonimi:

* I consumatori ricevono contenuti personalizzati, offerte di prodotto scontate e esperienze utente ottimizzate.
* I marchi ricevono flussi di entrate fondamentali che supportano più modelli aziendali online.

Nel supporto costante di questo modello, Audience Manager continua a garantire la trasparenza e il controllo ai consumatori, nonché a soddisfare o superare i principi autoregolamentali della pubblicità comportamentale (OBA) online.

## Opt-Out Management {#opt-out-management}

La documentazione di rinuncia è stata estesa e spostata in una parte separata della documentazione. See [Opt-out Management](../../overview/data-security-and-privacy/opt-out-management.md).

<!-- 

<p>  </p>
<table id="table_A1FF33B328BD451FAFF6C6B8422F928B"> 
 <tgroup cols="2">
  <colspec colnum="1" colname="col1" colwidth="1.00*" />
  <colspec colnum="2" colname="col2" colwidth="2.74*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> Opt-Out For </th> 
    <th colname="col2" class="entry"> Description </th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
    <td colname="col2"> <p>The <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Your Privacy Choices page</a> provides 1-click features that let you control and opt-out of data collection by the Adobe Experience Cloud advertising solutions (including Audience Manager). Specifically, see the <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> business customer section</a> of the Privacy Choices page. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>Browsers that do not support third-party cookies </p> </td> 
    <td colname="col2"> <p>See <a href="../../features/declared-ids.md#declared-id-targeting"> Declared ID Targeting</a>. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>Mobile devices </p> </td> 
    <td colname="col2"> <p>See the opt-out and privacy settings for: </p> <p> 
      <ul id="ul_86EFAB879215403D937B5148C26A41D9"> 
       <li id="li_C0B544E8F4FE473B94A5436D3A60BDB1"><a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html" format="https" scope="external"> Android devices</a> </li> 
       <li id="li_26C787BAB729499A9FEDF055E9AB0637"><a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html" format="https" scope="external"> iOS devices</a> </li> 
      </ul> </p> </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

 -->

## Collecting IP Addresses and IP Address Obfuscation {#collecting-ip-addresses}

<!-- 

Adobe has enabled processes and offers settings that allow customers to use Audience Manager in compliance with applicable data privacy laws.

-->

L'indirizzo IP di un visitatore nel sito Web di un cliente viene trasmesso a un Adobe Data Processing Center (DPC) dove può essere memorizzato l'indirizzo IP. A seconda della configurazione di rete per il visitatore, l'indirizzo IP potrebbe non rappresentare necessariamente l'indirizzo IP del computer del visitatore. Potrebbe essere ad esempio l’indirizzo IP esterno di un firewall con traduzione degli indirizzi di rete (Network Address Translation, NAT), di un proxy HTTP o di un gateway Internet.

**Metodologia offuscamento IP:** In base ai principi di "Privacy by Design", Adobe Audience Manager consente ai clienti di abilitare l'offuscamento IP dall'interfaccia utente, a livello globale in tutte le aree geografiche o per paesi specifici. Quando abilitate questa impostazione, l'ultimo ottetto (l'ultima parte) dell'indirizzo IP viene eliminato immediatamente quando l'indirizzo IP viene trasferito in Audience Manager. Audience Manager elimina questa parte dell'indirizzo IP prima dell'elaborazione (inclusa la ricerca geografica facoltativa o la registrazione dell'indirizzo IP). Ad esempio:

* Prima: `255.255.255.255`
* Dopo: `255.255.255.0`

>[!NOTE]
>
>See [IP Address Obfuscation](/help/using/features/administration/ip-obfuscation.md) to learn how to enable IP address obfuscation in the Audience Manager UI.

**Segmentazione geografica:** Se abilitate l'offuscamento dell'indirizzo IP, i restanti ottetti dell'indirizzo IP possono essere utilizzati per la segmentazione e il reporting in Audience Manager. Se non abilitate l'offuscamento dell'indirizzo IP, Audience Manager usa l'indirizzo IP completo. Potete utilizzare la funzione Segmentazione geografica per identificare una posizione IP per area geografica in entrambi i casi, ma con lievi perdite di precisione quando viene utilizzata l'offuscamento IP. L’ottenimento di informazioni a livello di città sarà probabilmente influenzato in modo significativo dall’oscuramento dell’indirizzo IP. L'acquisizione di informazioni a livello di paese e paese dovrebbe essere leggermente influenzata. I dati di segmentazione geografica sono granulari solo a livello di città o di codice postale, e non a livello individuale. Read more about [geo-targeting](/help/using/features/traits/trait-geotarget-keys.md) and how to set up traits with geographic variables.

## Concetti correlati {#related-concepts}

* [Gestione della rinuncia](/help/using/overview/data-security-and-privacy/opt-out-management.md)
* [Domande frequenti sulla privacy e sulla conservazione dei dati](/help/using/faq/faq-privacy.md)