---
title: 'Lync Server 2013: Übersicht über die Überwachung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of monitoring
ms:assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204937(v=OCS.15)
ms:contentKeyID: 48184261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27826948f9206c6053b166d901145ed6785a0189
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755489"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-monitoring-in-lync-server-2013"></a>Übersicht über die Überwachung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-05_

In Microsoft lync Server 2013 wird die Überwachung verwendet, um Nutzungsinformationen und QoE-Daten (Quality of Experience) zu den Kommunikationssitzungen zu sammeln, an denen Ihre Benutzer beteiligt sind. Bei einer Sitzung handelt es sich um einen generischen Ausdruck, der die Verbindung eines Benutzers mit einer der folgenden Bereiche abdeckt:

  - Konferenz

  - Konferenz Modalitäten (wie Audio/Video oder Anwendungsfreigabe)

  - Andere Benutzer über eine Peer-zu-Peer-Unterhaltung wie Sofortnachrichten oder Audioanruf

<div>


> [!NOTE]  
> Lync Server 2013 verfolgt Informationen zu den einzelnen Sitzungen: Wer hat wen angerufen? welche Endpunkte in der Sitzung verwendet wurden; wie lange dauerte die Sitzung? Was war die wahrgenommene Qualität der Sitzung; Und so weiter. Lync Server zeichnet aber den eigentlichen Anruf selbst nicht auf und speichert ihn. Dazu gehören auch Instant Messaging-Sitzungen: Obwohl lync Server Informationen zu Instant Messaging-Sitzungen aufzeichnet, wird keine Aufzeichnung der einzelnen Sofortnachrichten verwaltet, die während der Sitzung gesendet wurden.



</div>

Die von lync Server gesammelten Anruf Detailinformationen können für eine beliebige Anzahl von Verwendungen eingesetzt werden, einschließlich:

  - **Return on Investment (ROI)**. Administratoren können die von Monitoring Server gesammelten Nutzungsdaten mit ähnlichen Daten vergleichen, die für Ihr vorheriges Telefoniesystem erfasst wurden, um Kosteneinsparungen anzuzeigen und die Bereitstellung von lync Server zu rechtfertigen.

  - **Verwalten des Gerätebestands**: Informationen zur Inventarverwaltung unterstützen Administratoren bei der Identifikation alter Geräte, die ersetzt werden müssen. Informationen zur Vermögensverwaltung unterstützen Administratoren bei der Identifizierung veralteter Geräte, die noch verwendet werden müssen, sowie bei der Ermittlung teurer Geräte, die anscheinend überhaupt nicht verwendet werden.

  - Helpdesk. Die Problembehandlung von Daten ermöglicht Supportingenieuren, zu ermitteln, warum der Anruf eines Benutzers fehlgeschlagen ist, und dies ohne Server-oder clientseitige Protokolle zu erfassen. Diese Informationen können von Supportmitarbeitern, die nicht über fundierte technische Kenntnisse in Microsoft lync 2013 und lync Server 2013 verfügen, problemlos abgerufen und verstanden werden.

  - **Systemproblembehandlung**: Ermöglicht Administratoren das Erkennen grundlegender Probleme, die u. U. verhindern, dass Endbenutzer einfache Aufgaben wie das Beitreten zu einer Konferenz, das Durchführen eines Anrufs oder das Senden einer Chatnachricht ausführen können.

Zusätzlich zu diesen grundlegenden Anrufinformationen bietet der Monitoring Server auch einen Mechanismus, der es SIP-Endpunkten (wie lync 2013) ermöglicht, Informationen zur Problembehandlung bereitzustellen, auf die der Server sonst nicht zugreifen kann:

  - **Medienmetriken mit Auswirkungen auf die Qualität**: Die Metriken beziehen sich auf die eigentliche Übertragung des Anrufs. Diese Metriken befassen sich mit der eigentlichen Übertragung des Anrufs selbst; Das bedeutet, dass Sie eine Art Reiseprotokoll als Anruf Fahrten über das Netzwerk bereitstellen. Diese Metriken (wie beispielsweise Paketverlust, Jitter und Roundtrip-Zeiten) geben Informationen dazu, was mit dem Anruf geschehen ist, wenn der Endpunkt den Endpunkt der anderen Person erreicht hat.

  - **Probleme, die dem Endbenutzer gemeldet**wurden. Zu diesen Metriken gehören Benachrichtigungen über schlechte Qualität, die lync 2013 für Endbenutzer in Fällen vorstellt, in denen Sie zu weit von einem Mikrofon entfernt sind, zu leise sprechen, eine schlechte Netzwerkverbindung aufweisen oder eine schlechte Qualität aufweisen, weil ein anderes Programm auf dem Computer Nutzung der verfügbaren Ressourcen.

  - **Umgebungsinformationen**: Diese Metriken erfassen detaillierte Faktoren der Anrufqualität wie den Typ des verwendeten Mikrofons und Lautsprechers, Angaben darüber, ob eine VPN-Verbindung verwendet wurde, und darüber, ob eine WLAN-Verbindung verwendet wurde.

Am Ende jedes Anrufs übertragen SIP-kompatible Endpunkte diese Informationen automatisch an den Front-End-Server, der den Anruf erleichtert hat. Sie müssen nichts Unternehmen, um Endpunkte zur Übertragung dieser Informationen zu erhalten. Dieses Verhalten ist in das SIP-Protokoll integriert. Wenn Sie diese Informationen jedoch sammeln und speichern möchten, müssen Sie die Überwachung installieren und aktivieren. Wenn Sie die Überwachung installieren und aktivieren, werden die Anrufinformationen von Agents gesammelt, die auf dem Front-End-Server ausgeführt werden und an ein paar von SQL Server-Datenbanken weitergeleitet werden.

Beachten Sie, dass der Vorgang zum Installieren und Konfigurieren der Überwachung in lync Server 2013 vereinfacht wurde. In früheren Versionen der Software erforderte die Überwachung eine separate Überwachungsserver Rolle, was in der Regel einen separaten Computer für die Verwendung als Überwachungsserver bedeutete. In lync Server 2013 wurde die Monitoring Server-Rolle jedoch eliminiert. Stattdessen wurde der Überwachungsdienst (in Form von "Unified Data Collection Agents") in allen Front-End-Servern zusammengestellt. Dies hat mindestens zwei Hauptvorteile. Überprüfung des Überwachungsdiensts:

  - Verringert die Anzahl der Serverrollen, die bei der Implementierung von lync Server 2013 erforderlich sind. Durch die Dekrementierung der Monitoring Server-Rolle können Sie auch die Kosten reduzieren, indem Sie die Notwendigkeit, dedizierte Server für die Überwachung zu verwalten, eliminieren.

  - Verringert die Komplexität der Einrichtung und Verwaltung von lync Server 2013. Durch abstimmen der Überwachungsdienste auf jedem Front-End-Server müssen Sie nicht mehr die Monitoring Server-Rolle installieren, konfigurieren und verwalten.

Weitere Informationen finden Sie im Thema [Bereitstellen der Überwachung in lync Server 2013](lync-server-2013-deploying-monitoring.md) im Bereitstellungshandbuch für lync Server 2013 2013.

</div>

<span> </span>

</div>

</div>

</div>

