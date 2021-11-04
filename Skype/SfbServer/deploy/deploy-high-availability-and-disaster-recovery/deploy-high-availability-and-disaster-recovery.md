---
title: Bereitstellen der hohen Verfügbarkeit und Notfallwiederherstellung
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype for Business Server bietet hohe Verfügbarkeit mit Serverpooling, Notfallwiederherstellung mit Poolkopplung und verschiedene Modi der Back-End-Server-Hochverfügbarkeit, einschließlich AlwaysOn-Verfügbarkeitsgruppen, Datenbankspiegelung und SQL Failoverclustering.
ms.openlocfilehash: 03a7c1e91651f2d73b1e22692f726ed3188588e6
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60761483"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a>Bereitstellen der hohen Verfügbarkeit und Notfallwiederherstellung
 
Skype for Business Server bietet hohe Verfügbarkeit mit Serverpooling, Notfallwiederherstellung mit Poolkopplung und verschiedene Modi der Back-End-Server-Hochverfügbarkeit, einschließlich AlwaysOn-Verfügbarkeitsgruppen, Datenbankspiegelung und SQL Failoverclustering. 
  
Hohe Verfügbarkeit bezieht sich darauf, sicherzustellen, dass Skype for Business Server Dienste auch dann verfügbar sind, wenn mindestens ein Server ausfällt. Die Notfallwiederherstellung bezieht sich auf die Beibehaltung von Diensten im Falle einer natürlichen oder vom Menschen verursachten Notfalls und die Beibehaltung so vieler Daten vor dem Notfall wie möglich.
  
In diesem Abschnitt wird erläutert, wie diese Features bereitgestellt werden, und es wird erläutert, welche Schritte Sie für hohe Verfügbarkeit und Notfallwiederherstellung für einige Ihrer anderen Serverrollen ausführen können.

> [!NOTE]
> SQL Spiegelung ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die Methoden AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failoverclusterinstanzen (FCI) und SQL Failoverclustering werden mit Skype for Business Server 2019 bevorzugt.
  
## <a name="related-sections"></a>Verwandte Abschnitte

[Planen der hohen Verfügbarkeit und Notfallwiederherstellung in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a>Weitere Informationen

[Bereitstellen einer AlwaysOn-Verfügbarkeitsgruppe auf einem Back-End-Server in Skype for Business Server](alwayson-availability-group.md)

[Bereitstellen von front-End-Paarpools für die Notfallwiederherstellung in Skype for Business Server](front-end-pools-for-disaster-recovery.md)
  
[Bereitstellen SQL Spiegelung für hohe Verfügbarkeit von Back-End-Servern in Skype for Business Server 2015](sql-mirroring-for-high-availability.md)
  
