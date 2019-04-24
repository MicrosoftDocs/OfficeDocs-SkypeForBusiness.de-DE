---
title: McuJoinsAndLeaves-Tabelle in Skype für Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
description: Jeder Datensatz in dieser Tabelle enthält Anrufdetails zu eine Kombination aus einem Benutzer beitreten oder verlassen und Conferencing Server. Wenn ein Benutzer eine Konferenz beigetreten, die Webkonferenzen und a/v-Elemente enthält ist, beispielsweise für diesen Benutzer Web Conferencing Join würde ein Datensatz erstellt werden, und für den Benutzer a/v-Konferenzen teilnehmen würde einem anderen Datensatz erstellt werden.
ms.openlocfilehash: 7a31564ed770c956baa0ef7e968d0fba1dc3fd7d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212980"
---
# <a name="mcujoinsandleaves-table-in-skype-for-business-server-2015"></a>McuJoinsAndLeaves-Tabelle in Skype für Business Server 2015
 
Jeder Datensatz in dieser Tabelle enthält Anrufdetails zu eine Kombination aus einem Benutzer beitreten oder verlassen und Conferencing Server. Wenn ein Benutzer eine Konferenz beigetreten, die Webkonferenzen und a/v-Elemente enthält ist, beispielsweise für diesen Benutzer Web Conferencing Join würde ein Datensatz erstellt werden, und für den Benutzer a/v-Konferenzen teilnehmen würde einem anderen Datensatz erstellt werden.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primär, Fremd  <br/> |Zeitpunkt des Konferenz-Instanz. Zusammen mit **SessionIdSeq** verwendet zur eindeutigen Identifizierung eine Konferenz-Instanz. [Conferences-Tabelle in Skype für Business Server 2015](conferences.md) Weitere Informationen finden Sie. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primär, Fremd  <br/> |ID-Nummer zum Identifizieren der Konferenz-Instanz. In Verbindung mit **SessionIdTime** verwendet, um eine Instanz der Konferenz eindeutig zu identifizieren. [Conferences-Tabelle in Skype für Business Server 2015](conferences.md) Weitere Informationen finden Sie. <br/> |
|**Benutzer-ID** <br/> |int  <br/> |Primär, Fremd  <br/> |Eindeutige Zahl, die diesen Benutzer identifiziert. Finden Sie in der [Tabelle Benutzer](users.md) Weitere Informationen. <br/> |
|**McuUserInstance** <br/> |int  <br/> |Primary  <br/> |Wenn ein Benutzer auf mehreren Computern oder Geräten gleichzeitig angemeldet ist, die Benutzer/Geräte-Kombination eindeutig von McuUserInstance identifiziert.  <br/> |
|**IsFromPstn** <br/> |bit  <br/> | <br/> |Gibt an, ob der Benutzer aus dem FESTNETZ Beitritt oder nicht.  <br/> |
|**McuId** <br/> |int  <br/> |Primär, Fremd  <br/> |Eindeutige Zahl, die Konferenzserver identifiziert. [Mcus-Tabelle in Skype für Business Server 2015](mcus.md) Weitere Informationen finden Sie. <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Ausländisch  <br/> |Zeitpunkt der sitzungsanforderung. Zusammen mit **SessionIdSeq** verwendet zur eindeutigen Identifizierung eine Sitzung. Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Ausländisch  <br/> |ID-Nummer, um die Sitzung zu identifizieren. In Verbindung mit **SessionIdTime** verwendet, um eine Sitzung eindeutig zu identifizieren. Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen. <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |Die Zeit, die dieser Benutzer dem Konferenzserver Beitritt.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |Der Zeitpunkt, zu dem dieser Benutzer Konferenzserver verlässt.  <br/> |
|**ClientVerId** <br/> |int  <br/> |Ausländisch  <br/> |Verwenden Sie Bezeichner, der die Versionsnummer der Clientsoftware gibt an, in der Konferenz. [ClientVersions-Tabelle in Skype für Business Server 2015](clientversions.md) Weitere Informationen finden Sie. <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**ZuletztGeändertUm** <br/> |DateTime  <br/> ||Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Skype für Business Server 2015 eingeführt.  <br/> |
   

