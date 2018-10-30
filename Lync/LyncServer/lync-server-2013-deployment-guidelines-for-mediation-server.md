---
title: 'Lync Server 2013: Richtlinien für die Vermittlungsserverbereitstellung'
TOCTitle: Richtlinien für die Vermittlungsserverbereitstellung
ms:assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398622(v=OCS.15)
ms:contentKeyID: 49294527
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Richtlinien für die Vermittlungsserverbereitstellung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

In diesem Thema werden einige Richtlinien für die Planung einer Vermittlungsserver-Bereitstellung beschrieben. Nachdem Sie diese Richtlinien gelesen haben, sollten Sie das Planungstool zum Erstellen und Anzeigen möglicher alternativer Topologien verwenden, die als Modelle für Ihre endgültige, individuell angepasste Bereitstellungstopologie dienen können.

## Verbundene Vermittlungsserver im Vergleich zu eigenständigen Vermittlungsservern

Der Vermittlungsserver ist standardmäßig mit anderen Servern auf dem Standard Edition-Server oder Front-End-Server in einem Front-End-Pool an zentralen Standorten verbunden. Die Anzahl von Anrufen über das Telefonfestnetz (Public Switched Telephone Network, PSTN), die verarbeitet werden können, und die Anzahl von erforderlichen Computern im Pool hängt von folgenden Faktoren ab:

  - Anzahl von Gatewaypeers, die der Vermittlungsserverpool steuert

  - Datenverkehr zu Spitzenzeiten, der über diese Gateways verarbeitet wird

  - Der Prozentsatz an Anrufen, deren Medien den Vermittlungsserver umgehen

Berücksichtigen Sie bei der Planung unbedingt die Medienverarbeitungsanforderungen für PSTN-Anrufe und für A/V-Konferenzen, die nicht für eine Medienumgehung konfiguriert sind, sowie die erforderliche Leistung zur Verarbeitung von Signalinteraktionen für die Anzahl von Anrufen zu Spitzenzeiten, die unterstützt werden müssen. Wenn nicht genügend CPU-Kapazität verfügbar ist, müssen Sie einen eigenständigen Pool aus Vermittlungsserver bereitstellen, und PSTN-Gateways, IP-Nebenstellenanlagen und SBCs müssen in Teilmengen gegliedert werden, die von den verbundenen Vermittlungsserver in einem Pool und den eigenständigen Vermittlungsserver in einem oder mehreren eigenständigen Pools gesteuert werden.

Bei Bereitstellung von PSTN-Gateways, IP-Nebenstellenanlagen oder SBCs (Session Border Controller) ohne Unterstützung für die erforderlichen Funktionen zur Interaktion mit einem Pool aus Vermittlungsserver (u. a. die im Folgenden aufgeführten) müssen diese Komponenten einem eigenständigen Pool mit nur einem einzelnen Vermittlungsserver zugeordnet werden:

  - Durchführen von DNS-Lastenausgleich (Domain Name System) in der Vermittlungsschicht für die Vermittlungsserver in einem Pool (oder anderweitige einheitliche Weiterleitung des Datenverkehrs an alle Vermittlungsserver in einem Pool)

  - Akzeptieren von Datenverkehr von jedem Vermittlungsserver in einem Pool

Sie können mithilfe des Microsoft Lync Server 2013, Planungstools herausfinden, ob der Vermittlungsserver, den Sie mit Ihrem Front-End-Pool verbinden möchten, die Last bewältigen kann. Falls Ihre Umgebung diese Anforderungen nicht erfüllen kann, müssen Sie einen eigenständigen Vermittlungsserverpool bereitstellen.

## Überlegungen zum zentralen Standort und Zweigstellenstandort

Vermittlungsserver am zentralen Standort können zum Weiterleiten von Anrufen für IP-Nebenstellenanlagen oder PSTN-Gateways an Zweigstellenstandorten verwendet werden. Bei der Bereitstellung von SIP-Trunks müssen Sie jedoch einen Vermittlungsserver an dem Standort bereitstellen, der als Endpunkt für die einzelnen Trunks dient. Beim Einsatz eines Vermittlungsservers am zentralen Standort zum Weiterleiten von Anrufen für eine IP-Nebenstellenanlage oder ein PSTN-Gateway an einem Zweigstellenstandort ist keine Medienumgehung erforderlich. Wenn Sie die Medienumgehung jedoch aktivieren können, wird die Latenz für den Medienpfad reduziert und somit eine bessere Medienqualität erreicht, da der Medienpfad nicht länger dem Signalpfad folgen muss. Zudem wird durch die Medienumgehung die Verarbeitungslast des Pools verringert.


> [!NOTE]
> Die Medienumgehung funktioniert nicht mit allen PSTN-Gateways, IP-Nebenstellenanlagen oder SBCs. Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet und einige Tests mit IP-Nebenstellenanlagen von Cisco durchgeführt. Die Medienumgehung wird nur für die Produkte und Versionen unterstützt, die auf der Webseite für das Unified Communications Open Interoperability Program \endash Lync Server unter <A class=uri href="http://go.microsoft.com/fwlink/?linkid=268730">http://go.microsoft.com/fwlink/?linkid=268730</A> aufgelistet werden.



Wenn Ausfallsicherheit für Zweigstellenstandorte erforderlich ist, muss eine Survivable Branch-Anwendung oder eine Kombination aus einem Front-End-Server, einem Vermittlungsserver und einem Gateway am Zweigstellenstandort bereitgestellt werden. (Bei der Ausfallsicherheit für Zweigstellenstandorte wird davon ausgegangen, dass am jeweiligen Standort keine Ausfallsicherheit für Anwesenheitsinformationen und Konferenzfunktionen implementiert ist.) Anleitungen zur VoIP-Planung für Zweigstellen finden Sie unter [Planen von VoIP-Ausfallsicherheit für Zweigstellen in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).

Wenn bei Interaktionen mit einer IP-Nebenstellenanlage die IP-Nebenstellenanlage frühe Medieninteraktionen mit mehreren frühen Dialogen und RFC 3960-Interaktionen nicht ordnungsgemäß unterstützt, werden die ersten Grußworte bei eingehenden Anrufen von der IP-Nebenstellenanlage an Lync-Endpunkte möglicherweise abgeschnitten. Dieses Verhalten kann verstärkt werden, wenn ein Vermittlungsserver an einem zentralen Standort Anrufe für eine IP-Nebenstellenanlage weiterleitet und die Route an einem Zweigstellenstandort endet. Dies ist dadurch begründet, dass mehr Zeit zur Übertragung des Signaldatenverkehrs benötigt wird. Wenn dieses Verhalten auftritt, ist die Bereitstellung eines Vermittlungsservers am Zweigstellenstandort die einzige Möglichkeit, um das Abschneiden der ersten Grußworte zu reduzieren.

Wenn der zentrale Standort über eine TDM-Nebenstellenlage verfügt oder die Notwendigkeit eines PSTN-Gateways durch die IP-Nebenstellenanlage nicht eliminiert wird, müssen Sie ein Gateway zur Anrufroute hinzufügen, das mit dem Vermittlungsserver und der Nebenstellenanlage verbunden ist.


> [!NOTE]
> Um die Medienqualität von eigenständigen Vermittlungsservern zu verbessern, sollten Sie RSS (Receive-Side Scaling) für die Netzwerkadapter dieser Server aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Für ausführliche Informationen lesen Sie "Receive-Side Scaling Enhancements in Windows Server" unter <A class=uri href="http://go.microsoft.com/fwlink/?linkid=268731">http://go.microsoft.com/fwlink/?linkid=268731</A>. Weitere Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.


