---
title: 'Lync Server 2013: anzeigen und Analysieren von Monitoring Server-Berichten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing and analyzing monitoring server reports
ms:assetid: 4dd448f1-01d2-49b2-b109-0728f36566b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720332(v=OCS.15)
ms:contentKeyID: 63969599
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cc942c887175bacb0047c5d82d1ad9a89c18ef5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-and-analyzing-monitoring-server-reports-in-lync-server-2013"></a>Anzeigen und Analysieren von Monitoring Server-Berichten in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-05-19_

Monitoring Server-Berichte bieten verschiedene Maßnahmen zur Sprachqualität, um die QoE zu überwachen, die an Endbenutzer übermittelt wird. Darüber hinaus enthält Monitoring Server mehrere integrierte Berichte, die Ihre Organisation verwenden kann, um die Trends zur Verwendung und Medienqualität im Netzwerk Ihrer Organisation zu beobachten und Probleme mit der Medienqualität zu beheben.

Ein primärer Bestandteil des Haltens von Monitoring Server-Berichten, die für tägliche und wöchentliche Vorgänge interessant sind, ist das Anzeigen und Analysieren von Berichten zur Medienqualität, insbesondere:

  - QoE-Zusammenfassung/Trend Berichte

  - QoE-Leistungsberichte

<div>

## <a name="view-reports-from-the-monitoring-server"></a>Anzeigen von Berichten vom Monitoring Server

1.  Suchen Sie in einem Webbrowser nach den Servern, die die SQL Reporting Services hosten.

2.  Zeigen Sie die erforderlichen Berichte über den Browser-Bildschirm an.

3.  Optional Exportieren eines Berichts durch Auswählen der Exportoption und des erforderlichen Ausgabeformats

</div>

<div>

## <a name="configure-call-detail-recording-cdr"></a>Konfigurieren der Anrufdetailaufzeichnung (CDR)

1.  Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Berechtigungen verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.

3.  Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Aufzeichnung von Kommunikationsdatensätzen**.

4.  Klicken Sie auf der Seite **Aufzeichnung von Kommunikationsdatensätzen** in der Tabelle auf den geeigneten Standort, klicken Sie auf **Bearbeiten** und anschließend auf **Details einblenden**.

5.  Wenn Sie die Bereinigung aktivieren möchten, wählen Sie die Option **zum Entfernen von Überwachungs Servern aktivieren**aus.

6.  Unter " **Anrufdetails aufzeichnen" für maximale Dauer (Tage):** wählen Sie die maximale Anzahl von Tagen aus, für die Anruf Detail Aufzeichnungen aufbewahrt werden sollen.

7.  Wählen Sie unter **Maximale Aufbewahrungsdauer von Fehlerberichtsdaten (in Tagen):** die maximale Anzahl von Tagen, für die Fehlerberichte gespeichert werden sollen.

8.  Klicken Sie auf **Commit**.

</div>

<div>

## <a name="configure-qoe"></a>Konfigurieren von QoE

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter Delegate Setup Permissions.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.

3.  Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **QoE-Daten**.

4.  Klicken Sie auf der Seite **QoE-Daten** in der Tabelle auf den geeigneten Standort, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.

5.  Wenn Sie die Bereinigung aktivieren möchten, wählen Sie die Option **zum Entfernen von Überwachungs Servern aktivieren**aus.

6.  In " **Anrufdetails aufzeichnen" für maximale Dauer (Tage):** wählen Sie die maximale Anzahl von Tagen aus, die QoE-Daten beibehalten werden sollen.

7.  Klicken Sie auf Commit ausführen.

</div>

<div>

## <a name="change-the-archiving-policy"></a>Ändern der Archivierungsrichtlinie

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.

3.  Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**.

4.  Klicken Sie in der Liste der Richtlinien auf **Global**, dann auf **Bearbeiten** und anschließend auf **Details anzeigen**.

5.  Führen Sie im Abschnitt **Bearbeiten der Archivierungsrichtlinie – Global** folgende Aktionen aus:

6.  Aktivieren oder deaktivieren Sie das Kontrollkästchen **interne Kommunikation archivieren** , um die interne Archivierung für die Bereitstellung zu aktivieren oder zu deaktivieren.

7.  Wenn Sie die externe Archivierung für die Bereitstellung aktivieren oder deaktivieren möchten, aktivieren oder deaktivieren Sie das Kontrollkästchen **externe Kommunikation archivieren** .

8.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="apply-an-archiving-policy-to-a-user"></a>Anwenden einer Archivierungsrichtlinie auf einen Benutzer

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer** und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.

4.  Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.

5.  Wählen Sie in **lync Server-Benutzer bearbeiten** unter **Archivierungsrichtlinie**die Archivierungs Benutzerrichtlinie aus, die Sie anwenden möchten.

6.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Verwenden von Überwachungsberichten in lync Server 2013](lync-server-2013-using-monitoring-reports.md)  
[Bericht zur Server Leistung in lync Server 2013](lync-server-2013-server-performance-report.md)  
[Bericht zum Vergleich der Medienqualität in lync Server 2013](lync-server-2013-media-quality-comparison-report.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

