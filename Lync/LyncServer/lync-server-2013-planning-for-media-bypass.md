---
title: 'Lync Server 2013: Planung der Medienumgehung'
TOCTitle: Planung der Medienumgehung
ms:assetid: 8ac732b6-8538-4d7b-b1a9-2035e419dac2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398703(v=OCS.15)
ms:contentKeyID: 49294682
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planung der Medienumgehung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Bei der Medienumgehung wird für Anrufe, deren Signaldaten über den Vermittlungsserver verarbeitet werden, der Vermittlungsserver nach Möglichkeit aus dem Medienpfad entfernt.

Die Medienumgehung kann die Sprachqualität verbessern, indem die Latenz verringert, eine unnötige Übersetzung und Paketverluste verhindert sowie potenzielle Fehlerstellen minimiert werden. Der Vermittlungsserver muss für Anrufe mit Umgehung keine Mediendatenverarbeitung durchführen, sodass die Vermittlungsserverlast reduziert und die Skalierbarkeit verbessert wird. Diese geringere Last trägt dazu bei, dass der Vermittlungsserver mehrere Gateways steuern kann.

Wenn eine Zweigstelle ohne Vermittlungsserver mit einem zentralen Standort über eine oder mehrere WAN-Leitungen mit Bandbreitenbeschränkung verbunden ist, werden die Bandbreitenanforderungen durch die Medienumgehung reduziert, indem Mediendaten von einem Client am Zweigstellenstandort direkt an das lokale Gateway übermittelt werden, ohne zunächst über die WAN-Leitung an einen Vermittlungsserver am zentralen Standort und zurück gesendet werden zu müssen.

Wenn der Vermittlungsserver keine Mediendaten verarbeiten muss, kann durch die Medienumgehung auch die Anzahl von erforderlichen Vermittlungsserver in einer Enterprise-VoIP-Infrastruktur reduziert werden.

Die folgende Abbildung zeigt grundlegende Pfade für Medien- und Signaldatenverkehr in Topologien mit und ohne Umgehung.

**Pfade für Medien- und Signaldatenverkehr mit und ohne Medienumgehung**

![VoIP-Anrufsteuerung: Medienumgehung – Verbindungserzwingung](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "VoIP-Anrufsteuerung: Medienumgehung – Verbindungserzwingung")

Allgemein gilt, dass die Medienumgehung wenn möglich aktiviert werden sollte.

## In diesem Abschnitt

  - [Übersicht über die Medienumgehung in Lync Server 2013](lync-server-2013-overview-of-media-bypass.md)

  - [Modi für die Medienumgehung in Lync Server 2013](lync-server-2013-media-bypass-modes.md)

  - [Medienumgehung und Anrufsteuerung in Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [Technische Anforderungen für die Medienumgehung in Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)

## Zugehörige Abschnitte

[Bereitstellen von erweiterten Enterprise-VoIP-Features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

## Siehe auch

#### Aufgaben

[Konfigurieren eines Trunks mit Medienumgehung in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  

#### Konzepte

[Optionen für die globale Medienumgehung in Lync Server 2013](lync-server-2013-global-media-bypass-options.md)

