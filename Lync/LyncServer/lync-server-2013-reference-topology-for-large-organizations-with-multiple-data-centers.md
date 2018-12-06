---
title: 'Lync Server 2013: Referenztopologie für große Organisationen mit mehreren Rechenzentren'
TOCTitle: Referenztopologie für große Organisationen mit mehreren Rechenzentren
ms:assetid: 9a6aeae6-629b-49e6-9804-7ef369d7c3dc
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398797(v=OCS.15)
ms:contentKeyID: 49294865
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Referenztopologie für Lync Server 2013 für große Organisationen mit mehreren Rechenzentren

 

_**Letztes Änderungsdatum des Themas:** 2012-10-22_

Die Referenztopologie für eine große Organisation mit mehreren Rechenzentren gilt für jede Organisationsgröße mit mehr als einem zentralen Standort. Die genaue Topologie in dem folgenden Diagramm bezieht sich auf eine Organisation mit 50.000 Benutzern, von denen sich 20.000 Benutzer am zentralen Standort A, 20.000 Benutzer am zentralen Standort B und insgesamt 10.000 Benutzer am zentralen Standort C und an Zweigstellenstandorten befinden. Der in diesem Diagramm gezeigte Topologietyp kann Organisationen mit einer beliebigen Benutzeranzahl umfassen.

Neben der durch Pools auf den Front-End-Servern bereitgestellten Hochverfügbarkeit unterstützt diese Topologie außerdem eine Notfallwiederherstellung. Die Front-End-Pools an den zentralen Standorten A und B sind miteinander kombiniert. Wenn einer dieser Pools ausfällt, kann der Administrator die Dienste für die betroffenen Benutzer in den kombinierten Pool des nicht betroffenen Standorts verlagern.

Diese Topologie wird in mehreren Diagrammen gezeigt. Zunächst sehen Sie einen Überblick, gefolgt von detaillierten Ansichten der zentralen Standorte.

**Überblick über die Referenztopologie für große Organisationen mit mehreren Rechenzentren**

![Referenztopologie für mehrere Rechenzentren](images/Gg398797.471e1ce9-be11-44b9-9f4a-59e0551b7b30(OCS.15).jpg "Referenztopologie für mehrere Rechenzentren")

**Referenztopologie für große Organisationen: Detaillierte Ansicht des zentralen Standorts A**

![Planen von Referenztopologien A](images/Gg398797.dab33f19-e77b-42da-9047-858fb9851264(OCS.15).jpg "Planen von Referenztopologien A")

**Referenztopologie für große Organisationen: Detaillierte Ansicht des zentralen Standorts B**

![Planen von Referenztopologien B](images/Gg398797.5ccaf1d4-bd53-4cb7-96fe-723147334e7f(OCS.15).jpg "Planen von Referenztopologien B")

**Referenztopologie für große Organisationen: Detaillierte Ansicht des zentralen Standorts C**

![Planen von Referenztopologien C](images/Gg398797.7238ca40-340c-491f-b497-ddc2665dadb6(OCS.15).jpg "Planen von Referenztopologien C")

  - Die **Front-End-Pools sind für die Notfallwiederherstellung kombiniert.**   Die Front-End-Pools an den Standorten A und B sind miteinander kombiniert, um eine Notfallwiederherstellung zu unterstützen. Wenn der Pool eines Standorts ausfällt, kann der Administrator die Benutzer des ausgefallenen Standorts mit einer minimalen Dienstunterbrechung in den kombinierten Front-End-Pool des anderen Standorts übernehmen. Jeder dieser beiden Front-End-Pools hat sechs Server, was ausreicht, um alle 40.000 Benutzer beider Pools im Fall eines Failovers zu unterstützen. Weitere Informationen finden Sie unter [Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

  - Die **Back-End-Server sind gespiegelt**   Um die Hochverfügbarkeit der grundlegenden Benutzerfunktionen zu erhöhen, hat die Organisation ein gespiegeltes Paar Back-End-Server für jeden Front-End-Pool bereitgestellt. Dies ist eine optionale Topologie und Sie können sich auch für die Bereitstellung eines einzelnen Back-End-Servers entscheiden.

  - **Verwenden eines Standard Edition-Servers an einem Zweigstellenstandort.**Diese Organisation stuft Standort C als Zweigstellenstandort ein, da er nur 600 Mitarbeiter umfasst. Die dortigen Benutzer halten jedoch untereinander viele A/V-Konferenzen ab. Wenn der Standort in Lync Server als Zweigstellenstandort bereitgestellt würde, liefen die Medien für diese Konferenzen über das WAN zum zentralen Standort mit einem bereitgestellten Front-End-Server und wieder zurück. Um dieses potenzielle Bandbreitenproblem zu vermeiden, haben sie an diesem Standort zwei Standard Edition-Server installiert, auf denen diese Konferenzen gehostet werden. Da dort Standard Edition-Server installiert wurden, betrachtet Lync Server ihn laut Definition als zentralen Standort, und er wird im Topologie-Generator und im Planungstool als solcher behandelt.
    
    Hier würde im Hinblick auf die Leistung nur ein Standard Edition-Server ausreichen, die Organisation hat aber zwei bereitgestellt und miteinander kombiniert, um die Hochverfügbarkeit sicherzustellen falls ein Server ausfällt.
    
    Auch wenn Standort C als zentraler Standort betrachtet wird, müssen Sie dort keine Edgeserver bereitstellen. In diesem Beispiel verwendet Standort C die an Standort A bereitgestellten Edgeserver.

  - **Überwachen und Archivieren**   Diese Organisation hat sowohl die Überwachung als auch die Archivierung bereitgestellt. Wenn Sie die Überwachung oder die Archivierung bereitstellen, werden diese auf allen Front-End-Servern ausgeführt. Die Datenbanken für diese Funktionen können mit der Back-End-Datenbank verbunden oder auf einem separaten Server gespeichert werden. Diese Organisation hat diese Datenbanken am zentralen Standort B auf einem von den Back-End-Servern getrennten Server gespeichert. Die Datenbanken empfangen hier Überwachungs- und Archivierungsdaten von den Front-End-Servern aller Standorte.

  - **Optionen für Bereitstellungen an Zweigstellenstandorten.**   Diese Organisation besitzt aktuell über 50 Zweigstellen. Im Diagramm werden davon lediglich drei dargestellt. Die Zweigstellenstandorte 1 und 3 besitzen keine ausfallsichere WAN-Verbindung mit dem zentralen Standort. Daher werden Survivable Branch-Anwendungen eingesetzt, um bei Ausfall der WAN-Verbindung mit dem zentralen Standort Telefondienste bereitzustellen. Zweigstellenstandort 2 verfügt jedoch über eine ausfallsichere WAN-Verbindung, daher wird nur ein PSTN-Gateway benötigt. Das dort bereitgestellte PSTN-Gateway unterstützt die Medienumgehung, deshalb wird an Zweigstellenstandort B kein Vermittlungsserver benötigt. Ausführliche Informationen dazu, welche Komponenten an einem Zweigstellenstandort installiert werden sollten, finden Sie unter [Planen der Ausfallsicherheit für Enterprise-VoIP in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) in der Planungsdokumentation.

  - **SIP-Trunking und Vermittlungsserver.**   Beachten Sie, dass an Standort B der Vermittlungsserver nicht gemeinsam mit den Front-End-Servern ausgeführt wird. Der Grund hierfür liegt darin, dass für Standorte mit SIP-Trunking ein eigenständiger Vermittlungsserver empfohlen wird. In den meisten anderen Fällen empfiehlt sich die gemeinsame Ausführung des Vermittlungsservers mit dem Front-End-Server. Ausführliche Informationen zu den Vermittlungsservertopologien finden Sie unter [Komponenten und Topologien für den Vermittlungsserver in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in der Planungsdokumentation.

  - **Beständiger Chat bereitgestellt.**   Diese Organisation hat die für den beständigen Chat erforderlichen Server bereitgestellt. Sie hat mehrere Front-End-Server für den beständigen Chat bereitgestellt, um die Last für die Benutzer im Pool zu bewältigen und Hochverfügbarkeit zu bieten. Sie hat außerdem Kompatibilität für den beständigen Chat bereitgestellt und den Speicher für den beständigen Chat und den Kompatibilitätsspeicher auf separaten Servern bereitgestellt. Diese Speicher können verbunden werden, und dies sogar mit dem Back-End-Server. Diese Organisation hat aber beschlossen, diese für eine bessere Leistung zu trennen.

  - **DNS-Lastenausgleich.**   Der Front-End-Pool und der Edgeserverpool. Auf diese Weise sind keine Hardwaregeräte zum Lastenausgleich für die interne Schnittstelle der Edgeserver erforderlich, und der für Setup und Wartung der Hardwaregeräte zum Lastenausgleich für die weiteren Pools erforderliche Zeitraum wird erheblich verringert, da die Hardwaregeräte zum Lastenausgleich nur für HTTP-Datenverkehr benötigt werden. Ausführliche Informationen zum DNS-Lastenausgleich finden Sie unter [DNS-Lastenausgleich in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in der Planungsdokumentation.

  - **Exchange UM-Bereitstellung.**   Lync Server funktioniert sowohl mit *lokalen* Bereitstellungen von Exchange Unified Messaging (UM) als auch mit *gehosteten* Exchange UM-Diensten. Der zentrale Standort A umfasst einen Exchange Unified Messaging (UM)-Server, auf dem nicht Lync Server, sondern Microsoft Exchange Server ausgeführt wird. Die Exchange UM-Funktionalität für Lync Server wird im Front-End-Pool ausgeführt.
    
    Am zentralen Standort B wird gehostetes Exchange eingesetzt, daher wird die Exchange UM-Serverfunktionalität ebenfalls gehostet.
    
    Ausführliche Informationen zu Exchange UM finden Sie unter [Planen der Integration von Exchange Unified Messaging in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) und [Integration in gehostete Exchange Unified Messaging-Dienste in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) in der Planungsdokumentation.

  - **Office Web Apps Server.**   Wir empfehlen die Bereitstellung eines Office Web Apps Servers oder einer Office Web Apps Server-Farm in allen Organisation, die Webkonferenzen unterstützen. Sie können eine einzelne Office Web Apps Server-Farm an einem Standort bereitstellen, die den Datenverkehr von allen Standorten abwickelt, oder diese an allen Standorten bereitstellen. Mit Office Web Apps Server können Powerpoint-Folien in Webkonferenzen präsentiert werden. Weitere Informationen finden Sie unter [Konfigurieren der Integration mit Office Web Apps Server und Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **Directors können hinzugefügt werden.**   Wenn diese Organisation die Sicherheit im Hinblick auf Denial-of-Service-Angriffe erhöhen möchte, könnte sie auch einen Pool von Directors bereitstellen. Ein Director ist eine separate, optionale Serverrolle in Lync Server, die keine Benutzerkonten enthält oder Anwesenheits- oder Konferenzdienste bereitstellt. Sie dient als interner nächster Hopserver, an den ein Edgeserver eingehenden SIP-Datenverkehr, der für interne Server bestimmt ist, weiterleitet. Der Director nimmt eine Vorabauthentifizierung eingehender Anfragen vor und leitet diese an den Pool oder Server des Benutzers weiter. Die Vorabauthenitifizierung in Director ermöglicht das Aussortieren von Anfragen, die von Benutzerkonten stammen, die in der Bereitstellung nicht bekannt sind. Ein Director unterstützt die Isolierung der Front-End-Server von schädlichem Datenverkehr, wie Denial-of-Service-Angriffen (DoS). Wenn das Netzwerk bei einem solchen Angriff mit ungültigem externen Datenverkehr überflutet wird, endet der Angriff beim Director.

  - **System Center Operations Manager ist bereitgestellt.**   Wir empfehlen die Überwachung der Integrität Ihrer Lync Server-Bereitstellung, um die Dienstverfügbarkeit für Endbenutzer sicherzustellen. Sie können Lync mit dem System Center Operations Manager Management Pack für Lync überwachen, das als kostenloser Download bei Microsoft verfügbar ist. Mit dem Lync Management Pack erhalten Sie proaktiv Echtzeitwarnungen, sobald Probleme auftreten, können synthetische Transaktionen ausführen, um die Lync-Funktionalität von Ende zu Ende zu testen, Berichte zur Dienstverfügbarkeit erhalten usw. Dies hilft Ihnen bei der proaktiven Behandlung von Problemen mit Ihrer Bereitstellung, bevor diese für Endbenutzer spürbar werden.
    
    Diese Organisation hat an allen zentralen Standorten einen System Center Operations Manager-Server bereitgestellt.

