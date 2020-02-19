---
title: 'Lync Server 2013: Konfigurieren der Reaktionsgruppe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Response Group
ms:assetid: c56db929-cb21-4af0-be3f-c8f807b78a5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205249(v=OCS.15)
ms:contentKeyID: 48185359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60c224e83bc3d86dca647258540aee2551656d05
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-response-group-in-lync-server-2013"></a>Konfigurieren der Reaktionsgruppe in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-30_

Reaktionsgruppe ist eine Enterprise-VoIP-Funktion, mit der eingehende Anrufe an Personengruppen weitergeleitet und in die Warteschlange gestellt werden, die als *Agents*bezeichnet werden, wie beispielsweise ein Helpdesk oder ein Kundendienst Desk.

Die erforderlichen Komponenten für Reaktionsgruppen werden bei der Bereitstellung von Enterprise-VoIP automatisch auf dem Front-End-Server oder Standard Edition-Server installiert und aktiviert. Zur Bereitstellung der Reaktionsgruppenfunktion für Benutzer müssen Sie Agentgruppen, dann Warteschleifen und anschließend Workflows konfigurieren. Darüber hinaus kann ein Reaktionsgruppen Administrator die Konfiguration eines vorhandenen Workflows an einen Reaktionsgruppen Manager delegieren, der dann den Workflow und die zugehörigen Agentgruppen und Warteschlangen ändern und neu konfigurieren kann.

Dieser Abschnitt führt Sie durch die Konfiguration von lync Server 2013 Reaktionsgruppe. Es wird davon ausgegangen, dass Sie die Planungsabschnitte im Zusammenhang mit der Reaktionsgruppe bereits gelesen haben und ein Enterprise Edition-Server oder ein Standard Edition-Server mit Enterprise-VoIP bereitgestellt haben.

<div>


> [!TIP]  
> Ausführliche Informationen zum Erstellen einer Reaktionsgruppe mithilfe von lync Server-Verwaltungsshell, einschließlich eines Beispielskripts, finden Sie unter "Erstellen der ersten Reaktionsgruppe mit lync Server-Verwaltungsshell <A href="https://go.microsoft.com/fwlink/p/?linkid=204108">https://go.microsoft.com/fwlink/p/?linkId=204108</A>" unter.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Berechtigungen und Voraussetzungen für die Reaktionsgruppen Konfiguration in lync Server 2013](lync-server-2013-response-group-configuration-permissions-and-prerequisites.md)

  - [Bereitstellungsprozess für die Reaktionsgruppe in lync Server 2013](lync-server-2013-deployment-process-for-response-group.md)

  - [Übersicht über Szenarien zur Erstellung von Workflows in lync Server 2013](lync-server-2013-overview-of-workflow-creation-scenarios.md)

  - [Erstellen von Gruppen für Reaktionsgruppen-Agents lync Server 2013](lync-server-2013-create-response-group-agent-groups.md)

  - [Erstellen von Warteschlangen für Reaktionsgruppen in lync Server 2013](lync-server-2013-create-response-group-queues.md)

  - [Optional Definieren von Geschäftszeiten für Reaktionsgruppen in lync Server 2013](lync-server-2013-optional-define-response-group-business-hours.md)

  - [Optional Definieren von Feiertagssätzen für Reaktionsgruppen in lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [Erstellen von Workflows für Reaktionsgruppen in lync Server 2013](lync-server-2013-create-response-group-workflows.md)

  - [Optional Überprüfen der Bereitstellung von Reaktionsgruppen in lync Server 2013](lync-server-2013-optional-verify-response-group-deployment.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Planen von Funktionen für die Anrufverwaltung in lync Server 2013](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

