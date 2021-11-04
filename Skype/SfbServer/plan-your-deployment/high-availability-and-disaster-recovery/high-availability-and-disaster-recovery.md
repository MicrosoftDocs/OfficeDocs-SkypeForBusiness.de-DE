---
title: Planen der hohen Verfügbarkeit und Notfallwiederherstellung in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.custom:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype for Business Server bietet hohe Verfügbarkeit mit Serverpooling, Notfallwiederherstellung mit Poolkopplung und verschiedene Modi der Hohen Verfügbarkeit von Back-End-Servern, einschließlich AlwaysOn-Verfügbarkeitsgruppen, Datenbankspiegelung und SQL Failoverclustering.
ms.openlocfilehash: f9834c52a563282afe6db6ce91cf7e5fa0456480
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756512"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a>Planen der hohen Verfügbarkeit und Notfallwiederherstellung in Skype for Business Server
 
Skype for Business Server bietet hohe Verfügbarkeit mit Serverpooling, Notfallwiederherstellung mit Poolkopplung und verschiedene Modi der Hohen Verfügbarkeit von Back-End-Servern, einschließlich AlwaysOn-Verfügbarkeitsgruppen, Datenbankspiegelung und SQL Failoverclustering. 
  
Hohe Verfügbarkeit bedeutet, sicherzustellen, dass Skype for Business Server Dienste auch dann verfügbar sind, wenn mindestens ein Server ausgefallen ist. Die Notfallwiederherstellung bezieht sich auf die Beibehaltung von Diensten im Falle einer natürlichen oder vom Menschen verursachten Notfalls und die Beibehaltung so vieler Daten vor dem Notfall wie möglich.
  
Wie in früheren Versionen von Lync Server ist die Hauptfunktion für hohe Verfügbarkeit für die meisten Serverrollen in Skype for Business Server die Serverredundanz über Pooling. Wenn ein Server ausfällt, auf dem eine bestimmte Serverrolle ausgeführt wird, übernehmen die anderen Server im Pool, auf denen dieselbe Rolle ausgeführt wird, die Arbeitslast dieses Servers. Dies gilt für Front-End-Server, Edgeserver, Vermittlungsserver und Directors.
  
Skype for Business Server bietet auch Notfallwiederherstellungsoptionen für Front-End-Pools. Sie können zwei Pools in verschiedenen geografischen Bereichen einrichten, die als Sicherungen füreinander dienen. Wenn dann ein ganzer Pool oder Standort ausfällt, kann der Sicherungspool weiterhin Dienste für Benutzer an beiden Standorten bereitstellen.
  
Skype for Business Server unterstützt auch vier Modi mit hoher Verfügbarkeit für Ihre Back-End-Server: SQL Spiegelung, AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failoverclusterinstanzen (FCI) und SQL Failoverclustering.
  
> [!NOTE]
> SQL Spiegelung ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die Methoden AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failoverclusterinstanzen (FCI) und SQL Failoverclustering-Methoden werden mit Skype for Business Server 2019 bevorzugt.

> [!NOTE]
> AlwaysOn-Verfügbarkeitsgruppen werden bei Servern für beständigen Chat nicht unterstützt. 
  
In diesem Abschnitt werden diese Features erläutert, und es wird erläutert, welche Schritte Sie für hohe Verfügbarkeit und Notfallwiederherstellung für einige Ihrer anderen Serverrollen ausführen können. 
  
## <a name="see-also"></a>Weitere Informationen

[Hohe Verfügbarkeit und Verwaltung von Front-End-Pools](high-availability.md)
  
[Notfallwiederherstellung von Front-End-Pools in Skype for Business Server](disaster-recovery.md)
  
[Benutzerfreundlichkeit bei Poolfehlern in Skype for Business Server](user-experience.md)
  
[Hohe Verfügbarkeit von Back-End-Servern in Skype for Business Server](back-end-server.md)
  
[Hohe Verfügbarkeit der Dateifreigabe in Skype for Business Server](file-sharing.md)
