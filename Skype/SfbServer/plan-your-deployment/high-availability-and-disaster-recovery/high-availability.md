---
title: Hohe Verfügbarkeit und Verwaltung von Front-End-Pools
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: Learn about Front End pool management in Skype for Business Server, including managing pools, quorum loss, and special steps for pools with only two Front End Servers.
ms.openlocfilehash: f348fcc4fee6a48a41265da88fe432d9e4550b6c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="front-end-pool-high-availability-and-management"></a>Hohe Verfügbarkeit und Verwaltung von Front-End-Pools
 
Learn about Front End pool management in Skype for Business Server, including managing pools, quorum loss, and special steps for pools with only two Front End Servers.
  
In Skype for Business Server, the architecture of Front End pools uses a distributed systems model, with each user's data kept on as many as three Front End servers in the pool. We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers. 
  
## <a name="planning-for-the-management-of-front-end-pools"></a>Planen der Verwaltung von Front-End-Pools

 Skype for Business Server uses a distributed systems model based on Windows Fabric. In this model, important data for each user and conference is stored on three Front End Servers in a Front End pool. These three servers storing a certain set of data are calledreplicas.
  
With the distributed model for Front End pools, a certain numbers of a pool's servers must be running for the pool to function. There are two loss modes for a pool.
  
- Routing Group Level quorum loss, caused by not enough replica servers for a particular routing group. Bei einer Routinggruppe handelt es sich um eine Gruppe von Benutzern, die im Pool verwaltet werden. Jede Routinggruppe verfügt über drei Replikate im Pool: ein primäres und zwei sekundäre Replikate.
    
- Pool Level quorum loss, caused when not enough seed servers are running in the pool. 
    
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
   
Bei jedem nachfolgenden Start des Pools sollten 85 % der Server gestartet werden (wie in der vorstehenden Tabelle gezeigt). If this number of servers cannot be started (but enough servers can be started so that you are not at pool-level quorum loss), you can use the  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` cmdlet to enable the pool to recover from this routing group level quorum loss and make progress. For more information about how to use this cmdlet, see <link Reset-CsPoolRegistrarState>.
  
> [!NOTE]
> In Pools mit einer geraden Anzahl von Servern verwendet Skype for Business Server die primäre SQL-Datenbank als Zeuge. Wenn Sie in einem solchen Pool die primäre Datenbank herunterfahren, zur Spiegelkopie wechseln und ausreichend Front-End-Server herunterfahren, sodass (entsprechend der vorstehenden Tabelle) nicht genügend von ihnen aktiv sind, fällt der gesamte Pool aus. For more information, see [Database Mirroring Witness](https://go.microsoft.com/fwlink/?LinkId=393672). 
  
#### <a name="pool-level-quorum-loss"></a>Quorumverlust auf Poolebene

For a Front End pool to function at all, it cannot be in pool-level quorum loss. Unterschreitet die Anzahl der aktiven Server die in der folgenden Tabelle gezeigte Funktionsebene, halten die im Pool verbleibenden Server alle Skype for Business Server-Dienste an. Note that the numbers in the following table assume that the Back End Servers in the pool are running.
  
|Total number of Front End Servers in the pool  <br/> |Anzahl der Server, die aktiv sein müssen, damit der Pool funktioniert  <br/> |
|:-----|:-----|
|2  <br/> |1  <br/> |
|3-4  <br/> |Beliebige 2  <br/> |
|5-6  <br/> |Beliebige 3  <br/> |
|7  <br/> |Beliebige 4  <br/> |
|8-9  <br/> |Beliebige 4 der ersten 7 Server  <br/> |
|10-12  <br/> |Beliebige 5 der ersten 9 Server  <br/> |
   
In the preceding table, the "first servers" are the servers which were brought up first, chronologically, when the pool was started for the first time. To determine these servers, you can use the  `Get-CsComputer` cmdlet with the ` -PoolFqdn` option. This cmdlet will show the servers in the order that they appear in the topology, and the ones at the top of the list are the first servers.
  
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>Zusätzliche Schritte, um zu bestimmen, dass Pools funktionsbereit sind

Sie sollten auf eine Reihe anderer Faktoren achten, um sicherzustellen, dass Ihre Front-End-Pools funktionsbereit bleiben.
  
- When you move users to the pool for the first time, be sure at least three of the Front End Servers are running.
    
- Wenn Sie eine Paarbeziehung zwischen diesem Pool und einem anderen Pool zum Zweck der Notfallwiederherstellung konfigurieren, müssen Sie nach dem Erstellen dieser Beziehung sichergehen, dass in diesem Pool zu einem beliebigen Zeitpunkt drei Front-End-Server gleichzeitig ausgeführt werden, damit Daten korrekt mit dem Sicherungspool synchronisiert werden. For more information on pool pairing and disaster recovery features, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](high-availability-and-disaster-recovery.md). 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>Front-End-Pool mit zwei Front-End-Servern

We do not recommend deploying a Front End pool that contains only two Front End Servers. Ein derart kleiner Pool stellt keine robuste Lösung mit hoher Verfügbarkeit dar, wie dies bei einem größeren Pool der Fall ist, und benötigt besondere Aufmerksamkeit bei der Verwaltung. Additionally, if the Back End Server of a two-server pool went down, the whole pool itself would likely soon go down as well. If you want to deploy just one or two servers running Skype for Business Server, we recommend you deploy them as Standard Edition servers.
  
If you do ever need to deploy a pool with two Front End Servers, follow these guidelines:
  
- If one of the two Front End Servers goes down, you should try to bring the failed server back up as soon as you can. Entsprechend sollten Sie, wenn Sie einen der beiden Server upgraden müssen, diesen Server so bald wie möglich nach Abschluss des Upgrades wieder online schalten.
    
- Falls Sie aus irgendeinem Grund beide Server gleichzeitig herunterfahren müssen, führen Sie nach Beendigung der Downtime für den Pool folgende Schritte durch:
    
  - The best practice is to restart both Front End Servers at the same time. 
    
  - Ist dies nicht möglich, sollten Sie sie in der umgekehrten Reihenfolge wieder hochfahren, in der sie heruntergefahren wurden.
    
  - If you cannot bring them back up in that order, then use the following cmdlet before bringing the pool back up:  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>Front-End-Pool-Konfiguration – Fehler und Änderungen

Wenn ein Front-End-Server ausfällt und wahrscheinlich über mehrere Tage hinweg nicht ersetzt werden kann, entfernen Sie den Server aus der Topologie. Fügen Sie den neuen Front-End-Server der Topologie hinzu, sobald er wieder verfügbar ist.
  
Immer dann, wenn Sie eine Konfigurationsänderung an einem Front-End-Pool vornehmen (beispielsweise Hinzufügen oder Entfernen von Servern), müssen Sie die folgenden Richtlinien beachten:
  
- Nachdem die neue Topologie veröffentlicht wurde, müssen Sie jeden Front-End-Server im Pool neu starten. Starten Sie die Server einen nach dem anderen neu.
    
- If the entire pool has been down during the configuration change, then run the following cmdlet after the new topology is published:  `Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
    

