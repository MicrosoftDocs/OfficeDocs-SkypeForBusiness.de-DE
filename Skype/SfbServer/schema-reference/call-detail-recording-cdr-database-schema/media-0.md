---
title: Medienansicht
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
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: In der Medienansicht werden Informationen zu einem in einer Peer-zu-Peer-Sitzung verwendeten Medientyp gespeichert. Eine Sitzung wird durch mehrere Datensätze in der Tabelle dargestellt, wenn mehr als ein Medientyp verwendet wird. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 77c22246056a28cdb41a007ac0d7e2617fa00ad9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831787"
---
# <a name="media-view"></a>Medienansicht
 
In der Medienansicht werden Informationen zu einem in einer Peer-zu-Peer-Sitzung verwendeten Medientyp gespeichert. Eine Sitzung wird durch mehrere Datensätze in der Tabelle dargestellt, wenn mehr als ein Medientyp verwendet wird. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
> [!NOTE]
> Die Medienansicht sollte nicht zur Berechnung der Mediendauer für eine Sitzung verwendet werden. Diese Ansicht enthält die Signaldetails für den Austausch von Mediendaten in einem Anruf. Der Austausch von Mediendaten erfolgt durch die INVITE-Anforderung; StartTime gibt den Zeitpunkt an, zu dem die INVITE-Anforderung gesendet wurde. Der INVITE-Zeitpunkt gibt nicht notwendigerweise die Medienstartzeit an, da die Medien erst gestartet werden, nachdem die Sitzung angenommen wurde. 
  
Die Medienansicht enthält zusätzlich zu den unten aufgeführten Spalten alle Spalten in der Ansicht ["SessionDetails".](sessiondetails-0.md)
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**Medien** <br/> |nvarchar(256)  <br/> |Medientyp. Weitere Informationen [finden Sie in der Tabelle "MediaList".](medialist.md) <br/> |
|**MediaStartTime** <br/> |Datum/Uhrzeit  <br/> |Uhrzeit, zu der eine Medienanforderung gesendet wurde.  <br/> |
|**MediaEndTime** <br/> |Datum/Uhrzeit  <br/> |Sitzungsende.  <br/> |
   

