---
title: ConferenceMessageCount-Ansicht
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: In der ConferenceMessageCount-Ansicht werden Informationen darüber gespeichert, wie viele Nachrichten von einem Benutzer an eine Konferenz gesendet wurden. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: a766e63fbca5c30cec3c3891c9ccfc2355f16d2d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815383"
---
# <a name="conferencemessagecount-view"></a>ConferenceMessageCount-Ansicht
 
In der ConferenceMessageCount-Ansicht werden Informationen darüber gespeichert, wie viele Nachrichten von einem Benutzer an eine Konferenz gesendet wurden. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
  
> [!NOTE]
> Die ConferenceMessageCount-Ansicht enthält alle Spalten in der [ConferenceSessionDetails-Ansicht](conferencesessiondetails.md) sowie die unten aufgeführten Spalten.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**UserUri** <br/> |nvarchar (450)  <br/> |Der URI des Benutzers, der die Nachricht gesendet hat.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Der Typ des URIs des Benutzers, der die Nachrichten gesendet hat. Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**UserTenant** <br/> |uniqueidentifier  <br/> |Der Mandant des Benutzers, der die Nachrichten gesendet hat. Weitere Informationen finden Sie in der [Tabelle Mandanten](tenants.md) . <br/> |
|**UserMessageCount** <br/> |smallint  <br/> |Die Anzahl der Nachrichten, die der Benutzer während der Konferenzsitzung gesendet hat.  <br/> |
   

