---
title: SIPResponseMetaData-Tabelle
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: Die SIPResponseMetaData-Tabelle enthält eine Liste der SIP-Antwortcodes und die Klassifizierung und Definition für jeden dieser Codes. Diese Codes werden als Reaktion auf Ereignisse generiert, die SIP-Geräte und SIP-Kommunikationssitzungen betreffen. Beispielsweise wird der Antwortcode 403 generiert, wenn ein SIP-Gerät eine Anforderung ausstellt, aber der Server diese Anforderung ablehnt.
ms.openlocfilehash: 9fb5921b2ff0c371dc8771ce8627bdae23f651dc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58630349"
---
# <a name="sipresponsemetadata-table"></a>SIPResponseMetaData-Tabelle
 
Die SIPResponseMetaData-Tabelle enthält eine Liste der SIP-Antwortcodes und die Klassifizierung und Definition für jeden dieser Codes. Diese Codes werden als Reaktion auf Ereignisse generiert, die SIP-Geräte und SIP-Kommunikationssitzungen betreffen. Beispielsweise wird der Antwortcode 403 generiert, wenn ein SIP-Gerät eine Anforderung ausstellt, aber der Server diese Anforderung ablehnt.
  
Diese Tabelle wurde in Skype for Business Server 2015 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ResponseCode** <br/> |int  <br/> |Primary  <br/> |Numerischer Wert, der den SIP-Antwortcode repräsentiert.  <br/> |
|**Klasse** <br/> |int  <br/> || Allgemeine Klassifizierung für den Antwortcode. Es gibt folgende Klassifizierungen: <br/>  1 – Informationsantworten <br/>  2 – Erfolgreiche Antworten <br/>  3 – Umleitungsantworten <br/>  4 – Clientfehlerantworten <br/>  5 – Antworten auf Serverfehler <br/>  6 – Globale Fehlerantwort <br/> |
|**Beschreibung** <br/> |nvarchar(256)  <br/> ||Beschreibung des SIP-Antwortcodes. Beispielsweise gibt es für den Antwortcode 181 die folgende Beschreibung:  <br/> Anruf wird weitergeleitet  <br/> |
   

