---
title: High Availability (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: Das wichtigste Hochverfügbarkeits-Schema für die meisten Serverfunktionen in Skype for Business Server 2015 basiert auf Serverredundanz über Pooling. Wenn ein Server ausfällt, auf dem eine bestimmte Serverrolle ausgeführt wird, übernehmen die anderen Server im Pool, auf denen die gleiche Rolle ausgeführt wird, die Last dieses Servers.
ms.openlocfilehash: 740c12439683fcefccaef11358a8cb65a4fae65a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279158"
---
# <a name="high-availability-planning-tool"></a>High Availability (Planning Tool)
 
Das wichtigste Hochverfügbarkeits-Schema für die meisten Serverfunktionen in Skype for Business Server 2015 basiert auf Serverredundanz über Pooling. Wenn ein Server ausfällt, auf dem eine bestimmte Serverrolle ausgeführt wird, übernehmen die anderen Server im Pool, auf denen die gleiche Rolle ausgeführt wird, die Last dieses Servers.
  
Für Skype for Business Server 2015 sind mindestens zwei Front-End-Server erforderlich, um eine höhere Verfügbarkeit zu ermöglichen. Das Planungs Tool verwendet die folgenden Kriterien, um festzustellen, ob zusätzliche Server hinzugefügt werden, um eine höhere Verfügbarkeit zu unterstützen:
  
- Wenn die Bereitstellung zwei oder mehr Front-End-Server enthält, fügt das Planungs Tool keinen zusätzlichen Server hinzu.
    
- Wenn die Bereitstellung Edge-Server enthält, wird ein zusätzlicher Server hinzugefügt. 
    
- Wenn die Bereitstellung beständigen Chat enthält, wird vom Planungstool ein zusätzlicher Server hinzugefügt, aber nicht die Poolnummer erhöht. Wenn die Bereitstellung beispielsweise bereits vier Server enthält, schlägt das Planungs Tool vor, einen zusätzlichen Server hinzuzufügen (für insgesamt fünf Server), jedoch wird ein einzelner Pool verwaltet. 
    
Das Planungs Tool fügt auch eine Spiegel-SQL-Datenbank für alle Datenbanken hinzu. Wenn beispielsweise eine SQL Server-Front-End-Datenbank vorhanden ist, wird das Planungs Tool die andere Datenbank als Spiegeldatenbank für diese hinzufügen und als "Front-End-Spiegelungs-SQL-Datenbank benennen.
  
Weitere Informationen zum Vorbereiten Ihrer Umgebung für eine höhere Verfügbarkeit finden Sie unter [Planen von höchst Verfügbarkeit und Disaster Recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  

