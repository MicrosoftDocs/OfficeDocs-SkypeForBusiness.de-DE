---
title: VoIPDetails-Ansicht
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
ms.openlocfilehash: 9e8eeaa0e907496d03a4541792f6f100a9191324497ee7603a65ec5a71fba592
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351954"
---
# <a name="voipdetails-view"></a>VoIPDetails-Ansicht
 
Die VoIPDetails-Ansicht speichert Informationen zu Peer-zu-Peer-Sitzungen, an denen mindestens ein VoIP-Benutzer teilnimmt. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
> [!NOTE]
> Die VoIPDetails-Ansicht enthält alle Spalten in der [SessionDetails-Ansicht](sessiondetails-0.md) zusätzlich zu den unten aufgeführten Spalten.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**FromPhone** <br/> |nvarchar(450)  <br/> |Telefon-URI des Benutzers, der die Sitzung gestartet hat.  <br/> |
|**ToPhone** <br/> |nvarchar(450)  <br/> |Telefon-URI des Benutzers, der der Sitzung beigetreten ist.  <br/> |
|**DisconnectedByUri** <br/> |nvarchar(450)  <br/> |URI des Benutzers, der die Verbindung zur Sitzung unterbrochen hat.  <br/> |
|**DisconnectedByUriType** <br/> |nvarchar(256)  <br/> |URI-Typ des Benutzers, der die Verbindung zur Sitzung unterbrochen hat. Weitere Informationen finden Sie in der [UriTypes-Tabelle.](uritypes.md) <br/> |
|**DisconnectedByTenant** <br/> |nvarchar(256)  <br/> |Mandant des Benutzers, der die Sitzung gestartet hat.  <br/> |
|**DisconnectedByPhone** <br/> |nvarchar(450)  <br/> |Telefon-URI des Benutzers, der die Verbindung zur Sitzung unterbrochen hat.  <br/> |
|**FromMediationServer** <br/> |nvarchar(256)  <br/> |Vom Benutzer, der die Sitzung gestartet hat, verwendeter Vermittlungsserver.  <br/> |
|**ToMediationServer** <br/> |nvarchar(256)  <br/> |Vom Benutzer, der der Sitzung beigetreten ist, verwendeter Vermittlungsserver.  <br/> |
|**FromGateway** <br/> |nvarchar(256)  <br/> |Vom Benutzer, der die Sitzung gestartet hat, verwendetes Gateway.  <br/> |
|**ToGateway** <br/> |nvarchar(256)  <br/> |Vom Benutzer, der der Sitzung beigetreten ist, verwendetes Gateway.  <br/> |
   

