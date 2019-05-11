---
title: SIPResponseMetaData-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: Die SIPResponseMetaDataTable enthält eine Liste der SIP-Antwortcodes und der Klassifizierung und Definition der einzelnen Codes. Diese Codes werden als Antwort für Ereignisse, die SIP-Geräte generiert und SIP-kommunikationssitzungen; der Antwortcode 403 wird beispielsweise generiert, wenn ein SIP-Gerät eine Anforderung sendet, aber der Server die Anforderung annehmen ablehnt.
ms.openlocfilehash: edd1f4e60376b367f701864ff15d334c4d971e47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930286"
---
# <a name="sipresponsemetadata-table"></a>SIPResponseMetaData-Tabelle
 
Die SIPResponseMetaDataTable enthält eine Liste der SIP-Antwortcodes und der Klassifizierung und Definition der einzelnen Codes. Diese Codes werden als Antwort für Ereignisse, die SIP-Geräte generiert und SIP-kommunikationssitzungen; der Antwortcode 403 wird beispielsweise generiert, wenn ein SIP-Gerät eine Anforderung sendet, aber der Server die Anforderung annehmen ablehnt.
  
Diese Tabelle wurde in Skype für Business Server 2015 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ResponseCode** <br/> |int  <br/> |Primary  <br/> |Numerische Wert, der den SIP-Antwortcode repräsentiert.  <br/> |
|**Klasse** <br/> |int  <br/> || Allgemeine Klassifizierung für die Antwortcode. Klassifikationen umfassen: <br/>  1 – informative Antworten <br/>  2 – erfolgreiche Antworten <br/>  3 – Umleitungsantworten <br/>  4 – Clientfehlerantworten <br/>  5 – Serverfehlerantworten <br/>  6 – globale Fehlerantworten <br/> |
|**Beschreibung** <br/> |nvarchar(256)  <br/> ||Beschreibung des SIP-Antwortcode. Antwortcode 181 verfügt beispielsweise über die folgenden Beschreibung:  <br/> Anruf wird weitergeleitet.  <br/> |
   

