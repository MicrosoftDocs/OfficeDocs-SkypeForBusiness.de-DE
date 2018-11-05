---
title: 'Lync Server 2013: SIP-Trunking für Zweigstellenstandorte'
TOCTitle: SIP-Trunking für Zweigstellenstandorte
ms:assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412974(v=OCS.15)
ms:contentKeyID: 49295344
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# SIP-Trunking für Zweigstellenstandorte in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

In einigen Fällen ist es möglicherweise erforderlich, an ausgewählten Zweigstellen ein verteiltes SIP-Trunking zu implementieren. Zum Ermitteln, ob ein SIP-Trunk für eine Zweigstelle erforderlich ist, lesen Sie die Informationen unter [Implementierung von SIP-Trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).

Ausführliche Informationen zu den unterstützten Topologieoptionen für die Bereitstellung von SIP-Trunks in Zweigstellen finden Sie unter [Ausfallsicherheitslösungen für Zweigstellenstandorte in Lync Server 2013](lync-server-2013-branch-site-resiliency-solutions.md).

## Beispielanalyse für die SIP-Trunkanforderungen an einer Zweigniederlassung

Wenn Sie einen SIP-Trunk in einer Zweigstelle bereitstellen möchten, müssen Sie eine standortspezifische Kostenanalyse vornehmen. Beispiel: ein Unternehmen mit einem zentraler Standort in Redmond, Washington, und einer Zweigstelle in New York sollte eine Analyse ausführen, um zu ermitteln, ob eine SIP-Trunkverbindung zwischen dem Standort in New York und einem lokalen Dienstanbieter implementiert werden sollte.

Um festzustellen, ob ein verteilter SIP-Trunk in New York eine kosteneffektive Option ist, muss ermittelt werden, welche DID-Nummern (Direct Inward Dialing) den SIP-Trunk verwenden. Zudem muss die Anzahl von Anrufen analysiert werden, die vom Standort in New York an andere Bereiche als Redmond (425) getätigt werden. Die DID-Terminierung für die Zweigstelle kann am zentraler Standort erfolgen. Über den zentraler Standort in Redmond können z. B. DID-Nummern für die Zweigstelle in New York gehostet werden. Wenn die Kosten für die Implementierung eines verteilten SIP-Trunks geringer sind als die Kosten für diese Anrufe, sollten Sie die Implementierung eines SIP-Trunks in der Zweigstelle in New York in Betracht ziehen.

## Weitere SIP-Trunkanforderungen für Zweigniederlassungen

Die Entscheidung, ob anstelle eines Gateways ein SIP-Trunk bereitgestellt werden sollte, hängt von der Kostendifferenz bei Ferngesprächen der einzelnen Optionen ab. Bei Bereitstellung eines SIP-Trunks für eine Zweigstelle müssen Sie zusätzlich Ihre Anforderungen im Hinblick auf Ausfallsicherheit und Bandbreite ermitteln. Wenn die Verbindung zwischen Ihrer Zweigstelle und dem zentraler Standort ausfallsicher ist und über genügend Bandbreite verfügt, können Sie einen SIP-Trunk oder ein Gateway bereitstellen. Die Bereitstellung einer Survivable Branch-Anwendung in der Zweigstelle ist nicht erforderlich. Wenn die Verbindung zwischen Ihrer Zweigstelle und dem zentraler Standort nicht ausfallsicher ist, stellen Sie eine Survivable Branch-Anwendung oder einen Survivable Branch-Server entweder mit einem Gateway oder mit einem SIP-Trunk in der Zweigstelle bereit.

