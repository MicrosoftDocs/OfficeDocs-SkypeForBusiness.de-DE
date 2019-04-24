---
title: FileTransfers-Ansicht
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: Die Ansicht FileTransfer speichert Informationen zu Peer-zu-Peer-dateiübertragungssitzungen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: a39e00becd772e74eb12de1a8ce5975e6626cffa
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213088"
---
# <a name="filetransfers-view"></a>FileTransfers-Ansicht
 
Die Ansicht FileTransfer speichert Informationen zu Peer-zu-Peer-dateiübertragungssitzungen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
> [!NOTE]
> Die FileTransfers-Ansicht enthält alle Spalten in der [SessionDetails-Ansicht](sessiondetails-0.md) außerdem die unten aufgeführten Spalten.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**FileName** <br/> |nvarchar(256)  <br/> |Name der Datei übertragen.  <br/> |
|**Cookie** <br/> |nvarchar(128)  <br/> |Verwendet, um jede Nachricht zur nachverfolgung als wird hiermit zugeordnet zu identifizieren.  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> |Eindeutiger Bezeichner zum unterscheiden zwischen dateiübertragungen mit demselben Namen.  <br/> |
|**Akzeptieren** <br/> |bit  <br/> |TRUE oder NULL kann sein. Wenn TRUE, dann ablehnen, und Abbrechen werden NULL sein.  <br/> |
|**Ablehnen** <br/> |bit  <br/> |TRUE oder NULL kann sein. Bei TRUE wird annehmen und Abbrechen NULL sein.  <br/> |
|**Abbrechen** <br/> |bit  <br/> |TRUE oder NULL kann sein. Bei TRUE wird annehmen und Ablehnen NULL sein.  <br/> |
   

