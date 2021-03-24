---
title: Hohe Verfügbarkeit und Verwaltung des Front-End-Pools
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: Erfahren Sie mehr über die Front-End-Poolverwaltung in Skype for Business Server, einschließlich der Verwaltung von Pools, quorum loss und speziellen Schritten für Pools mit nur zwei Front-End-Servern.
ms.openlocfilehash: 47e4b2157961a2856256e3d96a0676dd86d3f996
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093073"
---
# <a name="front-end-pool-high-availability-and-management"></a>Hohe Verfügbarkeit und Verwaltung des Front-End-Pools
 
Erfahren Sie mehr über die Front-End-Poolverwaltung in Skype for Business Server, einschließlich der Verwaltung von Pools, quorum loss und speziellen Schritten für Pools mit nur zwei Front-End-Servern.
  
In Skype for Business Server verwendet die Architektur von Front-End-Pools ein verteiltes Systemmodell, bei dem die Daten jedes Benutzers auf bis zu drei Front-End-Servern im Pool gespeichert werden. Es wird empfohlen, dass alle Front-End-Pools der Enterprise Edition mindestens drei Front-End-Server umfassen.

> [!NOTE]
> Skype for Business Server 2019 unterstützt keine Enterprise Edition-Front-End-Pools mit zwei Front-End-Servern und lässt die Veröffentlichung der Topologie in diesem Szenario nicht zu.
  
## <a name="planning-for-the-management-of-front-end-pools"></a>Planen der Verwaltung von Front-End-Pools

 Skype for Business Server verwendet ein verteiltes Systemmodell, das auf Windows Fabric basiert. In diesem Modell werden wichtige Daten für jeden Benutzer und jede Konferenz auf drei Front-End-Servern in einem Front-End-Pool gespeichert. Diese drei Server, auf denen eine bestimmte Gruppe von Daten gespeichert wird, werden alsReplicas bezeichnet.
  
Mit dem verteilten Modell für Front-End-Pools muss eine bestimmte Anzahl von Servern eines Pools ausgeführt werden, damit der Pool funktioniert. Es gibt zwei Verlustmodi für einen Pool.
  
- Quorumverlust auf Routinggruppesebene, verursacht durch nicht genügend Replikatserver für eine bestimmte Routinggruppe. Eine Routinggruppe ist eine Gruppe von Benutzern, die im Pool zu Hause sind. Jede Routinggruppe verfügt über drei Replikate im Pool: ein primäres replikat und zwei sekundäre Replikate.
    
- Quorumverlust auf Poolebene, der verursacht wird, wenn nicht genügend Seedserver im Pool ausgeführt werden. 
    
### <a name="routing-group-level-quorum-loss"></a>Quorumverlust auf Routinggruppesebene

Beim ersten Starten eines neuen Front-End-Pools ist es wichtig, dass 85 % der Server ausgeführt werden, wie in der folgenden Tabelle dargestellt. Wenn weniger Server ausgeführt werden, befinden sich die Dienste möglicherweise im Anfangszustand, und der Pool wird möglicherweise nicht gestartet.
  
|Gesamtanzahl der Server im Pool  <br/> |Anzahl der Server, die ausgeführt werden müssen, damit der Pool zum ersten Mal gestartet werden kann  <br/> |
|:-----|:-----|
|2  <br/> |1  <br/> |
|3  <br/> |3  <br/> |
|4   <br/> |3  <br/> |
|5   <br/> |4   <br/> |
|6   <br/> |5   <br/> |
|7   <br/> |5   <br/> |
|8   <br/> |6   <br/> |
|9   <br/> |7   <br/> |
|10    <br/> |8   <br/> |
|11  <br/> |9   <br/> |
|12   <br/> |10    <br/> |
|16 **Für Skype for Business Server 2019** <br/> |12   <br/> |


   
Jedes nachfolgende Mal, wenn der Pool gestartet wird, sollten 85 % der Server gestartet werden (wie in der vorherigen Tabelle dargestellt). Wenn diese Anzahl von Servern nicht gestartet werden kann (es können jedoch genügend Server gestartet werden, damit sie nicht beim Quorumverlust auf Poolebene sind), können Sie das Cmdlet verwenden, um dem Pool die Wiederherstellung nach diesem Quorumverlust auf Routinggruppenebene zu ermöglichen und Fortschritte zu  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` erzielen. Weitere Informationen zur Verwendung dieses Cmdlets finden Sie unter [Reset-CsPoolRegistrarState](/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps). 
  
> [!NOTE]
> In Pools mit einer gleichmäßigen Anzahl von Servern verwendet Skype for Business Server die primäre SQL Als Zeuge. Wenn Sie in einem Pool wie diesem die primäre Datenbank herunterfahren und zur Spiegelkopie wechseln und genügend Front-End-Server herunterfahren, damit nicht genug gemäß der vorherigen Tabelle ausgeführt wird, wird der gesamte Pool heruntergefahren. Weitere Informationen finden Sie unter [Database Mirroring Witness](/sql/database-engine/database-mirroring/database-mirroring-witness). 
  
#### <a name="pool-level-quorum-loss"></a>Quorumverlust auf Poolebene

Damit ein Front-End-Pool überhaupt funktioniert, kann er nicht im Quorumverlust auf Poolebene sein. Wenn die Anzahl der ausgeführten Server unter die Funktionsebene fällt, wie in der folgenden Tabelle dargestellt, werden alle Skype for Business Server-Dienste von den verbleibenden Servern im Pool beendet. Beachten Sie, dass die Zahlen in der folgenden Tabelle davon ausgehen, dass die Back-End-Server im Pool ausgeführt werden.
  
|Gesamtanzahl der Front-End-Server im Pool  <br/> |Anzahl der Server, die für die korrekte Funktionsweise des Pools ausgeführt werden müssen  <br/> |
|:-----|:-----|
|2  <br/> |1  <br/> |
|3-4  <br/> |Beliebige 2  <br/> |
|5-6  <br/> |Beliebige 3  <br/> |
|7   <br/> |Beliebige 4  <br/> |
|8-9  <br/> |Alle 4 der ersten 7 Server  <br/> |
|10-12  <br/> |Jeder 5 der ersten 9 Server  <br/> |
|12-16  **For Skype for Business Server 2019**  <br/> |Alle 7 der ersten 12 Server  <br/> |
   
In der vorstehenden Tabelle sind die "ersten Server" die Server, die beim ersten Start des Pools chronologisch zuerst hoch gelaufen wurden. Um diese Server zu ermitteln, können Sie das  `Get-CsComputer` Cmdlet mit der Option `-PoolFqdn` verwenden. Dieses Cmdlet zeigt die Server in der Reihenfolge an, in der sie in der Topologie angezeigt werden, und die Server oben in der Liste sind die ersten Server.
  
> [!IMPORTANT]
> Die maximale Anzahl von Front-End-Servern wurde in [Skype for Business Server 2019 auf 16 erhöht.](../../../SfBServer2019/plan/user-model-2019.md)
> 
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>Zusätzliche Schritte, um sicherzustellen, dass Pools funktionsfähig sind

Sie sollten auf einige andere Faktoren achten, um sicherzustellen, dass Ihre Front-End-Pools funktionsfähig bleiben.
  
- Wenn Sie das erste Mal Benutzer in den Pool verschieben, stellen Sie sicher, dass mindestens drei der Front-End-Server aktiv sind.
    
- Wenn Sie eine Kopplungsbeziehung zwischen diesem Pool und einem anderen Pool für Notfallwiederherstellungszwecke einrichten, müssen Sie nach dem Herstellen dieser Beziehung sicherstellen, dass dieser Pool über drei Front-End-Server verfügt, die zu einem bestimmten Zeitpunkt gleichzeitig ausgeführt werden, um Daten ordnungsgemäß mit dem Sicherungspool zu synchronisieren. Weitere Informationen zu Poolkopplungs- und Notfallwiederherstellungsfeatures finden Sie unter [Plan for high availability and disaster recovery in Skype for Business Server](high-availability-and-disaster-recovery.md). 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>Front-End-Pool mit zwei Front-End-Servern

Das Bereitstellen eines Front-End-Pools, der nur zwei Front-End-Server enthält, wird nicht empfohlen. Dieser kleine Pool bietet keine stabile Hochverfügbarkeitslösung wie ein größerer Pool und benötigt zusätzliche Sorgfalt bei der Verwaltung. Wenn der Back-End-Server eines Zwei-Server-Pools nicht mehr funktioniert, würde auch der gesamte Pool selbst wahrscheinlich bald heruntergehen. Wenn Sie nur einen oder zwei Server mit Skype for Business Server bereitstellen möchten, wird empfohlen, sie als Standard Edition-Server zu bereitstellen.
  
Wenn Sie jemals einen Pool mit zwei Front-End-Servern bereitstellen müssen, befolgen Sie die folgenden Richtlinien:
  
- Wenn einer der beiden Front-End-Server ausfällt, sollten Sie versuchen, den ausgefallenen Server so schnell wie möglich wieder in Betrieb zu bekommen. Entsprechend sollten Sie, wenn Sie einen der beiden Server upgraden müssen, diesen Server so bald wie möglich nach Abschluss des Upgrades wieder online schalten.
    
- Falls Sie aus irgendeinem Grund beide Server gleichzeitig herunterfahren müssen, führen Sie nach Beendigung der Downtime für den Pool folgende Schritte durch:
    
  - Die bewährte Methode ist, beide Front-End-Server gleichzeitig neu zu starten. 
    
  - Ist dies nicht möglich, sollten Sie sie in der umgekehrten Reihenfolge wieder hochfahren, in der sie heruntergefahren wurden.
    
  - Wenn Sie sie nicht in dieser Reihenfolge wieder hochbringen können, verwenden Sie das folgende Cmdlet, bevor Sie den Pool sichern:  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>Fehler und Änderungen bei der Konfiguration des Front-End-Pools

Wenn ein Front-End-Server ausfällt und wahrscheinlich für ein paar Tage oder mehr ersetzt wird, entfernen Sie den Server aus der Topologie. Fügen Sie der Topologie den neuen Front-End-Server hinzu, wenn er wieder verfügbar ist.
  
Wenn Sie eine Konfigurationsänderung an einem Front-End-Pool, z. B. beim Hinzufügen oder Entfernen von Servern, vor sich haben, müssen Sie die folgenden Richtlinien befolgen:
  
- Nachdem die neue Topologie veröffentlicht wurde, müssen Sie jeden Front-End-Server im Pool neu starten. Starten Sie die Server einen nach dem anderen neu.
    
- Wenn der gesamte Pool während der Konfigurationsänderung nicht mehr ausgeführt wurde, führen Sie das folgende Cmdlet aus, nachdem die neue Topologie veröffentlicht wurde:  `Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
