---
title: Tool zum Schwenken mit hoher Verfügbarkeit
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: Das Hauptschema für hohe Verfügbarkeit für die meisten Serverrollen in Skype for Business Server 2015 basiert auf Serverredundanz über Pooling. Wenn ein Server mit einer bestimmten Serverrolle fehlschlägt, übernehmen die anderen Server im Pool, auf denen dieselbe Rolle ausgeführt wird, die Last von diesem Server.
ms.openlocfilehash: e8fbc679d4711ae41306a60d6a9c40114fab5f29
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756916"
---
# <a name="high-availability-planning-tool"></a>Planungstool für hohe Verfügbarkeit
 
Das Hauptschema für hohe Verfügbarkeit für die meisten Serverrollen in Skype for Business Server 2015 basiert auf Serverredundanz über Pooling. Wenn ein Server ausfällt, auf dem eine bestimmte Serverrolle ausgeführt wird, übernehmen die anderen Server im Pool, auf denen dieselbe Rolle ausgeführt wird, die Arbeitslast dieses Servers.
  
Skype for Business Server 2015 erfordert mindestens zwei Front-End-Server, um hohe Verfügbarkeit zu ermöglichen. Das Planungstool verwendet die folgenden Kriterien, um zu bestimmen, ob zusätzliche Server hinzugefügt werden, um hohe Verfügbarkeit zu unterstützen:
  
- Wenn die Bereitstellung mindestens zwei Front-End-Server enthält, fügt das Planungstool keinen zusätzlichen Server hinzu.
    
- Wenn die Bereitstellung den Edgeserver enthält, wird ein weiterer Server hinzugefügt. 
    
- Wenn die Bereitstellung den beständigen Chat enthält, fügt das Planungstool einen zusätzlichen Server hinzu, erhöht jedoch nicht die Poolnummer. Wenn die Bereitstellung beispielsweise bereits vier Server enthält, schlägt das Planungstool das Hinzufügen eines anderen Servers (für insgesamt fünf Server) vor, verwaltet jedoch einen einzelnen Pool. 
    
Das Planungstool fügt außerdem eine Spiegeldatenbank SQL für alle Datenbanken hinzu. Wenn beispielsweise eine Front-End-SQL Server-Datenbank vorhanden ist, fügt das Planungstool die andere Datenbank als Spiegeldatenbank für diese Hinzufügedatenbank hinzu und bezeichnet sie als "Front-End-Spiegel SQL Datenbank.
  
Weitere Informationen zur Vorbereitung Ihrer Umgebung auf hohe Verfügbarkeit finden Sie unter [Plan for high availability and disaster recovery in Skype for Business Server 2015.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  

