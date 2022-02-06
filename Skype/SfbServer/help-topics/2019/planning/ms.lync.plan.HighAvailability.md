---
title: Hochverfügbarkeit (Planungstool)
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.plan.HighAvailability
  - ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
ROBOTS: 'NOINDEX, NOFOLLOW'
description: 'Das Hauptschema für hohe Verfügbarkeit für die meisten Serverrollen in Skype for Business Server basiert auf Serverredundanz über Pooling. Wenn ein Server ausfällt, auf dem eine bestimmte Serverrolle ausgeführt wird, übernehmen die anderen Server im Pool, auf denen dieselbe Rolle ausgeführt wird, die Arbeitslast dieses Servers.'
---

# <a name="high-availability-planning-tool"></a>Hochverfügbarkeit (Planungstool)
 
Das Hauptschema für hohe Verfügbarkeit für die meisten Serverrollen in Skype for Business Server basiert auf Serverredundanz über Pooling. Wenn ein Server ausfällt, auf dem eine bestimmte Serverrolle ausgeführt wird, übernehmen die anderen Server im Pool, auf denen dieselbe Rolle ausgeführt wird, die Arbeitslast dieses Servers.
  
Skype for Business Server erfordert mindestens zwei Front-End-Server, um hohe Verfügbarkeit zu ermöglichen. Das Planungstool verwendet die folgenden Kriterien, um zu bestimmen, ob zusätzliche Server hinzugefügt werden, um hohe Verfügbarkeit zu unterstützen:
  
- Wenn die Bereitstellung zwei oder mehr Front-End-Server enthält, fügt das Planungstool keinen zusätzlichen Server hinzu.
    
- Wenn die Bereitstellung edgeserver enthält, wird ein zusätzlicher Server hinzugefügt. 
    
- Wenn die Bereitstellung den beständigen Chat enthält, fügt das Planungstool einen zusätzlichen Server hinzu, erhöht jedoch nicht die Poolnummer. Wenn die Bereitstellung beispielsweise bereits vier Server enthält, schlägt das Planungstool das Hinzufügen eines zusätzlichen Servers (für insgesamt fünf Server) vor, verwaltet jedoch einen einzelnen Pool. 

    > [!NOTE] 
    > Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Skype for Business zum Microsoft Teams Upgrade](/MicrosoftTeams/upgrade-start-here). Wenn Sie beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität benötigen, Teams oder Skype for Business Server 2015 weiterhin verwenden. 

    
Das Planungstool fügt auch eine Spiegeldatenbank SQL für alle Datenbanken hinzu. Wenn z. B. eine Front-End-SQL Server-Datenbank vorhanden ist, fügt das Planungstool die andere Datenbank als Spiegeldatenbank für diese hinzu und bezeichnet sie als "Front-End-Spiegel SQL Datenbank.
  
Weitere Informationen zur Vorbereitung Ihrer Umgebung auf hohe Verfügbarkeit finden Sie unter [Plan for high availability and disaster recovery in Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
