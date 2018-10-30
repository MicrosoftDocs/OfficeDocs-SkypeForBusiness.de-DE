---
title: 'Lync Server 2013: Planen des Zugriffs externer Benutzer'
TOCTitle: Planen des Zugriffs externer Benutzer
ms:assetid: ea098933-eff5-461e-aba3-e7f128784dc2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg399048(v=OCS.15)
ms:contentKeyID: 49295778
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planen des Zugriffs externer Benutzer in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-01-19_

Die Kommunikation beinhaltet in den meisten Organisationen Dienste und Benutzer, die sich nicht innerhalb des internen Netzwerks befinden. Diese Dienste und Benutzer umfassen Mitarbeiter, die zeitweise oder dauerhaft außerhalb des Standorts arbeiten, Mitarbeiter von Kunden- oder Partnerorganisationen, Benutzer von öffentlichen Chatdiensten sowie potenzielle Kunden, Partner und anonyme Benutzer, die Sie zu Besprechungen und Präsentationen einladen möchten. Diese Benutzer werden in dieser Dokumentation kollektiv als *externe Benutzer* bezeichnet.

Mit Microsoft Lync Server 2013 können Benutzer in Ihrer Organisation Instant Messaging- und Anwesenheitsfunktionen zur Kommunikation mit externen Benutzern verwenden sowie zusammen mit Ihren standortexternen Mitarbeitern und anderen externen Benutzern an A/V-Konferenzen (Audio/Video) und Webkonferenzen teilnehmen. Sie können auch externen Zugriff über mobile Geräte und über Enterprise-VoIP unterstützen. Externe Benutzer, die nicht zu Ihrer Organisation gehören, können ohne Anmeldung beim Intranet an Lync Server 2013-Besprechungen teilnehmen, d. h. anonyme Teilnehmer sind zulässig.

Stellen Sie in Ihrem Umkreisnetzwerk (auch als überwachtes Subnetz bezeichnet) einen Lync Server 2013-Edgeserver bereit, um die Kommunikation über die Firewall Ihrer Organisation hinweg zu ermöglichen. Der Edgeserver steuert den Zugriff von Benutzern außerhalb der Firewall auf Ihre interne Lync Server 2013-Bereitstellung. Der Edgeserver steuert darüber hinaus die Kommunikation von Benutzern innerhalb der Firewall mit externen Benutzern.

Je nach Ihren Anforderungen können Sie einen oder mehrere Edgeserver an einem oder mehreren Standorten bereitstellen. In diesem Abschnitt werden Szenarios für den Zugriff externer Benutzer in Lync Server 2013 beschrieben, und es wird erläutert, wie Sie eine Edge- und Reveresproxytopologie planen können.


> [!NOTE]
> Sie brauchen zwar einen Edgeserver, um Enterprise-VoIP und externen Benutzerzugriff zu unterstützen, doch geht es in diesem Abschnitt primär um die Unterstützung von Instant Messaging, Anwesenheit, A/V-Konferenzen, Partnerverbünden, Webkonferenzen und Lync Mobile. Ausführliche Informationen zur Unterstützung von Enterprise-VoIP finden Sie unter <A href="lync-server-2013-planning-for-enterprise-voice.md">Planen von Enterprise-VoIP in Lync Server 2013</A> in der Planungsdokumentation.



## In diesem Abschnitt

  - [Änderungen in Lync Server 2013, die die Planung für Edgeserver betreffen](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [Systemanforderungen für Komponenten für den Zugriff durch externe Benutzer für Lync Server 2013](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [Übersicht über den Zugriff durch externe Benutzer in Lync Server 2013](lync-server-2013-overview-of-external-user-access.md)

  - [Grundlegendes zur AutoErmittlung](lync-server-2013-understanding-autodiscover.md)

  - [Auswählen einer Topologie in Lync Server 2013](lync-server-2013-choosing-a-topology.md)

  - [Datenerfassung in Lync Server 2013](lync-server-2013-data-collection.md)

  - [Ermitteln von DNS-Anforderungen für Lync Server 2013](lync-server-2013-determine-dns-requirements.md)

  - [Ermitteln der Anforderungen für externe A/V-Firewalls und Ports für Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [Planen von Edgeserver-Zertifikaten in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)

  - [Szenarien für den Zugriff durch externe Benutzer in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)

