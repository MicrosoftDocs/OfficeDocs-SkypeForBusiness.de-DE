---
title: McuJoinsAndLeaves-Tabelle in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
description: Jeder Datensatz in dieser Tabelle enthält Anrufdetails zu einer Kombination aus einem Benutzer-Join oder Leave-und Konferenzserver. Wenn ein Benutzer beispielsweise an einer Konferenz teilnimmt, die Webkonferenzen und Audio/Video-Elemente umfasst, wird ein Datensatz für die Webkonferenz Verknüpfung dieses Benutzers erstellt, und es wird ein anderer Eintrag für die Audio-und Videokonferenz Teilnahme des Benutzers erstellt.
ms.openlocfilehash: d61b3c1ef1aa6fe481a4022f7bc434b523b68213
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296070"
---
# <a name="mcujoinsandleaves-table-in-skype-for-business-server-2015"></a>McuJoinsAndLeaves-Tabelle in Skype for Business Server 2015
 
Jeder Datensatz in dieser Tabelle enthält Anrufdetails zu einer Kombination aus einem Benutzer-Join oder Leave-und Konferenzserver. Wenn ein Benutzer beispielsweise an einer Konferenz teilnimmt, die Webkonferenzen und Audio/Video-Elemente umfasst, wird ein Datensatz für die Webkonferenz Verknüpfung dieses Benutzers erstellt, und es wird ein anderer Eintrag für die Audio-und Videokonferenz Teilnahme des Benutzers erstellt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionID** <br/> |datetime  <br/> |Primär, fremd  <br/> |Uhrzeit der Konferenz Instanz. Wird in Verbindung mit **SessionIdSeq** verwendet, um eine Konferenz Instanz eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle "Konferenzen" in Skype for Business Server 2015](conferences.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primär, fremd  <br/> |Die ID-Nummer zum Identifizieren der Konferenz Instanz. Wird in Verbindung mit **SessionID** -Mal verwendet, um eine Konferenz Instanz eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle "Konferenzen" in Skype for Business Server 2015](conferences.md) . <br/> |
|**UserID** <br/> |int  <br/> |Primär, fremd  <br/> |Eindeutige Nummer, die diesen Benutzer kennzeichnet. Weitere Informationen finden Sie in der [Tabelle "Benutzer](users.md) ". <br/> |
|**McuUserInstance** <br/> |int  <br/> |Primary  <br/> |Wenn ein Benutzer auf mehreren Computern oder Geräten gleichzeitig angemeldet ist, identifiziert McuUserInstance die Kombination aus Benutzer und Gerät eindeutig.  <br/> |
|**IsFromPstn** <br/> |bit  <br/> | <br/> |Gibt an, ob der Benutzer ein PSTN hat oder nicht.  <br/> |
|**McuId** <br/> |int  <br/> |Primär, fremd  <br/> |Eindeutige Nummer, die diesen Konferenzserver identifiziert. Weitere Informationen finden Sie [in der Tabelle "Tabelle" in Skype for Business Server 2015](mcus.md) . <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Fremd  <br/> |Uhrzeit der Sitzungsanforderung. Wird in Verbindung mit **SessionIdSeq** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Fremd  <br/> |Die ID-Nummer, um die Sitzung zu identifizieren. Wird in Verbindung mit **SessionID** -Mal verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |Der Zeitpunkt, zu dem dieser Benutzer diesem Konferenzserver Beitritt.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |Der Zeitpunkt, zu dem dieser Benutzer diesen Konferenzserver verlässt.  <br/> |
|**ClientVerId** <br/> |int  <br/> |Fremd  <br/> |Bezeichner, der die Versionsnummer der Client Software in der Konferenz angibt. Weitere Informationen finden Sie [in der Tabelle ClientVersions in Skype for Business Server 2015](clientversions.md) . <br/> Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**LastModifiedTime** <br/> |DateTime  <br/> ||Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Skype for Business Server 2015 eingeführt.  <br/> |
   

