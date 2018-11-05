---
title: 'Lync Server 2013: Konfigurieren von Reaktionsgruppen'
TOCTitle: Konfigurieren von Reaktionsgruppen
ms:assetid: c56db929-cb21-4af0-be3f-c8f807b78a5a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205249(v=OCS.15)
ms:contentKeyID: 49295346
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Reaktionsgruppen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Eine Reaktionsgruppe ist ein Enterprise-VoIP-Feature, mit dem eingehende Anrufe an Benutzergruppen, so genannte *Agents* (z. B. für einen Helpdesk oder einen Kundendienst) weitergeleitet und in der Warteschleife platziert werden.

Die erforderlichen Komponenten für Reaktionsgruppen werden bei der Bereitstellung von Enterprise-VoIP automatisch auf dem Front-End-Server oder Standard Edition-Server installiert und aktiviert. Zur Bereitstellung des Reaktionsgruppenfeatures für Benutzer müssen Sie Agentgruppen, dann Warteschleifen und anschließend Workflows konfigurieren. Darüber hinaus kann ein Reaktionsgruppenadministrator die Konfiguration eines vorhandenen Workflows an einen Reaktionsgruppenmanager delegieren, der dann den Workflow und die zugehörigen Agentgruppen und Warteschlangen ändern und erneut konfigurieren kann.

In diesem Abschnitt wird die Konfiguration von Lync Server 2013- Reaktionsgruppen behandelt. Es wird davon ausgegangen, dass Sie die Planungsabschnitte zu Reaktionsgruppen gelesen und einen Enterprise Edition-Server oder Standard Edition-Server mit Enterprise-VoIP bereitgestellt haben.


> [!TIP]
> Ausführliche Informationen und ein Beispielskript für die Erstellung einer Reaktionsgruppe mithilfe der Lync Server-Verwaltungsshell finden Sie unter "Creating Your First Response Group Using Lync Server Management Shell" unter <A href="http://go.microsoft.com/fwlink/p/?linkid=204108">http://go.microsoft.com/fwlink/p/?linkId=204108</A>.



## In diesem Abschnitt

  - [Berechtigungen und Voraussetzungen für die Konfiguration von Reaktionsgruppen in Lync Server 2013](lync-server-2013-response-group-configuration-permissions-and-prerequisites.md)

  - [Bereitstellungsprozess für Reaktionsgruppen in Lync Server 2013](lync-server-2013-deployment-process-for-response-group.md)

  - [Übersicht über Szenarios zur Erstellung von Workflows in Lync Server 2013](lync-server-2013-overview-of-workflow-creation-scenarios.md)

  - [Erstellen von Agent-Gruppen für Reaktionsgruppen Lync Server 2013](lync-server-2013-create-response-group-agent-groups.md)

  - [Erstellen von Warteschleifen für Reaktionsgruppen in Lync Server 2013](lync-server-2013-create-response-group-queues.md)

  - [(Optional) Definieren von Geschäftszeiten für Reaktionsgruppen in Lync Server 2013](lync-server-2013-optional-define-response-group-business-hours.md)

  - [(Optional) Definieren von Feiertagsschemas für Reaktionsgruppen in Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [Erstellen von Workflows für Reaktionsgruppen in Lync Server 2013](lync-server-2013-create-response-group-workflows.md)

  - [(Optional) Überprüfen der Reaktionsgruppenbereitstellung in Lync Server 2013](lync-server-2013-optional-verify-response-group-deployment.md)

## Siehe auch

#### Weitere Ressourcen

[Planen der Anrufverwaltungsfunktionen in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)

