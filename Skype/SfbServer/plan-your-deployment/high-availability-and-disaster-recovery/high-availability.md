---
title: Hohe Verfügbarkeit und Verwaltung von Front-End-Pools
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: Erfahren Sie mehr über die Front-End-Poolverwaltung in Skype for Business Server, einschließlich der Verwaltung von Pools, Quorumverlust und spezieller Schritte für Pools mit nur zwei Front-End-Servern.
ms.openlocfilehash: f8ad22c7728fc4fb62980a81fa659558aaba4be7
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60831849"
---
# <a name="front-end-pool-high-availability-and-management"></a>Hohe Verfügbarkeit und Verwaltung von Front-End-Pools
 
Erfahren Sie mehr über die Front-End-Poolverwaltung in Skype for Business Server, einschließlich der Verwaltung von Pools, Quorumverlust und spezieller Schritte für Pools mit nur zwei Front-End-Servern.
  
In Skype for Business Server verwendet die Architektur von Front-End-Pools ein Modell verteilter Systeme, wobei die Daten jedes Benutzers auf bis zu drei Front-End-Servern im Pool gespeichert werden. Es wird empfohlen, dass alle Enterprise Edition Front-End-Pools mindestens drei Front-End-Server enthalten.

> [!NOTE]
> Skype for Business Server 2019 unterstützt Enterprise Edition Front-End-Pools mit zwei Front-End-Servern nicht und lässt nicht zu, dass die Topologie in diesem Szenario veröffentlicht wird.
  
## <a name="planning-for-the-management-of-front-end-pools"></a>Planen der Verwaltung von Front-End-Pools

 Skype for Business Server verwendet ein verteiltes Systemmodell, das auf Windows Fabric basiert. In diesem Modell werden wichtige Daten für jeden Benutzer und jede Konferenz auf drei Front-End-Servern in einem Front-End-Pool gespeichert. Diese drei Server, die einen bestimmten Satz von Daten speichern, werden als "replicas" bezeichnet.
  
Mit dem verteilten Modell für Front-End-Pools muss eine bestimmte Anzahl von Servern eines Pools ausgeführt werden, damit der Pool funktioniert. Es gibt zwei Verlustmodi für einen Pool.
  
- Quorumverlust auf Routinggruppenebene, der durch nicht genügend Replikatserver für eine bestimmte Routinggruppe verursacht wird. Eine Routinggruppe ist eine Gruppe von Benutzern, die im Pool verwaltet werden. Jede Routinggruppe verfügt über drei Replikate im Pool: ein primäres Replikat und zwei sekundäre Replikate.
    
- Quorumverlust auf Poolebene, der verursacht wird, wenn nicht genügend Startserver im Pool ausgeführt werden. 
    
### <a name="routing-group-level-quorum-loss"></a>Quorumverlust auf Routinggruppenebene

Wenn Sie einen neuen Front-End-Pool zum ersten Mal starten, ist es wichtig, dass 85 % der Server betriebsbereit sind, wie in der folgenden Tabelle dargestellt. Wenn weniger Server ausgeführt werden, bleiben die Dienste möglicherweise im Startzustand hängen, und der Pool wird möglicherweise nicht gestartet.
  
|Gesamtanzahl der Server im Pool  <br/> |Anzahl der Server, die ausgeführt werden müssen, damit der Pool zum ersten Mal gestartet wird  <br/> |
|:-----|:-----|
|2  <br/> |1  <br/> |
|3  <br/> |3  <br/> |
|4  <br/> |3  <br/> |
|5  <br/> |4  <br/> |
|6   <br/> |5  <br/> |
|7   <br/> |5  <br/> |
|8   <br/> |6   <br/> |
|9   <br/> |7   <br/> |
|10  <br/> |8   <br/> |
|11  <br/> |9   <br/> |
|12   <br/> |10  <br/> |
|16 **Für Skype for Business Server 2019** <br/> |12   <br/> |


   
Bei jedem nachfolgenden Start des Pools sollten 85 % der Server gestartet werden (wie in der vorherigen Tabelle dargestellt). Wenn diese Anzahl von Servern nicht gestartet werden kann (aber genügend Server gestartet werden können, damit kein Quorumverlust auf Poolebene besteht), können Sie das Cmdlet verwenden,  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` um dem Pool zu ermöglichen, nach diesem Quorumverlust auf Routinggruppenebene wiederherzustellen und Fortschritte zu machen. Weitere Informationen zur Verwendung dieses Cmdlets finden Sie unter [Reset-CsPoolRegistrarState](/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps). 
  
> [!NOTE]
> In Pools mit einer geraden Anzahl von Servern verwendet Skype for Business Server die primäre SQL-Datenbank als Zeuge. Wenn Sie in einem solchen Pool die primäre Datenbank herunterfahren und zur Spiegelkopie wechseln und genügend Front-End-Server herunterfahren, sodass gemäß der vorherigen Tabelle nicht genügend Ausgeführt werden, wird der gesamte Pool heruntergefahren. Weitere Informationen finden Sie unter [Datenbankspiegelungszeugen.](/sql/database-engine/database-mirroring/database-mirroring-witness) 
  
#### <a name="pool-level-quorum-loss"></a>Quorumverlust auf Poolebene

Damit ein Front-End-Pool überhaupt funktioniert, kann der Quorumverlust auf Poolebene nicht auftreten. Wenn die Anzahl der ausgeführten Server unter die Funktionsebene fällt, wie in der folgenden Tabelle dargestellt, beenden die verbleibenden Server im Pool alle Skype for Business Server Dienste. Beachten Sie, dass bei den Zahlen in der folgenden Tabelle davon ausgegangen wird, dass die Back-End-Server im Pool ausgeführt werden.
  
|Gesamtanzahl der Front-End-Server im Pool  <br/> |Anzahl der Server, die für die korrekte Funktionsweise des Pools ausgeführt werden müssen  <br/> |
|:-----|:-----|
|2  <br/> |1  <br/> |
|3-4  <br/> |Beliebige 2  <br/> |
|5-6  <br/> |Beliebige 3  <br/> |
|7   <br/> |Beliebige 4  <br/> |
|8-9  <br/> |Alle 4 der ersten 7 Server  <br/> |
|10-12  <br/> |Jeder 5 der ersten 9 Server  <br/> |
|12-16 **For Skype for Business Server 2019**  <br/> |Alle 7 der ersten 12 Server  <br/> |
   
In der obigen Tabelle sind die "ersten Server" die Server, die beim ersten Start des Pools chronologisch zuerst gestartet wurden. Um diese Server zu ermitteln, können Sie das  `Get-CsComputer` Cmdlet mit der Option `-PoolFqdn` verwenden. Dieses Cmdlet zeigt die Server in der Reihenfolge an, in der sie in der Topologie angezeigt werden, und die Server am Anfang der Liste sind die ersten Server.
  
> [!IMPORTANT]
> Die maximale Anzahl von Front-End-Servern wurde Skype for Business Server [2019 auf 16](../../../SfBServer2019/plan/user-model-2019.md) erhöht.
> 
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>Zusätzliche Schritte, um sicherzustellen, dass Pools funktionsfähig sind

Sie sollten auf einige andere Faktoren achten, um sicherzustellen, dass Ihre Front-End-Pools funktionsfähig bleiben.
  
- Wenn Sie das erste Mal Benutzer in den Pool verschieben, stellen Sie sicher, dass mindestens drei der Front-End-Server aktiv sind.
    
- Wenn Sie eine Kopplungsbeziehung zwischen diesem Pool und einem anderen Pool für Notfallwiederherstellungszwecke einrichten, müssen Sie nach dem Einrichten dieser Beziehung sicherstellen, dass dieser Pool zu einem bestimmten Zeitpunkt drei Front-End-Server gleichzeitig ausgeführt hat, um Daten ordnungsgemäß mit dem Sicherungspool zu synchronisieren. Weitere Informationen zu Poolpaaren und Notfallwiederherstellungsfeatures finden Sie unter [Plan for high availability and disaster recovery in Skype for Business Server.](high-availability-and-disaster-recovery.md) 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>Front-End-Pool mit zwei Front-End-Servern

Das Bereitstellen eines Front-End-Pools, der nur zwei Front-End-Server enthält, wird nicht empfohlen. Dieser kleine Pool bietet keine stabile Hochverfügbarkeitslösung wie ein größerer Pool und erfordert besondere Vorsicht bei der Verwaltung. Wenn der Back-End-Server eines Pools mit zwei Servern ausgefallen wäre, würde wahrscheinlich auch der gesamte Pool selbst bald ausfallen. Wenn Sie nur einen oder zwei Server bereitstellen möchten, auf denen Skype for Business Server ausgeführt wird, empfehlen wir, sie als Standard Edition Server bereitzustellen.
  
Wenn Sie jemals einen Pool mit zwei Front-End-Servern bereitstellen müssen, befolgen Sie die folgenden Richtlinien:
  
- Wenn einer der beiden Front-End-Server ausfällt, sollten Sie versuchen, den ausgefallenen Server so schnell wie möglich wieder in Betrieb zu bekommen. Entsprechend sollten Sie, wenn Sie einen der beiden Server upgraden müssen, diesen Server so bald wie möglich nach Abschluss des Upgrades wieder online schalten.
    
- Falls Sie aus irgendeinem Grund beide Server gleichzeitig herunterfahren müssen, führen Sie nach Beendigung der Downtime für den Pool folgende Schritte durch:
    
  - Die bewährte Methode besteht darin, beide Front-End-Server gleichzeitig neu zu starten. 
    
  - Ist dies nicht möglich, sollten Sie sie in der umgekehrten Reihenfolge wieder hochfahren, in der sie heruntergefahren wurden.
    
  - Wenn Sie sie nicht in dieser Reihenfolge wieder aufsteigen können, verwenden Sie das folgende Cmdlet, bevor Sie den Pool wieder hochschalten:  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>Fehler und Änderungen bei der Konfiguration des Front-End-Pools

Wenn ein Front-End-Server fehlschlägt und wahrscheinlich nicht für ein paar Tage oder mehr ersetzt wird, entfernen Sie den Server aus der Topologie. Fügen Sie den neuen Front-End-Server zur Topologie hinzu, wenn er wieder verfügbar ist.
  
Jedes Mal, wenn Sie eine Konfigurationsänderung an einem Front-End-Pool vornehmen, z. B. beim Hinzufügen oder Entfernen von Servern, müssen Sie die folgenden Richtlinien befolgen:
  
- Nachdem die neue Topologie veröffentlicht wurde, müssen Sie jeden Front-End-Server im Pool neu starten. Starten Sie die Server einen nach dem anderen neu.
    
- Wenn der gesamte Pool während der Konfigurationsänderung ausgefallen ist, führen Sie das folgende Cmdlet aus, nachdem die neue Topologie veröffentlicht wurde:  `Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
