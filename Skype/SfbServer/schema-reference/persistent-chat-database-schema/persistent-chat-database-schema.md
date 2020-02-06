---
title: Datenbankschema für beständigen Chat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: b042f4490648760f4750e45fa1e35e032a8bf8b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814743"
---
# <a name="persistent-chat-database-schema"></a>Datenbankschema für beständigen Chat
 
Dadurch wird das Schema der Datenbank für beständigen Chat in Skype for Business Server dokumentiert.
  
Die persistent-Chat-Datenbank bezieht sich auf die Datenbank, die den Skype for Business Server-Back-End-Serverrollen **PersistentChatStore** (entsprechend der MGC-Datenbank) und **PersistentChatComplianceStore** (entsprechend der mgccomp-Datenbank) entspricht. Das Ziel der Veröffentlichung dieses Schemas ist es, Ihnen zu ermöglichen, Abfragen zu erstellen und einige Einblicke in das Erstellen nützlicher Berichte rund um die Chat-Nutzung, in Active rooms, in Top-Poster usw. zu erhalten.
  
> [!IMPORTANT]
> Wir behalten uns das Recht vor, dieses Schema weiterzuentwickeln. Microsoft übernimmt keine Garantien, um die vollständige Abwärtskompatibilität mit diesem veröffentlichten Schema zu gewährleisten. 
  
Befolgen Sie diese bewährten Methoden:
  
- Es wird\* keine SELECT//-Auswahl unterstützt, da die Spaltenliste vergrößert werden kann.
    
- Es werden keine vom benutzergenerierten Schemaänderungen unterstützt.
    
- Es werden keine Schreibvorgänge unterstützt.
    
- Testen Sie alle Abfragen, die Sie auf repräsentativ sortierten Datenbankenerstellen, um sicherzustellen, dass die Abfragen auf einer Ebene ausgeführt werden können, um Ihre Anforderungen zu erfüllen.
    
## <a name="in-this-section"></a>Inhalt dieses Abschnitts

- [Liste der Tabellen für den Server für beständigen Chat](list-of-persistent-chat-server-tables.md)
    
- [Liste der beständigen Chat Server-Kompatibilitätstabellen in Skype for Business Server](list-of-persistent-chat-server-compliance-tables.md)
    
- [Ausführliche Informationen zur Tabelle für den Server für beständigen Chat](persistent-chat-server-table-details.md)
    
- [Beispieldatenbankabfragen für beständigen Chat](sample-persistent-chat-database-queries.md)
    

