---
description: Codice richiesto da DART Enterprise (e altri tipi di destinazione) per acquisire il valore  ID utente univoco Audience Manager (UUID).
seo-description: Codice richiesto da DART Enterprise (e altri tipi di destinazione) per acquisire il valore  ID utente univoco Audience Manager (UUID).
seo-title: get_aamCookie Code
solution: Audience Manager
title: get_aamCookie Code
uuid: 89c30fe3-dbe6-4d18-b161-104167d75bcd
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 1%

---


# `get_aamCookie` Codice {#get-aamcookie-code}

Codice richiesto da [!DNL DART Enterprise] (e altri tipi di destinazione) per acquisire il valore ID utente univoco ([!DNL UUID])  Audience Manager.

Definite questa funzione nella parte superiore della pagina, idealmente all&#39;interno del blocco di `<head>` codice.

<!-- r_aam_de_cookie.xml -->

```js
<script type="text/javascript">
function get_aamCookie (c_name)
{
var i,x,y,ARRcookies=document.cookie.split(";");
for (i=0;i<ARRcookies.length;i++)
   {
   x=ARRcookies[i].substr(0,ARRcookies[i].indexOf("="));
   y=ARRcookies[i].substr(ARRcookies[i].indexOf("=")+1);
   x=x.replace(/^\s+|\s+$/g,"");
   if (x==c_name)
      { 
      return unescape(y);
      }
   }
}
</script>
```
