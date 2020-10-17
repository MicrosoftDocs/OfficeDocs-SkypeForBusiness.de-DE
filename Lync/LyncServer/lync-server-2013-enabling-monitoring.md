---
title: 'Lync Server 2013: Aktivieren der Überwachung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling monitoring
ms:assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687994(v=OCS.15)
ms:contentKeyID: 49733584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0b637ea06d0255d53f73eef0385c3e929045071
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528532"
---
# <a name="enabling-monitoring-in-lync-server-2013"></a>Aktivieren der Überwachung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-17_

Obwohl die Unified Data Collection-Agents auf jedem Front-End-Server automatisch installiert und aktiviert werden, bedeutet das nicht, dass Sie automatisch mit der Erfassung von Überwachungsdaten beginnen, sobald Sie Microsoft lync Server 2013 fertig gestellt haben. Stattdessen müssen Sie zwei Schritte ausführen: Sie müssen Ihre Front-End-Server/Front-End-Pools einer Überwachungsdatenbank zuweisen und die Überwachung der Aufzeichnung von Kommunikationsdatensätzen (KDS) und/oder von QoE (Quality of Experience) auf globaler und/oder Standortebene aktivieren.

Eine Schritt-für-Schritt-Anleitung zum Zuordnen von Front-End-Servern und Front-End-Pools zu einer Überwachungsdatenbank finden Sie im Bereitstellungshandbuch im Thema [Zuordnen eines überwachungsspeichers mit einem Front-End-Pool in lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) . Nach dem Festlegen dieser Zuweisungen und dem Veröffentlichen der neuen Lync Server-Topologie können Sie trotzdem noch keine Überwachungsdaten erfassen. Das liegt daran, dass die KDS-und QoE-Datensammlung standardmäßig deaktiviert ist, wenn Sie lync Server 2013 installieren.

Um mit der Datensammlung beginnen zu können, müssen Sie die KDS-und/oder QoE-Überwachung aktivieren. (Beachten Sie, dass Sie nicht sowohl die KDS-als auch die QoE-Überwachung aktivieren müssen, wenn Sie es vorziehen, können Sie eine Überwachungsart aktivieren, während Sie den anderen Typ deaktiviert lassen.) Führen Sie den folgenden Befehl in der lync Server-Verwaltungsshell aus, um die KDS-Überwachung auf globaler Ebene zu aktivieren:

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

Alternativ können Sie die KDS-Überwachung in der lync Server 2013-Systemsteuerung aktivieren. Führen Sie in der lync Server-Systemsteuerung das folgende Verfahren aus:

1.  Klicken Sie auf **Überwachung**.

2.  Doppelklicken Sie auf der Registerkarte **Aufzeichnung von Kommunikationsdatensätzen** auf die Einstellung **Global**.

3.  Wählen Sie im Bereich **Einstellung für die Aufzeichnung von Kommunikationsdatensätzen (KDS) bearbeiten** die Option **KDS-Überwachung aktivieren** aus, und klicken Sie auf **Commit**.

Um die QoE-Überwachung auf globaler Ebene zu aktivieren, führen Sie diesen Befehl in der lync Server-Verwaltungsshell aus:

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $True

Wenn es Ihnen lieber ist, können Sie die QoE-Überwachung auch in der lync Server-Systemsteuerung aktivieren. Führen Sie in der Systemsteuerung die folgenden Schritte aus:

1.  Klicken Sie auf **Überwachung**.

2.  Doppelklicken Sie auf der Registerkarte **Quality of Experience-Daten** auf die Einstellung **Global**.

3.  Wählen Sie im Bereich **Quality of Experience (QoE)-Einstellung bearbeiten** die Option **Überwachung von QoE-Daten aktivieren** aus, und klicken Sie dann auf **Commit**.

Wie bereits erwähnt, ermöglichen die obigen Beispiele die Überwachung auf globaler Ebene; Das bedeutet, dass Sie die KDS-und QoE-Überwachung in Ihrer Organisation aktivieren. Alternativ können Sie separate KDS-und QoE-Konfigurationseinstellungen auf Standortebene erstellen und dann die Überwachung für jeden Standort selektiv aktivieren oder deaktivieren. Beispielsweise können Sie die KDS-Überwachung für Ihren Standort in Redmond aktivieren und dennoch die KDS-Überwachung für Ihren Standort in Dublin deaktivieren. Weitere Informationen zum Verwalten der Überwachungs Konfigurationseinstellungen finden Sie im Bereitstellungshandbuch unter Konfigurieren der Einstellungen für die Aufzeichnung von Kommunikationsdatensätzen [und der Qualität der Benutzerfreundlichkeit in lync Server 2013](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md).

</div>

<span> </span>

</div>

</div>

</div>

