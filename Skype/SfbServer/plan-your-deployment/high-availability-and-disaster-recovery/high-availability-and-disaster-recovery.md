---
title: Planen Sie für hohe Verfügbarkeit und Disaster Recovery in Skype für Business Server
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
ms.openlocfilehash: 94db95c097fca62e31a01efd1d254ab6d3cd6d37
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20996459"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a>Planen Sie für hohe Verfügbarkeit und Disaster Recovery in Skype für Business Server
 
Skype für Business Server bietet eine hohe Verfügbarkeit mit pooling Disaster Recovery mit poolpaaren und mehreren Modi für die Back-End-Server hohe Verfügbarkeit, einschließlich AlwaysOn Availability Groups, datenbankspiegelung und Failover-Clusterunterstützung mit SQL Server. 
  
Hoher Verfügbarkeit bezieht sich auf und stellen Sie sicher, dass Skype für Business Server-Dienste verfügbar sind, auch wenn Sie einen oder mehrere Server ausfällt. Für die Notfallwiederherstellung müssen die Dienste auch bei Naturkatastrophen oder von Menschen verursachten Katastrophen aktiv gehalten und so viele Daten wie möglich bewahrt werden.
  
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