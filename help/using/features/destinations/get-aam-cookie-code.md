---
description: Codice richiesto da DART Enterprise (e altri tipi di destinazione) per acquisire il valore ID utente univoco di Audience Manager (UUID).
seo-description: Codice richiesto da DART Enterprise (e altri tipi di destinazione) per acquisire il valore ID utente univoco di Audience Manager (UUID).
seo-title: get_aamCookie Code
solution: Audience Manager
title: get_aamCookie Code
uuid: 89c30fe3-dbe6-4d18-b161-104167d75bcd
translation-type: tm+mt
source-git-commit: abb66d75a0d47f5257ea8c63bdb59e604db801d3

---


# `get_aamCookie` Codice {#get-aamcookie-code}

Codice richiesto da [!DNL DART Enterprise] (e altri tipi di destinazione) per acquisire il valore ID utente univoco ([!DNL UUID]) di Audience Manager.

Definite questa funzione nella parte superiore della pagina, idealmente all'interno del blocco di `<head>` codice.

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
