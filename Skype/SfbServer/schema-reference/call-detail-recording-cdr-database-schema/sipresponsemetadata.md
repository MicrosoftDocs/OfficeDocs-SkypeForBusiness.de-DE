---
title: SIPResponseMetaData-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: Das SIPResponseMetaDataTable enthält eine Liste der SIP-Antwortcodes sowie die Klassifizierung und Definition der einzelnen Codes. Diese Codes werden als Reaktion auf Ereignisse generiert, die sich auf SIP-Geräte und SIP-Kommunikationssitzungen auswirken. So wird beispielsweise der Antwortcode 403 generiert, wenn ein SIP-Gerät eine Anforderung stellt, aber der Server lehnt die Anerkennung dieser Anforderung ab.
ms.openlocfilehash: 2c302793dc9f9c53d445d231a261bf43a0c385df
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814893"
---
# <a name="sipresponsemetadata-table"></a>SIPResponseMetaData-Tabelle
 
Das SIPResponseMetaDataTable enthält eine Liste der SIP-Antwortcodes sowie die Klassifizierung und Definition der einzelnen Codes. Diese Codes werden als Reaktion auf Ereignisse generiert, die sich auf SIP-Geräte und SIP-Kommunikationssitzungen auswirken. So wird beispielsweise der Antwortcode 403 generiert, wenn ein SIP-Gerät eine Anforderung stellt, aber der Server lehnt die Anerkennung dieser Anforderung ab.
  
Diese Tabelle wurde in Skype for Business Server 2015 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Response Code** <br/> |int  <br/> |Primary  <br/> |Numerischer Wert, der den SIP-Antwortcode darstellt.  <br/> |
|**Klasse** <br/> |int  <br/> || Allgemeine Klassifizierung für den Antwortcode. Zu den Klassifizierungen gehören: <br/>  1 – Informations Antworten <br/>  2 – erfolgreiche Antworten <br/>  3-Umleitungsantworten <br/>  4 – Antworten auf Client Fehler <br/>  5 – Server Fehlerantworten <br/>  6 – globale Fehlerantwort <br/> |
|**Beschreibung** <br/> |nvarchar(256)  <br/> ||Beschreibung des SIP-Antwortcodes. Antwortcode 181 weist beispielsweise die folgende Beschreibung auf:  <br/> Anruf wird weitergeleitet  <br/> |
   

