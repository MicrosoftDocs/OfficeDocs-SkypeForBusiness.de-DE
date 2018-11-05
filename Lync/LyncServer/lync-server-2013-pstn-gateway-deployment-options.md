---
title: 'Lync Server 2013: Bereitstellungsoptionen für PSTN-Gateways'
TOCTitle: Bereitstellungsoptionen für PSTN-Gateways
ms:assetid: d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398899(v=OCS.15)
ms:contentKeyID: 49295487
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellungsoptionen für PSTN-Gateways in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

## PSTN-Gateways

Bei PSTN-Gateways (Public Switched Telephone Network) handelt es sich um Hardwarekomponenten von Drittanbietern, die für eine Signal- und Mediendatenübersetzung zwischen der Enterprise-VoIP-Infrastruktur und dem Festnetz sorgen, entweder direkt oder über eine Verbindung zu SIP-Trunks. In beiden Topologien stellt das Gateway den Endpunkt für das Telefonfestnetz dar. Das Gateway ist in einem eigenen Subnetz isoliert und über den Vermittlungsserver mit dem Unternehmensnetzwerk verbunden.

In einem Unternehmen mit mehreren Standorten wird üblicherweise mindestens ein Gateway pro Standort bereitgestellt. Zweigniederlassungen können entweder über ein Gateway oder über eine Survivable Branch-Anwendung, die Gateway und Server in einem einzigen Gerät kombiniert, eine Verbindung zum Telefonfestnetz herstellen. Wenn Zweigstellen ein Gateway verwenden, müssen sich am Standort sowohl eine Registrierungstelle als auch ein Vermittlungsserver befinden, es sei denn, die WAN-Verbindung ist ausfallsicher. Ein oder mehrere Vermittlungsserver, die mit Front-End-Servern verbunden sind, können Anrufe an ein oder mehrere Gateways an jedem Standort weiterleiten. Es wird empfohlen, die am Standort erforderlichen Komponenten - Registrierungsstelle, Vermittlungsserver und Gateway - als Survivable Branch-Anwendung bereitzustellen.

Das Festlegen von Anzahl, Größe und Standort der PSTN-Gateways ist möglicherweise die wichtigste und teuerste Entscheidung, die Sie bei der Planung Ihrer Enterprise-VoIP-Infrastruktur treffen müssen.

Sie müssen folgende wichtige Fragen bedenken. Keine dieser Fragen kann unabhängig von den anderen beantwortet werden.

  - Wie viele PSTN-Gateways sind erforderlich? Die Antwort richtet sich nach der Anzahl von Benutzern, der erwarteten Anzahl gleichzeitiger Anrufe (Datenverkehr) und der Anzahl von Standorten (jeder Standort benötigt ein Gateway).

  - Wie groß sollen die Gateways sein? Die Antwort richtet sich nach der Anzahl von Benutzern am Standort und dem zu erwartenden Datenverkehr.

  - Wo sollen sich die Gateways befinden? Die Antwort richtet sich zum Teil nach der Topologie und zum Teil nach der geografischen Verteilung Ihrer Organisation.

Sie sollten auch die Optionen für die Gatewaytopologie berücksichtigen (weitere Informationen hierzu finden Sie im Abschnitt "Gatewaytopologien" weiter unten in diesem Thema).

## M:N-Trunkunterstützung

Die Vermittlungsserver können Anrufe über verschiedene Gateways oder von Internettelefoniedienstanbietern bereitgestellte SBCs (Session Border Controllers) oder eine Kombination dieser beiden Optionen weiterleiten. Außerdem ist die Interaktion mehrerer Vermittlungsserver im Pool mit einem mehreren Gateways möglich. Die zwischen einem Vermittlungsserver und einem Gateway definierte logische Route wird als *Trunk* bezeichnet. Wenn ein interner Benutzer einen PSTN-Anruf tätigt, entscheidet die Routinglogik für ausgehende Anrufe im Front-End-Pool, welcher der für das Routen dieses Anrufs verfügbaren Trunks verwendet werden soll. Wenn in einer Umgebung mit DNS-Lastenausgleich ein Anruf aufgrund eines Problems mit einem bestimmten Vermittlungsserver im Pool nicht an ein Gateway geleitet werden kann, wird dieser Anruf an einen anderen Vermittlungsserver im Pool weitergeleitet.

Ausführliche Informationen zum Planen von mehreren Gateways finden Sie unter [M:N-Trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).

Ausführliche Informationen zu weiteren Verbesserungen beim Ausgangsrouting finden Sie unter [VoIP-Routen in Lync Server 2013](lync-server-2013-voice-routes.md).

## Gatewaytopologien

Halten Sie sich bei Ihren Überlegungen zu den grundlegenden Fragen zur Gatewaybereitstellung an die folgenden Schritte:

1.  Zählen Sie die Standorte, an denen Sie eine PSTN-Anbindung über Enterprise-VoIP bereitstellen möchten.

2.  Schätzen Sie den zu erwartenden Datenverkehr für jeden Standort (Anzahl von Benutzern und durchschnittliche Anzahl von Anrufen pro Stunde und Benutzer).

3.  Stellen Sie mindestens ein Gateway an jedem Standort bereit, um den zu erwartenden Datenverkehr zu verarbeiten.

Die folgende Abbildung zeigt die verteilte Gatewaytopologie, die Sie auf diese Weise erhalten.

**Verteilte Gatewaytopologie**

![Verteilte Gatewaytopologie (Diagramm)](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Verteilte Gatewaytopologie (Diagramm)")

In dieser Topologie werden alle Anrufe zwischen Mitarbeitern innerhalb jedes Standorts sowie zwischen den Standorten über Ihr Intranet weitergeleitet. Anrufe in das Telefonfestnetz werden über das IP-Unternehmensnetzwerk an die Gateways weitergeleitet, die dem Standort der Zielrufnummern am nächsten sind. Wie sollte die Bereitstellung jedoch aussehen, wenn Ihre Organisation Dutzende, Hunderte oder sogar Tausende von Standorten unterstützt, die über mehrere Kontinente verteilt sind - was beispielsweise bei vielen Finanzinstituten und anderen großen Unternehmen der Fall ist? In solchen Fällen ist es nicht empfehlenswert, an jedem Standort ein separates Gateway bereitzustellen.

Zur Lösung dieses Problems stellen viele große Unternehmen mindestens einen oder mehrere große zentraler Standorte für die Telefonie bereit, wie in folgender Abbildung gezeigt.

**Topologie mit einem zentralen Standort für die Telefonie**

![Rechenzentrum-Gatewaytopologie](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Rechenzentrum-Gatewaytopologie")

In dieser Topologie werden in jedem zentraler Standort mehrere große Gateways bereitgestellt, die für die erwartete Benutzerlast ausreichend sind. Alle Anrufe bei Benutzern im Unternehmen werden durch den Telefondienstanbieter des Unternehmens an einen zentralen Standort weitergeleitet. Die Routinglogik am zentraler Standort bestimmt, ob der Anruf über das Intranet oder an das Telefonfestnetz weitergeleitet werden muss.

## Gatewaystandort

Auch der Gatewaystandort bestimmt möglicherweise, welche Typen von Gateways Sie auswählen und wie Sie diese konfigurieren können. Es gibt Dutzende von PSTN-Protokollen, von denen jedoch keines weltweiter Standard ist. Wenn sich all Ihre Gateways in einem einzigen Land bzw. einer einzigen Region befinden, stellt dies kein Problem dar. Wenn Sie jedoch Gateways in mehreren Ländern/Regionen platzieren, muss jedes Gateway gemäß den dort verwendeten PSTN-Standards konfiguriert werden. Außerdem sind die Gateways, die beispielsweise für den Betrieb in Kanada zugelassen sind, in Indien, Brasilien oder der Europäischen Union möglicherweise nicht zugelassen.

## Größe und Anzahl von Gateways

Die Größe der PSTN-Gateways, deren Bereitstellung für die meisten Organisationen in Betracht kommt, liegt im Bereich von 2 bis 960 Ports. (Es gibt sogar noch größere Gateways; diese werden jedoch hauptsächlich von Telefonanbietern verwendet.) Um zu schätzen, wie viele Ports in Ihrer Organisation benötigt werden, beachten Sie die folgenden Richtlinien:

  - Wenn in Ihrer Organisation wenig telefoniert wird (ein PSTN-Anruf pro Benutzer und Stunde), sollten Sie einen Port für jeweils 15 Benutzer zuordnen. Wenn beispielsweise 20 Benutzer vorhanden sind, benötigen Sie ein Gateway mit zwei Ports.

  - Wenn in Ihrer Organisation mäßig viel telefoniert wird (zwei PSTN-Anrufe pro Benutzer und Stunde), sollten Sie einen Port für jeweils 10 Benutzer zuordnen. Wenn beispielsweise 100 Benutzer vorhanden sind, benötigen Sie insgesamt 10 Ports, die Sie auf einem oder auf mehreren Gateways zuordnen können.

  - Wenn in Ihrer Organisation viel telefoniert wird (mindestens drei PSTN-Anrufe pro Benutzer und Stunde), sollten Sie einen Port für jeweils 5 Benutzer zuordnen. Wenn beispielsweise 47.000 Benutzer vorhanden sind, benötigen Sie insgesamt 9.400 Ports, die Sie auf mindestens 10 großen Gateways zuordnen sollten.

  - Zusätzliche Ports können erworben werden, wenn die Benutzeranzahl oder der Umfang des Datenverkehrs in Ihrer Organisation steigt.

Für jede zu unterstützende Benutzeranzahl können Sie entweder wenige größere Gateways oder mehrere kleine bereitstellen. Prinzipiell werden für jede Organisation mindestens zwei Gateways empfohlen, um die Verfügbarkeit sicherzustellen, falls ein Gateway ausfällt.

Für jedes bereitgestellte PSTN-Gateway muss mindestens ein entsprechender Vermittlungsserver vorhanden sein.

