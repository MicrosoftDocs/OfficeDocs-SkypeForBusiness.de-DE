---
title: Aktivieren der Überwachung in Lync Server 2013
TOCTitle: Aktivieren der Überwachung in Lync Server 2013
ms:assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ687994(v=OCS.15)
ms:contentKeyID: 49890663
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren der Überwachung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-17_

Die einheitlichen Datenerfassungs-Agents werden zwar auf jedem Front-End-Server automatisch installiert und aktiviert, das bedeutet jedoch nicht, dass direkt nach der Installation von Microsoft Lync Server 2013 automatisch mit der Erfassung von Überwachungsdaten begonnen wird. Stattdessen müssen Sie zwei Schritte ausführen: Sie müssen Ihre Front-End-Server/Front-End-Pools einer Überwachungsdatenbank zuweisen und die Überwachung der Aufzeichnung von Kommunikationsdatensätzen (KDS) und/oder von QoE (Quality of Experience) auf globaler und/oder Standortebene aktivieren.

Schrittweise Anleitungen zum Zuweisen von Front-End-Servern oder Front-End-Pools zu einer Überwachungsdatenbank finden Sie im Thema [Zuordnen eines Überwachungsspeichers zu einem Front-End-Pool](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) im Bereitstellungshandbuch. Nach dem Festlegen dieser Zuweisungen und dem Veröffentlichen der neuen Lync Server-Topologie können Sie trotzdem noch keine Überwachungsdaten erfassen. Das liegt daran, dass sowohl die KDS- als auch die QoE-Datenerfassung bei der Installation von Lync Server 2013 deaktiviert ist.

Um die Datenerfassung zu starten, müssen Sie die KDS- und/oder QoE-Überwachung aktivieren. (Beachten Sie, dass nicht beide Überwachungsarten aktiviert werden müssen. Sie können einen Überwachungstyp aktivieren und den anderen deaktiviert lassen.) Führen Sie zum Aktivieren der KDS-Überwachung auf globaler Ebene den folgenden Befehl in der Lync Server-Verwaltungsshell aus:

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

Als Alternative können Sie die KDS-Überwachung in der Systemsteuerung für Lync Server 2013 aktivieren. Führen Sie in der Lync Server-Systemsteuerung die folgenden Schritte aus:

1.  Klicken Sie auf **Überwachung**.

2.  Doppelklicken Sie auf der Registerkarte **Aufzeichnung von Kommunikationsdatensätzen** auf die Einstellung **Global**.

3.  Wählen Sie im Bereich **Einstellung für die Aufzeichnung von Kommunikationsdatensätzen (KDS) bearbeiten** die Option **KDS-Überwachung aktivieren** aus, und klicken Sie auf **Commit**.

Führen Sie zum Aktivieren der QoE-Überwachung auf globaler Ebene diesen Befehl in der Lync Server-Verwaltungsshell aus:

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $True

Sie können die QoE-Überwachung jedoch auch in der Lync Server-Systemsteuerung aktivieren. Führen Sie in der Systemsteuerung die folgenden Schritte aus:

1.  Klicken Sie auf **Überwachung**.

2.  Doppelklicken Sie auf der Registerkarte **Quality of Experience-Daten** auf die Einstellung **Global**.

3.  Wählen Sie im Bereich **Quality of Experience (QoE)-Einstellung bearbeiten** die Option **Überwachung von QoE-Daten aktivieren** aus, und klicken Sie dann auf **Commit**.

Wie bereits erwähnt, wird mit den vorhergehenden Beispielen die Überwachung auf globaler Ebene aktiviert, d. h. die KDS- und QoE-Überwachung wird in der gesamten Organisation aktiviert. Alternativ können Sie separate KDS- und QoE-Konfigurationseinstellungen auf Standortebene aktivieren und anschließend selektiv die Überwachung für die einzelnen Standorte aktivieren bzw. deaktivieren. Sie können beispielsweise die KDS-Überwachung für den Standort aktivieren, die KDS-Überwachung für den Standort Dublin hingegen deaktivieren. Weitere Informationen zum Verwalten der Überwachungskonfigurationseinstellungen finden Sie im Bereitstellungshandbuch im Thema [Konfigurieren von KDS (Aufzeichnung von Kommunikationsdatensätzen) und QoE-Einstellungen](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md).

