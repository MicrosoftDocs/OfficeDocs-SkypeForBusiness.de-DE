---
title: Hohe Verfügbarkeit und Verwaltung von Front-End-Pools
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: In diesem Artikel erfahren Sie mehr über Front-End-Pool Verwaltung in Skype for Business Server, einschließlich der Verwaltung von Pools, des Quorum Verlusts und spezieller Schritte für Pools mit nur zwei Front-End-Servern.
ms.openlocfilehash: 2982e2da0e7a103b5b598019baa7403a73da826d
ms.sourcegitcommit: 397c4840fb053238de24b8b24ae75588b33b693d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2020
ms.locfileid: "45098433"
---
# <a name="front-end-pool-high-availability-and-management"></a>Hohe Verfügbarkeit und Verwaltung von Front-End-Pools
 
In diesem Artikel erfahren Sie mehr über Front-End-Pool Verwaltung in Skype for Business Server, einschließlich der Verwaltung von Pools, des Quorum Verlusts und spezieller Schritte für Pools mit nur zwei Front-End-Servern.
  
In Skype for Business Server verwendet die Architektur von Front-End-Pools ein Modell für verteilte Systeme, wobei die Daten der einzelnen Benutzer auf bis zu drei Front-End-Servern im Pool aufbewahrt werden. Es wird empfohlen, dass alle Ihre Enterprise Edition-Front-End-Pools mindestens drei Front-End-Server umfassen.

> [!NOTE]
> Skype for Business Server 2019 unterstützt keine Enterprise Edition-Front-End-Pools mit zwei Front-End-Servern und lässt nicht zu, dass die Topologie in diesem Szenario veröffentlicht wird.
  
## <a name="planning-for-the-management-of-front-end-pools"></a>Planen der Verwaltung von Front-End-Pools

 Skype for Business Server verwendet ein auf Windows Fabric basierendes verteiltes Systemmodell. In diesem Modell werden wichtige Daten für jeden Benutzer und jede Konferenz auf drei Front-End-Servern in einem Front-End-Pool gespeichert. Diese drei Server, die eine bestimmte Gruppe von Daten speichern, sind calledreplicas.
  
Mit dem verteilten Modell für Front-End-Pools müssen eine bestimmte Anzahl von Servern eines Pools für die Funktion des Pools installiert sein. Es gibt zwei Verlust Modi für einen Pool.
  
- Quorum Verlust auf Routing Gruppenebene, der durch nicht genügend Replikatserver für eine bestimmte Routinggruppe verursacht wird. Eine Routinggruppe ist eine Gruppe von Benutzern, die im Pool verwaltet werden. Jede Routinggruppe verfügt über drei Replikate im Pool: ein primäres Replikat und zwei sekundäre Replikate.
    
- Quorum Verlust auf Poolebene, verursacht werden, wenn nicht genügend Seed-Server im Pool ausgeführt werden. 
    
### <a name="routing-group-level-quorum-loss"></a>Quorum Verlust auf Routing Gruppenebene

Wenn Sie ein neues Front-End-Pool zum ersten Mal starten, ist es wichtig, dass 85% der Serverbetriebs bereit sind, wie in der folgenden Tabelle dargestellt. Wenn weniger Server aktiv sind, können die Dienste möglicherweise in den Startzustand verfallen, und der Pool wird möglicherweise nicht gestartet.
  
|Gesamtanzahl der Server im Pool  <br/> |Anzahl der Server, die ausgeführt werden müssen, damit der Pool beim ersten Mal gestartet wird  <br/> |
|:-----|:-----|
|2   <br/> |1   <br/> |
|3   <br/> |3   <br/> |
|4   <br/> |3   <br/> |
|5   <br/> |4   <br/> |
|6   <br/> |5   <br/> |
|7   <br/> |5   <br/> |
|8   <br/> |6   <br/> |
|9   <br/> |7   <br/> |
|10   <br/> |8   <br/> |
|11   <br/> |9   <br/> |
|12   <br/> |10   <br/> |
|16 **für Skype for Business Server 2019** <br/> |12   <br/> |


   
Bei jedem nachfolgenden Start des Pools sollten 85% der Server gestartet werden (siehe obige Tabelle). Wenn diese Anzahl von Servern nicht gestartet werden kann (es können jedoch genügend Server gestartet werden, damit Sie nicht auf der Ebene des Quorums auf der Poolebene sind), können Sie das Cmdlet verwenden, um `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` den Pool für die Wiederherstellung von Quorum Verlusten auf Routinggruppen Ebene zu aktivieren und Fortschritte zu erzielen. Weitere Informationen zur Verwendung dieses Cmdlets finden Sie unter [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps). 
  
> [!NOTE]
> In Pools mit einer geraden Anzahl von Servern verwendet Skype for Business Server die primäre SQL-Datenbank als Zeugen. Wenn Sie in einem solchen Pool die primäre Datenbank Herunterfahren und zur Spiegelkopie wechseln und genügend Front-End-Server herunterfahren, sodass nicht genügend entsprechend der obigen Tabelle ausgeführt wird, wird der gesamte Pool nach unten verschoben. Weitere Informationen finden Sie unter [Datenbank-Spiegelungs Zeuge](https://go.microsoft.com/fwlink/?LinkId=393672). 
  
#### <a name="pool-level-quorum-loss"></a>Quorum Verlust auf Poolebene

Damit ein Front-End-Pool überhaupt funktioniert, kann es nicht auf dem Quorum Verlust auf Poolebene liegen. Wenn die Anzahl der Server, die in der folgenden Tabelle aufgeführt sind, unter die Funktionsebene fällt, werden die restlichen Server im Pool alle Skype for Business Server Dienste beenden. Beachten Sie, dass die Nummern in der folgenden Tabelle davon ausgehen, dass die Back-End-Server im Pool aktiv sind.
  
|Gesamtanzahl der Front-End-Server im Pool  <br/> |Anzahl der Server, die für die korrekte Funktionsweise des Pools ausgeführt werden müssen  <br/> |
|:-----|:-----|
|2   <br/> |1   <br/> |
|3-4  <br/> |Any 2  <br/> |
|5-6  <br/> |Beliebige 3  <br/> |
|7   <br/> |Beliebige 4  <br/> |
|8-9  <br/> |4 der ersten 7 Server  <br/> |
|10-12  <br/> |5 der ersten 9 Server  <br/> |
|12-16 **für Skype for Business Server 2019**  <br/> |7 der ersten 12 Server  <br/> |
   
In der obigen Tabelle sind die "ersten Server" die Server, die zunächst chronologisch aufgelegt wurden, als der Pool zum ersten Mal gestartet wurde. Zum bestimmen dieser Server können Sie das `Get-CsComputer` Cmdlet mit der Option verwenden `-PoolFqdn` . Dieses Cmdlet zeigt die Server in der Reihenfolge an, in der Sie in der Topologie angezeigt werden, und diejenigen, die sich oben in der Liste befinden, sind die ersten Server.
  
> [!IMPORTANT]
> Die maximale Anzahl von Front-End-Servern wurde in [Skype for Business Server 2019](https://docs.microsoft.com/skypeforbusiness/plan/user-model-2019) auf 16 erhöht.
> 
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>Zusätzliche Schritte zum Sicherstellen der Funktionsweise von Pools

Sie sollten sich einige andere Faktoren ansehen, um sicherzustellen, dass Ihre Front-End-Pools funktionsfähig bleiben.
  
- Wenn Sie das erste Mal Benutzer in den Pool verschieben, stellen Sie sicher, dass mindestens drei der Front-End-Server aktiv sind.
    
- Wenn Sie eine Paarungs Beziehung zwischen diesem Pool und einem anderen Pool für notfallwiederherstellungszwecke einrichten, müssen Sie sicherstellen, dass in diesem Pool drei Front-End-Server zu einem bestimmten Zeitpunkt zur korrekten Synchronisierung der Daten mit dem Sicherungspool gleichzeitig ausgeführt werden, nachdem Sie diese Beziehung hergestellt haben. Weitere Informationen zu Pool Kopplung und Notfall Wiederherstellungsfeatures finden Sie unter [Plan for High Availability and Disaster Recovery in Skype for Business Server](high-availability-and-disaster-recovery.md). 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>Front-End-Pool mit zwei Front-End-Servern

Das Bereitstellen eines Front-End-Pools, der nur zwei Front-End-Server enthält, wird nicht empfohlen. Dieser kleine Pool bietet keine robuste Hochverfügbarkeitslösung wie ein größerer Pool und erfordert zusätzliche Sorgfalt bei der Verwaltung. Wenn der Back-End-Server eines Pools mit zwei Servern ebenfalls ausfiel, würde der gesamte Pool wahrscheinlich auch bald nach unten gehen. Wenn Sie nur einen oder zwei Server mit Skype for Business Server bereitstellen möchten, empfehlen wir, diese als Standard Edition-Server bereitzustellen.
  
Wenn Sie jemals einen Pool mit zwei Front-End-Servern bereitstellen müssen, befolgen Sie diese Richtlinien:
  
- Wenn einer der beiden Front-End-Server ausfällt, sollten Sie versuchen, den ausgefallenen Server so schnell wie möglich wieder in Betrieb zu bekommen. Entsprechend sollten Sie, wenn Sie einen der beiden Server upgraden müssen, diesen Server so bald wie möglich nach Abschluss des Upgrades wieder online schalten.
    
- Falls Sie aus irgendeinem Grund beide Server gleichzeitig herunterfahren müssen, führen Sie nach Beendigung der Downtime für den Pool folgende Schritte durch:
    
  - Die bewährte Methode besteht darin, beide Front-End-Server gleichzeitig neu zu starten. 
    
  - Ist dies nicht möglich, sollten Sie sie in der umgekehrten Reihenfolge wieder hochfahren, in der sie heruntergefahren wurden.
    
  - Wenn Sie Sie nicht in dieser Reihenfolge sichern können, verwenden Sie das folgende Cmdlet, bevor Sie den Pool sichern:`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>Front-End-Pool von Konfigurationsfehlern und-Änderungen

Wenn ein Front-End-Server ausfällt und für einige Tage oder länger nicht ersetzt werden kann, entfernen Sie den Server aus der Topologie. Fügen Sie den neuen Front-End-Server der Topologie hinzu, wenn er wieder verfügbar ist.
  
Wenn Sie eine Konfigurationsänderung an einer Front-End-Pool vornehmen, beispielsweise das Hinzufügen oder Entfernen von Servern, müssen Sie die folgenden Richtlinien befolgen:
  
- Nachdem die neue Topologie veröffentlicht wurde, müssen Sie jeden Front-End-Server im Pool neu starten. Starten Sie die Server einen nach dem anderen neu.
    
- Wenn während der Konfigurationsänderung der gesamte Pool heruntergefahren wurde, führen Sie das folgende Cmdlet aus, nachdem die neue Topologie veröffentlicht wurde:`Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
    

