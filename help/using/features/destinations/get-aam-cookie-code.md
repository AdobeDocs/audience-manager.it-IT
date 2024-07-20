---
description: Codice richiesto da DART Enterprise (e da altri tipi di destinazione) per acquisire il valore dell'ID utente univoco di Audience Manager (UUID).
seo-description: Code required by DART Enterprise (and other destination types) to capture the Audience Manager unique user ID (UUID) value.
seo-title: get_aamCookie Code
solution: Audience Manager
title: Codice get_aamCookie
uuid: 89c30fe3-dbe6-4d18-b161-104167d75bcd
feature: Destination Basics
exl-id: 66e61a4b-908e-4950-8953-37a9920b67b5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 0%

---

# Codice `get_aamCookie` {#get-aamcookie-code}

Codice richiesto da [!DNL DART Enterprise] (e altri tipi di destinazione) per acquisire il valore dell&#39;ID utente univoco dell&#39;Audience Manager ([!DNL UUID]).

Definisci questa funzione nella parte superiore della pagina, idealmente all&#39;interno del blocco di codice `<head>`.

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
