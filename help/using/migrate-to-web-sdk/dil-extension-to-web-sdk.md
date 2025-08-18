---
title: Migrare dall’estensione tag Audience Manager all’estensione tag Web SDK
description: Comprendere i passaggi per aggiornare la libreria di raccolta dati per Audience Manager dall’estensione tag Audience Manager all’estensione tag Web SDK
exl-id: 7f0486db-4511-4311-90df-290580fdcd78
source-git-commit: a50aaeb5e384685100dc3ecc1d6d45f1c41461d0
workflow-type: tm+mt
source-wordcount: '1309'
ht-degree: 0%

---

# Aggiornare la libreria di raccolta dati per Audience Manager dall’estensione tag Audience Manager all’estensione tag Web SDK

## Pubblico previsto

Questa pagina è destinata ai clienti Audience Manager che utilizzano l&#39;estensione tag [Audience Manager](https://experienceleague.adobe.com/it/docs/experience-platform/tags/extensions/client/audience-manager/overview) per inserire dati della raccolta Web in Audience Manager. Per i clienti che utilizzano la libreria JavaScript di AppMeasurement, leggere la guida su come aggiornare la libreria di raccolta dati per Audience Manager [dalla libreria JavaScript di AppMeasurement alla libreria JavaScript Web SDK](appmeasurement-to-web-sdk.md).

## Vantaggi e svantaggi di questo percorso di implementazione

L’utilizzo di questo approccio alla migrazione presenta sia vantaggi che svantaggi. Valuta attentamente ogni opzione per decidere quale approccio è meglio per la tua organizzazione.

| Vantaggi | Svantaggi |
| --- | --- |
| <ul><li>**Nessuna modifica al codice nel sito**: poiché l&#39;implementazione dispone già di tag installati, è possibile eseguire tutti gli aggiornamenti della migrazione nell&#39;interfaccia dei tag.</li><li>**Utilizza l&#39;implementazione esistente**: questo approccio non richiede una nuova implementazione. Anche se richiede nuove azioni della regola, puoi riutilizzare gli elementi dati e le condizioni della regola esistenti con modifiche minime.</li><li>**Non richiede uno schema**: per questa fase della migrazione al Web SDK non è necessario uno schema XDM. È invece possibile popolare l&#39;oggetto `data`, che invia i dati direttamente a Adobe Audience Manager. Una volta completata la migrazione al Web SDK, puoi creare uno schema per la tua organizzazione e utilizzare la mappatura dello stream di dati per popolare i campi XDM applicabili. Se in questa fase del processo di migrazione fosse necessario uno schema, l’organizzazione sarebbe costretta a utilizzare uno schema XDM di Adobe Audience Manager. L’utilizzo di questo schema rende più difficile per l’organizzazione utilizzare il proprio schema in futuro.</li></ul> | <ul><li>**Debito tecnico per l&#39;implementazione**: poiché questo approccio utilizza una forma modificata dell&#39;implementazione esistente, può essere più difficile tenere traccia della logica di implementazione ed eseguire modifiche quando necessario. Il debug del codice personalizzato può essere particolarmente difficile.</li><li>**È necessaria la mappatura per inviare dati a Platform**: quando l&#39;organizzazione è pronta per utilizzare Real-Time CDP, è necessario inviare dati a un set di dati in Adobe Experience Platform. Questa azione richiede che ogni campo nell&#39;oggetto `data` sia una voce nello strumento di mappatura dello stream di dati che lo assegna a un campo dello schema XDM. La mappatura deve essere eseguita una sola volta per questo flusso di lavoro e non richiede l’apporto di modifiche all’implementazione. Si tratta tuttavia di un passaggio aggiuntivo non richiesto per l’invio di dati in un oggetto XDM.</li></ul> |

Adobe consiglia di seguire questo percorso di implementazione quando disponi di un’implementazione esistente utilizzando l’estensione tag Adobe Audience Manager.

## Passaggi necessari per la migrazione al Web SDK

Le seguenti fasi contengono obiettivi concreti da perseguire. Seleziona ogni passaggio per istruzioni dettagliate su come eseguirlo.

+++**1. Crea e configura un flusso di dati**

Segui le istruzioni riportate di seguito per creare un flusso di dati in Raccolta dati di Adobe Experience Platform. Quando invii dati a questo stream di dati, questi vengono inoltrati ad Audience Manager. In futuro, lo stesso flusso di dati inoltra i dati a Real-Time CDP.

1. Passa a [experience.adobe.com](https://experience.adobe.com) e accedi con le tue credenziali.
1. Utilizzare la home page o il selettore di prodotti in alto a destra per passare a **[!UICONTROL Data Collection]**.
1. Nel menu di navigazione a sinistra, selezionare **[!UICONTROL Datastreams]**.
1. Selezionare **[!UICONTROL New Datastream]**.
1. Immettere il nome desiderato, quindi selezionare **[!UICONTROL Save]**.
1. Una volta creato lo stream di dati, selezionare **[!UICONTROL Add Service]**.
1. Nel menu a discesa del servizio, selezionare **[!UICONTROL Adobe Audience Manager]**.
1. Verificare che l&#39;opzione **[!UICONTROL Enable XDM Flattened Fields]** sia deselezionata.

   ![Aggiungi servizio Audience Manager](assets/add-service.png) {style="border:1px solid lightslategray"}

Il flusso di dati è ora pronto per ricevere e trasmettere dati ad Audience Manager.

+++

+++**2. Aggiungi l&#39;estensione Web SDK alla proprietà tag**

Questa sezione prepara il tag per la maggior parte dell’impegno di migrazione che verrà eseguito nel passaggio successivo.

1. Seleziona l&#39;icona dell&#39;hamburger in alto a sinistra nell&#39;interfaccia di Adobe Experience Platform, quindi seleziona **[!UICONTROL Tags]**.
1. Seleziona la proprietà tag desiderata.
1. Nel menu di navigazione a sinistra della proprietà tag, seleziona **[!UICONTROL Extensions]**.
1. Seleziona **[!UICONTROL Catalog]** nella parte superiore per visualizzare un elenco di tutte le estensioni disponibili.
1. Cerca e seleziona l&#39;estensione **[!UICONTROL Adobe Experience Platform Web SDK]**, quindi seleziona **[!UICONTROL Install]** a destra.

   ![Catalogo](assets/catalog.png) {style="border:1px solid lightslategray"}

1. Vengono visualizzate le impostazioni di configurazione dell’estensione. Individua la sezione **[!UICONTROL Datastreams]** e seleziona la sandbox in uso e lo stream di dati creato nel passaggio precedente.

   ![Selezione dello stream di dati](assets/datastream-select.png) {style="border:1px solid lightslategray"}

1. Selezionare **[!UICONTROL Save]**.

Il Web SDK è installato nella proprietà del tag.

+++

+++**3. Crea un elemento dati dell&#39;oggetto dati**

L’elemento dati dell’oggetto dati fornisce un framework intuitivo per configurare un payload che il Web SDK utilizza per inviare a un flusso di dati. La maggior parte delle regole che aggiorni nel passaggio seguente interagisce con questo elemento dati.

1. Nel menu di navigazione a sinistra dell&#39;interfaccia dei tag, selezionare **[!UICONTROL Data Elements]**.
1. Seleziona **[!UICONTROL Add Data Element]**
1. Attribuisci all’elemento dati le seguenti impostazioni:
   * **[!UICONTROL Name]**: qualsiasi cosa desideri, ad esempio &quot;Livello dati&quot; o &quot;Oggetto dati&quot;
   * **[!UICONTROL Extension]**: [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Data Element Type]**: [!UICONTROL Variable]
   * Le caselle di controllo possono rimanere invariate.
1. Sul lato destro, selezionare le impostazioni seguenti:
   * Pulsante di scelta Proprietà: **[!UICONTROL Data]**
   * **[!UICONTROL Solution]**: [!UICONTROL Adobe Audience Manager]
1. Selezionare **[!UICONTROL Save]**.

   ![Crea elemento dati](assets/create-data-element.png) {style="border:1px solid lightslategray"}

La proprietà tag ora dispone di tutto il necessario per aggiornare ogni regola.

+++

+++**4. Aggiorna le regole per utilizzare l&#39;estensione Web SDK anziché l&#39;estensione Audience Manager**

Questo passaggio contiene la maggior parte dello sforzo necessario per migrare al Web SDK e richiede la conoscenza di come funziona la tua implementazione. Di seguito è riportato un esempio di come modificare una tipica regola di tag. Aggiorna tutte le regole di tag nell’implementazione per sostituire tutti i riferimenti all’estensione Audience Manager con l’estensione Web SDK.

1. Nel menu di navigazione a sinistra dell&#39;interfaccia dei tag, selezionare **[!UICONTROL Rules]**.
1. Seleziona una regola da modificare.
1. Selezionare l&#39;azione **[!UICONTROL Audience Manager - Set Variables]**
1. Nota tutte le variabili Audience Manager impostate all’interno di questa regola. Includi sia le variabili impostate nei menu a discesa che le variabili impostate nel codice personalizzato.
1. Cambia [!UICONTROL Action Configuration] con le impostazioni seguenti:
   * **[!UICONTROL Extension]**: [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Action type]**: Aggiorna variabile
1. Verificare che l&#39;oggetto dati creato al passaggio 3 sia selezionato nel menu a discesa a destra, nel campo **[!UICONTROL Data element]**.
1. Imposta le coppie chiave-valore Audience Manager sugli stessi valori rispettivi configurati nell’estensione Audience Manager.
1. Una volta replicata la logica di tutte le regole tramite l&#39;estensione Web SDK, selezionare **[!UICONTROL Keep Changes]**.
1. Ripeti questi passaggi per ogni configurazione di azione che utilizza l’estensione tag Audience Manager per impostare i valori.

I passaggi precedenti si applicano solo alle regole che impostano valori. I passaggi seguenti sostituiscono tutte le azioni che utilizzano [!UICONTROL Action Configuration] [!UICONTROL Send Event].

1. Selezionare una regola che invia un evento Web SDK.
1. Selezionare il tipo di azione **[!UICONTROL Send Event]**.
1. Cambia [!UICONTROL Action Configuration] con le impostazioni seguenti:
   * **[!UICONTROL Extension]**: [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Action type]**: [!UICONTROL Send event]
1. A destra, modifica le impostazioni delle azioni come segue:
   * **[!UICONTROL Type]**: Utilizzare **[!UICONTROL Web Webpagedetails Page Views]**.
   * **[!UICONTROL Data]**: selezionare l&#39;oggetto dati creato al passaggio 3.
1. Selezionare **[!UICONTROL Keep Changes]**.
1. Ripeti questi passaggi per ogni configurazione di azione che utilizza Audience Manager per inviare un evento.

+++

+++**5. Pubblica regole aggiornate**

La pubblicazione delle regole aggiornate segue lo stesso flusso di lavoro di qualsiasi altra modifica alla configurazione dei tag.

1. Nel menu di navigazione a sinistra dell&#39;interfaccia dei tag, selezionare **[!UICONTROL Publishing Flow]**.
1. Selezionare **[!UICONTROL Add Library]**.
1. Assegna un nome al commit del tag, ad esempio &quot;Esegui aggiornamento a Web SDK&quot;.
1. Selezionare **[!UICONTROL Add All Changed Resources]**.
1. Selezionare **[!UICONTROL Save]**.
1. Il flusso di lavoro di pubblicazione visualizza un punto arancione, che indica che è in corso la creazione. Quando il punto diventa verde, le modifiche sono disponibili nell’ambiente di sviluppo.
1. Verifica le modifiche nell’ambiente di sviluppo per assicurarti che tutte le regole vengano attivate correttamente e che l’oggetto dati venga popolato con i valori previsti.
1. Quando è pronta, invia la libreria per l’approvazione, la build alla staging, quindi alla fine approva e pubblica in produzione.

   ![Flusso di pubblicazione](assets/publishing-flow.png) {style="border:1px solid lightslategray"}

+++

+++**6. Disabilita estensione Audience Manager**

Una volta completata la migrazione dell’implementazione tag al Web SDK, puoi disabilitare l’estensione Audience Manager.

1. Nel menu di navigazione a sinistra dell&#39;interfaccia dei tag, selezionare **[!UICONTROL Extensions]**.
1. Individuare e selezionare l&#39;estensione [!UICONTROL Audience Manager]. A destra, selezionare **[!UICONTROL Disable]**.
1. Seguire lo stesso flusso di lavoro di pubblicazione riportato sopra per pubblicare la rimozione dell&#39;estensione [!UICONTROL Audience Manager].
1. Una volta che l’estensione è disabilitata in produzione, puoi disinstallarla completamente. Seleziona l&#39;estensione, fai clic sul menu a tre punti a destra, quindi seleziona **[!UICONTROL Uninstall]**.
1. Segui lo stesso flusso di lavoro di pubblicazione indicato sopra per pubblicare tali modifiche in produzione.

+++

A questo punto, l’implementazione di Audience Manager viene completamente migrata al Web SDK ed è pronta per il passaggio a Real-Time CDP in futuro.
