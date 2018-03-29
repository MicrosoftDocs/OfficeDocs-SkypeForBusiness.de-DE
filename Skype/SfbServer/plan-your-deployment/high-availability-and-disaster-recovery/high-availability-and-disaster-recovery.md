---
title: Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 1/29/2018
ms.audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype für Business Server bietet eine hohe Verfügbarkeit mit pooling Disaster Recovery mit poolpaaren und mehreren Modi für die Back-End-Server hohe Verfügbarkeit, einschließlich AlwaysOn Availability Groups, datenbankspiegelung und Failover-Clusterunterstützung mit SQL Server.
ms.openlocfilehash: e2e433112146e3be771abb12ef50e09749e8e325
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server-2015"></a>Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in Skype for Business Server 2015
 
Skype für Business Server bietet eine hohe Verfügbarkeit mit pooling Disaster Recovery mit poolpaaren und mehreren Modi für die Back-End-Server hohe Verfügbarkeit, einschließlich AlwaysOn Availability Groups, datenbankspiegelung und Failover-Clusterunterstützung mit SQL Server. 
  
Hoher Verfügbarkeit bezieht sich auf und stellen Sie sicher, dass Skype für Business Server-Dienste verfügbar sind, auch wenn Sie einen oder mehrere Server ausfällt. Für die Notfallwiederherstellung müssen die Dienste auch bei Naturkatastrophen oder von Menschen verursachten Katastrophen aktiv gehalten und so viele Daten wie möglich bewahrt werden.
  
Wie in früheren Versionen von Lync Server ist das Hauptfenster hohe Verfügbarkeit-Feature für die meisten Serverrollen in Skype für Business Server Serverredundanz über pooling. Wenn ein Server in einer bestimmten Serverrolle ausfällt, wird die Last dieses Servers von den anderen Servern im Pool mit der gleichen Rolle übernommen. Dies gilt für Front End- und Edge-Server ebenso wie für Vermittlungsserver und Directors.
  
Skype für Business Server bietet auch Disaster Recovery-Optionen für Front-End-Pools. Sie können zwei Pools in verschiedenen geografischen Bereichen einrichten, die einander als Sicherung dienen. Wenn dann ein gesamter Pool oder Standort ausfällt, kann der Sicherungspool den Benutzern an beiden Standorten weiterhin Dienste bereitstellen.
  
Unterstützt Skype für Business Server auch Kommunikationsmodi hohe Verfügbarkeit für die Back-End-Server: Database mirroring, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instanzen (FCI) und SQL-Failover-Clusterunterstützung.
  
> [!NOTE]
> AlwaysOn Availability Groups werden für Persistent Chatserver nicht unterstützt. 
  
In diesem Abschnitt werden diese Features erläutert, und welche Schritte Sie für hohe Verfügbarkeit und Disaster Recovery für die anderen Serverrollen einiger annehmen können auch behandelt. 
  
## <a name="see-also"></a>Siehe auch

#### 

[Front-End-Pool hohe Verfügbarkeit und Verwaltung](high-availability.md)
  
[Front-End-Pool Disaster Recovery in Skype für Business Server 2015](disaster-recovery.md)
  
[Benutzerfreundlichkeit während des Ausfalls eines Pools in Skype für Business Server 2015](user-experience.md)
  
[Back-End-Server hohe Verfügbarkeit in Skype für Business Server 2015](back-end-server.md)
  
[Hohen Verfügbarkeit in Skype-Dateifreigabe für Business Server 2015](file-sharing.md)

