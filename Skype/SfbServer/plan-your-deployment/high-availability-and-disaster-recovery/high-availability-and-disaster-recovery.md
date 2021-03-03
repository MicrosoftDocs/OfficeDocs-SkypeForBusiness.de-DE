---
title: Planen von hoher Verfügbarkeit und Notfallwiederherstellung in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.custom:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype for Business Server bietet hohe Verfügbarkeit mit Serverpooling, Notfallwiederherstellung mit Poolpaarung und mehreren Modi der hohen Verfügbarkeit von Back-End-Servern, einschließlich AlwaysOn-Verfügbarkeitsgruppen, Datenbankspiegelung und SQL Failoverclustering.
ms.openlocfilehash: 61b720bc9dce5bc8dc54a6c493429b0a3c9b27d2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802815"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a>Planen von hoher Verfügbarkeit und Notfallwiederherstellung in Skype for Business Server
 
Skype for Business Server bietet hohe Verfügbarkeit mit Serverpooling, Notfallwiederherstellung mit Poolpaarung und mehreren Modi der hohen Verfügbarkeit von Back-End-Servern, einschließlich AlwaysOn-Verfügbarkeitsgruppen, Datenbankspiegelung und SQL Failoverclustering. 
  
Hohe Verfügbarkeit bezieht sich darauf, sicherzustellen, dass Skype for Business Server-Dienste auch dann verfügbar sind, wenn ein oder mehrere Server aus dem Betrieb gehen. Die Notfallwiederherstellung bezieht sich auf das Beibehalten von Diensten im Falle einer natürlichen oder vom Menschen verursachten Notfalls und das Beibehalten so viel Daten wie möglich vor der Notfallwiederherstellung.
  
Wie in früheren Versionen von Lync Server ist die Hauptfunktion für hohe Verfügbarkeit für die meisten Serverrollen in Skype for Business Server die Serverredundanz über Pooling. Wenn ein Server ausfällt, auf dem eine bestimmte Serverrolle ausgeführt wird, übernehmen die anderen Server im Pool, auf denen dieselbe Rolle ausgeführt wird, die Arbeitslast dieses Servers. Dies gilt für Front-End-Server, Edgeserver, Vermittlungsserver und Directors.
  
Skype for Business Server bietet auch Notfallwiederherstellungsoptionen für Front-End-Pools. Sie können zwei Pools in unterschiedlichen geografischen Bereichen einrichten, die als Sicherungen füreinander dienen. Wenn dann ein ganzer Pool oder Standort aus ist, kann der Sicherungspool weiterhin Dienste für Benutzer an beiden Standorten bereitstellen.
  
Skype for Business Server unterstützt außerdem vier Modi für hohe Verfügbarkeit für Ihre Back-End-Server: SQL-Spiegelung, AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failoverclusterinstanzen (FCI) und SQL Failoverclustering.
  
> [!NOTE]
> SQL Spiegelung ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt. Die Methoden für AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failoverclusterinstanzen (FCI) und SQL-Failoverclustering werden mit Skype for Business Server 2019 bevorzugt.

> [!NOTE]
> AlwaysOn-Verfügbarkeitsgruppen werden von Servern für beständigen Chat nicht unterstützt. 
  
In diesem Abschnitt werden diese Features erläutert, und außerdem werden die Schritte erläutert, die Sie für hohe Verfügbarkeit und Notfallwiederherstellung für einige Ihrer anderen Serverrollen ausführen können. 
  
## <a name="see-also"></a>Weitere Informationen

[Hohe Verfügbarkeit und Verwaltung von Front-End-Pools](high-availability.md)
  
[Notfallwiederherstellung für Front-End-Pools in Skype for Business Server](disaster-recovery.md)
  
[Benutzerfreundlichkeit bei Poolfehlern in Skype for Business Server](user-experience.md)
  
[Hohe Verfügbarkeit von Back-End-Servern in Skype for Business Server](back-end-server.md)
  
[Hohe Verfügbarkeit der Dateifreigabe in Skype for Business Server](file-sharing.md)
