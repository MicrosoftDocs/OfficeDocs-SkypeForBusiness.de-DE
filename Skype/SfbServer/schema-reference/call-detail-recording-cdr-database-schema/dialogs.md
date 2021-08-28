---
title: Dialogs-Tabelle in Skype for Business Server 2015
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
ms.localizationpriority: medium
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: Die Dialogs-Tabelle ist eine Unterstützende Tabelle, in der die Informationen zu DialogIDs für Peer-to-Peer-Sitzungen gespeichert werden.
ms.openlocfilehash: 6f5abd6326ca1f00a631462c43c8814fb3822f41
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580429"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>Dialogs-Tabelle in Skype for Business Server 2015
 
Die Dialogs-Tabelle ist eine Unterstützende Tabelle, in der die Informationen zu DialogIDs für Peer-to-Peer-Sitzungen gespeichert werden.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Datum/Uhrzeit  <br/> |Primary  <br/> |Zeitpunkt der Sitzungsanforderung; wird in Verbindung mit SessionIDSeq verwendet, um eine Sitzung eindeutig zu identifizieren.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |ID zur Identifikation der Sitzung. Wird in Verbindung mit SessionIDTime verwendet, um eine Sitzung eindeutig zu identifizieren.  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |Prüfsumme der ExternalID. Dieses Feld wird verwendet, um die Geschwindigkeit der Datenbanksuchen zu erhöhen.  <br/> |
|**ExternalId** <br/> |varbinary(775)  <br/> | <br/> |SIP-Dialog-ID, gespeichert als Binärdatei. Das Format der Binärdatei lautet:  <br/> dialog;from-tag;to-tag  <br/> Diese Daten können mithilfe der folgenden Syntax in das Textformat konvertiert werden:  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

