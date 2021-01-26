---
title: Hohe Verfügbarkeit und Verwaltung von Front-End-Pools
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
description: Erfahren Sie mehr über die Verwaltung von Front-End-Pools in Skype for Business Server, einschließlich der Verwaltung von Pools, Quorumverlusten und speziellen Schritten für Pools mit nur zwei Front-End-Servern.
ms.openlocfilehash: 3f1924b7a8ad26b880f8674ada4f0c99a1bc4596
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802795"
---
# <a name="front-end-pool-high-availability-and-management"></a>Hohe Verfügbarkeit und Verwaltung von Front-End-Pools
 
Erfahren Sie mehr über die Verwaltung von Front-End-Pools in Skype for Business Server, einschließlich der Verwaltung von Pools, Quorumverlusten und speziellen Schritten für Pools mit nur zwei Front-End-Servern.
  
In Skype for Business Server verwendet die Architektur von Front-End-Pools ein verteiltes Systemmodell, bei dem die Daten jedes Benutzers auf bis zu drei Front-End-Servern im Pool gespeichert werden. Es wird empfohlen, dass alle Front-End-Pools der Enterprise Edition mindestens drei Front-End-Server umfassen.

> [!NOTE]
> Skype for Business Server 2019 unterstützt keine Enterprise Edition-Front-End-Pools mit zwei Front-End-Servern und lässt die Veröffentlichung der Topologie in diesem Szenario nicht zu.
  
## <a name="planning-for-the-management-of-front-end-pools"></a>Planen der Verwaltung von Front-End-Pools

 Skype for Business Server verwendet ein verteiltes Systemmodell, das auf Windows Fabric basiert. In diesem Modell werden wichtige Daten für jeden Benutzer und jede Konferenz auf drei Front-End-Servern in einem Front-End-Pool gespeichert. Diese drei Server, auf denen eine bestimmte Gruppe von Daten gespeichert wird, werden als "Replicas" bezeichnet.
  
Mit dem verteilten Modell für Front-End-Pools muss eine bestimmte Anzahl von Servern eines Pools ausgeführt werden, damit der Pool funktioniert. Es gibt zwei Verlustmodi für einen Pool.
  
- Quorumverlust auf Routinggruppenebene, verursacht durch nicht genügend Replikatserver für eine bestimmte Routinggruppe. Eine Routinggruppe ist eine Gruppe von Benutzern, die im Pool zu Hause sind. Jede Routinggruppe verfügt über drei Replikate im Pool: ein primäres Replikat und zwei sekundäre Replikate.
    
- Quorumverlust auf Poolebene, der verursacht wird, wenn nicht genügend Seedserver im Pool ausgeführt werden. 
    
### <a name="routing-group-level-quorum-loss"></a>Quorumverlust auf Routinggruppenebene

Wenn Sie einen neuen Front-End-Pool zum ersten Mal starten, ist es wichtig, dass 85 % der Server ausgeführt werden, wie in der folgenden Tabelle dargestellt. Wenn weniger Server ausgeführt werden, bleiben die Dienste möglicherweise im Startzustand hängen, und der Pool wird möglicherweise nicht gestartet.
  
|Gesamtanzahl der Server im Pool  <br/> |Anzahl der Server, die ausgeführt werden müssen, damit der Pool zum ersten Mal gestartet wird  <br/> |
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
|16 **For Skype for Business Server 2019** <br/> |12   <br/> |


   
Jedes nachfolgende Mal, wenn der Pool gestartet wird, sollten 85 % der Server gestartet werden (wie in der vorherigen Tabelle dargestellt). Wenn diese Anzahl von Servern nicht gestartet werden kann (es können jedoch genügend Server gestartet werden, damit kein Quorumverlust auf Poolebene erreicht wird), können Sie das Cmdlet verwenden, um dem Pool die Wiederherstellung nach diesem Quorumverlust auf Routinggruppenebene zu ermöglichen und fortschritte zu  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` machen. Weitere Informationen zur Verwendung dieses Cmdlets finden Sie unter [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps). 
  
> [!NOTE]
> In Pools mit einer gleichmäßigen Anzahl von Servern verwendet Skype for Business Server die primäre SQL als Zeuge. Wenn Sie in einem Pool wie diesem die primäre Datenbank herunterfahren und zur Spiegelkopie wechseln und so viele Front-End-Server herunterfahren, dass nicht genügend Server wie in der vorstehenden Tabelle ausgeführt werden, geht der gesamte Pool aus. Weitere Informationen finden Sie unter [Datenbankspiegelungszeuge](https://go.microsoft.com/fwlink/?LinkId=393672). 
  
#### <a name="pool-level-quorum-loss"></a>Quorumverlust auf Poolebene

Damit ein Front-End-Pool überhaupt funktioniert, kann er nicht zu einem Quorumverlust auf Poolebene führen. Wenn die Anzahl der ausgeführten Server unter die in der folgenden Tabelle dargestellte Funktionsebene fällt, beenden die verbleibenden Server im Pool alle Skype for Business Server-Dienste. Beachten Sie, dass bei den Zahlen in der folgenden Tabelle davon ausgegangen wird, dass die Back-End-Server im Pool ausgeführt werden.
  
|Gesamtanzahl der Front-End-Server im Pool  <br/> |Anzahl der Server, die für die korrekte Funktionsweise des Pools ausgeführt werden müssen  <br/> |
|:-----|:-----|
|2   <br/> |1   <br/> |
|3-4  <br/> |Any 2  <br/> |
|5-6  <br/> |Beliebige 3  <br/> |
|7   <br/> |Alle 4  <br/> |
|8-9  <br/> |Alle 4 der ersten 7 Server  <br/> |
|10-12  <br/> |Alle 5 der ersten 9 Server  <br/> |
|12-16  **Für Skype for Business Server 2019**  <br/> |Alle 7 der ersten 12 Server  <br/> |
   
In der vorstehenden Tabelle sind die "ersten Server" die Server, die beim ersten Start des Pools chronologisch zuerst hoch gelaufen wurden. Um diese Server zu ermitteln, können Sie das  `Get-CsComputer` Cmdlet mit der Option `-PoolFqdn` verwenden. Dieses Cmdlet zeigt die Server in der Reihenfolge an, in der sie in der Topologie angezeigt werden, und die Server oben in der Liste sind die ersten Server.
  
> [!IMPORTANT]
> Die maximale Anzahl von Front-End-Servern wurde in [Skype for Business Server 2019 auf 16 erhöht.](https://docs.microsoft.com/skypeforbusiness/plan/user-model-2019)
> 
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>Zusätzliche Schritte, um sicherzustellen, dass Pools funktionsfähig sind

Sie sollten auf einige andere Faktoren achten, um sicherzustellen, dass Ihre Front-End-Pools funktionsfähig bleiben.
  
- Wenn Sie das erste Mal Benutzer in den Pool verschieben, stellen Sie sicher, dass mindestens drei der Front-End-Server aktiv sind.
    
- Wenn Sie eine Paarungsbeziehung zwischen diesem Pool und einem anderen Pool für Notfallwiederherstellungszwecke einrichten, müssen Sie nach dem Einrichten dieser Beziehung sicherstellen, dass in diesem Pool zu einem bestimmten Zeitpunkt drei Front-End-Server gleichzeitig ausgeführt werden, um die Daten mit dem Sicherungspool ordnungsgemäß zu synchronisieren. Weitere Informationen zu Poolpaarungs- und Notfallwiederherstellungsfeatures finden Sie unter [Plan for high availability and disaster recovery in Skype for Business Server](high-availability-and-disaster-recovery.md). 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>Front-End-Pool mit zwei Front-End-Servern

Das Bereitstellen eines Front-End-Pools, der nur zwei Front-End-Server enthält, wird nicht empfohlen. Dieser kleine Pool bietet keine stabile Hochverfügbarkeitslösung wie ein größerer Pool und benötigt zusätzliche Sorgfalt bei der Verwaltung. Wenn außerdem der Back-End-Server eines Pools mit zwei Servern ausbiert wird, würde wahrscheinlich auch der gesamte Pool selbst bald aus dem System gehen. Wenn Sie nur einen oder zwei Server mit Skype for Business Server bereitstellen möchten, empfehlen wir die Bereitstellung als Standard Edition-Server.
  
Wenn Sie jemals einen Pool mit zwei Front-End-Servern bereitstellen müssen, befolgen Sie die folgenden Richtlinien:
  
- Wenn einer der beiden Front-End-Server ausfällt, sollten Sie versuchen, den ausgefallenen Server so schnell wie möglich wieder in Betrieb zu bekommen. Entsprechend sollten Sie, wenn Sie einen der beiden Server upgraden müssen, diesen Server so bald wie möglich nach Abschluss des Upgrades wieder online schalten.
    
- Falls Sie aus irgendeinem Grund beide Server gleichzeitig herunterfahren müssen, führen Sie nach Beendigung der Downtime für den Pool folgende Schritte durch:
    
  - Die bewährte Methode besteht im gleichzeitigen Neustart beider Front-End-Server. 
    
  - Ist dies nicht möglich, sollten Sie sie in der umgekehrten Reihenfolge wieder hochfahren, in der sie heruntergefahren wurden.
    
  - Wenn Sie sie nicht in dieser Reihenfolge wieder hochsenieren können, verwenden Sie das folgende Cmdlet, bevor Sie den Pool wieder hochsenieren:  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>Fehler und Änderungen bei der Konfiguration des Front-End-Pools

Wenn ein Front-End-Server ausfällt und wahrscheinlich für ein paar Tage oder mehr nicht ersetzt wird, entfernen Sie den Server aus der Topologie. Fügen Sie den neuen Front-End-Server der Topologie hinzu, wenn er wieder verfügbar ist.
  
Wenn Sie eine Konfigurationsänderung an einem Front-End-Pool, z. B. beim Hinzufügen oder Entfernen von Servern, vor sich nehmen, müssen Sie die folgenden Richtlinien befolgen:
  
- Nachdem die neue Topologie veröffentlicht wurde, müssen Sie jeden Front-End-Server im Pool neu starten. Starten Sie die Server einen nach dem anderen neu.
    
- Wenn der gesamte Pool während der Konfigurationsänderung aus ist, führen Sie nach der Veröffentlichung der neuen Topologie das folgende Cmdlet aus:  `Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
    

