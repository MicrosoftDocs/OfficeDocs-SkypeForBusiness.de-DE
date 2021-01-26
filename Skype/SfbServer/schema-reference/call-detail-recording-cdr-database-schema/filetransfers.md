---
title: Ansicht "FileTransfers"
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
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: In der Ansicht "FileTransfer" werden Informationen zu Peer-zu-Peer-Dateiübertragungssitzungen gespeichert. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 8b3c2db012b8969bd4b5b75ca19ed090f8227c53
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821685"
---
# <a name="filetransfers-view"></a>Ansicht "FileTransfers"
 
In der Ansicht "FileTransfer" werden Informationen zu Peer-zu-Peer-Dateiübertragungssitzungen gespeichert. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
> [!NOTE]
> Die Ansicht "FileTransfers" enthält zusätzlich zu den unten aufgeführten Spalten alle Spalten in der Ansicht ["SessionDetails".](sessiondetails-0.md)
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**FileName** <br/> |nvarchar(256)  <br/> |Name der übertragenen Datei.  <br/> |
|**Cookie** <br/> |nvarchar(128)  <br/> |Wird verwendet, um jede Nachricht zur Nachverfolgung als hiermit zugeordnet zu identifizieren.  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> |Eindeutiger Bezeichner zum Unterscheiden zwischen Dateiübertragungen mit demselben Dateinamen.  <br/> |
|**Accept** <br/> |bit  <br/> |Kann TRUE oder NULL sein. Falls TRUE erhalten Reject und Cancel den Wert NULL.  <br/> |
|**Reject** <br/> |bit  <br/> |Kann TRUE oder NULL sein. Falls TRUE erhalten Accept und Cancel den Wert NULL.  <br/> |
|**Cancel** <br/> |bit  <br/> |Kann TRUE oder NULL sein. Falls TRUE erhalten Accept und Reject den Wert NULL.  <br/> |
   

