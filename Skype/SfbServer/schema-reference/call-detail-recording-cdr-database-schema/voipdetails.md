---
title: VoIPDetails-Ansicht
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
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: In der VoIPDetails-Ansicht werden Informationen zu Peer-to-Peer-Sitzungen gespeichert, wobei mindestens ein Benutzer ein VoIP-Benutzer ist. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: 4d3aec4c58c2cb11f21ec6403f7532bcde46b05e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814773"
---
# <a name="voipdetails-view"></a>VoIPDetails-Ansicht
 
In der VoIPDetails-Ansicht werden Informationen zu Peer-to-Peer-Sitzungen gespeichert, wobei mindestens ein Benutzer ein VoIP-Benutzer ist. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
  
> [!NOTE]
> Die VoIPDetails-Ansicht enthält alle Spalten in der [SessionDetails-Ansicht](sessiondetails-0.md) sowie die unten aufgeführten Spalten.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**Vom Telefon** <br/> |nvarchar (450)  <br/> |Telefon-URI des Benutzers, der die Sitzung gestartet hat.  <br/> |
|**Tophone** <br/> |nvarchar (450)  <br/> |Telefon-URI des Benutzers, der der Sitzung beigetreten ist.  <br/> |
|**DisconnectedByUri** <br/> |nvarchar (450)  <br/> |Der URI des Benutzers, der die Sitzung getrennt hat.  <br/> |
|**DisconnectedByUriType** <br/> |nvarchar(256)  <br/> |Der Typ des URIs des Benutzers, der die Sitzung getrennt hat. Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**DisconnectedByTenant** <br/> |nvarchar(256)  <br/> |Der Mandant des Benutzers, der die Sitzung getrennt hat.  <br/> |
|**DisconnectedByPhone** <br/> |nvarchar (450)  <br/> |Telefon-URI des Benutzers, der die Sitzung getrennt hat.  <br/> |
|**FromMediationServer** <br/> |nvarchar(256)  <br/> |Der von dem Benutzer, der die Sitzung gestartet hat, verwendete Vermittlungs Server.  <br/> |
|**ToMediationServer** <br/> |nvarchar(256)  <br/> |Vermittlungs Server, der von dem Benutzer verwendet wird, der der Sitzung beigetreten ist.  <br/> |
|**FromGateway** <br/> |nvarchar(256)  <br/> |Gateway, das vom Benutzer verwendet wird, der die Sitzung gestartet hat.  <br/> |
|**Togateway** <br/> |nvarchar(256)  <br/> |Gateway, das vom Benutzer verwendet wird, der der Sitzung beigetreten ist.  <br/> |
   

