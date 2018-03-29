---
title: SIPResponseMetaData-Tabelle
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: Die SIPResponseMetaDataTable enthält eine Liste der SIP-Antwortcodes und der Klassifizierung und Definition der einzelnen Codes. Diese Codes werden als Antwort für Ereignisse, die SIP-Geräte generiert und SIP-kommunikationssitzungen; der Antwortcode 403 wird beispielsweise generiert, wenn ein SIP-Gerät eine Anforderung sendet, aber der Server die Anforderung annehmen ablehnt.
ms.openlocfilehash: a90a248837dd705746fe3b342874aad10480e8a6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="sipresponsemetadata-table"></a>SIPResponseMetaData-Tabelle
 
Die SIPResponseMetaDataTable enthält eine Liste der SIP-Antwortcodes und der Klassifizierung und Definition der einzelnen Codes. Diese Codes werden als Antwort für Ereignisse, die SIP-Geräte generiert und SIP-kommunikationssitzungen; der Antwortcode 403 wird beispielsweise generiert, wenn ein SIP-Gerät eine Anforderung sendet, aber der Server die Anforderung annehmen ablehnt.
  
Diese Tabelle wurde in Skype für Business Server 2015 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ResponseCode** <br/> |int  <br/> |Primary  <br/> |Numerische Wert, der den SIP-Antwortcode repräsentiert.  <br/> |
|**Klasse** <br/> |int  <br/> || Allgemeine Klassifizierung für die Antwortcode. Klassifikationen umfassen: <br/>  1 – informative Antworten <br/>  2 – erfolgreiche Antworten <br/>  3 – Umleitungsantworten <br/>  4 – Clientfehlerantworten <br/>  5 – Serverfehlerantworten <br/>  6 – globale Fehlerantworten <br/> |
|**Beschreibung** <br/> |nvarchar(256)  <br/> ||Beschreibung des SIP-Antwortcode. Antwortcode 181 verfügt beispielsweise über die folgenden Beschreibung:  <br/> Anruf wird weitergeleitet.  <br/> |
   

