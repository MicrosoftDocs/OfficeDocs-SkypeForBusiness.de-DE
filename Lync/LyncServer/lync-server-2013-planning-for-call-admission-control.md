---
title: 'Lync Server 2013: Planen des Anrufsteuerungsdiensts'
TOCTitle: Planen des Anrufsteuerungsdiensts
ms:assetid: ca367138-adf5-4119-bc40-5ddf335ed22f
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398842(v=OCS.15)
ms:contentKeyID: 49295402
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planen des Anrufsteuerungsdiensts in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

In LAN-Umgebungen stellt die verfügbare Bandbreite von Unternehmensnetzwerken für IP-basierte UC-Anwendungen (Unified Communications) wie zum Beispiel Telefonie, Video und Anwendungsfreigabe im Allgemeinen keine Einschränkung dar. Wenn Standorte jedoch über ein WAN verbunden sind, kann die Bandbreite eingeschränkt sein. Wird eine WAN-Verbindung durch übermäßig hohen Netzwerkdatenverkehr überlastet, werden aktuelle Mechanismen wie Queuing, Pufferung und das Verwerfen von Paketen eingesetzt, um das Problem zu lösen. Der zusätzliche Datenverkehr wird üblicherweise verzögert, bis die Überlastung aufgehoben ist, oder gegebenenfalls verworfen. Bei herkömmlichem Datenverkehr kann der Empfängerclient die Daten in solchen Situationen wiederherstellen. Bei Echtzeitdatenverkehr wie Unified Communications lässt sich eine Netzwerküberlastung nicht auf diese Weise beheben, da UC-Datenverkehr sowohl für Latenz als auch für Paketverluste anfällig ist. Eine Überlastung des WAN kann zu einer unzureichenden QoE (Quality of Experience) für Benutzer führen. Bei Echtzeitdatenverkehr in überlasteten Netzwerken ist es besser, Anrufe abzuweisen als Verbindungen mit schlechter Qualität zuzulassen.

Die Anrufsteuerung (Call Admission Control, CAC) ermittelt, ob ausreichend Netzwerkbandbreite für eine Echtzeitsitzung in akzeptabler Qualität vorhanden ist. In Lync Server 2013 steuert die Anrufsteuerung den Echtzeitdatenverkehr nur für Audio- und Videodaten, hat jedoch keinen Einfluss auf anderen Datenverkehr. Wenn der WAN-Standardpfad nicht die erforderliche Bandbreite aufweist, kann die Anrufsteuerung versuchen, den Anruf über einen Internetpfad oder das Festnetz zu leiten. Die Anrufsteuerung ist nur in Lync Server verfügbar.

In diesem Abschnitt wird die Funktionsweise der Anrufsteuerung beschrieben, und es wird erläutert, wie die Anrufsteuerung geplant werden kann.


> [!NOTE]
> Lync Server umfasst drei erweiterte Enterprise-VoIP-Funktionen: Anrufsteuerung (Call Admission Control, CAC), Notrufdienste (E9-1-1) und Medienumgehung. Eine Übersicht über die Planungsinformationen, die für alle drei Funktionen benötigt werden, finden Sie unter <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Netzwerkeinstellungen für die erweiterten Enterprise-VoIP-Funktionen in Lync Server 2013</A>.



## In diesem Abschnitt

  - [Übersicht über die Anrufsteuerung in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md)

  - [Definieren der Anforderungen Ihrer Organisation für die Anrufsteuerung in Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [Beispiel: Zusammenstellen der Anforderungen Ihrer Organisation für die Anrufsteuerung in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [Komponenten und Topologien für die Anrufsteuerung in Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md)

  - [Bewährte Methoden für die Anrufsteuerung in Lync Server 2013](lync-server-2013-best-practices-for-call-admission-control.md)

  - [Prüfliste für die Bereitstellung der Anrufsteuerung in Lync Server 2013](lync-server-2013-deployment-checklist-for-call-admission-control.md)

