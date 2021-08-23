---
description: Lo stato di autenticazione del visitatore in Audience Manager determina se le nuove informazioni sulle caratteristiche vengono scritte sul profilo autenticato del visitatore o sul profilo del dispositivo da cui sono stati raccolti i dati. Audience Manager gestisce nello stesso modo gli stati di autenticazione ID visitatore UNKNOWN e LOGGED_OUT nelle chiamate evento.
keywords: dpm.demdex.net
seo-description: Lo stato di autenticazione del visitatore in Audience Manager determina se le nuove informazioni sulle caratteristiche vengono scritte sul profilo autenticato del visitatore o sul profilo del dispositivo da cui sono stati raccolti i dati. Audience Manager gestisce nello stesso modo gli stati di autenticazione ID visitatore UNKNOWN e LOGGED_OUT nelle chiamate evento.
seo-title: Stati di autenticazione dei visitatori in Audience Manager
solution: Audience Manager
title: Stati di autenticazione dei visitatori in Audience Manager
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: 'Riferimenti '
exl-id: 55aec28d-02f6-4e6d-9be1-4ce40deb8dc3
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 7%

---

# Stati di autenticazione dei visitatori in Audience Manager{#visitor-authentication-states-in-audience-manager}

Lo stato di autenticazione del visitatore in Audience Manager determina se le nuove informazioni sulle caratteristiche vengono scritte sul profilo autenticato del visitatore o sul profilo del dispositivo da cui sono stati raccolti i dati. Audience Manager gestisce nello stesso modo gli stati di autenticazione ID visitatore UNKNOWN e LOGGED_OUT nelle chiamate evento.

A partire dalla versione 1.5 del servizio ID [!DNL Experience Cloud], il metodo `setCustomerID` include l&#39;oggetto facoltativo `AuthState`. `AuthState` identifica i visitatori in base al loro stato  [di autenticazione](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html). [!DNL Audience Manager] gestisce le caratteristiche realizzate in modo diverso, a seconda dello stato di autenticazione trasmesso nella chiamata e della regola di unione  [profili ](../features/profile-merge-rules/merge-rules-dashboard.md) utilizzata per la segmentazione.

## Stato autenticazione: SCONOSCIUTO {#auth-status-unknown}

| Valore richiesta | Leggi informazioni dal profilo autenticato | Scrivere nuove caratteristiche al profilo autenticato |
|---|---|---|
| 0 | <ul><li>Sì, se [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles].</li><li>No, se [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] o [!UICONTROL No Authenticated Profile].</li></ul> | No, i dati delle caratteristiche vengono aggiunti al profilo del dispositivo. |

Chiamata di esempio (viene evidenziato il valore della richiesta corrispondente allo stato di autenticazione):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Stato autenticazione: AUTENTICATO {#auth-status-authenticated}

| Valore richiesta | Leggi informazioni dal profilo autenticato | Scrivere nuove caratteristiche al profilo autenticato |
|---|---|---|
| 1 | <ul><li>Sì, se [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] o [!UICONTROL Last Authenticated Profiles].</li><li>No, se [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL No Authenticated Profile].</li></ul> | Sì, i dati delle caratteristiche vengono aggiunti al profilo autenticato. |

Chiamata di esempio (viene evidenziato il valore della richiesta corrispondente allo stato di autenticazione):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Stato autenticazione: LOGGED_OUT {#auth-status-logged-out}

| Valore richiesta | Leggi informazioni dal profilo autenticato | Scrivere nuove caratteristiche al profilo autenticato |
|---|---|---|
| 2 | <ul><li>Sì, se [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles].</li><li>No, se [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] o [!UICONTROL No Authenticated Profile].</li></ul> | No, i dati delle caratteristiche vengono scritti nel profilo del dispositivo. |

Chiamata di esempio (viene evidenziato il valore della richiesta corrispondente allo stato di autenticazione):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] esegue una sincronizzazione ID tra  [CID e ](../reference/ids-in-aam.md) UUID in tutti e tre i casi.

>[!MORELIKETHIS]
>
>* [ID cliente e stati di autenticazione](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html)

