---
title: Hohe Verfügbarkeit und Verwaltung von Front-End-Pools
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: Erfahren Sie mehr über die Verwaltung von Front-End-Pools in Skype for Business Server, einschließlich Verwalten von Pools, Quorum Verlust und speziellen Schritten für Pools mit nur zwei Front-End-Servern.
ms.openlocfilehash: e42e192d224d509356203c059751624fc706707b
ms.sourcegitcommit: a6e44256c024fc3953cfd6a511ee024c4c7b8408
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047092"
---
# <a name="front-end-pool-high-availability-and-management"></a>Hohe Verfügbarkeit und Verwaltung von Front-End-Pools
 
Erfahren Sie mehr über die Verwaltung von Front-End-Pools in Skype for Business Server, einschließlich Verwalten von Pools, Quorum Verlust und speziellen Schritten für Pools mit nur zwei Front-End-Servern.
  
In Skype for Business Server verwendet die Architektur der Front-End-Pools ein Modell mit verteilten Systemen, wobei die Daten jedes Benutzers auf bis zu drei Front-End-Servern im Pool aufbewahrt werden. Wir empfehlen, dass alle Ihre Enterprise Edition-Front-End-Pools mindestens drei Front-End-Server enthalten. 
  
## <a name="planning-for-the-management-of-front-end-pools"></a>Planen der Verwaltung von Front-End-Pools

 Für Skype for Business Server wird ein Modell für verteilte Systeme verwendet, das auf Windows-Fabric basiert. In diesem Modell werden wichtige Daten für jeden Benutzer und jede Konferenz auf drei Front-End-Servern in einem Front-End-Pool gespeichert. Diese drei Server, die einen bestimmten Satz von Daten speichern, sind calledreplicas.
  
Mit dem verteilten Modell für Front-End-Pools müssen eine bestimmte Anzahl von Servern eines Pools ausgeführt werden, damit der Pool funktioniert. Für einen Pool gibt es zwei Verlust Modi.
  
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
   
Bei jedem nachfolgenden Start des Pools sollten 85 % der Server gestartet werden (wie in der vorstehenden Tabelle gezeigt). Wenn diese Anzahl von Servern nicht gestartet werden kann (aber genügend Server gestartet werden können, damit Sie nicht auf einem Quorum Verlust auf Poolebene sind), können Sie `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` das Cmdlet verwenden, um den Pool zu aktivieren, um den Quorum Verlust auf Routinggruppen Ebene wiederherzustellen und Fortschritte zu erzielen. Weitere Informationen zur Verwendung dieses Cmdlets finden Sie unter [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps). 
  
> [!NOTE]
> In Pools mit einer geraden Anzahl von Servern verwendet Skype for Business Server die primäre SQL-Datenbank als Zeuge. Wenn Sie in einem solchen Pool die primäre Datenbank herunterfahren, zur Spiegelkopie wechseln und ausreichend Front-End-Server herunterfahren, sodass (entsprechend der vorstehenden Tabelle) nicht genügend von ihnen aktiv sind, fällt der gesamte Pool aus. Weitere Informationen finden Sie unter [Daten Bank Spiegelungs Zeuge](https://go.microsoft.com/fwlink/?LinkId=393672). 
  
#### <a name="pool-level-quorum-loss"></a>Quorumverlust auf Poolebene

Damit ein Front-End-Pool überhaupt funktioniert, kann er keinen Quorum Verlust auf Poolebene aufweisen. Unterschreitet die Anzahl der aktiven Server die in der folgenden Tabelle gezeigte Funktionsebene, halten die im Pool verbleibenden Server alle Skype for Business Server-Dienste an. Beachten Sie, dass die Zahlen in der folgenden Tabelle davon ausgehen, dass die Back-End-Server im Pool ausgeführt werden.
  
|Gesamtzahl der Front-End-Server im Pool  <br/> |Anzahl der Server, die aktiv sein müssen, damit der Pool funktioniert  <br/> |
|:-----|:-----|
|2  <br/> |1  <br/> |
|3-4  <br/> |Beliebige 2  <br/> |
|5-6  <br/> |Beliebige 3  <br/> |
|7  <br/> |Beliebige 4  <br/> |
|8-9  <br/> |Beliebige 4 der ersten 7 Server  <br/> |
|10-12  <br/> |Beliebige 5 der ersten 9 Server  <br/> |
   
In der vorstehenden Tabelle sind die "ersten Server" die Server, die in chronologischer Reihenfolge beim ersten Start des Pools aufgeholt wurden. Um diese Server zu ermitteln, können Sie das `Get-CsComputer` Cmdlet mit der `-PoolFqdn` Option verwenden. Dieses Cmdlet zeigt die Server in der Reihenfolge an, in der Sie in der Topologie angezeigt werden, und die oben in der Liste sind die ersten Server.
  
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>Zusätzliche Schritte, um zu bestimmen, dass Pools funktionsbereit sind

Sie sollten auf eine Reihe anderer Faktoren achten, um sicherzustellen, dass Ihre Front-End-Pools funktionsbereit bleiben.
  
- Wenn Sie Benutzer zum ersten Mal in den Pool verschieben, stellen Sie sicher, dass mindestens drei der Front-End-Server ausgeführt werden.
    
- Wenn Sie eine Paarbeziehung zwischen diesem Pool und einem anderen Pool zum Zweck der Notfallwiederherstellung konfigurieren, müssen Sie nach dem Erstellen dieser Beziehung sichergehen, dass in diesem Pool zu einem beliebigen Zeitpunkt drei Front-End-Server gleichzeitig ausgeführt werden, damit Daten korrekt mit dem Sicherungspool synchronisiert werden. Weitere Informationen zu Pool-Kopplungs-und Disaster Recovery-Features finden Sie unter [Planen von Höchstverfügbarkeit und Disaster Recovery in Skype for Business Server](high-availability-and-disaster-recovery.md). 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>Front-End-Pool mit zwei Front-End-Servern

Wir empfehlen nicht die Bereitstellungeines Front-End-Pools, in dem nur zwei Front-End-Server enthalten sind. Ein derart kleiner Pool stellt keine robuste Lösung mit hoher Verfügbarkeit dar, wie dies bei einem größeren Pool der Fall ist, und benötigt besondere Aufmerksamkeit bei der Verwaltung. Wenn der Back-End-Server eines Pools mit zwei Servern ebenfalls abstürzte, würde der gesamte Pool selbst wahrscheinlich bald auch nach unten gehen. Wenn Sie nur einen oder zwei Server mit Skype for Business Server bereitstellen möchten, empfehlen wir, diese als Standard Edition-Server bereitzustellen.
  
Wenn Sie jemals einen Pool mit zwei Front-End-Servern bereitstellen müssen, befolgen Sie diese Richtlinien:
  
- Wenn einer der beiden Front-End-Server ausfällt, sollten Sie versuchen, den fehlerhaften Server so schnell wie möglich wieder aufzunehmen. Entsprechend sollten Sie, wenn Sie einen der beiden Server upgraden müssen, diesen Server so bald wie möglich nach Abschluss des Upgrades wieder online schalten.
    
- Falls Sie aus irgendeinem Grund beide Server gleichzeitig herunterfahren müssen, führen Sie nach Beendigung der Downtime für den Pool folgende Schritte durch:
    
  - Die bewährte Vorgehensweise besteht darin, beide Front-End-Server gleichzeitig neu zu starten. 
    
  - Ist dies nicht möglich, sollten Sie sie in der umgekehrten Reihenfolge wieder hochfahren, in der sie heruntergefahren wurden.
    
  - Wenn Sie Sie nicht in dieser Reihenfolge sichern können, verwenden Sie das folgende Cmdlet, bevor Sie den Pool sichern:`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>Front-End-Pool-Konfiguration – Fehler und Änderungen

Wenn ein Front-End-Server ausfällt und wahrscheinlich über mehrere Tage hinweg nicht ersetzt werden kann, entfernen Sie den Server aus der Topologie. Fügen Sie den neuen Front-End-Server der Topologie hinzu, sobald er wieder verfügbar ist.
  
Immer dann, wenn Sie eine Konfigurationsänderung an einem Front-End-Pool vornehmen (beispielsweise Hinzufügen oder Entfernen von Servern), müssen Sie die folgenden Richtlinien beachten:
  
- Nachdem die neue Topologie veröffentlicht wurde, müssen Sie jeden Front-End-Server im Pool neu starten. Starten Sie die Server einen nach dem anderen neu.
    
- Wenn der gesamte Pool während der Konfigurationsänderung inaktiv war, führen Sie nach der Veröffentlichung der neuen Topologie das folgende Cmdlet aus:`Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
    

