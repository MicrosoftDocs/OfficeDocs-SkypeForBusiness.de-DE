---
title: Bereitstellen der hohen Verfügbarkeit und Notfallwiederherstellung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype for Business Server bietet eine große Verfügbarkeit mit Server-Pooling, Disaster Recovery mit Pool-Kopplung und verschiedenen Modi des Back-End-Servers mit höherer Verfügbarkeit, einschließlich AlwaysOn-Verfügbarkeitsgruppen, Datenbankspiegelung und SQL-Failover-Clustering.
ms.openlocfilehash: 68c6a12f80ac2d915c678f69146d0001daedbe5c
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790123"
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
  
