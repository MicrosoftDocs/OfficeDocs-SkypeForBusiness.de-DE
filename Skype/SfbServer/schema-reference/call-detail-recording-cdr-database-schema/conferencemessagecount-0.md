---
title: Ansicht "ConferenceMessageCount"
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: Die Ansicht "ConferenceMessageCount" speichert Informationen dazu, wie viele Nachrichten von einem Benutzer an eine Konferenz gesendet wurden. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 8394ed37d4b85e8ec5fcda4234b4c28f4276fb17
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813295"
---
# <a name="conferencemessagecount-view"></a>Ansicht "ConferenceMessageCount"
 
Die Ansicht "ConferenceMessageCount" speichert Informationen dazu, wie viele Nachrichten von einem Benutzer an eine Konferenz gesendet wurden. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
> [!NOTE]
> Die Ansicht "ConferenceMessageCount" enthält zusätzlich zu den unten aufgeführten Spalten alle Spalten in der [Ansicht "ConferenceSessionDetails".](conferencesessiondetails.md)
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**UserUri** <br/> |nvarchar(450)  <br/> |URI des Benutzers, der die Nachricht gesendet hat.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Typ des URI des Benutzers, der die Nachrichten gesendet hat. Weitere Informationen finden Sie in der [Tabelle "UriTypes".](uritypes.md) <br/> |
|**UserTenant** <br/> |uniqueidentifier  <br/> |Mandant des Benutzers, der die Nachrichten gesendet hat. Weitere Informationen [finden Sie in der Tabelle "Mandanten".](tenants.md) <br/> |
|**UserMessageCount** <br/> |smallint  <br/> |Die Anzahl der Nachrichten, die der Benutzer während der Konferenzsitzung gesendet hat.  <br/> |
   

