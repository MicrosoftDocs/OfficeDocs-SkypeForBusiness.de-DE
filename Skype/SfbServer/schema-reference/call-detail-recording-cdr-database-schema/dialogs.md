---
title: Tabelle "Dialogfelder" in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: Die Tabelle Dialogfelder ist eine unterstützende Tabelle, in der die Informationen zu DialogIDs für Peer-to-Peer-Sitzungen gespeichert werden.
ms.openlocfilehash: f6cfc3e078ee8f4492d6f5baf65f66df77d7aedf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815273"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>Tabelle "Dialogfelder" in Skype for Business Server 2015
 
Die Tabelle Dialogfelder ist eine unterstützende Tabelle, in der die Informationen zu DialogIDs für Peer-to-Peer-Sitzungen gespeichert werden.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionID** <br/> |datetime  <br/> |Primary  <br/> |Uhrzeit der Sitzungsanforderung; wird in Verbindung mit SessionIDSeq verwendet, um eine Sitzung eindeutig zu identifizieren.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |Die ID-Nummer, um die Sitzung zu identifizieren. Wird in Verbindung mit SessionID-Mal verwendet, um eine Sitzung eindeutig zu identifizieren.  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |Prüfsumme der externen-Nr. Dieses Feld wird verwendet, um die Geschwindigkeit von Datenbanksuchen zu erhöhen.  <br/> |
|**ExternalId** <br/> |varbinary (775)  <br/> | <br/> |SIP-Dialogfeld-ID, als Binärdatei gespeichert. Das Format der Binärdatei lautet wie folgt:  <br/> Dialogfeld; from-Tag; to-Tag  <br/> Diese Daten können mithilfe der folgenden Syntax in das Text Format konvertiert werden:  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

