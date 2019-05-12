---
title: Datenbankschema für beständigen Chat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: In diesem Artikel wird das Schema der Datenbank für beständigen Chat in Skype für Business Server.
ms.openlocfilehash: 5e10f47a7eeb04de08766bae2957773db35d88f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930008"
---
# <a name="persistent-chat-database-schema"></a>Datenbankschema für beständigen Chat
 
In diesem Artikel wird das Schema der Datenbank für beständigen Chat in Skype für Business Server.
  
Datenbank für beständigen Chat bezieht sich auf die Datenbank, die Skype für Business Server Back End-Server-Rollen **PersistentChatStore** (entsprechend der Mgc-Datenbank) und **PersistentChatComplianceStore** entspricht (entsprechend der Mgccomp-Datenbank). Das Ziel der Veröffentlichung von diesem Schemas ist, können Sie Abfragen erstellen und gewinnen Sie einige Einsichten in nützliche reporting um Chat Nutzung, aktiven Chatrooms, oberen Poster usw. erstellen.
  
> [!IMPORTANT]
> Wir behalten uns das Recht, die mit diesem Schema weiterentwickelt. Microsoft ist keine Garantien zum Aufrechterhalten der vollständigen Abwärtskompatibilität mit diesem Schema veröffentlichte stellen. 
  
Führen Sie die folgenden bewährten Methoden:
  
- Wählen Sie keine\* / / wird unterstützt, da die Spaltenliste Wachstum ausgelegt ist.
    
- Keine benutzergenerierten schemaänderungen Änderungen werden unterstützt.
    
- Es werden keine Schreibvorgänge unterstützt.
    
- Testen Sie alle Abfragen, die Sie erstellen Datenbanken ähnlicher Größe, um sicherzustellen, dass die Abfragen auf einer Ebene für Ihre Bedürfnisse ausführen können.
    
## <a name="in-this-section"></a>Inhalt dieses Abschnitts

- [Liste der Tabellen für den Server für beständigen Chat](list-of-persistent-chat-server-tables.md)
    
- [Liste der kompatibilitätstabellen für Persistent Chat Server in Skype für Business Server](list-of-persistent-chat-server-compliance-tables.md)
    
- [Ausführliche Informationen zur Tabelle für den Server für beständigen Chat](persistent-chat-server-table-details.md)
    
- [Beispieldatenbankabfragen für beständigen Chat](sample-persistent-chat-database-queries.md)
    

