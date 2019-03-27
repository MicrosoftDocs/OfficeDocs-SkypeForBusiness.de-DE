---
title: Verwalten von Disaster Recovery, hohe Verfügbarkeit und Sicherungsdienst
ms.reviewer: ''
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Informationen Sie zu Verfahren für Disaster Recovery-Vorgänge und für die Verwaltung des Sicherungsdienstes, der die Daten in einem Front-End-Pools synchronisiert.
ms.openlocfilehash: 103e0aa274e40fd997981bd6de595ceca089b710
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892413"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a>Verwalten von Skype für Business Server-Wiederherstellung, hohe Verfügbarkeit und Sicherungsdienst

Dieser Abschnitt enthält Verfahren für Disaster Recovery-Vorgänge und für die Verwaltung des Sicherungsdienstes, der die Daten in einem Front-End-Pools synchronisiert.

Verfahren für die notfallwiederherstellung, Failover und Failback und sind manuelle. Wenn ein Notfall vorhanden ist, muss der Administrator die FailoverVerfahren manuell aufrufen. Das gilt auch für Failback nach der Pool repariert wird.

Die Notfallwiederherstellungsverfahren in diesem Abschnitt wird Folgendes vorausgesetzt:

  - Sie haben eine Bereitstellung mit gekoppelten Front-End-Pools an verschiedenen Standorten befinden, wie unter [Planen für hohe Verfügbarkeit und notfallwiederherstellung](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)beschrieben. Den Sicherungsdienst wurde auf diese synchronisiert bleiben diese gekoppelten Pools ausgeführt.

  - Wenn Sie der zentralen Verwaltungsspeicher auf entweder Pool gehostet wird, ist es auf beide der gekoppelten Pools, mit einem dieser hosting aktive Masterseite Pools und das Standby-hosting Pool installiert und ausgeführt.

> [!IMPORTANT]
> In den folgenden Verfahren der Parameter *"poolfqdn"* verweist auf den FQDN des Pools, die vom Disaster betroffen ist, werden nicht auf der Pool, die Benutzer betroffen aus umgeleitet wird. Für den gleichen Satz von betroffenen Benutzer verweist es auf den gleichen Pool in Failover und Failback-Cmdlets (d. h., den Pool, die der Benutzer vor dem Failover zuerst verwaltet).<BR><br>Nehmen wir beispielsweise an einen Fall, in dem alle Benutzer in einem Pool P1 wurden mit dem Sicherungspool P2 Failover verwaltet. Wenn der Administrator möchte so verschieben Sie alle Benutzer, die aktuell verarbeitet vom P2 bis von P1 bedient werden, muss der Administrator die folgenden Schritte ausführen: 
> <OL>
> <LI>
> <P>Zurücksetzen der Benutzer verwaltet ursprünglich auf P1 aus P2 zu P1 Fail mit dem Failback-Cmdlet. In diesem Fall ist der *PoolFQDN* des P1 FQDN.</P>
> <LI>
> <P>Ausführen eines Failovers alle Benutzer ursprünglich auf P2 bis P1 verwaltet mithilfe des Failover-Cmdlet. In diesem Fall ist der PoolFQDN P2 FQDN.</P>
> <LI>
> <P>Wenn der Administrator später Failback dieser P2-Benutzer zurück zu P2 möchte, ist der PoolFQDN P2 FQDN.</P></LI></OL><br>Beachten Sie diesen Schritt 1 weiter oben ausgeführt werden muss, bevor Sie Schritt 2, um die Integrität der Pool zu erhalten. Schritt 2-Cmdlet schlägt fehl, wenn Sie versuchen, Schritt 2, bevor Sie Schritt 1.


## <a name="see-also"></a>Siehe auch

[Planen der hohen Verfügbarkeit und der Notfallwiederherstellung](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
