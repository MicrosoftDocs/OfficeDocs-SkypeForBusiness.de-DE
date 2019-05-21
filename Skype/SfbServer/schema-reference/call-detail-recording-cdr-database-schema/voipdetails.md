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
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: In der VoIPDetails-Ansicht werden Informationen zu Peer-to-Peer-Sitzungen gespeichert, wobei mindestens ein Benutzer ein VoIP-Benutzer ist. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: 7f5f1e3cf1540e1a12a9365753e494ff2d8a371e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295664"
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
   

