---
description: Codice richiesto da DART Enterprise (e altri tipi di destinazione) per acquisire il valore ID utente univoco del Audience Manager  (UUID).
seo-description: Codice richiesto da DART Enterprise (e altri tipi di destinazione) per acquisire il valore ID utente univoco del Audience Manager  (UUID).
seo-title: Codice get_aamCookie
solution: Audience Manager
title: Codice get_aamCookie
uuid: 89c30fe3-dbe6-4d18-b161-104167d75bcd
feature: Destination Basics
translation-type: tm+mt
source-git-commit: 7d0735fa9620b7765db7be8d3a7c8731536ffd32
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 11%

---


# Codice get_aamCookie {#get-aamcookie-code}

Codice richiesto da [!DNL DART Enterprise] (e altri tipi di destinazione) per acquisire il valore ID utente univoco ([!DNL UUID]) del Audience Manager .

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
