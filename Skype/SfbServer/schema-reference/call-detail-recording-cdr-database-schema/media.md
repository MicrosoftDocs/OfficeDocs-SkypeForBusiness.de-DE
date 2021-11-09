---
title: Medientabelle
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
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: Jeder Datensatz steht für einen Medientyp, der in einer Peer-zu-Peer-Sitzung verwendet wird. Eine Sitzung wird durch mehrere Datensätze in der Tabelle dargestellt, wenn mehr als ein Medientyp verwendet wird.
ms.openlocfilehash: 02a11f296ec24e9f907927d93bc0fb8acb103b8a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60855219"
---
# <a name="media-table"></a>Medientabelle
 
Jeder Datensatz steht für einen Medientyp, der in einer Peer-zu-Peer-Sitzung verwendet wird. Eine Sitzung wird durch mehrere Datensätze in der Tabelle dargestellt, wenn mehr als ein Medientyp verwendet wird.
  
> [!NOTE]
> Die Media-Tabelle sollte nicht zur Berechnung der Mediendauer für eine Sitzung verwendet werden. Diese Tabelle enthält die Signaldetails für den Austausch von Mediendaten in einer Sitzung. Der Austausch von Mediendaten erfolgt durch die INVITE-Anforderung; "StartTime" gibt den Zeitpunkt an, zu dem die INVITE-Anforderung gesendet wurde. Der INVITE-Zeitpunkt gibt nicht notwendigerweise die Medienstartzeit an, da die Medien erst gestartet werden, nachdem der Sitzungsteilnehmer die Sitzung angenommen hat. "EndTime" bezeichnet in der Regel das Ende der Sitzung. 
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Datum/Uhrzeit  <br/> |Primär, Fremd  <br/> |Zeitpunkt der Sitzungsanforderung. Wird zusammen mit **SessionIdSeq** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie in der [Dialogs-Tabelle in Skype for Business Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primär, Fremd  <br/> |ID zur Identifikation der Sitzung. Wird zusammen mit **SessionIdTime** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie in der [Dialogs-Tabelle in Skype for Business Server 2015.](dialogs.md) <br/> |
|**Mediaid** <br/> |Tinyint  <br/> |Primär, Fremd  <br/> |Eindeutige Zahl, die diesen Medientyp identifiziert. Weitere Informationen finden Sie in der [MediaList-Tabelle.](medialist.md) <br/> |
|**StartTime** <br/> |Datum/Uhrzeit  <br/> |Primary  <br/> |Dies ist der Zeitpunkt, zu dem eine Medienanforderung gesendet wurde, jedoch nicht die tatsächliche Medienstartzeit. **StartTime** schließt die Sitzungseinrichtungszeit mit ein.<br/> |
|**EndTime** <br/> |Datum/Uhrzeit  <br/> ||Bezeichnet das Ende der Sitzung.  <br/> |
   

