---
title: VoIPDetails-Ansicht
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: Die VoIPDetails-Ansicht speichert Informationen zu Peer-zu-Peer-Sitzungen, an denen mindestens ein VoIP-Benutzer teilnimmt. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 666959270167c5d1322cacef4acbbeb1a0d22dc9
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60833259"
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
   

