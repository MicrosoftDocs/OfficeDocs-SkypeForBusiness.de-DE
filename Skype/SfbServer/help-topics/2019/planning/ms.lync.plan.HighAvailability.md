---
title: High Availability (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
ROBOTS: NOINDEX, NOFOLLOW
description: Das wichtigste Hochverfügbarkeits-Schema für die meisten Serverfunktionen in Skype for Business Server basiert auf Serverredundanz über Pooling. Wenn ein Server ausfällt, auf dem eine bestimmte Serverrolle ausgeführt wird, übernehmen die anderen Server im Pool, auf denen die gleiche Rolle ausgeführt wird, die Last dieses Servers.
ms.openlocfilehash: 2a3327bcf5b17df7bc6eb4880a9966764786560d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34281589"
---
# <a name="high-availability-planning-tool"></a>High Availability (Planning Tool)
 
Das wichtigste Hochverfügbarkeits-Schema für die meisten Serverfunktionen in Skype for Business Server basiert auf Serverredundanz über Pooling. Wenn ein Server ausfällt, auf dem eine bestimmte Serverrolle ausgeführt wird, übernehmen die anderen Server im Pool, auf denen die gleiche Rolle ausgeführt wird, die Last dieses Servers.
  
Für Skype for Business Server sind mindestens zwei Front-End-Server erforderlich, um eine höhere Verfügbarkeit zu ermöglichen. Das Planungs Tool verwendet die folgenden Kriterien, um festzustellen, ob zusätzliche Server hinzugefügt werden, um eine höhere Verfügbarkeit zu unterstützen:
  
- Wenn die Bereitstellung zwei oder mehr Front-End-Server enthält, fügt das Planungs Tool keinen zusätzlichen Server hinzu.
    
- Wenn die Bereitstellung Edge-Server enthält, wird ein zusätzlicher Server hinzugefügt. 
    
- Wenn die Bereitstellung beständigen Chat enthält, wird vom Planungstool ein zusätzlicher Server hinzugefügt, aber nicht die Poolnummer erhöht. Wenn die Bereitstellung beispielsweise bereits vier Server enthält, schlägt das Planungs Tool vor, einen zusätzlichen Server hinzuzufügen (für insgesamt fünf Server), jedoch wird ein einzelner Pool verwaltet. 

    > [!NOTE] 
    > Der beständige Chat ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt. In Teams steht dieselbe Funktionalität zur Verfügung. Weitere Informationen finden Sie unter [Upgrade von Skype for Business zu Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/journey-skypeforbusiness-teams). Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer, die diese Funktion benötigen, an Teams migrieren oder die Verwendung von Skype for Business Server 2015 fortsetzen. 

    
Das Planungs Tool fügt auch eine Spiegel-SQL-Datenbank für alle Datenbanken hinzu. Wenn beispielsweise eine SQL Server-Front-End-Datenbank vorhanden ist, wird das Planungs Tool die andere Datenbank als Spiegeldatenbank für diese hinzufügen und als "Front-End-Spiegelungs-SQL-Datenbank benennen.
  
Weitere Informationen zum Vorbereiten Ihrer Umgebung für eine höhere Verfügbarkeit finden Sie unter [Planen von Höchstverfügbarkeit und Disaster Recovery in Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  

