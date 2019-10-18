---
title: Quality of Service in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: Serdars
ms.date: 12/17/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Bereiten Sie das Netzwerk Ihrer Organisation für Quality of Service (QoS) in Microsoft Teams vor.
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.meetingsettings.qos
- ms.teamsadmincenter.meetingsettings.network.qosmarkers
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: efa2dfadc760d99f87d8d69137992712c90b32ef
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37567147"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>Implementieren von Quality of Service (QoS) in Microsoft Teams

Dieser Artikel unterstützt Sie beim Vorbereiten des Netzwerks Ihrer Organisation auf QoS (Quality of Service) in Microsoft Teams. Wenn Sie eine große Gruppe von Benutzern unterstützen und die unten aufgeführten Probleme auftreten, müssen Sie wahrscheinlich QoS implementieren. Ein kleines Unternehmen mit wenigen Benutzern braucht möglicherweise keine QoS, aber auch dort sollte es hilfreich sein.

QoS ist eine Möglichkeit, um Netzwerkdatenverkehr in Echtzeit (wie Sprach-oder Videostreams) zu ermöglichen, die für Netzwerkverzögerungen anfällig sind, um vor dem Verkehr, der weniger sensibel ist (wie beim Herunterladen einer neuen App, bei denen eine zusätzliche Sekunde zum herunterladen keine große Sache ist), "in der Schlange zu schneiden". QoS identifiziert und markiert alle Pakete in Echtzeit-Streams (unter Verwendung von Windows-Gruppenrichtlinienobjekten und einem Routing-Feature namens Port basierten Zugriffskontrolllisten, weitere Informationen dazu finden Sie unten), die dann dazu beitragen, dass Ihr Netzwerk sprach-, Video-und Bildschirmfreigabe Datenströme a erhält. dedizierter Anteil an Netzwerkbandbreite.

Ohne eine Art von QoS sehen Sie möglicherweise die folgenden Qualitätsprobleme in Sprache und Video:

- Jitter – Medienpakete, die zu unterschiedlichen Tarifen ankommen, was zu fehlenden Wörtern oder Silben bei Anrufen führen kann.
- Paketverlust – Pakete fallen ab, was auch zu einer niedrigeren Sprachqualität und zu einer schwer verständlichen Sprache führen kann.
- Verzögerte Roundtrip-Zeit (RTT) – Medienpakete dauern lange, bis Sie Ihre Ziele erreicht haben, was zu spürbaren Verzögerungen zwischen zwei Teilnehmern in einer Unterhaltung führt, die dazu führen, dass sich die Gesprächspartner über einander unterhalten.

Die am wenigsten komplexe Möglichkeit, diese Probleme zu beheben, besteht darin, die Größe der Datenverbindungen sowohl intern als auch über das Internet zu erhöhen. Da dies oft Kosten unerschwinglich ist, bietet QoS eine Möglichkeit, die Ressourcen effektiver zu verwalten, anstatt neue Ressourcen hinzuzufügen. Zur vollständigen Behebung von Qualitätsproblemen verwenden Sie QoS in der gesamten Implementierung, und fügen Sie dann nur dann Konnektivität hinzu, wenn dies absolut notwendig ist.

Damit QoS effektiv ist, haben Sie in Ihrer Organisation die konsistenten QoS-Einstellungen angewendet, da ein Teil des Pfads, der Ihre QoS-Prioritäten nicht unterstützt, die Qualität von anrufen, Video und Bildschirm Freigaben beeinträchtigen kann. Dazu gehören das Anwenden von Einstellungen auf alle Benutzer-PCs oder-Geräte, Netzwerk-Switches, Router zum Internet und der Online-Service von Teams.

_Abbildung 1 Die Beziehung zwischen den Netzwerken einer Organisation und den Office 365-Diensten_

![Abbildung der Beziehung zwischen Netzwerken und Diensten](media/Qos-in-Teams-Image1.png "Die Beziehung zwischen den Netzwerken einer Organisation und den Office 365-Diensten: lokales Netzwerk und Geräte stellen eine Verbindung mit einem Interconnect-Netzwerk her, das wiederum eine Verbindung mit Office 365 Cloud-VoIP-und-Audiokonferenzdienst herstellt.")

In den meisten Fällen ist das Netzwerk, das Ihr Unternehmen mit der Cloud verbindet, ein nicht verwaltetes Netzwerk, in dem Sie keine zuverlässigen QoS-Optionen einrichten können. Eine mögliche Lösung für den End-to-End-QoS ist [Azure Express Route](https://azure.microsoft.com/documentation/articles/expressroute-introduction/), aber wir empfehlen weiterhin, QoS in Ihrem lokalen Netzwerk für eingehenden und ausgehenden Datenverkehr zu implementieren. Dadurch wird die Qualität von Arbeitslasten in Echtzeit während der gesamten Bereitstellung erhöht und Engpässe verringert.

## <a name="verify-your-network-is-ready"></a>Überprüfen, ob Ihr Netzwerk bereit ist

Wenn Sie eine QoS-Implementierung in Betracht ziehen, sollten Sie bereits ihre Bandbreitenanforderungen und andere [Netzwerkanforderungen](prepare-network.md)festgelegt haben. 
  
  Verkehrsüberlastung in einem Netzwerk beeinträchtigt die Medienqualität erheblich. Mangelnde Bandbreite führt zu Leistungseinbußen und einer schlechten Benutzererfahrung. Wenn die Akzeptanz und Nutzung von Teams wächst, verwenden Sie Berichterstellung, [anrufanalyse und Dashboard für die Anrufqualität](difference-between-call-analytics-and-call-quality-dashboard.md) , um Probleme zu erkennen und Anpassungen mithilfe von QoS und selektiver Bandbreiten Erweiterungen vorzunehmen.

### <a name="vpn-considerations"></a>VPN-Überlegungen

QoS funktioniert nur erwartungsgemäß, wenn Sie für alle Verknüpfungen zwischen Anrufern implementiert werden. Wenn Sie QoS in einem internen Netzwerk verwenden und sich ein Benutzer von einem Remotestandort aus anmeldet, können Sie nur in Ihrem internen, verwalteten Netzwerk priorisiert werden. Obwohl Remotestandorte eine verwaltete Verbindung erhalten können, indem Sie ein VPN (virtuelles privates Netzwerk) implementieren, fügt ein VPN inhärent einen Paket Overhead hinzu und verursacht Verzögerungen im Echtzeitverkehr. Wir empfehlen, dass Sie den Echt Zeit Kommunikationsverkehr über ein VPN vermeiden.

In einer globalen Organisation mit verwalteten Links, die sich über Kontinente erstrecken, empfehlen wir QoS, da die Bandbreite für diese Links im Vergleich zum LAN begrenzt ist.

## <a name="introduction-to-qos-queues"></a>Einführung in QoS-Warteschlangen

Für die Bereitstellung von QoS müssen Netzwerkgeräte eine Möglichkeit zum Klassifizieren des Datenverkehrs und zur Unterscheidung von Sprach-oder Videodaten von anderem Netzwerkdatenverkehr aufweisen.

Wenn Netzwerkdatenverkehr in einen Router eintritt, wird der Datenverkehr in eine Warteschlange gestellt. Wenn eine QoS-Richtlinie nicht konfiguriert ist, gibt es nur eine Warteschlange, und alle Daten werden als First-in-First-Out mit der gleichen Priorität behandelt. Das bedeutet, dass der VoIP-Datenverkehr (der sehr anfällig für Verzögerungen ist) möglicherweise hinter dem Datenverkehr hängen bleibt, in dem eine Verzögerung von einigen zusätzlichen Millisekunden kein Problem darstellt.

Bei der Implementierung von QoS definieren Sie mehrere Warteschlangen mit einer von mehreren Funktionen zur Engpass Verwaltung (wie beispielsweise Ciscos Priority Queuing und Kurs basierter [CBWFQ](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641)für gewichtete faire Warteschlangen) sowie Features zur Überlastungs Vermeidung (wie gewichtete zufällige frühzeitige Erkennungs- [WRED](https://en.wikipedia.org/wiki/Weighted_random_early_detection)).

_Abbildung 2. Beispiele für QoS-Warteschlangen_

![Illustration von QoS-Warteschlangen und Bandbreiten Teilung](media/Qos-in-Teams-Image2.png "Die gesamte verfügbare Bandbreite ist auf mehrere Warteschlangen – Audio, Video und anderer Datenverkehr – aufgeteilt, denen unterschiedliche Prioritäten zugewiesen wurden.")

Eine einfache Analogie ist, dass QoS virtuelle "Fahrgemeinschaften-Lanes" in Ihrem Datennetzwerk erstellt, sodass einige Datentypen nie oder nur selten einer Verzögerung begegnen. Nachdem Sie diese Spuren erstellt haben, können Sie Ihre relative Größe anpassen und die von Ihnen genutzte Verbindungsbandbreite effektiver verwalten, während Sie dennoch unternehmensspezifische Erfahrungen für die Benutzer Ihrer Organisation bereitstellen.

## <a name="select-a-qos-implementation-method"></a>Auswählen einer QoS-Implementierungsmethode

Sie können QoS mithilfe von Port basiertem Tagging implementieren, indem Sie die Zugriffssteuerungslisten (ACLs) auf den Routern Ihres Netzwerks verwenden. Die Port basierte Kennzeichnung ist die zuverlässigste Methode, da Sie in gemischten Windows-und Mac-Umgebungen funktioniert und am einfachsten zu implementieren ist. Mobile Clients bieten keinen Mechanismus zum Kennzeichnen von Datenverkehr mithilfe von DSCP-Werten, sodass diese Methode erforderlich ist.  

Bei Verwendung dieser Methode untersucht der Router des Netzwerks ein eingehendes Paket, und wenn das Paket mit einem bestimmten Port oder Portbereich eingetroffen ist, wird es als bestimmter Medientyp identifiziert und in die Warteschlange für diesen Typ eingefügt, wobei der IP eine vordefinierte [DSCP](https://tools.ietf.org/html/rfc2474) -Marke hinzugefügt wird. Paketheader, damit andere Geräte den Datenverkehrstyp erkennen und ihm Priorität in der Warteschlange geben können.

Obwohl dies plattformübergreifend funktioniert, wird nur der Datenverkehr am WAN-Edge (nicht bis zum Clientcomputer) markiert, und der Verwaltungsaufwand wird verursacht. Anweisungen zur Implementierung dieser Methode finden Sie in der vom Router-Hersteller bereitgestellten Dokumentation.

* * *

Sie können auch QoS implementieren, indem Sie ein Gruppenrichtlinienobjekt (GPO) verwenden, um Clientgeräte zu verweisen, um eine DSCP-Markierung in IP-Paket Headern einzufügen, die diese als bestimmten Typ von Datenverkehr (beispielsweise Voice) identifizieren. Router und andere Netzwerkgeräte können konfiguriert werden, um dies zu erkennen und den Datenverkehr in eine separate Warteschlange mit höherer Priorität zu versetzen.

Obwohl dieses Szenario vollständig gültig ist, funktioniert es nur bei Windows-Clients, die mit der Domäne verbunden sind. Jedes Gerät, das kein mit der Domäne verbundener Windows-Client ist, ist für DSCP-Tagging nicht aktiviert. Clients wie Mac OS verfügen über hart codierte Tags und kennzeichnen immer den Datenverkehr.

Auf der positiven Seite wird durch die Steuerung der DSCP-Kennzeichnung über GPO sichergestellt, dass alle von der Domäne verbundenen Computer die gleichen Einstellungen erhalten und dass nur ein Administrator Sie verwalten kann. Clients, die das Gruppenrichtlinienobjekt verwenden können, werden auf dem ursprünglichen Gerät markiert, und dann können konfigurierte Netzwerkgeräte den echtzeitdatenstrom mithilfe des DSCP-Codes erkennen und ihm eine entsprechende Priorität zuweisen.

* * *

Wenn möglich, empfehlen wir eine Kombination aus DSCP-Markierungen am Endpunkt und portbasierten ACLs für Router. Wenn Sie ein Gruppenrichtlinienobjekt verwenden, um die Mehrzahl der Clients zu erfassen, und außerdem mithilfe von Port basierter DSCP-Tagging, wird sichergestellt, dass Mobile, Mac und andere Clients weiterhin QoS-Behandlung erhalten (zumindest teilweise).

DSCP-Markierungen können mit Briefmarken verglichen werden, die für Postangestellte angeben, wie wichtig die Zustellung ist und wie Sie für eine schnelle Zustellung bestens sortiert werden. Nachdem Sie Ihr Netzwerk so konfiguriert haben, dass es den Medienströmen in Echtzeit Vorrang gibt, sollten verloren gegangene Pakete und verspätete Pakete erheblich abnehmen.

Nachdem alle Geräte im Netzwerk die gleichen Klassifizierungen, Markierungen und Prioritäten verwendet haben, ist es möglich, Verzögerungen, verworfene Pakete und Jitter zu verringern oder zu eliminieren, indem die Größe der Portbereiche geändert wird, die den für die einzelnen Datenverkehrstypen verwendeten Warteschlangen zugewiesen sind. Aus der Perspektive der Teams ist der wichtigste Konfigurationsschritt die Klassifizierung und Kennzeichnung von Paketen, doch damit die End-to-End-QoS erfolgreich ist, müssen Sie auch die Konfiguration der Anwendung sorgfältig mit der zugrunde liegenden Netzwerkkonfiguration ausrichten. Sobald QoS vollständig implementiert ist, ist die laufende Verwaltung eine Frage der Anpassung der Portbereiche, die den einzelnen Datenverkehrstypen entsprechend den Anforderungen Ihrer Organisation und der tatsächlichen Nutzung zugewiesen sind.

## <a name="choose-initial-port-ranges-for-each-media-type"></a>Auswählen von anfänglichen Portbereichen für die einzelnen Medientypen

Der DSCP-Wert weist einem entsprechend konfigurierten Netzwerk die Priorität zu, die einem Paket oder Datenstrom zugewiesen werden soll, unabhängig davon, ob das DSCP-Zeichen von Clients oder dem Netzwerk selbst basierend auf ACL-Einstellungen zugewiesen wird. Jede Medien Auslastung erhält ihren eigenen eindeutigen DSCP-Wert (andere Dienste können es möglicherweise ermöglichen, dass Arbeitslasten eine DSCP-Markierung, Teams nicht) und einen definierten und separaten Portbereich für jeden Medientyp verwenden. In anderen Umgebungen ist möglicherweise eine vorhandene QoS-Strategie vorhanden, die Ihnen bei der Ermittlung der Priorität von Netzwerkarbeitsauslastungen hilft.

Die relative Größe der Portbereiche für verschiedene Echtzeit-Streaming-Arbeitsauslastungen legt den Anteil der gesamten verfügbaren Bandbreite für diese Arbeitsauslastung fest. So kehren Sie zu unserer früheren postalischen Analogie zurück: ein Brief mit dem Stempel "Luft Post" kann innerhalb einer Stunde zum nächstgelegenen Flughafen abgeholt werden, während ein kleines Paket, das als "Bulk-Mail" markiert ist, einen Tag warten kann, bevor er auf einer Reihe von Lastwagen über Land reist.

In der folgenden Tabelle sind die erforderlichen DSCP-Markierungen und die vorgeschlagenen entsprechenden Medien Portbereiche aufgeführt, die von Teams und Express Route verwendet werden. Diese Bereiche sind möglicherweise ein guter Ausgangspunkt für Kunden, die unsicher sind, was in ihrer eigenen Umgebung zu verwenden ist. Weitere Informationen finden Sie unter [QoS-Anforderungen für ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-qos).

_Empfohlene anfängliche Portbereiche_

|Media Traffic-Typ| Client Quellportbereich |Protokoll|DSCP-Wert|DSCP-Klasse|
|:--- |:--- |:--- |:--- |:--- |
|Audio| 50000 – 50019|TCP/UDP|46|Expedited Forwarding (EF)|
|Video| 50020 – 50039|TCP/UDP|34|Assured Forwarding (AF41)|
|Anwendung/Bildschirmübertragung| 50040 – 50059|TCP/UDP|18|Sichere Weiterleitung (AF21)|
||||||

Beachten Sie Folgendes, wenn Sie diese Einstellungen verwenden:

- Wenn Sie beabsichtigen, Express Route in Zukunft zu implementieren und QoS noch nicht implementiert haben, empfehlen wir, dass Sie die Richtlinien befolgen, damit DSCP-Werte vom Absender zum Empfänger identisch sind.
- Alle Clients, einschließlich mobiler Clients und Teams, verwenden diese Portbereiche und sind von der von Ihnen implementierten DSCP-Richtlinie betroffen, die diese Quell Portbereiche verwendet. Die einzigen Clients, die weiterhin dynamische Ports verwenden, sind die browserbasierten Clients (also die Clients, mit denen Teilnehmer mithilfe Ihres Browsers an Besprechungen teilnehmen können).
- Obwohl der Mac-Client dieselben Portbereiche verwendet, werden auch hart codierte Werte für Audio (EF) und Video (AF41) verwendet. Diese Werte können nicht konfiguriert werden.
- Wenn Sie die Portbereiche später anpassen müssen, um die Benutzerfreundlichkeit zu verbessern, können sich die Portbereiche nicht überlappen und benachbart sein.

## <a name="migrate-qos-to-teams"></a>Migrieren von QoS zu Teams

Wenn Sie bereits zuvor Skype for Business Online, einschließlich QoS-Tagging und Portbereiche, bereitgestellt haben und jetzt Teams bereitstellen, werden Teams die vorhandene Konfiguration respektieren und die gleichen Portbereiche und Tagging verwenden wie der Skype for Business-Client. In den meisten Fällen wird keine zusätzliche Konfiguration benötigt.

> [!NOTE]
> Wenn Sie das QoS-Tagging für Anwendungsnamen über Gruppenrichtlinien verwenden, müssen Sie "Teams. exe" als Anwendungsnamen hinzufügen.

## <a name="qos-implementation-steps"></a>QoS-Implementierungsschritte

Auf einer sehr hohen Ebene erfordert die Implementierung von QoS die folgenden Schritte:

1. [Überprüfen, ob Ihr Netzwerk bereit ist](#verify-your-network-is-ready)
2. [Auswählen einer QoS-Implementierungsmethode](#select-a-qos-implementation-method)
3. [Auswählen von anfänglichen Portbereichen für die einzelnen Medientypen](#choose-initial-port-ranges-for-each-media-type)
4. Implementieren von QoS-Einstellungen:
   1. Auf Clients, die ein GPO verwenden, um [Clientgeräte-Portbereiche und-Markierungen einzurichten](QoS-in-Teams-clients.md)
   2. Auf Routern (siehe Herstellerdokumentation) oder auf anderen Netzwerkgeräten. Dies kann Portbasierte ACLs oder einfach die Definition von QoS-Warteschlangen und DSCP-Markierungen oder all diesen umfassen.

      > [!IMPORTANT]
      > Es wird empfohlen, diese QoS-Richtlinien mithilfe der Clientports und einer Quell-und Ziel-IP-Adresse von "Any" zu implementieren. Dadurch wird sowohl ein-und ausgehenden Mediendatenverkehr im internen Netzwerk abgefangen.  

   3. Im [Team Admin Center](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)
5. Über [prüfen Sie die QoS-Implementierung](#validate-the-qos-implementation) , indem Sie den Datenverkehr des Teams im Netzwerk analysieren.

Beachten Sie beim Vorbereiten der Implementierung von QoS die folgenden Richtlinien:

- Der kürzeste Weg zu Office 365 ist am besten.
- Das Schließen von Ports führt nur zur Verschlechterung der Qualität.
- Es werden keine Hindernisse dazwischen, wie etwa Proxies, empfohlen.
- Beschränken Sie die Anzahl der Hops:
  - Client-zu-Netzwerk-Edge – 3 bis 5 Hops.
  - ISP zu Microsoft Network Edge – 3 Hops
  - Microsoft-Netzwerk-Edge bis zum endgültigen Zielort – irrelevant

Informationen zum Konfigurieren von Firewall-Ports finden Sie unter [Office 365-URLs und IP-Bereiche](office-365-urls-ip-address-ranges.md).

## <a name="managing-source-ports-in-the-teams-admin-center"></a>Verwalten von Quell Anschlüssen im Team Admin Center

In Teams sollten QoS-Quell Anschlüsse, die von den unterschiedlichen Arbeitslasten verwendet werden, aktiv verwaltet und bei Bedarf angepasst werden. In Bezug auf die Tabelle in [Wählen Sie anfängliche Portbereiche für jeden Medientyp](#choose-initial-port-ranges-for-each-media-type)aus, sind die Portbereiche einstellbar, die DSCP-Markierungen können aber nicht konfiguriert werden. Nachdem Sie diese Einstellungen implementiert haben, stellen Sie möglicherweise fest, dass für einen bestimmten Medientyp mehr oder weniger Ports erforderlich sind. Das Dashboard für die [anrufanalyse und die Anrufqualität](difference-between-call-analytics-and-call-quality-dashboard.md) sollte verwendet werden, um eine Entscheidung zur Anpassung der Portbereiche nach der Implementierung von Teams und in regelmäßigen Abständen bei Bedarf zu ändern.

> [!NOTE]
> Wenn Sie QoS bereits auf der Grundlage von Quell Portbereichen und DSCP-Markierungen für Skype for Business Online konfiguriert haben, gilt die gleiche Konfiguration für Teams, und es werden keine weiteren Client-oder Netzwerkänderungen an der Zuordnung erforderlich sein, doch müssen Sie möglicherweise [die Bereiche angeben. wird im Team Admin Center verwendet](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) , um dem zu entsprechen, was für Skype for Business Online konfiguriert wurde.

Wenn Sie zuvor Skype for Business Server lokal bereitgestellt haben, müssen Sie möglicherweise Ihre QoS-Richtlinien erneut überprüfen und bei Bedarf anpassen, damit die von Ihnen bestätigten Portbereichs Einstellungen eine qualitativ hochwertige Benutzeroberfläche für Teams bieten.

## <a name="validate-the-qos-implementation"></a>Überprüfen der QoS-Implementierung

Damit QoS effektiv ist, muss der DSCP-Wert, der durch das Gruppenrichtlinienobjekt gesetzt wurde, an beiden Enden eines Anrufs vorhanden sein. Durch Analysieren des vom Team Client generierten Datenverkehrs können Sie sicherstellen, dass der DSCP-Wert nicht geändert oder entfernt wird, wenn der Arbeits Auslastungsdaten Verkehr in Teams durch das Netzwerk verschoben wird.

Am besten erfassen Sie den Datenverkehr am Netzwerk Ausgangspunkt. Sie können die Portspiegelung auf einem Switch oder Router verwenden, um dies zu unterstützen.

### <a name="use-network-monitor-to-verify-dscp-values"></a>Verwenden des Netzwerkmonitors zum Überprüfen von DSCP-Werten

Netzwerk Monitor ist ein Tool, das Sie [von Microsoft herunterladen](https://www.microsoft.com/download/4865) können, um den Netzwerkdatenverkehr zu analysieren.

1. Stellen Sie auf dem PC mit Netzwerk Monitor eine Verbindung mit dem Port her, der für die Portspiegelung konfiguriert wurde, und beginnen Sie mit der Erfassung von Paketen.

2. Führen Sie einen Anruf über den Microsoft Teams-Client. Stellen Sie sicher, dass Medien eingerichtet wurden, bevor Sie den Anruf aufhängen.

3. Beenden Sie die Aufzeichnung.

4. Verwenden Sie im Feld **Anzeige Filter** die Quell-IP-Adresse des Computers, der den Anruf getätigt hat, und verfeinern Sie den Filter, indem Sie den DSCP-Wert 46 (Hex 0x2E) als Suchkriterien definieren, wie im folgenden Beispiel gezeigt:

    Source = = "192.168.137.201" und IPv4. DifferentiatedServicesField = = 0x2E

    ![Screenshot Filter im Dialogfeld "Anzeigefilter"](media/Qos-in-Teams-Image4.png "Das Dialogfeld "Anzeigefilter" im Netzwerk Monitor mit den Filtern, die angewendet werden sollen.")

5. Wählen Sie über **nehmen** aus, um den Filter zu aktivieren.

6. Wählen Sie im Fenster " **Frame Zusammenfassung** " das erste UDP-Paket aus.

7. Erweitern Sie im Fenster **Frame Details** das Element IPv4-Liste, und notieren Sie sich den Wert am Ende der Zeile, die mit **DSCP**beginnt.

    ![Screenshot mit DSCP-Einstellungen im Dialogfeld ' Frame Details '](media/Qos-in-Teams-Image5.png "Dialogfeld ' Frame Details ' im Netzwerk Monitor, mit dem die DSCP-Einstellungen markiert werden.")

In diesem Beispiel wird der DSCP-Wert auf 46 gesetzt. Das ist richtig, da der verwendete Quell Port 50019 ist, was darauf hindeutet, dass es sich um eine sprach Auslastung handelt.

Wiederholen Sie die Überprüfung für alle Arbeitsauslastungen, die durch das GPO markiert wurden.

## <a name="more-information"></a>Weitere Informationen

[Video: Netzwerkplanung](https://aka.ms/teams-networking)

[Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams](prepare-network.md)

[Express Route-QoS-Anforderungen](https://docs.microsoft.com/azure/expressroute/expressroute-qos)
