---
description: La segmentazione descrive i processi che qualificano e rimuovono i profili dispositivo dai segmenti. La possibilità di rimuovere un profilo dispositivo da un segmento dipende dall'opzione del dispositivo utilizzata per creare una regola di unione dei profili.
seo-description: La segmentazione descrive i processi che qualificano e rimuovono i profili dispositivo dai segmenti. La possibilità di rimuovere un profilo dispositivo da un segmento dipende dall'opzione del dispositivo utilizzata per creare una regola di unione dei profili.
seo-title: ' Regole di unione dei profili e processi di rimozione della segmentazione del dispositivo'
solution: Audience Manager
title: ' Regole di unione dei profili e processi di rimozione della segmentazione del dispositivo'
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Regole di unione dei profili e processi di rimozione della segmentazione del dispositivo {#profile-merge-rules-and-device-un-segmentation-processes}

La segmentazione descrive i processi che qualificano e rimuovono i profili dispositivo dai segmenti. La possibilità di rimuovere un profilo dispositivo da un segmento dipende dall'opzione del dispositivo utilizzata per creare un [!UICONTROL Profile Merge Rule].

## Opzioni dispositivo disponibili {#device-options}

Come promemoria, [!UICONTROL Device Options] sono disponibili nella [!UICONTROL Profile Merge Rules Setup] sezione quando create o modificate un [!UICONTROL Profile Merge Rule].

![](assets/merge-rules-options.png)

## Opzione profilo dispositivo corrente e segmentazione dispositivo {#current-device-profile-options}

**[!UICONTROL Current Device Profile]** è l'opzione di profilo dispositivo predefinita per un [!UICONTROL Profile Merge Rule]. [!DNL Audience Manager] può rimuovere un profilo dispositivo da un segmento quando [!UICONTROL Profile Merge Rule] si utilizza l' **[!UICONTROL Current Device Profile]** opzione. In queste condizioni, la segmentazione si verifica quando:

* Il profilo del dispositivo è rimasto inattivo per 120 giorni. Un processo settimanale di pulizia dei dati rimuove i profili dispositivo inattivi dai tuoi segmenti.
* Il dispositivo non si qualifica più per un segmento perché gli aggiornamenti o le modifiche al profilo del dispositivo lo qualificano. Ciò si verifica quando i criteri di qualificazione del segmento cambiano, o si applica un [!DNL AND NOT] operatore a una regola del segmento, o si specificano le condizioni di [aggiornamento e frequenza](../../features/segments/recency-and-frequency.md) che utilizzano le impostazioni minore di/uguale a. I casi di utilizzo sono descritti nella documentazione [Instant Cross-Device Suppression](../../features/profile-merge-rules/instant-cross-device-suppression.md) .

![](assets/single_device_use_case.png)

<!-- 

<p> <span class="keyword"> Audience Manager</span> can remove a device profile from a segment when your <span class="wintitle"> Profile Merge Rule</span> uses the <b><span class="uicontrol"> Current Device Profile</span></b> option. Under these conditions, unsegmentation happens when: </p> 
<p> 
 <ul id="ul_596501272A224228BD330DD56E01D973"> 
  <li id="li_E4FA1A5C722748CD82AE3A49FCBE86F6">The device profile has been inactive for 120-days. A weekly data cleanup process removes inactive device profiles from your segments. </li> 
  <li id="li_DB0CCD28425048D5B35309B8C2C384F9">The device no longer qualifies for a segment because updates or changes to the device profile disqualify it. This happens when segment qualification criteria change, or you apply an AND NOT operator to a segment rule, or specify <a href="../../features/segments/recency-and-frequency.md"> recency and frequency</a> conditions that use the less than/equal to settings. </li> 
 </ul> </p> 
<p style="text-align: center;"> <img src="assets/unsegment3.png" id="image_B55E5A5EB1964AA08C817211006294E1" /> </p>

 -->

## Nessuna opzione dispositivo e nessuna segmentazione dispositivo {#no-device-option}

[!DNL Audience Manager] può rimuovere un ID cross-device da un segmento quando [!UICONTROL Profile Merge Rule] utilizza l'opzione **[!UICONTROL No Device Profile]** + **[!UICONTROL Current Authenticated]** . In queste condizioni, la segmentazione avviene quando l'ID cross-device non si qualifica più per un segmento perché gli aggiornamenti o le modifiche al profilo cross-device non lo qualificano più. Ciò si verifica quando i criteri di qualificazione del segmento cambiano, o si applica un [!UICONTROL AND NOT] operatore a una regola del segmento, o si specificano le condizioni di [aggiornamento e frequenza](../../features/segments/recency-and-frequency.md) che utilizzano le impostazioni minore di/uguale a. I casi di utilizzo sono descritti nella documentazione [Instant Cross-Device Suppression](../../features/profile-merge-rules/instant-cross-device-suppression.md) .

![](assets/no_device_use_case.png)

## Opzioni di Device Graph e Separazione dispositivo {#device-graph-options-unsegmentation}

[!DNL Audience Manager] può rimuovere più profili dispositivo da un segmento quando [!UICONTROL Profile Merge Rule] si utilizza un'opzione di grafico del dispositivo. La segmentazione avviene quando il profilo unito del dispositivo dal grafico del dispositivo non è più idoneo per il segmento, perché gli aggiornamenti o le modifiche a questo profilo unito non lo qualificano più dal segmento. Ciò si verifica quando i criteri di qualificazione del segmento cambiano, o si applica un [!UICONTROL AND NOT] operatore a una regola del segmento, o si specificano le condizioni di [aggiornamento e frequenza](../../features/segments/recency-and-frequency.md) che utilizzano le impostazioni minore di/uguale a. I casi di utilizzo sono descritti nella documentazione [Instant Cross-Device Suppression](../../features/profile-merge-rules/instant-cross-device-suppression.md) .

>[!NOTE]
>
>**Il limite di quattro dispositivi per la valutazione dei segmenti e l'esclusione** dalla qualifica [!DNL Audience Manager] unisce fino a quattro dispositivi durante la valutazione dei segmenti con un grafico [!UICONTROL Profile Merge Rule] che utilizza un dispositivo. [!DNL Audience Manager] valuta il dispositivo *corrente e tre dispositivi aggiuntivi visti per l’ultima volta in tempo* reale. Se viene emesso il segnale di dissegmento, il dispositivo corrente e tre altri dispositivi visti in tempo reale verranno rimossi dal segmento nella destinazione. Ad esempio, in un cluster a sei dispositivi, vengono uniti, valutati e qualificati fino a quattro dispositivi per un segmento. Allo stesso modo, vengono uniti, valutati e non segmentati fino a quattro dispositivi.

![](assets/cross_device_workflow.png)

<!-- 

<p>Currently, <span class="keyword"> Audience Manager</span> <i>cannot </i> remove a device profile from a segment when your <span class="wintitle"> Profile Merge Rule</span> uses a device graph option. This applies to rules created with these <span class="wintitle"> Device Options</span> settings: </p> 
<p> 
 <ul id="ul_0923834C984F464E9AB12FF5A8773214"> 
  <li id="li_731F67B7A07342988B13D7F91ECA5A9E">Profile Link Device Graph. </li> 
  <li id="li_D1EFC6F124124E64A0732DD060F788BE">The <span class="keyword"> Adobe</span> device graph. </li> 
  <li id="li_CFD4189D4488432D92732532D23B30C7">Other third-party device graph options available that are available to you. </li> 
 </ul> </p> 
<p> Unlike the previous case above, using the AND NOT operator or less than/equal to settings won't remove all of the devices from a segment profile. However, you can unsegment device profiles if you create simple segment rules and apply unsegment logic in the destination that receives your data. The following sections walks you through different unsegmentation use cases. </p>

 -->



<!-- 

<p>This workaround shows you how to unsegment with Boolean <span class="wintitle"> AND NOT</span> logic when your <span class="wintitle"> Profile Merge Rule</span> uses a device graph option. This procedure uses separate, simple segments mapped to the same destination. In this case, you apply AND NOT logic on the destination rather than creating rules in Segment Builder. To set up unsegment rules for this use case: </p> 
<p> 
 <ol id="ol_677F0F9E6CB640079D9021DE66819916"> 
  <li id="li_95F898FDFB2D4F5395201FEA2E60A3AF">Create separate, single-trait segments as shown in the following example. <p style="text-align: center;"><img src="assets/unsegment1.png" id="image_9574D599F449482F8475D9AD2B725DE1" /> </p> </li> 
  <li id="li_3A9F6D8B3CBB4F65B9A06EEC3B265158">Map the segments to the same destination. In this case, we're sending these to <span class="keyword"> Media Optimizer</span>. </li> 
  <li id="li_092BB5887D0D4EE4B09F4B1C6703D454">Set AND NOT logic on the destination (<span class="keyword"> Media Optimizer</span>) rather than in <span class="keyword"> Audience Manager</span>. <p style="text-align: center;"><img src="assets/unsegment2.png" id="image_1E707693ABED41129F11F9FBA334DA58" /> </p> </li> 
 </ol> </p> 
<p> If you're not using <span class="keyword"> Media Optimizer</span>, apply AND NOT logic on whatever destination receives these segments. </p>

 -->



<!-- 

<p>This workaround shows you how to unsegment with the < = (less than/equal to) recency and frequency settings when your <span class="wintitle"> Profile Merge Rule</span> uses a device graph option. To set up unsegment rules for this use case: </p> 
<p> 
 <ol id="ol_DCBEE004B9FE40A881E4EC17FAEA50C2"> 
  <li id="li_DB8C1B6D5C5546E68769902A4F367966">Create a segment that contains a single trait and apply a > = (greater than/equal to) recency and frequency rule to the trait. <p style="text-align: center;"><img src="assets/unsegment4.png" id="image_38069E00B8E8435AAD6E4420CC788D1E" /> </p> </li> 
  <li id="li_0DC50960D83B4B27A40F0BC76B944E0B">Map the segment to a destination. In this case, we're sending the segment to <span class="keyword"> Media Optimizer</span>. </li> 
  <li id="li_FC23194A9FE54296914393F8067A6672">Set NOT logic on the destination (<span class="keyword"> Media Optimizer</span>) rather than in <span class="keyword"> Audience Manager</span>. Use NOT logic to exclude all devices that qualify for this segment from your campaign. <p style="text-align: center;"><img src="assets/unsegment5.png" id="image_BE4408DCB12041A191F208CB1807B9E6" /> </p> </li> 
 </ol> </p> 
<p> If you're not using <span class="keyword"> Media Optimizer</span>, apply NOT logic on whatever destination receives these segments. </p>

 -->

>[!MORE_LIKE_this]
>
>* [Domande frequenti su Regole di unione dei profili e Device Graph](../../faq/faq-profile-merge.md)
>* [Soppressione immediata su diversi dispositivi](../../features/profile-merge-rules/instant-cross-device-suppression.md)
>* [Considerazioni importanti per le regole di unione dei profili con i grafici del dispositivo](../../features/profile-merge-rules/considerations-pmr-device-graph.md)

