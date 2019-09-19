---
description: Descrive l'integrazione di Audience Manager e la conformità alle best practice generalmente accettate relative alla privacy dei consumatori e alle procedure di rifiuto.
seo-description: Descrive l'integrazione di Audience Manager e la conformità alle best practice generalmente accettate relative alla privacy dei consumatori e alle procedure di rifiuto.
seo-title: Privacy dei dati
solution: Audience Manager
title: Privacy dei dati
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
translation-type: tm+mt
source-git-commit: e6dcd0a33489ae388df25a95d3ad4841030afe31

---


# Privacy dei dati{#data-privacy}

Descrive l'integrazione di Audience Manager e la conformità alle best practice generalmente accettate relative alla privacy dei consumatori e alle procedure di rifiuto.

## Privacy dei dati {#data-privacy-center}

See the [Adobe Privacy Center](https://www.adobe.com/privacy/opt-out.html).

## Protezione della privacy dei consumatori {#consumer-privacy-protection}

Audience Manager riconosce il patto implicito tra i consumatori e i marchi online con cui interagiscono. Entrambe le parti beneficiano dello scambio trasparente di dati anonimi:

* I consumatori ricevono contenuti personalizzati, offerte scontate per i prodotti ed esperienze utente semplificate.
* I marchi ricevono flussi di entrate vitali che supportano più modelli aziendali online.

Nel nostro continuo supporto a questo modello, Audience Manager continua a impegnarsi a fornire trasparenza e controllo ai consumatori e a rispettare o superare i principi di autoregolamentazione della pubblicità comportamentale online (OBA).

## Gestione del rifiuto {#opt-out-management}

La documentazione di rinuncia è stata estesa e spostata in una parte separata della nostra documentazione. Consultate [Gestione](../../overview/data-security-and-privacy/opt-out-management.md)del rifiuto.

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

## Raccolta di indirizzi IP e offuscamento indirizzi IP {#collecting-ip-addresses}

<!-- 

Adobe has enabled processes and offers settings that allow customers to use Audience Manager in compliance with applicable data privacy laws.

-->

L'indirizzo IP di un visitatore sul sito Web di un cliente viene trasmesso a un Adobe Data Processing Center (DPC), dove l'indirizzo IP può essere memorizzato. A seconda della configurazione di rete del visitatore, l'indirizzo IP potrebbe non rappresentare necessariamente l'indirizzo IP del computer del visitatore. Potrebbe essere ad esempio l’indirizzo IP esterno di un firewall con traduzione degli indirizzi di rete (Network Address Translation, NAT), di un proxy HTTP o di un gateway Internet.

**** Metodologia di offuscamento IP: In base ai principi di "Privacy By Design", Adobe Audience Manager consente ai clienti di abilitare l’offuscamento IP dall’interfaccia utente, a livello globale in tutte le aree geografiche o per specifici paesi. Quando abilitate questa impostazione, l'ultimo ottetto (l'ultima parte) dell'indirizzo IP viene immediatamente eliminato quando l'indirizzo IP viene assimilato in Audience Manager. Audience Manager ignora questa parte dell'indirizzo IP prima dell'elaborazione (inclusa prima di qualsiasi ricerca geografica facoltativa o registrazione dell'indirizzo IP). Ad esempio:

* Prima: `255.255.255.255`
* Dopo: `255.255.255.0`

>[!NOTE]
>
>Consulta [IP Address Obfuscation](/help/using/features/administration/ip-obfuscation.md) (Oscuramento degli indirizzi IP) per informazioni su come abilitare l'offuscamento degli indirizzi IP nell'interfaccia utente di Audience Manager.

**** Segmentazione geografica: Se abilitate l'offuscamento degli indirizzi IP, gli ottetti rimanenti dell'indirizzo IP possono ancora essere utilizzati per la segmentazione geografica e la generazione di rapporti in Audience Manager. Se non abilitate l'offuscamento degli indirizzi IP, Audience Manager utilizza l'indirizzo IP completo. È possibile utilizzare la funzione di segmentazione geografica che consente di identificare una posizione IP per area geografica in entrambi i casi, ma con una leggera perdita di precisione quando si utilizza l'offuscamento IP. L’ottenimento di informazioni a livello di città sarà probabilmente influenzato in modo significativo dall’oscuramento dell’indirizzo IP. L'ottenimento di informazioni a livello di regione e di paese dovrebbe essere influenzato solo leggermente. I dati di segmentazione geografica sono granulari solo a livello di città o codice postale, e non a livello individuale. Ulteriori informazioni sul [geotargeting](/help/using/features/traits/trait-geotarget-keys.md) e su come impostare caratteristiche con variabili geografiche.

## Concetti correlati {#related-concepts}

* [Gestione del rifiuto](/help/using/overview/data-security-and-privacy/opt-out-management.md)
* [Domande frequenti sulla privacy e sulla conservazione dei dati](/help/using/faq/faq-privacy.md)