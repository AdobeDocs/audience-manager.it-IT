---
description: Metodi che consentono di lavorare a livello di programmazione con la libreria DIL (Data Integration Library).
seo-description: Metodi che consentono di lavorare a livello di programmazione con la libreria DIL (Data Integration Library).
seo-title: Metodi API della libreria integrazione dati
solution: Audience Manager
title: Metodi API della libreria integrazione dati
uuid: 507 e 7 afd -3 ae 7-44 de -98 b 0-589 d 699 c 453 b
translation-type: tm+mt
source-git-commit: 5e08861f8bfe88559b089fae00bd14e576f2d0ac

---


# Metodi API della libreria integrazione dati {#data-integration-library-api-methods}

Metodi che consentono di lavorare a livello di programmazione con ( [!UICONTROL Data Integration Library][!UICONTROL DIL].

>[!IMPORTANT]
>
>L&#39;API Library Integration Library è stata rimossa. Questa API utilizzata per generare DIL, che ora potete autoscaricare qui: [Download DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases).

<!-- c_data_integr_library_api.xml -->

## Restituzione versioni per DIL {#return-version-dil}

`GET` Un metodo che restituisce un elenco di versioni ordinate dalla meno recente alla più recente.

<!-- r_api_return_versions_dil.xml -->

### Richiesta

`GET https://api.demdex.com/v1/dil/`

### Risposta

Una richiesta corretta restituisce il codice `["4.0", "4.1"]` di risposta come mostrato di seguito.

```
["4.0", "4.1"]
```

## Return JSON Schema for Version {#return-json-schema-version}

`GET` Un metodo che restituisce lo [!DNL JSON] schema per la [!UICONTROL DIL] versione. Supports using alias [!UICONTROL LATEST] for version to get the latest version of [!UICONTROL DIL].

<!-- r_api_return_json_schema_for_version.xml -->

### Richiesta

`GET https://api.demdex.com/v1/dil/`*`<version>`*

### Risposta

Una richiesta corretta restituisce il codice di risposta `["4.0", "4.1"]` e i dati come mostrato di seguito.

```
{ 
    "type": "object", 
    "$schema": "https://json-schema.org/draft-03/schema", 
    "required": true, 
    "additionalProperties": false, 
    "properties": { 
        "core": { 
            "id": "core", 
            "required": true, 
            "type": "object", 
            "properties": { 
                "code": { 
                    "type": "boolean", 
                    "required": true, 
                    "id": "code" 
                }, 
                "instanceVariable": { 
                    "type": "string", 
                    "id": "instanceVariable", 
                    "required": false 
                }, 
                "create": { 
                    "type": "object", 
                    "id": "create", 
                    "required": false, 
                    "properties": { 
                        "initConfig": { 
                            "additionalProperties": false, 
                            "type": "object", 
                            "id": "initConfig", 
                            "required": true, 
                            "properties": { 
                                "declaredId": { 
                                    "id": "declaredId", 
                                    "required": false, 
                                    "type": "object", 
                                    "additionalProperties": false, 
                                    "properties": { 
                                        "dpid": { 
                                            "id": "dpid", 
                                            "required": true, 
                                            "type": "string" 
                                        }, 
                                        "dpuuid": { 
                                            "id": "dpuuid", 
                                            "required": true, 
                                            "type": "string" 
                                        } 
                                    } 
                                }, 
                                "containerNSID": { 
                                    "type": "number", 
                                    "id": "containerNSID", 
                                    "required": false 
                                }, 
                                "disableDestinationPublishingIframe": { 
                                    "type": "boolean", 
                                    "id": "disableDestinationPublishingIframe", 
                                    "required": false 
                                }, 
                                "enableErrorReporting": { 
                                    "type": "boolean", 
                                    "id": "enableErrorReporting", 
                                    "required": false 
                                }, 
                                "iframeAkamaiHTTPS": { 
                                    "type": "boolean", 
                                    "id": "iframeAkamaiHTTPS", 
                                    "required": false 
                                }, 
                                "iframeAttachmentDelay": { 
                                    "type": "number", 
                                    "id": "iframeAttachmentDelay", 
                                    "required": false 
                                }, 
                                "mappings": { 
                                    "type": "object", 
                                    "id": "mappings", 
                                    "required": false, 
                                    "additionalProperties": { 
                                        "type": "string" 
                                    } 
                                }, 
                                "removeFinishedScriptsAndCallbacks": { 
                                    "type": "boolean", 
                                    "id": "removeFinishedScriptsAndCallbacks", 
                                    "required": false 
                                }, 
                                "uuidCookie": { 
                                    "type": "object", 
                                    "id": "uuidCookie", 
                                    "additionalProperties": false, 
                                    "required": false, 
                                    "properties": { 
                                        "days": { 
                                            "type": "number", 
                                            "id": "days", 
                                            "required": false 
                                        }, 
                                        "domain": { 
                                            "type": "string", 
                                            "id": "domain", 
                                            "required": false 
                                        }, 
                                        "name": { 
                                            "type": "string", 
                                            "id": "name", 
                                            "required": true 
                                        }, 
                                        "path": { 
                                            "type": "string", 
                                            "id": "path", 
                                            "required": false 
                                        }, 
                                        "secure": { 
                                            "type": "boolean", 
                                            "id": "secure", 
                                            "required": false 
                                        } 
                                    } 
                                }, 
                                "visitorService": { 
                                    "type": "object", 
                                    "id": "visitorService", 
                                    "required": false, 
                                    "properties": { 
                                        "namespace": { 
                                            "type": "string", 
                                            "id": "namespace", 
                                            "required": true 
                                        } 
                                    } 
                                } 
                            } 
                        } 
                    } 
                } 
            } 
        }, 
        "options": { 
            "id": "options", 
            "type": "object", 
            "required": false, 
            "properties": { 
                "minify": { 
                    "id": "minify", 
                    "required": false, 
                    "type": "boolean" 
                } 
            } 
        }, 
        "include": { 
            "type": "object", 
            "id": "include", 
            "required": false, 
            "properties": { 
                "modules": { 
                    "type": "object", 
                    "id": "modules", 
                    "required": false, 
                    "additionalProperties": false, 
                    "properties": { 
                        "GoogleAnalytics": { 
                            "type": "object", 
                            "id": "GoogleAnalytics", 
                            "required": false, 
                            "properties": { 
                                "code": { 
                                    "id": "code", 
                                    "type": "boolean", 
                                    "required": true 
                                } 
                            } 
                        }, 
                        "Peer39": { 
                            "type": "object", 
                            "id": "Peer39", 
                            "required": false, 
                            "properties": { 
                                "code": { 
                                    "id": "code", 
                                    "type": "boolean", 
                                    "required": true 
                                } 
                            } 
                        }, 
                        "SiteCatalyst": { 
                            "type": "object", 
                            "id": "SiteCatalyst", 
                            "required": false, 
                            "additionalProperties": false, 
                            "properties": { 
                                "code": { 
                                    "type": "boolean", 
                                    "id": "code", 
                                    "required": true 
                                }, 
                                "init": { 
                                    "type": "object", 
                                    "id": "init", 
                                    "required": false, 
                                    "additionalProperties": false, 
                                    "properties": { 
                                        "siteCatalystInstance": { 
                                            "type": "string", 
                                            "id": "siteCatalystInstance", 
                                            "required": true 
                                        }, 
                                        "dilInstance": { 
                                            "type": "string", 
                                            "id": "dilInstance", 
                                            "required": true 
                                        }, 
                                        "trackedVariables": { 
                                            "id": "trackedVariables", 
                                            "required": false, 
                                            "type": "object", 
                                            "properties": { 
                                                "iteratedNames": { 
                                                    "type": "array", 
                                                    "id": "iteratedNames", 
                                                    "required": false, 
                                                    "items": { 
                                                        "type": "object", 
                                                        "id": "0", 
                                                        "required": true, 
                                                        "properties": { 
                                                            "maxIndex": { 
                                                                "type": "number", 
                                                                "id": "maxIndex", 
                                                                "required": true 
                                                            }, 
                                                            "name": { 
                                                                "type": "string", 
                                                                "id": "name", 
                                                                "required": true 
                                                            } 
                                                        } 
                                                    } 
                                                }, 
                                                "names": { 
                                                    "type": "array", 
                                                    "additionalItems": false, 
                                                    "id": "names", 
                                                    "required": false, 
                                                    "items": [ 
                                                        { 
                                                            "type": "string", 
                                                            "required": true 
                                                        }, 
                                                        { 
                                                            "type": "string", 
                                                            "required": false 
                                                        }, 
                                                        { 
                                                            "type": "string", 
                                                            "required": false 
                                                        }, 
                                                        { 
                                                            "type": "string", 
                                                            "required": false 
                                                        }, 
                                                        { 
                                                            "type": "string", 
                                                            "required": false 
                                                        }, 
                                                        { 
                                                            "type": "string", 
                                                            "required": false 
                                                        }, 
                                                        { 
                                                            "type": "string", 
                                                            "required": false 
                                                        }, 
                                                        { 
                                                            "type": "string", 
                                                            "required": false 
                                                        }, 
                                                        { 
                                                            "type": "string", 
                                                            "required": false 
                                                        } 
                                                    ] 
                                                } 
                                            } 
                                        } 
                                    } 
                                } 
                            } 
                        } 
                    } 
                }, 
                "tools": { 
                    "type": "object", 
                    "id": "tools", 
                    "required": false, 
                    "additionalProperties": false, 
                    "properties": { 
                        "getMetaTags": { 
                            "type": "boolean", 
                            "id": "getMetaTags", 
                            "required": false 
                        }, 
                        "getSearchReferrer": { 
                            "type": "boolean", 
                            "id": "getSearchReferrer", 
                            "required": false 
                        }, 
                        "decomposeURI": { 
                            "type": "boolean", 
                            "id": "decomposeURI", 
                            "required": false 
                        } 
                    } 
                } 
            } 
        } 
    } 
} 
```

## Genera DIL {#generate-dil}

A `GET` method that generates [!UICONTROL DIL] based on passed in request body using the specified version of [!UICONTROL DIL]. Se l&#39;alias `LATEST` viene usato per la versione nell&#39;URL, viene generata la versione [!UICONTROL DIL] più recente.

<!-- r_api_generate_dil.xml -->

### Richiesta

`POST https://api.demdex.com/v1/dil/`*`<version>`*`/generate`

### Richiesta di esempio

```
{ 
    core: { 
        code: true, 
        instanceVariable: 'dil_instance', 
        create: { 
            initConfig: { 
                declaredId: { 
                    dpid: '159', 
                    dpuuid: '456' 
                }, 
                containerNSID: 81, 
                disableDestinationPublishingIframe: false, 
                enableErrorReporting: false, 
                iframeAkamaiHTTPS: false, 
                iframeAttachmentDelay: 575, 
                mappings: { 
                    c_k1: 'd_k1', 
                    c_k2: 'd_k2' 
                }, 
                removeFinishedScriptsAndCallbacks: false, 
                uuidCookie: { 
                    days: 12, 
                    domain: 'adobe.com', 
                    name: 'adobe_did', 
                    path: '/', 
                    secure: false 
                }, 
                visitorService: { 
                    namespace: 'demofirst' 
                } 
            } 
        } 
    }, 
    options: { 
        minify: true 
    }, 
    include: { 
        modules: { 
            GoogleAnalytics: { 
                code: true 
            }, 
            Peer39: { 
                code: true 
            }, 
            SiteCatalyst: { 
                code: true, 
                init: { 
                    siteCatalystInstance: 'sc_instance', 
                    dilInstance: 'dil_instance', 
                    trackedVariables: { 
                        iteratedNames: [{ 
                            name: 'prop', 
                            maxIndex: 5 
                        }, { 
                            name: 'pev', 
                            maxIndex: 3 
                        }], 
                        names: ['pageName', 'channel', 'campaign', 'products', 'events', 'spe', 'spev1', 'spev2', 'spev3'] 
                    } 
                } 
            } 
        }, 
        tools: { 
            getMetaTags: true, 
            getSearchReferrer: true, 
            decomposeURI: true 
        } 
    } 
} 
```

### Risposta

Un aggiornamento riuscito restituisce il codice `201 created` di risposta insieme al [!UICONTROL DIL][!DNL JavaScript] codice.
