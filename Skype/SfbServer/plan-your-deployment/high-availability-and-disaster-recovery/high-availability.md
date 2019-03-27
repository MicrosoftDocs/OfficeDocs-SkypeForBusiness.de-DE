---
title: Hohe Verfügbarkeit und Verwaltung von Front-End-Pools
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: Informationen Sie zu Front-End-Pool-Verwaltung in Skype für Business Server, einschließlich der Verwaltung von Pools, Quorum Verlust und speziellen Schritte für Pools mit nur zwei Front-End-Servern.
ms.openlocfilehash: 43c8e3fffb010bf268f94970b5cca25ecee7cd58
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894195"
---
# <a name="front-end-pool-high-availability-and-management"></a>Hohe Verfügbarkeit und Verwaltung von Front-End-Pools
 
Informationen Sie zu Front-End-Pool-Verwaltung in Skype für Business Server, einschließlich der Verwaltung von Pools, Quorum Verlust und speziellen Schritte für Pools mit nur zwei Front-End-Servern.
  
In Skype für Business Server verwendet die Architektur von Front-End-Pools ein Modell verteilter Systeme mit jeder Benutzer Daten auf bis zu drei Front-End-Servern im Pool gespeichert. Es wird empfohlen, dass alle Enterprise Edition-Front-End-Pools mindestens drei Front-End-Server enthalten. 
  
## <a name="planning-for-the-management-of-front-end-pools"></a>Planen der Verwaltung von Front-End-Pools

 Skype für Business Server verwendet ein basierend auf Windows Fabric verteilter Systeme-Modell. In diesem Modell werden wichtige Daten für jeden Benutzer und Konferenz auf drei Front-End-Servern in einem Front-End-Pool gespeichert. Diese drei Server Speichern von einem bestimmten Satz von Daten sind Calledreplicas.
  
Mit dem verteilten Objektmodell für Front-End-Pools muss eine bestimmte Anzahl von Servern des Pools für den Pool-Funktion ausgeführt werden. Es gibt zwei Verlust Modi für einen Pool.
  
- Quorumverlust auf Routinggruppenebene, wenn nicht genügend Replikatserver für eine bestimmte Routinggruppe vorhanden sind. Bei einer Routinggruppe handelt es sich um eine Gruppe von Benutzern, die im Pool verwaltet werden. Jede Routinggruppe verfügt über drei Replikate im Pool: ein primäres und zwei sekundäre Replikate.
    
- Quorumverlust auf Poolebene, der verursacht wird, wenn nicht genügend Seedserver im Pool aktiv sind. 
    
### <a name="routing-group-level-quorum-loss"></a>Quorumverlust auf Routinggruppenebene

Wenn Sie einen neuen Front-End-Pool zum ersten Mal starten, ist es wichtig, dass wie in der folgenden Tabelle gezeigt 85 % der Server aktiv sind. Wenn weniger Server aktiv sind, bleiben die Dienste möglicherweise im Startstatus hängen und der Pool wird nicht gestartet.
  
|Gesamtzahl der Server im Pool  <br/> |Anzahl der Server, die aktiv sein müssen, damit der Pool zum ersten Mal gestartet wird  <br/> |
|:-----|:-----|
|2  <br/> |1  <br/> |
|3  <br/> |3  <br/> |
|4  <br/> |3  <br/> |
|5  <br/> |4  <br/> |
|6  <br/> |5  <br/> |
|7  <br/> |5  <br/> |
|8  <br/> |6  <br/> |
|9  <br/> |7  <br/> |
|10  <br/> |8  <br/> |
|11  <br/> |9  <br/> |
|12  <br/> |10  <br/> |
   
Bei jedem nachfolgenden Start des Pools sollten 85 % der Server gestartet werden (wie in der vorstehenden Tabelle gezeigt). Wenn diese Anzahl der Server kann nicht gestartet werden (jedoch nicht genügend Server gestartet werden können, so, dass Sie sich nicht auf Poolebene Quorum Verlust befinden), können Sie die `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` -Cmdlet zum Aktivieren des Pools aus diesem routing Group Ebene Quorum Verlust wiederherzustellen und Fortschritte. Weitere Informationen dazu, wie Sie dieses Cmdlet verwenden, finden Sie unter <link Reset-CsPoolRegistrarState>.
  
> [!NOTE]
> In Pools mit einer geraden Anzahl von Servern verwendet Skype for Business Server die primäre SQL-Datenbank als Zeuge. Wenn Sie in einem solchen Pool die primäre Datenbank herunterfahren, zur Spiegelkopie wechseln und ausreichend Front-End-Server herunterfahren, sodass (entsprechend der vorstehenden Tabelle) nicht genügend von ihnen aktiv sind, fällt der gesamte Pool aus. Weitere Informationen finden Sie unter [Datenbank-Spiegelungszeuge](https://go.microsoft.com/fwlink/?LinkId=393672). 
  
#### <a name="pool-level-quorum-loss"></a>Quorumverlust auf Poolebene

Für einen Front-End-Pool funktionsfähig es Poolebene Quorum Verlust nicht möglich. Unterschreitet die Anzahl der aktiven Server die in der folgenden Tabelle gezeigte Funktionsebene, halten die im Pool verbleibenden Server alle Skype for Business Server-Dienste an. Beachten Sie, dass die Zahlen in der folgenden Tabelle wird davon ausgegangen, dass die Back End-Server im Pool ausgeführt werden.
  
|Gesamtanzahl der Front-End-Servern im pool  <br/> |Anzahl der Server, die aktiv sein müssen, damit der Pool funktioniert  <br/> |
|:-----|:-----|
|2  <br/> |1  <br/> |
|3-4  <br/> |Beliebige 2  <br/> |
|5-6  <br/> |Beliebige 3  <br/> |
|7  <br/> |Beliebige 4  <br/> |
|8-9  <br/> |Beliebige 4 der ersten 7 Server  <br/> |
|10-12  <br/> |Beliebige 5 der ersten 9 Server  <br/> |
   
In der obigen Tabelle sind die "ersten Server" die Server die geschaltet wurden einrichten, wenn der Pool zum ersten Mal gestartet wurde zunächst, chronologisch. Um diese Server zu bestimmen, verwenden Sie die `Get-CsComputer` -Cmdlet mit den ` -PoolFqdn` Option. Dieses Cmdlet die Server in der Reihenfolge, die sie in der Topologie angezeigt werden, und es am oberen Rand der Liste sind die ersten Server.
  
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>Zusätzliche Schritte, um zu bestimmen, dass Pools funktionsbereit sind

Sie sollten auf eine Reihe anderer Faktoren achten, um sicherzustellen, dass Ihre Front-End-Pools funktionsbereit bleiben.
  
- Wenn Sie Benutzer zum ersten Mal in den Pool verschieben, müssen Sie mindestens, dass drei der Front-End-Server ausgeführt werden.
    
- Wenn Sie eine Paarbeziehung zwischen diesem Pool und einem anderen Pool zum Zweck der Notfallwiederherstellung konfigurieren, müssen Sie nach dem Erstellen dieser Beziehung sichergehen, dass in diesem Pool zu einem beliebigen Zeitpunkt drei Front-End-Server gleichzeitig ausgeführt werden, damit Daten korrekt mit dem Sicherungspool synchronisiert werden. Weitere Informationen zum Pool eine Kopplung und Disaster Recovery-Funktionen finden Sie unter [Planen für hohe Verfügbarkeit und notfallwiederherstellung in Skype für Business Server](high-availability-and-disaster-recovery.md). 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>Front-End-Pool mit zwei Front-End-Servern

Wir empfehlen nicht Bereitstellen eines Front-End-Pools, das nur zwei Front-End-Server enthält. Ein derart kleiner Pool stellt keine robuste Lösung mit hoher Verfügbarkeit dar, wie dies bei einem größeren Pool der Fall ist, und benötigt besondere Aufmerksamkeit bei der Verwaltung. Darüber hinaus Wenn des Back End-Servers eines Pools zwei Servern ausgefallen, würde der gesamte Pool selbst wahrscheinlich bald auch ausfallen. Wenn Sie nur ein oder zwei Server mit Skype für Business Server bereitstellen möchten, wird empfohlen, dass Sie diese Funktionen als Standard Edition-Server bereitstellen.
  
Wenn Sie jemals einen Pool mit zwei Front-End-Servern bereitstellen müssen, folgen Sie diesen Richtlinien:
  
- Wenn eine der zwei Front-End-Server ausfällt, sollten Sie den fehlerhaften Server wieder verfügbar zu machen, sobald Sie können. Entsprechend sollten Sie, wenn Sie einen der beiden Server upgraden müssen, diesen Server so bald wie möglich nach Abschluss des Upgrades wieder online schalten.
    
- Falls Sie aus irgendeinem Grund beide Server gleichzeitig herunterfahren müssen, führen Sie nach Beendigung der Downtime für den Pool folgende Schritte durch:
    
  - Bewährt hat, beide Front-End-Server gleichzeitig neu zu starten. 
    
  - Ist dies nicht möglich, sollten Sie sie in der umgekehrten Reihenfolge wieder hochfahren, in der sie heruntergefahren wurden.
    
  - Wenn Sie diese in dieser Reihenfolge können nicht wieder verfügbar zu machen, verwenden Sie das folgende Cmdlet vor dem Pool sichern:`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>Front-End-Pool-Konfiguration – Fehler und Änderungen

Wenn ein Front-End-Server ausfällt und wahrscheinlich über mehrere Tage hinweg nicht ersetzt werden kann, entfernen Sie den Server aus der Topologie. Fügen Sie den neuen Front-End-Server der Topologie hinzu, sobald er wieder verfügbar ist.
  
Immer dann, wenn Sie eine Konfigurationsänderung an einem Front-End-Pool vornehmen (beispielsweise Hinzufügen oder Entfernen von Servern), müssen Sie die folgenden Richtlinien beachten:
  
- Nachdem die neue Topologie veröffentlicht wurde, müssen Sie jeden Front-End-Server im Pool neu starten. Starten Sie die Server einen nach dem anderen neu.
    
- Wenn während der konfigurationsänderung der gesamte Pool nach unten durchgeführt wurde, führen Sie das folgende Cmdlet, nachdem die neue Topologie veröffentlicht wurde:`Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
    

