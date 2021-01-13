---
title: Datenbankschema für beständigen Chat
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: Dadurch wird das Schema der Datenbank für beständigen Chat in Skype for Business Server dokumentiert.
ms.openlocfilehash: ba50f4391ce35d8a938318e96e1483bbfe0e3dfa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809875"
---
# <a name="persistent-chat-database-schema"></a>Datenbankschema für beständigen Chat
 
Dadurch wird das Schema der Datenbank für beständigen Chat in Skype for Business Server dokumentiert.
  
Die Datenbank für beständigen Chat bezieht sich auf die Datenbank, die den Skype for Business Server-Back-End-Serverrollen **"PersistentChatStore"** (entsprechend der mgc-Datenbank) und **"PersistentChatComplianceStore"** (entsprechend der mgccomp-Datenbank) entspricht. Durch die Veröffentlichung dieses Schemas können Sie Abfragen erstellen und erhalten Einblick in das Erstellen hilfreicher Berichte zur Verwendung der Chatfunktion, zu aktiven Räumen, Benutzern mit den meisten Beiträgen usw.
  
> [!IMPORTANT]
> Wir behalten uns das Recht zur Weiterentwicklung dieses Schemas vor. Microsoft übernimmt keinerlei Garantie für eine dauerhafte vollständige Abwärtskompatibilität mit diesem veröffentlichten Schema. 
  
Halten Sie sich an folgende bewährte Methoden:
  
- Select \* / wird nicht unterstützt, da die Spaltenliste wachsen kann.
    
- Es werden keine benutzergenerierten Schemaänderungen unterstützt.
    
- Auch Schreibvorgänge werden nicht unterstützt.
    
- Testen Sie alle Abfragen, die Sie erstellen, mit Datenbanken ähnlicher Größe, um sicherzustellen, dass die Leistung der Abfragen Ihren Anforderungen entspricht.
    
## <a name="in-this-section"></a>Inhalt dieses Abschnitts

- [Liste der Tabellen für den Server für beständigen Chat](list-of-persistent-chat-server-tables.md)
    
- [Liste der Kompatibilitätstabellen für den Server für beständigen Chat in Skype for Business Server](list-of-persistent-chat-server-compliance-tables.md)
    
- [Ausführliche Informationen zur Tabelle für den Server für beständigen Chat](persistent-chat-server-table-details.md)
    
- [Beispieldatenbankabfragen für beständigen Chat](sample-persistent-chat-database-queries.md)
    

