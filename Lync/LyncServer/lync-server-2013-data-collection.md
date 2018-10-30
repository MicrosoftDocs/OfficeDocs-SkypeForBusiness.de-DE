---
title: 'Lync Server 2013: Datenerfassung'
TOCTitle: Datenerfassung
ms:assetid: e40b03e5-455d-4bbc-831a-c61b1380db53
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg399008(v=OCS.15)
ms:contentKeyID: 49295698
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Datenerfassung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-08_

In der Microsoft Lync Server 2013- Kommunikationssoftware können Sie das Microsoft Lync Server 2013, Planungstool ausführen, ohne Ihre vorhandenen und vorgeschlagenen IP-Adressen und FQDNs des Edgeservers zu dokumentieren. In diesem Fall können jedoch häufiger Konfigurationsfehler auftreten. Wenn beispielsweise für einen bestimmten Zeitraum eine Koexistenz erforderlich ist, besteht ein häufiger Fehler darin, dass FQDNs einer vorhandenen Edgebereitstellung für die Lync Server 2013-Edgebereitstellung verwendet werden. Durch Festhalten vorhandener und vorgeschlagener IP-Adressen und FQDNs in Excel- oder anderen Tabellen oder in anderer visueller Form können solche Einrichtungsprobleme während der Installation vermieden werden.


> [!WARNING]
> Wenn Sie vorherige Versionen des Planungstools verwendet haben, haben Sie damit möglicherweise eine Topologie erstellt und dann das Topologiedokument für die Verwendung im Topologie-Generator exportiert, um Ihre Topologie zu veröffentlichen. Die Funktion zum Exportieren der Topologie gibt es im Planungstool nicht mehr. Es wird dringend davon abgeraten, mithilfe einer vorherigen Version des Planungstools ein Topologiedokument für Lync Server 2013 zu erstellen, da dies zu unerwünschten Ergebnissen führen kann.



Es wird deshalb empfohlen, die Ihrer Edgetopologie entsprechende Vorlage zur Datenerfassung zu verwenden, um die verschiedenen FQDNs und IP-Adressen zusammenzutragen, die Sie in das Planungstool eingeben müssen. Durch das Dokumentieren der aktuellen und vorgeschlagenen Konfiguration können Sie die Werte in den richtigen Kontext für Ihre Produktionsumgebung setzen. Gleichzeitig müssen Sie die Konfiguration von Koexistenz und Features, wie z. B. einfachen URLs, Dateifreigaben und Lastenausgleich, planen.

Für die erfolgreiche Bereitstellung von Microsoft Lync Server 2013 müssen Sie mit der Interaktion und der gegenseitigen Abhängigkeit der einzelnen Komponenten vertraut sein. Durch die Erfassung von Daten in Ihrer vorhandenen Netzwerk- und Serverinfrastruktur und die Berücksichtigung der Informationen zur Planung in diesen Abschnitten können Sie Lync Server 2013- Edgeserverkomponenten in Ihre Infrastruktur integrieren.

Es gibt drei Hauptarchitekturen mit zwei Varianten für insgesamt fünf mögliche Bereitstellungsszenarien (siehe [Auswählen einer Topologie in Lync Server 2013](lync-server-2013-choosing-a-topology.md)). Eines dieser Szenarien ist der Ausgangspunkt für die Datenerfassung. Die IP-Adressen, Servernamen und Domänennamen sind Beispiele, die den Zertifikat-, Firewall und DNS-Diagrammen entsprechen, welche die erforderlichen Informationen für eine umfassende Planungslösung enthalten. Die Diagramme und die Angabe der erforderlichen Werte für Zertifikate, DNS und Firewalls spielen bei der teamübergreifenden Kommunikation eine besonders wichtige Rolle, bei der die Verwaltung von Zertifizierungsstelle, Firewallkonfiguration und DNS von anderen Teams als dem Team, das die Bereitstellung plant, ausgeführt wird. Die Diagramme liefern Informationen zu erforderlichen Komponenten, die für die Weitergabe dieser Anforderungen für die teamübergreifende Zusammenarbeit verwendet werden können.

Die abgebildeten Diagramme sind absichtlich allgemein gehalten. Dennoch ermöglichen sie die Erfassung aller Daten, die für die Weitergabe von Anforderungen in einem Szenario mit teamübergreifender Zusammenarbeit erforderlich wären, bei dem für Netzwerk, Firewall, Zertifikaterstellung und -verwaltung, Serverbereitstellung und Serververwaltung unterschiedliche Gruppen zuständig sind. Die Verfügbarkeit der benötigten Informationen für die Konfiguration von Netzwerk, Firewalls, Ports und Protokollen, Zertifikaten und Servern ist bei der Bereitstellung von Lync Server von unschätzbarem Wert.

**Edgeserver und Edgepool**

![Edgeserver und Edgepool](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "Edgeserver und Edgepool")

**Reverseproxy**

![Reverseproxy](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "Reverseproxy")

**Director oder Directorpool**

![Director und Directorpool](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "Director und Directorpool")

