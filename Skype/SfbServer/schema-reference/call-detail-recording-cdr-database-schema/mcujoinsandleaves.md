---
title: Tabelle "McuJoinsAndLeaves" in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
description: Jeder Datensatz in dieser Tabelle enthält Anrufdetails zu einer Kombination aus einem Benutzer, der einem Benutzer beitritt oder den Konferenzserver verlässt. Wenn beispielsweise ein Benutzer einer Konferenz beitritt, die Webkonferenz- und Audio-/Videoelemente umfasst, wird ein Datensatz für den Webkonferenz beitritt dieses Benutzers erstellt, und ein weiterer Datensatz für den Audio-/Videokonferenz-Beitritt des Benutzers.
ms.openlocfilehash: 8c9e6cba970e113d119ab3ce894dee8d5b4f6b28
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821495"
---
# <a name="mcujoinsandleaves-table-in-skype-for-business-server-2015"></a>Tabelle "McuJoinsAndLeaves" in Skype for Business Server 2015
 
Jeder Datensatz in dieser Tabelle enthält Anrufdetails zu einer Kombination aus einem Benutzer, der einem Benutzer beitritt oder den Konferenzserver verlässt. Wenn beispielsweise ein Benutzer einer Konferenz beitritt, die Webkonferenz- und Audio-/Videoelemente umfasst, wird ein Datensatz für den Webkonferenz beitritt dieses Benutzers erstellt, und ein weiterer Datensatz für den Audio-/Videokonferenz-Beitritt des Benutzers.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Datum/Uhrzeit  <br/> |Primär, Fremd  <br/> |Zeitpunkt der Konferenzinstanz. Wird in Verbindung mit **SessionIdSeq verwendet,** um eine Konferenzinstanz eindeutig zu identifizieren. Weitere Informationen finden Sie in der [Tabelle "Konferenzen" in Skype for Business Server 2015.](conferences.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primär, Fremd  <br/> |ID zur Identifikation der Konferenzinstanz. Wird in Verbindung mit **SessionIdTime verwendet,** um eine Konferenzinstanz eindeutig zu identifizieren. Weitere Informationen finden Sie in der [Tabelle "Konferenzen" in Skype for Business Server 2015.](conferences.md) <br/> |
|**UserId** <br/> |int  <br/> |Primär, Fremd  <br/> |Eindeutige Zahl, die diesen Benutzer identifiziert. Weitere Informationen [finden Sie in der Tabelle](users.md) "Benutzer". <br/> |
|**McuUserInstance** <br/> |int  <br/> |Primary  <br/> |Wenn ein Benutzer auf mehreren Computern oder Geräten gleichzeitig angemeldet ist, identifiziert McuUserInstance die Kombination aus Benutzer und Gerät eindeutig.  <br/> |
|**IsFromPstn** <br/> |bit  <br/> | <br/> |Gibt an, ob der Benutzer aus einem PSTN beitritt oder nicht.  <br/> |
|**McuId** <br/> |int  <br/> |Primär, Fremd  <br/> |Eindeutige Nummer, die diesen Konferenzserver identifiziert. Weitere Informationen finden Sie in der [Tabelle "Mcus" in Skype for Business Server 2015.](mcus.md) <br/> |
|**DialogSessionIdTime** <br/> |Datum/Uhrzeit  <br/> |Fremd  <br/> |Zeitpunkt der Sitzungsanforderung. Wird zusammen mit **SessionIdSeq** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen [finden Sie in der Tabelle "Dialogfelder" in Skype for Business Server 2015.](dialogs.md) <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Fremd  <br/> |ID zur Identifikation der Sitzung. Wird zusammen mit **SessionIdTime** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen [finden Sie in der Tabelle "Dialogfelder" in Skype for Business Server 2015.](dialogs.md) <br/> |
|**UserJoinTime** <br/> |Datum/Uhrzeit  <br/> | <br/> |Der Zeitpunkt, zu dem dieser Benutzer diesem Konferenzserver beitritt.  <br/> |
|**UserLeaveTime** <br/> |Datum/Uhrzeit  <br/> | <br/> |Der Zeitpunkt, zu dem dieser Benutzer diesen Konferenzserver verlässt.  <br/> |
|**ClientVerId** <br/> |int  <br/> |Fremd  <br/> |Bezeichner, der die Versionsnummer der Clientsoftware angibt, die in der Konferenz verwendet wird. Weitere Informationen finden Sie in der [Tabelle "ClientVersions" in Skype for Business Server 2015.](clientversions.md) <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Skype for Business Server 2015 eingeführt.  <br/> |
   

