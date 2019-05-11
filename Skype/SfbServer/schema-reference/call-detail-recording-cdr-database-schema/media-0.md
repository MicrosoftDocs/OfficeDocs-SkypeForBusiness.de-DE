---
title: Media-Ansicht
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: Die Medienansicht speichert Informationen über einen Medientyp in einer Peer-zu-Peer-Sitzung verwendet. Eine Sitzung würde durch mehrere Datensätze in der Tabelle dargestellt werden, wenn mehr als eine Medientyp verwendet wird. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 83caf609efae4e97961e7c62c3a1ed6c6004e8e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930693"
---
# <a name="media-view"></a>Media-Ansicht
 
Die Medienansicht speichert Informationen über einen Medientyp in einer Peer-zu-Peer-Sitzung verwendet. Eine Sitzung würde durch mehrere Datensätze in der Tabelle dargestellt werden, wenn mehr als eine Medientyp verwendet wird. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
> [!NOTE]
> Die Medienansicht sollte nicht verwendet werden, um die Dauer Medien für eine Sitzung berechnen. Diese Ansicht enthält die Signalisierung Details der Austausch von Mediendaten in einer Sitzung. Austausch von Mediendaten erfolgt durch die INVITE-Anforderung und StartTime gibt die Zeit an, der die INVITE-Nachricht gesendet wurde. Die Zeit einladen bedeutet nicht unbedingt, dass das Medium Startzeit, da Media gestartet wird, nachdem die Sitzung akzeptiert wird. 
  
Die Medienansicht enthält alle Spalten in der [SessionDetails View](sessiondetails-0.md) außerdem die unten aufgeführten.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**Media** <br/> |nvarchar(256)  <br/> |Medientyp. Finden Sie weitere Informationen die [MediaList-Tabelle](medialist.md) . <br/> |
|**MediaStartTime** <br/> |datetime  <br/> |Uhrzeit, zu der eine medienanforderung gesendet wurde.  <br/> |
|**MediaEndTime** <br/> |datetime  <br/> |Die Endzeit der Sitzung.  <br/> |
   

