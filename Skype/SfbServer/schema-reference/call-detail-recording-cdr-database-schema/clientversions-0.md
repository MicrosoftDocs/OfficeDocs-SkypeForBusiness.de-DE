---
title: ClientVersions-Ansicht
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: ClientVersions-Ansicht speichert Informationen über die verschiedenen Clienttypen und Versionen, die in der Datenbank aufgezeichnet Sitzungen teilgenommen haben. Jeder Datensatz in der Ansicht steht für eine Clientversion. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 0906e35d0912684c9aeb169017b5df0a53202c50
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="clientversions-view"></a>ClientVersions-Ansicht
 
ClientVersions-Ansicht speichert Informationen über die verschiedenen Clienttypen und Versionen, die in der Datenbank aufgezeichnet Sitzungen teilgenommen haben. Jeder Datensatz in der Ansicht steht für eine Clientversion. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
> [!NOTE]
> Möglicherweise gibt es mehrere Datensätze für bestimmte Spalten. 
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**VersionId** <br/> |int  <br/> |Eindeutige Zahl, identifiziert dieser Clienttyp und Version.  <br/> |
|**Version** <br/> |nvarchar(256)  <br/> |Stellt den Benutzer-Agent.  <br/> |
|**Clienttyp** <br/> |int  <br/> |Der Typ des Clients.  <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Kategorie, zu der Client gehört. Der Client Conferencing_Attendant_1.0 beispielsweise die ClientCategory CAA gehört.  <br/> |
   

