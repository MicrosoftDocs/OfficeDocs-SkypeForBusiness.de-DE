---
title: FileTransfers-Ansicht
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
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: In der FileTransfer-Ansicht werden Informationen zu Peer-to-Peer-Dateiübertragungssitzungen gespeichert. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: eae94d0220cb3443e90665d420b888e86a37d11a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60850638"
---
# <a name="filetransfers-view"></a>FileTransfers-Ansicht
 
In der FileTransfer-Ansicht werden Informationen zu Peer-to-Peer-Dateiübertragungssitzungen gespeichert. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
> [!NOTE]
> Die FileTransfers-Ansicht enthält zusätzlich zu den unten aufgeführten Spalten alle Spalten in der [SessionDetails-Ansicht.](sessiondetails-0.md)
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**FileName** <br/> |nvarchar(256)  <br/> |Name der übertragenen Datei.  <br/> |
|**Cookie** <br/> |nvarchar(128)  <br/> |Wird verwendet, um jede Nachricht zur Nachverfolgung als hiermit zugeordnet zu identifizieren.  <br/> |
|**FileIdentity** <br/> |Uniqueidentifier  <br/> |Eindeutiger Bezeichner zum Unterscheiden zwischen Dateiübertragungen mit demselben Dateinamen.  <br/> |
|**Accept** <br/> |Bit  <br/> |Kann TRUE oder NULL sein. Falls TRUE erhalten Reject und Cancel den Wert NULL.  <br/> |
|**Reject** <br/> |Bit  <br/> |Kann TRUE oder NULL sein. Falls TRUE erhalten Accept und Cancel den Wert NULL.  <br/> |
|**Cancel** <br/> |Bit  <br/> |Kann TRUE oder NULL sein. Falls TRUE erhalten Accept und Reject den Wert NULL.  <br/> |
   

