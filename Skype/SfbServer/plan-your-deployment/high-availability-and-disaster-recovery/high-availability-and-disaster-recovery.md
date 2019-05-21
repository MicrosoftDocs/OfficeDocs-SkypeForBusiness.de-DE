---
title: Planen von Höchstverfügbarkeit und Disaster Recovery in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype for Business Server bietet eine große Verfügbarkeit mit Server-Pooling, Disaster Recovery mit Pool-Kopplung und verschiedenen Modi des Back-End-Servers mit höherer Verfügbarkeit, einschließlich AlwaysOn-Verfügbarkeitsgruppen, Datenbankspiegelung und SQL-Failover-Clustering.
ms.openlocfilehash: 3ed1a3e5eff5d793f835c901e2cc5683da22bc77
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297463"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a>Planen von Höchstverfügbarkeit und Disaster Recovery in Skype for Business Server
 
Skype for Business Server bietet eine große Verfügbarkeit mit Server-Pooling, Disaster Recovery mit Pool-Kopplung und verschiedenen Modi des Back-End-Servers mit höherer Verfügbarkeit, einschließlich AlwaysOn-Verfügbarkeitsgruppen, Datenbankspiegelung und SQL-Failover-Clustering. 
  
Die Höchstverfügbarkeit bezieht sich darauf, sicherzustellen, dass Skype for Business Server-Dienste auch dann verfügbar sind, wenn ein oder mehrere Server ausfällt. Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.
  
Wie in früheren Versionen von lync Server ist die wichtigste Funktion der großen Verfügbarkeit für die meisten Serverfunktionen in Skype for Business Server die Serverredundanz über Pooling. Wenn ein Server in einer bestimmten Serverrolle ausfällt, wird die Last dieses Servers von den anderen Servern im Pool mit der gleichen Rolle übernommen. Dies gilt für Front End- und Edge-Server ebenso wie für Vermittlungsserver und Directors.
  
Skype for Business Server bietet auch Disaster Recovery-Optionen für Front-End-Pools. Sie können zwei Pools in verschiedenen geografischen Bereichen einrichten, die einander als Sicherung dienen. Wenn dann ein gesamter Pool oder Standort ausfällt, kann der Sicherungspool den Benutzern an beiden Standorten weiterhin Dienste bereitstellen.
  
Skype for Business Server unterstützt außerdem vier Modi für die Höchstverfügbarkeit für Ihre Back-End-Server: SQL-Spiegelung, AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failover-Cluster Instanzen (FCI) und SQL-Failover-Clusterunterstützung.
  
> [!NOTE]
> Die SQL-Spiegelung ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt. Die AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failover-Cluster Instanzen (FCI) und SQL-Failover-Clustering-Methoden werden in Skype for Business Server 2019 bevorzugt.

> [!NOTE]
> AlwaysOn-Verfügbarkeitsgruppen werden von beständigen Chat Servern nicht unterstützt. 
  
In diesem Abschnitt werden diese Funktionen erläutert. Zudem wird erklärt, welche Schritte Sie für die hohe Verfügbarkeit und Notfallwiederherstellung für einige Ihrer anderen Serverrollen ausführen können. 
  
  
## <a name="see-also"></a>Siehe auch

[Hohe Verfügbarkeit und Verwaltung von Front-End-Pools](high-availability.md)
  
[Disaster Recovery des Front-End-Pools in Skype for Business Server](disaster-recovery.md)
  
[Benutzerfreundlichkeit während eines Pool Fehlers in Skype for Business Server](user-experience.md)
  
[Verfügbarkeit von Back-End-Servern in Skype for Business Server](back-end-server.md)
  
[Höhere Verfügbarkeit von Dateien in Skype for Business Server](file-sharing.md)
