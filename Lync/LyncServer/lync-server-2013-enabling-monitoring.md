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
ms.openlocfilehash: 0f11aab3c58a43ac0746cb1f297bf4f3f85d28c0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735825"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-monitoring-in-lync-server-2013"></a>Aktivieren der Überwachung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-17_

Obwohl die Unified Data Collection-Agents automatisch auf jedem Front-End-Server installiert und aktiviert werden, bedeutet dies nicht, dass Sie automatisch mit dem Sammeln von Überwachungsdaten beginnen, sobald Sie die Installation von Microsoft lync Server 2013 abgeschlossen haben. Stattdessen müssen Sie zwei Schritte ausführen: Sie müssen Ihre Front-End-Server/Front-End-Pools mit einer Überwachungsdatenbank verknüpfen, und Sie müssen die Überwachung der Anrufdetailaufzeichnung (CDR) und/oder der Quality of Experience (QoE) auf globaler Ebene und/oder im Bereich der Website aktivieren.

Eine Schritt-für-Schritt-Anleitung zum Zuordnen von Front-End-Servern oder Front-End-Pools zu einer Überwachungsdatenbank finden Sie unter dem Thema [Zuordnen eines überwachungsspeichers zu einem Front-End-Pool in lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) im Bereitstellungshandbuch. Nachdem diese Zuordnungen vorgenommen wurden und nachdem die neue lync Server-Topologie veröffentlicht wurde, können Sie weiterhin keine Überwachungsdaten sammeln. Das liegt daran, dass die Datensammlung für CDR und QoE standardmäßig deaktiviert ist, wenn Sie lync Server 2013 installieren.

Um mit der Datensammlung beginnen zu können, müssen Sie die CDR-und/oder QoE-Überwachung aktivieren. (Beachten Sie, dass Sie nicht sowohl die CDR-als auch die QoE-Überwachung aktivieren müssen; Wenn Sie möchten, können Sie eine Art von Überwachung aktivieren, während der andere Typ deaktiviert bleibt.) Führen Sie den folgenden Befehl in der lync Server-Verwaltungsshell aus, um die CDR-Überwachung im globalen Bereich zu aktivieren:

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

Alternativ können Sie die CDR-Überwachung in der lync Server 2013-Systemsteuerung aktivieren. Führen Sie in der lync Server-Systemsteuerung die folgenden Schritte aus:

1.  Klicken Sie auf **Überwachung**.

2.  Doppelklicken Sie auf der Registerkarte **Aufzeichnung von Kommunikationsdatensätzen** auf die Einstellung **Global**.

3.  Wählen Sie im Bereich **KDS-Einstellungen (Aufzeichnung von Kommunikationsdatensätzen) bearbeiten** die Option **Überwachung von KDS-Aufzeichnungen aktivieren** aus und klicken Sie auf **Commit ausführen**.

Um die QoE-Überwachung im globalen Bereich zu aktivieren, führen Sie diesen Befehl in der lync Server-Verwaltungsshell aus:

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $True

Wenn Sie möchten, können Sie auch die QoE-Überwachung in der lync Server-Systemsteuerung aktivieren. Führen Sie in der Systemsteuerung die folgenden Schritte aus:

1.  Klicken Sie auf **Überwachung**.

2.  Doppelklicken Sie auf der Registerkarte **Quality of Experience-Daten** auf die Einstellung **Global**.

3.  Wählen Sie im Bereich **QoE-Einstellungen (Quality of Experience) bearbeiten** die Option **Überwachung von QoE-Daten aktivieren** aus und klicken Sie dann auf **Commit ausführen**.

Wie bereits erwähnt, ermöglichen die obigen Beispiele die Überwachung auf globaler Ebene; Das bedeutet, dass Sie die CDR-und QoE-Überwachung in Ihrer Organisation aktivieren. Alternativ können Sie separate CDR-und QoE-Konfigurationseinstellungen im Website Bereich erstellen und dann die Überwachung für jede Website selektiv aktivieren oder deaktivieren. So können Sie beispielsweise die CDR-Überwachung für Ihre Redmond-Website aktivieren und dennoch die CDR-Überwachung für Ihre Dublin-Website deaktivieren. Weitere Informationen zum Verwalten ihrer Überwachungs Konfigurationseinstellungen finden Sie im Bereitstellungshandbuch unter [Konfigurieren der Einstellungen für die Anrufdetailaufzeichnung und der Qualität der Benutzerfreundlichkeit in lync Server 2013](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md).

</div>

<span> </span>

</div>

</div>

</div>

