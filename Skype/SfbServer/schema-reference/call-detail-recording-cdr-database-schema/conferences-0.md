---
title: Ansicht "Konferenzen"
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
ms.assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
description: Die Konferenzansicht enthält Informationen zu den Konferenzen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: b31b0baa7a33b28ab9df8d78d2b49e569dfef831
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813255"
---
# <a name="conferences-view"></a>Ansicht "Konferenzen"
 
Die Konferenzansicht enthält Informationen zu den Konferenzen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Datum/Uhrzeit  <br/> |Zeitpunkt der Sitzungsanforderung. Wird zusammen mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren.. Weitere Informationen [finden Sie in der Tabelle "Dialogfelder" in Skype for Business Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |ID zur Identifikation der Sitzung. Wird zusammen mit SessionIdTime verwendet, um eine Konferenzinstanz eindeutig zu identifizieren. Weitere Informationen [finden Sie in der Tabelle "Dialogfelder" in Skype for Business Server 2015.](dialogs.md) <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |Der URI für die Konferenz.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Der Typ des Konferenz-URI. Weitere Informationen finden Sie in der [Tabelle "UriTypes".](uritypes.md) <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> |Wird für wiederkehrende Konferenzen verwendet. Jede Instanz einer wiederkehrenden Konferenz hat die gleiche ConferenceUri, aber eine andere ConfInstance.  <br/> |
|**ConferenceStartTime** <br/> |Datum/Uhrzeit  <br/> |Die Startzeit für die Konferenz.  <br/> |
|**ConferenceEndTime** <br/> |Datum/Uhrzeit  <br/> |Die Endzeit für die Konferenz.  <br/> |
|**OrganizerUri** <br/> |nvarchar(450)  <br/> |Der URI des Benutzers, der die Sitzung organisiert hat.  <br/> |
|**OrganizerType** <br/> |nvarchar(256)  <br/> |Der URI-Typ des Benutzers, der die Konferenz organisiert hat. Weitere Informationen finden Sie in der [Tabelle "UriTypes".](uritypes.md) <br/> |
|**OrganizerTenant** <br/> |nvarchar(256)  <br/> |Der Mandant des Benutzers, der die Konferenz organisiert hat. Weitere Informationen [finden Sie in der Tabelle "Mandanten".](tenants.md) <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |Der vollqualifizierte Domänenname des Pools, von dem die Konferenz gehostet wurde.  <br/> |
|**Wert** <br/> |smallint  <br/> |Eine Bitmaske, die Konferenzattribute enthält. Mögliche Werte sind:  <br/> 0X01 – Synthetische Transaktion  <br/> |
   

