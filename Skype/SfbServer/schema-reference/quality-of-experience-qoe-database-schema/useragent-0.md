---
title: UserAgent-Ansicht
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: Die UserAgent-Ansicht speichert Informationen zu den Benutzer-Agents, die an Sitzungen teilgenommen haben, die Datensätze in der Datenbank aufweisen. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: 874a9c986ec77c3e19b557cd65dcf6dbeb045752
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294607"
---
# <a name="useragent-view"></a>UserAgent-Ansicht
 
Die UserAgent-Ansicht speichert Informationen zu den Benutzer-Agents, die an Sitzungen teilgenommen haben, die Datensätze in der Datenbank aufweisen. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |Eindeutige Nummer, die diesen Benutzer-Agent kennzeichnet.  <br/> |
|UserAgent  <br/> |nvarchar(256)  <br/> |Benutzer-Agent-Zeichenfolge.  <br/> |
|UAType  <br/> |smallint  <br/> |Der Typ des Benutzer-Agents. Weitere Informationen finden Sie in der [userAgent-Tabelle](useragent.md) . <br/> |
|UACategory  <br/> |nvarchar (64)  <br/> |Die Kategorie, zu der der Benutzer-Agent gehört. Beispielsweise gehört der Benutzer-Agent conferencing_attendant_ 1.0 zum UACategory CAA.  <br/> |
   

