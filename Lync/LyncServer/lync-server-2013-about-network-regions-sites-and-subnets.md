---
title: 'Lync Server 2013: Informationen zu Netzwerkregionen, Standorten und Subnetzen'
TOCTitle: Informationen zu Netzwerkregionen, Standorten und Subnetzen
ms:assetid: 6662123a-d011-408c-a290-92b2a8589943
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398467(v=OCS.15)
ms:contentKeyID: 49294241
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Informationen zu Netzwerkregionen, Standorten und Subnetzen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-24_

Für die in diesem Abschnitt beschriebenen erweiterten Enterprise-VoIP-Funktionen gelten einige gemeinsame Konfigurationsanforderungen für Netzwerkregionen, Netzwerkstandorte und Subnetze. Beispielsweise ist es für alle drei erweiterten Funktionen erforderlich, dass jedes Subnetz in Ihrer Topologie einem bestimmten *Netzwerkstandort* und jeder Netzwerkstandort einer *Netzwerkregion* zugeordnet wird.


> [!IMPORTANT]
> Bevor Sie mit der Netzwerkkonfiguration für die Anrufsteuerung, E9-1-1 oder Medienumgehung beginnen, stellen Sie sicher, dass Sie sich mit den zusätzlichen Informationen zu Netzwerkeinstellungen in dem Thema <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Netzwerkeinstellungen für die erweiterten Enterprise-VoIP-Funktionen in Lync Server 2013</A> in der Planungsdokumentation vertraut gemacht haben. Ausführliche Informationen zur Netzwerkkonfiguration, die sich in erster Linie auf die Anrufsteuerung beziehen, finden Sie zudem unter <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definieren der Anforderungen Ihrer Organisation für die Anrufsteuerung in Lync Server 2013</A> in der Planungsdokumentation.



Für die Anrufsteuerung und E9-1-1 gelten bei den Netzwerkstandorten zusätzliche Konfigurationsanforderungen:

  - Die Anrufsteuerung erfordert, dass ein *Bandbreitenrichtlinienprofil* für jeden Standort angegeben wird, für den WAN-Bandbreiteneinschränkungen gelten. Wenn Sie planen, Anrufsteuerung bereitzustellen, müssen Sie die unter [Erstellen von Bandbreitenrichtlinienprofilen in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md) aufgeführten Schritte durchführen, bevor Sie Ihre Netzwerkstandorte konfigurieren.

  - Für E9-1-1 ist es erforderlich, dass für jeden Standort eine *Standortrichtlinie* angegeben ist. Wenn Sie planen, E9-1-1 bereitzustellen, müssen Sie die unter [Erstellen von Ortungsrichtlinien in Lync Server 2013](lync-server-2013-create-location-policies.md) aufgeführten Schritte durchführen, bevor Sie Ihre Netzwerkstandorte konfigurieren.

## Erstellen oder Ändern von Netzwerkregionen, Netzwerkstandorten und Subnetzen

In den folgenden Themen werden die Schritte zum Erstellen oder Ändern von Netzwerkregionen und Netzwerkstandorten sowie zum Zuordnen von Subnetzen zu Netzwerkstandorten beschrieben. Diese Themen sind nicht auf eine bestimmte erweiterte Enterprise-VoIP-Funktion beschränkt.

  - [Erstellen oder Ändern einer Netzwerkregion in Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md)

  - [Erstellen oder Ändern eines Netzwerkstandorts in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)

  - [Zuordnen eines Subnetzes zu einem Netzwerkstandort in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)

