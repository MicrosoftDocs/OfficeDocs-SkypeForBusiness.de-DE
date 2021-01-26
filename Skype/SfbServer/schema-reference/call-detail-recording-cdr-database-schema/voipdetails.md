---
title: '#A0'
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
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: Die VoIPDetails-Ansicht speichert Informationen zu Peer-zu-Peer-Sitzungen, an denen mindestens ein VoIP-Benutzer teilnimmt. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: b42fecc7a0f43f86dba2439a373c7013c605a5e0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813075"
---
# <a name="voipdetails-view"></a>#A0
 
Die VoIPDetails-Ansicht speichert Informationen zu Peer-zu-Peer-Sitzungen, an denen mindestens ein VoIP-Benutzer teilnimmt. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
> [!NOTE]
> Die Ansicht "VoIPDetails" enthält alle Spalten in der [Ansicht "SessionDetails"](sessiondetails-0.md) sowie die unten aufgeführten Spalten.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**FromPhone** <br/> |nvarchar(450)  <br/> |Telefon-URI des Benutzers, der die Sitzung gestartet hat.  <br/> |
|**ToPhone** <br/> |nvarchar(450)  <br/> |Telefon-URI des Benutzers, der der Sitzung beigetreten ist.  <br/> |
|**DisconnectedByUri** <br/> |nvarchar(450)  <br/> |URI des Benutzers, der die Verbindung zur Sitzung unterbrochen hat.  <br/> |
|**DisconnectedByUriType** <br/> |nvarchar(256)  <br/> |URI-Typ des Benutzers, der die Verbindung zur Sitzung unterbrochen hat. Weitere Informationen finden Sie in der [Tabelle "UriTypes".](uritypes.md) <br/> |
|**DisconnectedByTenant** <br/> |nvarchar(256)  <br/> |Mandant des Benutzers, der die Sitzung gestartet hat.  <br/> |
|**DisconnectedByPhone** <br/> |nvarchar(450)  <br/> |Telefon-URI des Benutzers, der die Verbindung zur Sitzung unterbrochen hat.  <br/> |
|**FromMediationServer** <br/> |nvarchar(256)  <br/> |Vom Benutzer, der die Sitzung gestartet hat, verwendeter Vermittlungsserver.  <br/> |
|**ToMediationServer** <br/> |nvarchar(256)  <br/> |Vom Benutzer, der der Sitzung beigetreten ist, verwendeter Vermittlungsserver.  <br/> |
|**FromGateway** <br/> |nvarchar(256)  <br/> |Vom Benutzer, der die Sitzung gestartet hat, verwendetes Gateway.  <br/> |
|**ToGateway** <br/> |nvarchar(256)  <br/> |Vom Benutzer, der der Sitzung beigetreten ist, verwendetes Gateway.  <br/> |
   

