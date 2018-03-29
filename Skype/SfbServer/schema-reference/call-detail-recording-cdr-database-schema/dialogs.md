---
title: Dialogs-Tabelle in Skype für Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: Dialogs-Tabelle ist eine unterstützende Tabelle, die Informationen über DialogIDs für Peer-zu-Peer-Sitzungen gespeichert.
ms.openlocfilehash: b2953ff2bec35575221bc0d43785eb6c0d90e2d1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>Dialogs-Tabelle in Skype für Business Server 2015
 
Dialogs-Tabelle ist eine unterstützende Tabelle, die Informationen über DialogIDs für Peer-zu-Peer-Sitzungen gespeichert.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |Zeitpunkt der sitzungsanforderung; zusammen mit SessionIDSeq verwendet zur eindeutigen Identifizierung eine Sitzung.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |ID-Nummer, um die Sitzung zu identifizieren. In Verbindung mit SessionIDTime verwendet, um eine Sitzung eindeutig zu identifizieren.  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |Prüfsumme der ExternalID. Dieses Feld wird verwendet, um die Datenbank Suchvorgänge zu beschleunigen.  <br/> |
|**ExternalId** <br/> |varbinary(775)  <br/> | <br/> |SIP-Dialog-ID als binäre gespeichert. Das Format der Binärdatei ist:  <br/> Dialogfeld; aus Tag; -tag  <br/> Diese Daten können mithilfe der folgenden Syntax in das Textformat konvertiert werden:  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

