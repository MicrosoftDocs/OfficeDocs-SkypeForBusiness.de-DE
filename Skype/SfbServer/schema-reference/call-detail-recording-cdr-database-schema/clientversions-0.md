---
title: ClientVersions-Ansicht
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: 'In der ClientVersions-Ansicht werden Informationen zu den verschiedenen Clienttypen und -versionen gespeichert, die an in der Datenbank aufgezeichneten Sitzungen teilgenommen haben. Jeder Datensatz in der Ansicht stellt eine Clientversion dar. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.'
---

# <a name="clientversions-view"></a>ClientVersions-Ansicht
 
In der ClientVersions-Ansicht werden Informationen zu den verschiedenen Clienttypen und -versionen gespeichert, die an in der Datenbank aufgezeichneten Sitzungen teilgenommen haben. Jeder Datensatz in der Ansicht stellt eine Clientversion dar. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
> [!NOTE]
> Für bestimmte Spalten können mehrere Datensätze vorhanden sein. 
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**VersionId** <br/> |int  <br/> |Eindeutige Zahl, die den Clienttyp und die Clientversion identifiziert.  <br/> |
|**Version** <br/> |nvarchar(256)  <br/> |Stellt den Benutzer-Agent dar.  <br/> |
|**ClientType** <br/> |int  <br/> |Typ des Clients.  <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Kategorie, zu der der Client gehört. Beispielsweise gehört der Client Conferencing_Attendant_1.0 zur ClientCategory CAA.  <br/> |
   

