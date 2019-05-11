---
title: VoIPDetails-Ansicht
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: Die VoIPDetails-Ansicht speichert Informationen zu Peer-zu-Peer-Sitzungen, wobei mindestens ein Benutzer einen VoIP-Benutzer ist. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 6fb1dede975e59c0ae56fe9872472310c914f685
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930029"
---
# <a name="voipdetails-view"></a>VoIPDetails-Ansicht
 
Die VoIPDetails-Ansicht speichert Informationen zu Peer-zu-Peer-Sitzungen, wobei mindestens ein Benutzer einen VoIP-Benutzer ist. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
> [!NOTE]
> Die VoIPDetails-Ansicht enthält alle Spalten in der [SessionDetails-Ansicht](sessiondetails-0.md) außerdem die unten aufgeführten Spalten.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**FromPhone** <br/> |nvarchar(450)  <br/> |Telefon-URI des Benutzers, der die Sitzung gestartet hat.  <br/> |
|**ToPhone** <br/> |nvarchar(450)  <br/> |Telefon-URI des Benutzers, der der Sitzung beigetreten ist.  <br/> |
|**DisconnectedByUri** <br/> |nvarchar(450)  <br/> |Der URI des Benutzers, der die Sitzung gestartet hat.  <br/> |
|**DisconnectedByUriType** <br/> |nvarchar(256)  <br/> |Typ der URI des Benutzers, der die Sitzung gestartet hat. Finden Sie weitere Informationen der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**DisconnectedByTenant** <br/> |nvarchar(256)  <br/> |Mandant des Benutzers, der die Sitzung gestartet hat.  <br/> |
|**DisconnectedByPhone** <br/> |nvarchar(450)  <br/> |Telefon-URI des Benutzers, der die Sitzung gestartet hat.  <br/> |
|**FromMediationServer** <br/> |nvarchar(256)  <br/> |Vom Benutzer, der die Sitzung gestartet hat, verwendeter Vermittlungsserver.  <br/> |
|**ToMediationServer** <br/> |nvarchar(256)  <br/> |Vom Benutzer, der der Sitzung beigetreten ist, verwendeter Vermittlungsserver.  <br/> |
|**FromGateway** <br/> |nvarchar(256)  <br/> |Vom Benutzer, der die Sitzung gestartet hat, verwendetes Gateway.  <br/> |
|**ToGateway** <br/> |nvarchar(256)  <br/> |Vom Benutzer, der der Sitzung beigetreten ist, verwendetes Gateway.  <br/> |
   

