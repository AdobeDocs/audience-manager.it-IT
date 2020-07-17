---
description: AamGpt è una funzione JavaScript che legge  i dati dei cookie Audience Manager e invia tali informazioni ai tag di Google Publisher.
seo-description: AamGpt è una funzione JavaScript che legge  i dati dei cookie Audience Manager e invia tali informazioni ai tag di Google Publisher.
seo-title: Codice di Audience Manager per i tag publisher di Google
solution: Audience Manager
title: Codice di Audience Manager per i tag publisher di Google
uuid: 24ff5d16-b360-46cc-a4c6-6db34d7fda75
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '116'
ht-degree: 19%

---


# Codice di Audience Manager per i tag publisher di Google {#audience-manager-code-for-google-publisher-tags}

`AamGpt` è una [!DNL JavaScript] funzione che legge  dati del cookie Audience Manager e invia tali informazioni a [!DNL Google Publisher Tags].

>[!NOTE]
>
>Questa funzione non è necessaria se disponete di un codice personalizzato per leggere  dati dei cookie Audience Manager dai cookie [!UICONTROL UUID] e di destinazione.

## Codice di esempio

Posizionare il `AamGpt` codice nella parte superiore della pagina, idealmente all’interno del blocco di `<head>` codice. Il `AamGpt` codice è disponibile di seguito:

```js
var AamGpt = {  
 strictEncode: function(str){ 
  return encodeURIComponent(str).replace(/[!'()]/g, escape).replace(/\*/g, "%2A"); 
 }, 
 getCookie: function(c_name) 
 { 
  var i,x,y,c=document.cookie.split(";"); 
  for (i=0;i<c.length;i++) 
  { 
   x=c[i].substr(0,c[i].indexOf("=")); 
   y=c[i].substr(c[i].indexOf("=")+1); 
   x=x.replace(/^\s+|\s+$/g,""); 
   if (x==c_name) 
   { 
    return unescape(y); 
   } 
  } 
 }, 
 getKey: function(c_name){ 
  var c=this.getCookie(c_name); 
  c=this.strictEncode(c); 
  if(typeof c != "undefined" && c.match(/\w+%3D/)){ 
   var cList=c.split("%3D"); 
   if(typeof cList[0] != "undefined" && cList[0].match(/\w+/)) 
   { 
    return cList[0]; 
   } 
  }  
 }, 
 getValues: function(c_name){ 
  var c=this.getCookie(c_name); 
  c=this.strictEncode(c); 
  if(typeof c != "undefined" && c.match(/\w+%3D\w+/)){ 
   var cList=c.split("%3D"); 
   if(typeof cList[1] != "undefined" && cList[1].match(/\w+/)) 
   { 
    var vList=cList[1].split("%2C"); 
    if(typeof vList[0] != "undefined") 
    { 
     return vList; 
    } else { 
     return null; 
    }    
   } else { 
    return null; 
   } 
  } else { 
   return null; 
  } 
 } 
};
```
