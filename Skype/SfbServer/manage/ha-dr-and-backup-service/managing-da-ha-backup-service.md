---
title: Verwalten von Disaster Recovery, Hochverfügbarkeits-und Sicherungsdiensten
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Informieren Sie sich über Verfahren für Disaster Recovery-Vorgänge sowie zum Verwalten des Sicherungsdiensts, der die Daten in gekoppelten Front-End-Pools synchronisiert.
ms.openlocfilehash: 9664a7d9d48ca084232e2a0473a15d29d970cea6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303898"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a>Verwalten von Skype for Business Server Disaster Recovery, Hochverfügbarkeits-und Backup-Service

Dieser Abschnitt enthält Verfahren für Wiederherstellungsvorgänge in Notfällen sowie für die Verwaltung des Sicherungsdiensts, der die Daten in gekoppelten Front-End-Pools synchronisiert.

Disaster Recovery-Verfahren, sowohl Failover als auch Failback, sind manuell. Wenn ein Notfall vorliegt, muss der Administrator die Failoververfahren manuell aufrufen. Das gleiche gilt für das Failback, nachdem der Pool repariert wurde.

Bei den Disaster Recovery-Verfahren in diesem Abschnitt wird Folgendes vorausgesetzt:

  - Sie verfügen über eine Bereitstellung mit gepaarten Front-End-Pools, die sich an verschiedenen Standorten befinden, wie unter [Planen von Höchstverfügbarkeit und Disaster Recovery](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)beschrieben. Der Sicherungsdienst wurde in diesen gekoppelten Pools ausgeführt, um sie synchron zu halten.

  - Wenn der zentrale Verwaltungsspeicher in einem der Pools gehostet wird, wird er in beiden Pools installiert und ausgeführt, wobei einer dieser Pools den aktiven Master und den anderen Pool hostet, in dem sich der Standby-Modus befindet.

> [!IMPORTANT]
> In den folgenden Verfahren bezieht sich der *PoolFQDN* -Parameter auf den FQDN des Pools, der von einem Notfall betroffen ist, nicht auf den Pool, von dem betroffene Benutzer umgeleitet werden. Für denselben Satz betroffener Benutzer verweist er sowohl in Failover-als auch in Failback-Cmdlets auf denselben Pool (also auf den Pool, der zuerst die Benutzer vor dem Failover verwaltet hat).<BR><br>Angenommen, ein Fall, in dem alle Benutzer, die sich in einem Pool P1 befanden, auf den Sicherungspool P2 umgestellt wurden. Wenn der Administrator alle Benutzer verschieben möchte, die von P2 aktuell gewartet werden, um von P1 gewartet zu werden, muss der Administrator die folgenden Schritte ausführen: 
> <OL>
> <LI>
> <P>Führen Sie mithilfe des Failback-Cmdlets alle Benutzer, die sich ursprünglich auf P1 benetzten, von P2 zu P1 zurück. In diesem Fall ist der *PoolFQDN* P1's-FQDN.</P>
> <LI>
> <P>Über das Failover-Cmdlet können alle Benutzer, die sich ursprünglich auf P2 mit P1 befanden, einen Failover durchführen. In diesem Fall ist der PoolFQDN P2-FQDN.</P>
> <LI>
> <P>Wenn der Administrator später diese P2-Benutzer wieder in P2 zurücksetzen möchte, ist der PoolFQDN P2-FQDN.</P></LI></OL><br>Beachten Sie, dass Schritt 1 oben vor Schritt 2 ausgeführt werden muss, um die Pool Integrität beizubehalten. Wenn Sie Schritt 2 vor Schritt 1 versuchen, tritt das Cmdlet "Schritt 2" nicht auf.


## <a name="see-also"></a>Siehe auch

[Planen der hohen Verfügbarkeit und der Notfallwiederherstellung](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
