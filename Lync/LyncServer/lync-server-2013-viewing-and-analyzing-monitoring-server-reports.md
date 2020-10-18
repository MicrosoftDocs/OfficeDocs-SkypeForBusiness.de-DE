---
title: 'Lync Server 2013: anzeigen und Analysieren von Monitoring Server-Berichten'
description: 'Lync Server 2013: anzeigen und Analysieren von Monitoring Server-Berichten.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing and analyzing monitoring server reports
ms:assetid: 4dd448f1-01d2-49b2-b109-0728f36566b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720332(v=OCS.15)
ms:contentKeyID: 63969599
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f2a1812d76a49d487bea35acae3e22ea403f105
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580041"
---
# <a name="viewing-and-analyzing-monitoring-server-reports-in-lync-server-2013"></a>Anzeigen und Analysieren von Monitoring Server-Berichten in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-05-19_

In Monitoring Server Berichten werden verschiedene Maßnahmen zur Sprachqualität bereitgestellt, um die QoE-Überwachung zu überwachen, die den Endbenutzern zugestellt wird. Darüber hinaus enthält Monitoring Server mehrere integrierte Berichte, die Ihre Organisation verwenden kann, um Trends im Zusammenhang mit der Verwendung und Medienqualität im Netzwerk Ihres Unternehmens zu beobachten und Probleme mit der Medienqualität zu beheben.

Ein primärer Bestandteil des Aufhaltens von Monitoring Server Berichten, die für tägliche und wöchentliche Vorgänge interessant sind, ist das Anzeigen und Analysieren von Medien Qualitätsberichten, insbesondere:

  - QoE-Zusammenfassung/Trend Berichte

  - QoE-Leistungsberichte

<div>

## <a name="view-reports-from-the-monitoring-server"></a>Anzeigen von Berichten vom Monitoring Server

1.  Suchen Sie in einem Webbrowser nach den Servern, die die SQL Reporting Services hosten.

2.  Zeigen Sie die erforderlichen Berichte auf dem Browser Bildschirm an.

3.  Optional Exportieren Sie einen Bericht, indem Sie die Exportoption und das erforderliche Ausgabeformat auswählen.

</div>

<div>

## <a name="configure-call-detail-recording-cdr"></a>Konfigurieren der Aufzeichnung von Anrufdetails (KDS)

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Berechtigungen verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, an jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.

3.  Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Aufzeichnung von Kommunikationsdatensätzen**.

4.  Klicken Sie auf der Seite **Aufzeichnung von Kommunikationsdatensätzen** in der Tabelle auf den geeigneten Standort, klicken Sie auf **Bearbeiten** und anschließend auf **Details einblenden**.

5.  Um die Bereinigung zu aktivieren, wählen Sie **für Monitoring Server die Option Löschen aus**.

6.  In **Keep Call Detail Recordings for Maximum Duration (Days):** wählen Sie die maximale Anzahl von Tagen aus, für die die Aufzeichnung von Gesprächs Details aufbewahrt werden soll.

7.  Wählen Sie unter **Maximale Aufbewahrungsdauer von Fehlerberichtsdaten (in Tagen):** die maximale Anzahl von Tagen, für die Fehlerberichte gespeichert werden sollen.

8.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="configure-qoe"></a>Konfigurieren von QoE

1.  Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an. Ausführliche Informationen finden Sie unter Delegate Setup Permissions.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.

3.  Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **QoE-Daten**.

4.  Klicken Sie auf der Seite **QoE-Daten** in der Tabelle auf den geeigneten Standort, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.

5.  Um die Bereinigung zu aktivieren, wählen Sie **für Monitoring Server die Option Löschen aus**.

6.  In **Keep Call Detail Recordings for Maximum Duration (Days):** wählen Sie die maximale Anzahl von Tagen aus, für die QoE-Daten aufbewahrt werden sollen.

7.  Klicken Sie auf Commit ausführen.

</div>

<div>

## <a name="change-the-archiving-policy"></a>Ändern der Archivierungsrichtlinie

1.  Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.

3.  Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Archivierungsrichtlinie**.

4.  Klicken Sie in der Liste der Richtlinien auf **Global**, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.

5.  Führen Sie im Abschnitt **Bearbeiten der Archivierungsrichtlinie – Global** die folgenden Aktionen aus:

6.  Aktivieren oder deaktivieren Sie das Kontrollkästchen **interne Kommunikation archivieren** , um die interne Archivierung für die Bereitstellung zu aktivieren oder zu deaktivieren.

7.  Aktivieren oder deaktivieren Sie das Kontrollkästchen **externe Kommunikation archivieren** , um die externe Archivierung für die Bereitstellung zu aktivieren oder zu deaktivieren.

8.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="apply-an-archiving-policy-to-a-user"></a>Anwenden einer Archivierungsrichtlinie auf einen Benutzer

1.  Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.

3.  Klicken Sie auf der linken Navigationsleiste auf **Benutzer**, und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.

4.  Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.

5.  Wählen Sie im Abschnitt **lync Server Benutzer bearbeiten** unter **Archivierungsrichtlinie**die Archivierungs Benutzerrichtlinie aus, die Sie anwenden möchten.

6.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Verwenden von Überwachungsberichten in lync Server 2013](lync-server-2013-using-monitoring-reports.md)  
[Bericht über die Server Leistung in lync Server 2013](lync-server-2013-server-performance-report.md)  
[Vergleichsbericht über Medienqualität in lync Server 2013](lync-server-2013-media-quality-comparison-report.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

