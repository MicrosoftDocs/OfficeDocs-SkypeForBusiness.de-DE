---
title: McuJoinsAndLeaves-Ansicht
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
ms.assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
description: Die McuJoinsAndLeaves-Ansicht speichert Informationen zu Benutzern, die an einem Konferenzserver teilnehmen und Informationen hinterlassen. Jeder Datensatz in dieser Ansicht enthält Anrufdetails zu einer Kombination aus einem Benutzer-Join oder Leave-und Konferenzserver. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: 7a7569795d55620051e617d9312d87f3c96c628a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815093"
---
# <a name="mcujoinsandleaves-view"></a>McuJoinsAndLeaves-Ansicht
 
Die McuJoinsAndLeaves-Ansicht speichert Informationen zu Benutzern, die an einem Konferenzserver teilnehmen und Informationen hinterlassen. Jeder Datensatz in dieser Ansicht enthält Anrufdetails zu einer Kombination aus einem Benutzer-Join oder Leave-und Konferenzserver. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**SessionID** <br/> |datetime  <br/> |Uhrzeit der Konferenz Instanz. Wird in Verbindung mit SessionIdSeq verwendet, um eine Konferenz Instanz eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle "Konferenzen" in Skype for Business Server 2015](conferences.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Die ID-Nummer zum Identifizieren der Konferenz Instanz. Wird in Verbindung mit SessionID-Mal verwendet, um eine Konferenz Instanz eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle "Konferenzen" in Skype for Business Server 2015](conferences.md) . <br/> |
|**McuUri** <br/> |nvarchar(256)  <br/> |Der URI des Konferenzservers, mit dem der Benutzer eine Verbindung hergestellt hat.  <br/> |
|**McuUriType** <br/> |nvarchar(256)  <br/> |Der URI des Konferenzservers, mit dem der Benutzer eine Verbindung hergestellt hat. Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> |Der URI des Benutzers, dessen Konferenzserver teilnehmen/Leave-Informationen erfasst wurde.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Der Typ des URIs des Benutzers, dessen Konferenzserver teilnehmen/Leave-Informationen erfasst wurde. Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Der Mandant des Benutzers, dessen Konferenzserver teilnehmen/Leave-Informationen erfasst wurde. Weitere Informationen finden Sie in der [Tabelle Mandanten](tenants.md) . <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Die Version des Clients, die von dem Benutzer verwendet wird, dessen Konferenzserver-Informationen aufgenommen wurden.  <br/> |
|**UserClientType** <br/> |int  <br/> |Der Client, der von dem Benutzer verwendet wird, dessen Konferenzserver an-und Abgangs Informationen erfasst wurde. Weitere Informationen finden Sie in der [UserAgentDef-Tabelle](useragentdef.md) . <br/> |
|**UserClientCategory** <br/> |nvarchar (64)  <br/> |Der Name der Kategorie des Clients, die von dem Benutzer verwendet wird, dessen Konferenzserver-Informationen aufgenommen wurden.  <br/> |
|**McuUserInstance** <br/> |int  <br/> |Kennzeichnet die Kombination von Benutzern/Geräten für Benutzer, die gleichzeitig an mehreren Geräten angemeldet sind.  <br/> |
|**IsUserFromPstn** <br/> |bit  <br/> |Bit, das darstellt, ob der Benutzer ein interner Benutzer ist oder nicht.  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Uhrzeit der Sitzungsanforderung. Wird in Verbindung mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Die ID-Nummer, um die Sitzung zu identifizieren. Wird in Verbindung mit SessionID-Mal verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**Dialogfeld-Nr** <br/> |varchar (775)  <br/> |SIP-Dialogfeld-ID der Sitzung. Das Format lautet: Dialogfeld; from-Tag; to-Tag.  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |Zeitpunkt, zu dem der Benutzer dem Konferenzserver beigetreten ist.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |Zeitpunkt, zu dem der Benutzer den Konferenzserver verlassen hat.  <br/> |
   

