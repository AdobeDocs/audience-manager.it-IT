---
title: Migrare dall’estensione tag Audienci Manager all’estensione tag Web SDK
description: Scopri i passaggi per aggiornare la libreria di raccolta dati, ad Audience Manager dall’estensione tag Audienci Manager all’estensione tag Web SDK
source-git-commit: c80f39c4001d2bcfa94012b9f4ffa720806487d4
workflow-type: tm+mt
source-wordcount: '1309'
ht-degree: 0%

---


# Aggiorna la libreria di raccolta dati, ad Audience Manager dall’estensione tag Audienci Manager all’estensione tag Web SDK

## Pubblico previsto

Questa pagina è destinata agli Audienci Manager di clienti che utilizzano [Estensione tag Audienci Manager](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview) per inserire i dati della raccolta web in Audienci Manager. Per i clienti che utilizzano la libreria JavaScript di AppMeasurement, consulta la guida su come aggiornare la libreria di raccolta dati, ad Audience Manager [dalla libreria JavaScript di AppMeasurement alla libreria JavaScript dell’SDK web](appmeasurement-to-web-sdk.md).

## Vantaggi e svantaggi di questo percorso di implementazione

L’utilizzo di questo approccio alla migrazione presenta sia vantaggi che svantaggi. Valuta attentamente ogni opzione per decidere quale approccio è meglio per la tua organizzazione.

| Vantaggi | Svantaggi |
| --- | --- |
| <ul><li>**Nessuna modifica al codice sul sito**: poiché nell’implementazione sono già installati i tag, è possibile eseguire tutti gli aggiornamenti della migrazione nell’interfaccia dei tag.</li><li>**Utilizza l’implementazione esistente**: questo approccio non richiede una nuova implementazione netta. Anche se richiede nuove azioni della regola, puoi riutilizzare gli elementi dati e le condizioni della regola esistenti con modifiche minime.</li><li>**Non richiede uno schema**: in questa fase della migrazione all’SDK per web non è necessario uno schema XDM. È invece possibile compilare il `data` , che invia i dati direttamente a Adobe Audience Manager. Una volta completata la migrazione all’SDK per web, puoi creare uno schema per la tua organizzazione e utilizzare la mappatura dello stream di dati per popolare i campi XDM applicabili. Se in questa fase del processo di migrazione fosse necessario uno schema, l’organizzazione sarebbe costretta a utilizzare uno schema XDM di Adobe Audience Manager. L’utilizzo di questo schema rende più difficile per l’organizzazione utilizzare il proprio schema in futuro.</li></ul> | <ul><li>**Obbligo tecnico di attuazione**: poiché questo approccio utilizza una forma modificata dell’implementazione esistente, può essere più difficile tracciare la logica di implementazione ed eseguire modifiche quando necessario. Il debug del codice personalizzato può essere particolarmente difficile.</li><li>**Richiede la mappatura per inviare dati a Platform**: quando la tua organizzazione è pronta per utilizzare Real-Time CDP, devi inviare dati a un set di dati in Adobe Experience Platform. Questa azione richiede che ogni campo nel `data` object può essere una voce nello strumento di mappatura dello stream di dati che lo assegna a un campo dello schema XDM. La mappatura deve essere eseguita una sola volta per questo flusso di lavoro e non richiede l’apporto di modifiche all’implementazione. Si tratta tuttavia di un passaggio aggiuntivo non richiesto per l’invio di dati in un oggetto XDM.</li></ul> |

L’Adobe consiglia di seguire questo percorso di implementazione quando disponi di un’implementazione esistente utilizzando l’estensione tag Adobe Audience Manager.

## Passaggi necessari per migrare a Web SDK

Le seguenti fasi contengono obiettivi concreti da perseguire. Seleziona ogni passaggio per istruzioni dettagliate su come eseguirlo.

+++**1. Creare e configurare uno stream di dati**

Segui le istruzioni riportate di seguito per creare un flusso di dati in Raccolta dati di Adobe Experience Platform. Quando invii dati a questo stream di dati, questi vengono inoltrati ad Audienci Manager. In futuro, lo stesso flusso di dati inoltra i dati a Real-Time CDP.

1. Accedi a [experience.adobe.com](https://experience.adobe.com) e accedere utilizzando le credenziali.
1. Utilizza la home page o il selettore di prodotti in alto a destra per passare a **[!UICONTROL Data Collection]**.
1. Nel menu di navigazione a sinistra, seleziona **[!UICONTROL Datastreams]**.
1. Seleziona **[!UICONTROL New Datastream]**.
1. Immetti il nome desiderato, quindi seleziona **[!UICONTROL Save]**.
1. Una volta creato lo stream di dati, seleziona **[!UICONTROL Add Service]**.
1. Nel menu a discesa del servizio, seleziona **[!UICONTROL Adobe Audience Manager]**.
1. Assicurati che le **[!UICONTROL Enable XDM Flattened Fields]** è deselezionata.

   ![Aggiungi servizio Audienci Manager](assets/add-service.png) {style="border:1px solid lightslategray"}

Il flusso di dati è ora pronto per ricevere e trasmettere i dati ad Audienci Manager.

+++

+++**2. Aggiungere l’estensione Web SDK alla proprietà tag**

Questa sezione prepara il tag per la maggior parte dell’impegno di migrazione che verrà eseguito nel passaggio successivo.

1. Seleziona l’icona dell’hamburger in alto a sinistra nell’interfaccia di Adobe Experience Platform, quindi seleziona **[!UICONTROL Tags]**.
1. Seleziona la proprietà tag desiderata.
1. Nel menu di navigazione a sinistra della proprietà tag, seleziona **[!UICONTROL Extensions]**.
1. Seleziona **[!UICONTROL Catalog]** nella parte superiore per visualizzare un elenco di tutte le estensioni disponibili.
1. Cerca e seleziona la **[!UICONTROL Adobe Experience Platform Web SDK]** , quindi seleziona **[!UICONTROL Install]** sul lato destro.

   ![Catalogo](assets/catalog.png) {style="border:1px solid lightslategray"}

1. Vengono visualizzate le impostazioni di configurazione dell’estensione. Individua il **[!UICONTROL Datastreams]** e seleziona la sandbox in uso e lo stream di dati creato nel passaggio precedente.

   ![Selezione dello stream di dati](assets/datastream-select.png) {style="border:1px solid lightslategray"}

1. Seleziona **[!UICONTROL Save]**.

L’SDK web è ora installato nella proprietà del tag.

+++

+++**3. Creare un elemento dati dell’oggetto dati**

L’elemento dati dell’oggetto dati fornisce un framework intuitivo per configurare un payload che l’SDK web utilizza per inviare a un flusso di dati. La maggior parte delle regole che aggiorni nel passaggio seguente interagisce con questo elemento dati.

1. Nel menu di navigazione a sinistra dell’interfaccia dei tag, seleziona **[!UICONTROL Data Elements]**.
1. Seleziona **[!UICONTROL Add Data Element]**
1. Attribuisci all’elemento dati le seguenti impostazioni:
   * **[!UICONTROL Name]**: qualsiasi cosa desideri, ad esempio &quot;Livello dati&quot; o &quot;Oggetto dati&quot;
   * **[!UICONTROL Extension]**: [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Data Element Type]**: [!UICONTROL Variable]
   * Le caselle di controllo possono rimanere invariate.
1. Sul lato destro, selezionare le impostazioni seguenti:
   * Pulsante di scelta Proprietà: **[!UICONTROL Data]**
   * **[!UICONTROL Solution]**: [!UICONTROL Adobe Audience Manager]
1. Seleziona **[!UICONTROL Save]**.

   ![Creare un elemento dati](assets/create-data-element.png) {style="border:1px solid lightslategray"}

La proprietà tag ora dispone di tutto il necessario per aggiornare ogni regola.

+++

+++**4. Aggiorna le regole per utilizzare l&#39;estensione Web SDK invece dell&#39;estensione Audienci Manager**

Questo passaggio contiene la maggior parte dello sforzo necessario per migrare all’SDK per web e richiede la conoscenza di come funziona l’implementazione. Di seguito è riportato un esempio di come modificare una tipica regola di tag. Aggiorna tutte le regole di tag nell’implementazione per sostituire tutti i riferimenti all’estensione Audienci Manager con l’estensione Web SDK.

1. Nel menu di navigazione a sinistra dell’interfaccia dei tag, seleziona **[!UICONTROL Rules]**.
1. Seleziona una regola da modificare.
1. Seleziona l’azione **[!UICONTROL Audience Manager - Set Variables]**
1. Nota tutte le variabili di Audience Manager impostate all’interno di questa regola. Includi sia le variabili impostate nei menu a discesa che le variabili impostate nel codice personalizzato.
1. Modificare il [!UICONTROL Action Configuration] alle seguenti impostazioni:
   * **[!UICONTROL Extension]**: [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Action type]**: Aggiorna variabile
1. Assicurati che l’oggetto dati creato al passaggio 3 sia selezionato nel menu a discesa a destra, nella sezione **[!UICONTROL Data element]** campo.
1. Imposta le coppie chiave-valore di Audience Manager sugli stessi valori rispettivi configurati nell’estensione di Audience Manager.
1. Una volta replicata tutta la logica della regola utilizzando l’estensione Web SDK, seleziona **[!UICONTROL Keep Changes]**.
1. Ripeti questi passaggi per ogni configurazione di azione che utilizza l’estensione tag Audienci Manager per impostare i valori.

I passaggi precedenti si applicano solo alle regole che impostano valori. I passaggi seguenti sostituiscono tutte le azioni che utilizzano [!UICONTROL Action Configuration] [!UICONTROL Send Event].

1. Seleziona una regola che invia un evento Web SDK.
1. Seleziona il tipo di azione **[!UICONTROL Send Event]**.
1. Modificare il [!UICONTROL Action Configuration] alle seguenti impostazioni:
   * **[!UICONTROL Extension]**: [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Action type]**: [!UICONTROL Send event]
1. A destra, modifica le impostazioni delle azioni come segue:
   * **[!UICONTROL Type]**: Utilizzare **[!UICONTROL Web Webpagedetails Page Views]**.
   * **[!UICONTROL Data]**: seleziona l’oggetto dati creato al passaggio 3.
1. Seleziona **[!UICONTROL Keep Changes]**.
1. Ripeti questi passaggi per ogni configurazione di azione che utilizza Audienci Manager per inviare un evento.

+++

+++**5. Pubblicare regole aggiornate**

La pubblicazione delle regole aggiornate segue lo stesso flusso di lavoro di qualsiasi altra modifica alla configurazione dei tag.

1. Nel menu di navigazione a sinistra dell’interfaccia dei tag, seleziona **[!UICONTROL Publishing Flow]**.
1. Seleziona **[!UICONTROL Add Library]**.
1. Assegna un nome al commit del tag, ad esempio &quot;Aggiorna a Web SDK&quot;.
1. Seleziona **[!UICONTROL Add All Changed Resources]**.
1. Seleziona **[!UICONTROL Save]**.
1. Il flusso di lavoro di pubblicazione visualizza un punto arancione, che indica che è in corso la creazione. Quando il punto diventa verde, le modifiche sono disponibili nell’ambiente di sviluppo.
1. Verifica le modifiche nell’ambiente di sviluppo per assicurarti che tutte le regole vengano attivate correttamente e che l’oggetto dati venga popolato con i valori previsti.
1. Quando è pronta, invia la libreria per l’approvazione, la build alla staging, quindi alla fine approva e pubblica in produzione.

   ![Flusso di pubblicazione](assets/publishing-flow.png) {style="border:1px solid lightslategray"}

+++

+++**6. Disattiva estensione Audience Manager**

Una volta completata la migrazione dell’implementazione tag all’SDK per web, puoi disabilitare l’estensione Audienci Manager.

1. Nel menu di navigazione a sinistra dell’interfaccia dei tag, seleziona **[!UICONTROL Extensions]**.
1. Individua e seleziona la [!UICONTROL Audience Manager] estensione. A destra, seleziona **[!UICONTROL Disable]**.
1. Segui lo stesso flusso di lavoro di pubblicazione indicato sopra per pubblicare la rimozione del [!UICONTROL Audience Manager] estensione.
1. Una volta che l’estensione è disabilitata in produzione, puoi disinstallarla completamente. Seleziona l’estensione, fai clic sul menu a tre punti a destra, quindi seleziona **[!UICONTROL Uninstall]**.
1. Segui lo stesso flusso di lavoro di pubblicazione indicato sopra per pubblicare tali modifiche in produzione.

+++

A questo punto, l’implementazione Audienci Manager viene completamente migrata all’SDK per web ed è pronta per il passaggio a Real-Time CDP in futuro.

