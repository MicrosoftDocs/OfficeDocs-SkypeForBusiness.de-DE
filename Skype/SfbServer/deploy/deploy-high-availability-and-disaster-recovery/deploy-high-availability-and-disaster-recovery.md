---
title: Bereitstellen der hohen Verfügbarkeit und Notfallwiederherstellung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype for Business Server bietet eine große Verfügbarkeit mit Server-Pooling, Disaster Recovery mit Pool-Kopplung und verschiedenen Modi des Back-End-Servers mit höherer Verfügbarkeit, einschließlich AlwaysOn-Verfügbarkeitsgruppen, Datenbankspiegelung und SQL-Failover-Clustering.
ms.openlocfilehash: 7997f71fb1f45801436caa50c4d6b258cc1b843b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306678"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a>Bereitstellen der hohen Verfügbarkeit und Notfallwiederherstellung
 
Skype for Business Server bietet eine große Verfügbarkeit mit Server-Pooling, Disaster Recovery mit Pool-Kopplung und verschiedenen Modi des Back-End-Servers mit höherer Verfügbarkeit, einschließlich AlwaysOn-Verfügbarkeitsgruppen, Datenbankspiegelung und SQL-Failover-Clustering. 
  
Die Höchstverfügbarkeit bezieht sich darauf, sicherzustellen, dass Skype for Business Server-Dienste auch dann verfügbar sind, wenn ein oder mehrere Server ausfällt. Disaster Recovery bezieht sich auf die Beibehaltung der Dienste, die im Fall eines natürlichen oder von Menschen verursachten notfalls durchgeführt werden, und so viele Daten wie möglich vor dem Notfall zu erhalten.
  
In diesem Abschnitt wird erläutert, wie Sie diese Funktionen bereitstellen. Außerdem erfahren Sie, welche Schritte Sie für die hohe Verfügbarkeit und Notfallwiederherstellung für einige Ihrer anderen Serverrollen ausführen können.

> [!NOTE]
> Die SQL-Spiegelung ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt. Die AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failover-Cluster Instanzen (FCI) und SQL-Failover-Clustering-Methoden werden in Skype for Business Server 2019 bevorzugt.
  
## <a name="related-sections"></a>Verwandte Abschnitte

[Planen von Höchstverfügbarkeit und Disaster Recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a>Siehe auch

[Bereitstelleneiner AlwaysOn-verfügbarkeitsgruppe auf einem Back-End-Server in Skype for Business Server](alwayson-availability-group.md)

[Bereitstellen gekoppelter Front-End-Pools für Disaster Recovery in Skype for Business Server](front-end-pools-for-disaster-recovery.md)
  
[Bereitstellen der SQL-Spiegelung für hohe Verfügbarkeit von Back-End-Servern in Skype for Business Server 2015](sql-mirroring-for-high-availability.md)
  
