---
title: Planen Sie für hohe Verfügbarkeit und Disaster Recovery in Skype für Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype für Business Server bietet eine hohe Verfügbarkeit mit pooling Disaster Recovery mit poolpaaren und mehreren Modi für die Back-End-Server hohe Verfügbarkeit, einschließlich AlwaysOn Availability Groups, datenbankspiegelung und Failover-Clusterunterstützung mit SQL Server.
ms.openlocfilehash: 9e48fa65572dea5c0e6a297397d2a502cefcdc36
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875257"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a>Planen Sie für hohe Verfügbarkeit und Disaster Recovery in Skype für Business Server
 
Skype für Business Server bietet eine hohe Verfügbarkeit mit pooling Disaster Recovery mit poolpaaren und mehreren Modi für die Back-End-Server hohe Verfügbarkeit, einschließlich AlwaysOn Availability Groups, datenbankspiegelung und Failover-Clusterunterstützung mit SQL Server. 
  
Hoher Verfügbarkeit bezieht sich auf und stellen Sie sicher, dass Skype für Business Server-Dienste verfügbar sind, auch wenn Sie einen oder mehrere Server ausfällt. Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.
  
Wie in früheren Versionen von Lync Server ist das Hauptfenster hohe Verfügbarkeit-Feature für die meisten Serverrollen in Skype für Business Server Serverredundanz über pooling. Wenn ein Server in einer bestimmten Serverrolle ausfällt, wird die Last dieses Servers von den anderen Servern im Pool mit der gleichen Rolle übernommen. Dies gilt für Front End- und Edge-Server ebenso wie für Vermittlungsserver und Directors.
  
Skype für Business Server bietet auch Disaster Recovery-Optionen für Front-End-Pools. Sie können zwei Pools in verschiedenen geografischen Bereichen einrichten, die einander als Sicherung dienen. Wenn dann ein gesamter Pool oder Standort ausfällt, kann der Sicherungspool den Benutzern an beiden Standorten weiterhin Dienste bereitstellen.
  
Unterstützt Skype für Business Server auch Kommunikationsmodi hohe Verfügbarkeit für die Back-End-Server: SQL-Spiegelung, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instanzen (FCI) und SQL-Failover-Clusterunterstützung.
  
> [!NOTE]
> SQL-Spiegelung wird steht in Skype für Business Server 2015 jedoch nicht mehr in unterstützt Skype für Business Server 2019. Die AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instanzen (FCI) und SQL clustering Failovermethoden werden bevorzugt mit Skype für Business Server 2019.

> [!NOTE]
> AlwaysOn Availability Groups werden für Persistent Chatserver nicht unterstützt. 
  
In diesem Abschnitt werden diese Funktionen erläutert. Zudem wird erklärt, welche Schritte Sie für die hohe Verfügbarkeit und Notfallwiederherstellung für einige Ihrer anderen Serverrollen ausführen können. 
  
  
## <a name="see-also"></a>Siehe auch

[Hohe Verfügbarkeit und Verwaltung von Front-End-Pools](high-availability.md)
  
[Front-End-Pool Disaster Recovery in Skype für Business Server](disaster-recovery.md)
  
[Benutzerfreundlichkeit während des Ausfalls eines Pools in Skype für Business Server](user-experience.md)
  
[Back-End-Server hohe Verfügbarkeit in Skype für Business Server](back-end-server.md)
  
[Hohen Verfügbarkeit in Skype-Dateifreigabe für Business Server](file-sharing.md)
