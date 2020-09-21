---
description: Lo stato di autenticazione del visitatore in  Audience Manager determina se le nuove informazioni sulle caratteristiche vengono scritte nel profilo autenticato del visitatore o nel profilo del dispositivo, da cui sono stati raccolti i dati.  Audience Manager gestisce allo stesso modo gli stati di autenticazione dell’ID visitatore UNKNOWN e LOGGED_OUT nelle chiamate dell’evento.
keywords: dpm.demdex.net
seo-description: Lo stato di autenticazione del visitatore in  Audience Manager determina se le nuove informazioni sulle caratteristiche vengono scritte nel profilo autenticato del visitatore o nel profilo del dispositivo, da cui sono stati raccolti i dati.  Audience Manager gestisce allo stesso modo gli stati di autenticazione dell’ID visitatore UNKNOWN e LOGGED_OUT nelle chiamate dell’evento.
seo-title: Stati di autenticazione dei visitatori in Audience Manager
solution: Audience Manager
title: Stati di autenticazione dei visitatori in Audience Manager
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: reference
translation-type: tm+mt
source-git-commit: a41f0beffba686f283a2933ad7066cb124e4d380
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 5%

---


# Stati di autenticazione dei visitatori in Audience Manager{#visitor-authentication-states-in-audience-manager}

Lo stato di autenticazione del visitatore in  Audience Manager determina se le nuove informazioni sulle caratteristiche vengono scritte nel profilo autenticato del visitatore o nel profilo del dispositivo, da cui sono stati raccolti i dati.  Audience Manager gestisce allo stesso modo gli stati di autenticazione dell’ID visitatore UNKNOWN e LOGGED_OUT nelle chiamate dell’evento.

A partire dalla versione 1.5 del servizio [!DNL Experience Cloud] ID, il `setCustomerID` metodo include l’ `AuthState` oggetto facoltativo. `AuthState` identifica i visitatori in base al loro stato [di](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)autenticazione. [!DNL Audience Manager] gestisce le caratteristiche realizzate in modo diverso, a seconda dello stato di autenticazione passato nella chiamata e della regola [di unione dei](../features/profile-merge-rules/merge-rules-dashboard.md) profili utilizzata per la segmentazione.

## Stato autenticazione: SCONOSCIUTO {#auth-status-unknown}

| Valore richiesta | **Leggere** le informazioni dal profilo autenticato | **Scrivere** nuove caratteristiche al profilo autenticato |
---------|----------|---------
| 0 | <ul><li>Sì, se la regola di unione delle opzioni autenticate = &quot;Ultimi profili autenticati&quot;.</li><li>No, se la regola di unione delle opzioni autenticate = &quot;Profili autenticati correnti&quot; o &quot;Nessun profilo autenticato&quot;.</li></ul> | No, i dati sulle caratteristiche vengono aggiunti al profilo del dispositivo. |


Chiamata di esempio (il valore della richiesta corrispondente allo stato di autenticazione è evidenziato):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Stato autenticazione: AUTENTICATO {#auth-status-authenticated}

| Valore richiesta | **Leggere** le informazioni dal profilo autenticato | **Scrivere** nuove caratteristiche al profilo autenticato |
---------|----------|---------
| 1 | <ul><li>Sì, se la regola di unione delle opzioni autenticate = &quot;Profili autenticati correnti&quot; o &quot;Ultimi profili autenticati&quot;.</li><li>No, se la regola di unione delle opzioni autenticate è &quot;Nessun profilo autenticato&quot;.</li></ul> | Sì, i dati sulle caratteristiche vengono aggiunti al profilo autenticato. |

Chiamata di esempio (il valore della richiesta corrispondente allo stato di autenticazione è evidenziato):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Stato autenticazione: LOGGED_OUT {#auth-status-logged-out}

| Valore richiesta | **Leggere** le informazioni dal profilo autenticato | **Scrivere** nuove caratteristiche al profilo autenticato |
---------|----------|---------
| 2 | <ul><li>Sì, se la regola di unione delle opzioni autenticate = &quot;Ultimi profili autenticati&quot;</li><li>No, se la regola di unione delle opzioni autenticate = &quot;Profili autenticati correnti&quot; o &quot;Nessun profilo autenticato&quot;</li></ul> | No, i dati sulle caratteristiche vengono scritti nel profilo del dispositivo. |

Chiamata di esempio (il valore della richiesta corrispondente allo stato di autenticazione è evidenziato):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] esegue una sincronizzazione ID tra [CID e UUID](../reference/ids-in-aam.md) in tutti e tre i casi.

>[!MORELIKETHIS]
>
>* [ID cliente e stati di autenticazione](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)

