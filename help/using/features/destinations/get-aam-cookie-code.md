---
description: Codice richiesto da DART Enterprise (e altri tipi di destinazione) per acquisire il valore ID univoco di Audience Manager (UUID).
seo-description: Codice richiesto da DART Enterprise (e altri tipi di destinazione) per acquisire il valore ID univoco di Audience Manager (UUID).
seo-title: get_ aamcookie Code
solution: Audience Manager
title: get_ aamcookie Code
uuid: 89 c 30 fe 3-dbe 6-4 d 18-b 161-104167 d 75 bcd
translation-type: tm+mt
source-git-commit: abb66d75a0d47f5257ea8c63bdb59e604db801d3

---


# `get_aamCookie` Codice {#get-aamcookie-code}

Codice richiesto da [!DNL DART Enterprise] (e altri tipi di destinazione) per acquisire il valore ID univoco di Audience Manager ([!DNL UUID]).

Definisce questa funzione nella parte superiore della pagina, idealmente all&#39;interno del `<head>` blocco di codice.

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
