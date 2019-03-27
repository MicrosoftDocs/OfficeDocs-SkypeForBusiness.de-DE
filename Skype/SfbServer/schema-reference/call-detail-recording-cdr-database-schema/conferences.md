---
title: Conferences-Tabelle in Skype für Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c3da6271-b3c6-4898-894f-10456ec794d0
description: Jeder Datensatz in dieser Tabelle enthält Anrufdetails zu einer Konferenz.
ms.openlocfilehash: f0401c150f3835772ba0df20f8c02c64c9919921
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881953"
---
# <a name="conferences-table-in-skype-for-business-server-2015"></a>Conferences-Tabelle in Skype für Business Server 2015
 
Jeder Datensatz in dieser Tabelle enthält Anrufdetails zu einer Konferenz.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |Uhrzeit, zu die Konferenz Anforderung vom CDR-Agent gesammelt wurde. Nur als Primärschlüssel verwendet, um eine Instanz der Konferenz eindeutig zu identifizieren.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |ID-Nummer, um die Sitzung zu identifizieren. In Verbindung mit **SessionIdTime** verwendet, um eine Instanz der Konferenz eindeutig zu identifizieren. * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Ausländisch  <br/> |Konferenz-URI. [ConferenceUris-Tabelle in Skype für Business Server 2015](conferenceuris.md) Weitere Informationen finden Sie. <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> | <br/> |Nützlich für wiederkehrende Konferenzen. Jede Instanz einer wiederkehrenden Konferenz hat die gleiche **ConferenceUri**, aber es muss eine andere **ConfInstance**. <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> | <br/> |Startzeitpunkt der Konferenz.  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> | <br/> |Startzeitpunkt der Konferenz.  <br/> |
|**PoolId** <br/> |int  <br/> |Ausländisch  <br/> |ID-Nummer, um den Pool zu identifizieren, in dem die Konferenz erfasst wurde. Finden Sie weitere Informationen der [Pools-Tabelle](pools.md) . <br/> |
|**OrganizerId** <br/> |Int  <br/> |Ausländisch  <br/> |ID-Nummer zum Identifizieren des Organisators URI der Konferenz. Finden Sie in der [Tabelle Benutzer](users.md) Weitere Informationen. <br/> |
|**Kennzeichnung** <br/> |smallint  <br/> || Eine Bitmaske, die Konferenz Attribute enthält. Mögliche Werte: <br/>  0 x 01 <br/>  Synthetische <br/>  Transaktion <br/> |
|**Verarbeitet** <br/> |bit  <br/> ||Ein internes Feld vom Überwachungsdienst verwendet.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**ZuletztGeändertUm** <br/> |DateTime  <br/> ||Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Skype für Business Server 2015 eingeführt.  <br/> |
   
\*Für die meisten Sitzungen müssen SessionIdSeq den Wert 1. Wenn zwei Sitzungen gleichzeitig genau, die SessionIdSeq starten, eine 1 werden und für die andere 2, und so weiter.
  

