---
title: Verwalten von Notfallwiederherstellung, hoher Verfügbarkeit und Sicherungsdienst
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Erfahren Sie mehr über Verfahren für Notfallwiederherstellungsvorgänge sowie für die Verwaltung des Sicherungsdiensts, der die Daten in gekoppelten Front-End-Pools synchronisiert.
ms.openlocfilehash: e486a71203b64b4fc351888869ac64a24689ba7b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817155"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a>Verwalten von Notfallwiederherstellung, hoher Verfügbarkeit und Sicherungsdienst für Skype for Business Server

Dieser Abschnitt enthält Verfahren für Notfallwiederherstellungsvorgänge sowie für die Verwaltung des Sicherungsdiensts, der die Daten in gekoppelten Front-End-Pools synchronisiert.

Die Verfahren zur Notfallwiederherstellung, sowohl Failover als auch Failback, sind manuell. Bei einem Notfall muss der Administrator die Failoverprozeduren manuell aufrufen. Dasselbe gilt für failback nach der Reparatur des Pools.

Bei den Verfahren zur Notfallwiederherstellung in diesem Abschnitt wird Folgendes vorausgesetzt:

  - Sie verfügen über eine Bereitstellung mit gekoppelten Front-End-Pools, die sich an unterschiedlichen Standorten befinden, wie unter [Plan for high availability and disaster recovery beschrieben.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) Der Sicherungsdienst wurde in diesen Paarpools ausgeführt, um sie synchron zu halten.

  - Wenn der zentrale Verwaltungsspeicher in einem der Pools gehostet wird, wird er in beiden Paarpools installiert und ausgeführt, und einer dieser Pools hostet den aktiven Master und der andere Pool hostet den Standbymodus.

> [!IMPORTANT]
> In den folgenden Verfahren bezieht sich der Parameter *"PoolFQDN"* auf den FQDN des Pools, der von einem Notfall betroffen ist, nicht auf den Pool, von dem die betroffenen Benutzer umgeleitet werden. Bei denselben betroffenen Benutzern bezieht sich dies sowohl in Failover- als auch in Failback-Cmdlets auf denselben Pool (d. h. auf den Pool, in dem die Benutzer zuerst vor dem Failover zu Hause waren).<BR><br>Nehmen wir beispielsweise einen Fall an, in dem alle Benutzer, die in einem Pool P1 gespeichert sind, auf den Sicherungspool P2 überfehlt wurden. Wenn der Administrator alle benutzer verschieben möchte, die derzeit von P2 für die Dienstverwaltung von P1 verwendet werden, muss der Administrator die folgenden Schritte ausführen: 
> <OL>
> <LI>
> <P>Führen Sie mithilfe des Failback-Cmdlets ein Failback für alle Benutzer durch, die ursprünglich auf P1 von P2 zu P1 verwendet wurden. In diesem Fall ist *der PoolFQDN* der FQDN von P1.</P>
> <LI>
> <P>Führen Sie mithilfe des Failover-Cmdlets ein Failover für alle Benutzer durch, die ursprünglich auf P2 zu P1 vorhanden waren. In diesem Fall ist der PoolFQDN der FQDN von P2.</P>
> <LI>
> <P>Wenn der Administrator später ein Fail back für diese P2-Benutzer auf P2 ausführen möchte, ist der PoolFQDN der FQDN von P2.</P></LI></OL><br>Beachten Sie, dass Schritt 1 oben vor Schritt 2 ausgeführt werden muss, um die Poolintegrität zu erhalten. Wenn Sie Schritt 2 vor Schritt 1 ausprobieren, tritt beim Cmdlet schritt 2 ein Fehler auf.


## <a name="see-also"></a>Siehe auch

[Planen von hoher Verfügbarkeit und Notfallwiederherstellung](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
