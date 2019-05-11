---
title: Conferences-Ansicht
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
description: Conferences-Ansicht speichert Informationen zu Konferenzen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 008895e43fb62377f256cb64fdd5f1b24ed0768e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901345"
---
# <a name="conferences-view"></a>Conferences-Ansicht
 
Conferences-Ansicht speichert Informationen zu Konferenzen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Zeitpunkt der sitzungsanforderung. Zusammen mit SessionIdSeq verwendet zur eindeutigen Identifizierung eine Sitzung. Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |ID-Nummer, um die Sitzung zu identifizieren. In Verbindung mit SessionIdTime verwendet, um eine Sitzung eindeutig zu identifizieren. Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen. <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |Der URI für die Konferenz.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Typ des Konferenz-URI. Finden Sie weitere Informationen der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> |Wird für wiederkehrende Konferenzen verwendet. Jede Instanz einer wiederkehrenden Konferenz hat die gleiche ConferenceUri aber einen anderen ConfInstance.  <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> |Die Startzeit für die Konferenz.  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> |Die Endzeit für die Konferenz.  <br/> |
|**OrganizerUri** <br/> |nvarchar(450)  <br/> |Der URI des Benutzers, der die Sitzung organisiert hat.  <br/> |
|**OrganizerType** <br/> |nvarchar(256)  <br/> |Typ der URI des Benutzers, der die Sitzung organisiert hat. Finden Sie weitere Informationen der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**OrganizerTenant** <br/> |nvarchar(256)  <br/> |Mandant des Benutzers, die Sitzung organisiert hat. Finden Sie weitere Informationen der [Tenants-Tabelle](tenants.md) . <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |Vollqualifizierter Domänenname des Pools, die die Konferenz gehostet.  <br/> |
|**Kennzeichnung** <br/> |smallint  <br/> |Bitmaske, die Konferenz Attribute enthält. Mögliche Werte:  <br/> 0 x 01 – synthetische Transaktion  <br/> |
   

