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
ms.openlocfilehash: c44ef02ef0685b4f930d7a264915d5338600ef71
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520842"
---
# <a name="overview-of-monitoring-in-lync-server-2013"></a>Übersicht über die Überwachung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-05_

In Microsoft lync Server 2013 wird die Überwachung verwendet, um Verwendungsinformationen und QoE-Daten (Quality of Experience) zu den Kommunikationssitzungen zu erfassen, an denen Ihre Benutzer beteiligt sind. Eine Sitzung ist ein allgemeiner Begriff, der sich auf die Verbindungen von Benutzern mit folgenden Elementen bezieht:

  - Konferenz

  - Konferenzmodalitäten (wie Audio/Video oder Anwendungsfreigabe)

  - Andere Benutzer über eine Peer-zu-Peer-Unterhaltung wie Sofortnachrichten oder Audioanruf

<div>


> [!NOTE]  
> Lync Server 2013 verfolgt die Informationen zu jeder Sitzung: Wer hat wen angerufen? welche Endpunkte in der Sitzung verwendet wurden; wie lange dauerte die Sitzung zuletzt; Was war die wahrgenommene Qualität der Sitzung; Und so weiter. In lync Server wird jedoch der tatsächliche Aufruf selbst nicht aufgezeichnet und gespeichert. Dies umfasst auch Sofortnachrichtensitzungen: Obwohl lync Server Informationen zu Chatsitzungen aufzeichnet, wird keine Aufzeichnung aller Sofortnachrichten verwaltet, die während der Sitzung gesendet wurden.



</div>

Die von lync Server gesammelten Anruf Detailinformationen können für eine beliebige Anzahl von Verwendungszwecken verwendet werden, einschließlich:

  - **Renditeanalyse (Return on Investment, ROI)**. Administratoren können die von Monitoring Server gesammelten Nutzungsdaten mit ähnlichen Daten vergleichen, die für Ihr bisheriges Telefoniesystem erfasst wurden, um Kosteneinsparungen anzuzeigen und die Bereitstellung von lync Server zu rechtfertigen.

  - **Verwalten des Gerätebestands**. Informationen bezüglich der Inventarverwaltung unterstützen Administratoren bei der Identifizierung alter Geräte, die ersetzt werden müssen. Außerdem können auf diese Weise kostenintensive Geräte identifiziert werden, die anscheinend gar nicht genutzt werden.

  - Helpdesk. Durch die Problembehandlung von Daten können Supporttechniker ermitteln, warum der Anruf eines Benutzers fehlgeschlagen ist, und zwar ohne dass Server-oder clientseitige Protokolle erfasst werden müssen. Diese Informationen können von Supportmitarbeitern, die nicht über umfassende technische Kenntnisse in Microsoft lync 2013 und lync Server 2013 verfügen, leicht zugänglich und verstanden werden.

  - **Systemproblembehandlung**. Ermöglicht Administratoren das Erkennen grundlegender Probleme, die u. U. verhindern, dass Endbenutzer einfache Aufgaben wie das Beitreten zu einer Konferenz, das Tätigen eines Anrufs oder das Senden einer Sofortnachricht ausführen können.

Zusätzlich zu diesen grundlegenden Anrufinformationen stellt der Monitoring Server auch einen Mechanismus bereit, der SIP-Endpunkten (wie lync 2013) ermöglicht, Informationen zur Problembehandlung bereitzustellen, auf die der Server andernfalls keinen Zugriff hat:

  - **Medienmetriken mit Auswirkungen auf die Qualität**. Die Metriken beziehen sich auf die eigentliche Übertragung des Anrufs. Sie stellen eine Art "Reiseprotokoll" des Anrufs durch das Netzwerk dar und beinhalten Daten wie Paketverluste, Jitter und Roundtripzeiten. Anhand dieser Informationen lässt sich erkennen, was mit dem Anruf zwischen dem Verlassen des einen Benutzerendpunkts und dem Eintreffen am anderen Benutzerendpunkt passiert.

  - **Dem Endbenutzer gemeldete Probleme**. Zu diesen Metriken gehören Benachrichtigungen über schlechte Qualität, die Endbenutzern in Fällen angezeigt lync 2013, in denen Sie zu weit von einem Mikrofon entfernt sind, zu leise sprechen, eine schlechte Netzwerkverbindung haben oder eine schlechte Qualität aufweisen, da ein anderes Programm auf dem Computer die verfügbaren Ressourcen verbraucht.

  - **Umgebungsinformationen**. Diese Metriken erfassen detaillierte Faktoren der Anrufqualität wie den Typ des verwendeten Mikrofons und Lautsprechers, Angaben darüber, ob eine VPN-Verbindung verwendet wurde und Angaben darüber, ob eine WLAN-Verbindung verwendet wurde.

Am Ende jedes Anrufs übertragen SIP-kompatible Endpunkte diese Informationen automatisch an den Front-End-Server, von dem der Anruf bereitgestellt wurde. Sie müssen nichts tun, damit diese Informationen von den Endpunkten übertragen werden. Das SIP-Protokoll ist bereits entsprechend konfiguriert. Wenn Sie diese Informationen jedoch erfassen und speichern möchten, müssen Sie die Überwachung aktivieren. Wenn Sie die Überwachung installieren und aktivieren, werden die Anrufinformationen von den Agents gesammelt, die auf dem Front-End-Server ausgeführt werden, und an ein SQL Server-Datenbankpaar weitergeleitet.

Beachten Sie, dass der Prozess der Installation und Konfiguration der Überwachung in lync Server 2013 vereinfacht wurde. In früheren Versionen der Software war für die Überwachung eine separate Monitoring Server Rolle erforderlich, was in der Regel einen separaten Computer bedeutete, der als Monitoring Server verwendet wurde. In lync Server 2013 wurde jedoch die Monitoring Server Rolle eliminiert. Stattdessen wurde der Überwachungsdienst (in Form von "Unified Data Collection Agents") in allen Front-End-Servern zusammengefasst. Dies hat mindestens zwei Hauptvorteile. Anordnung des Überwachungsdiensts:

  - Verringert die Anzahl der Serverrollen, die bei der Implementierung von lync Server 2013 erforderlich sind. Weniger Monitoring Server-Rollen bedeuten gleichzeitig weniger Kosten, da weniger dedizierte Server für die Überwachung unterhalten werden müssen.

  - Reduziert die Komplexität von lync Server 2013-Setup und-Verwaltung. Durch das Platzieren der Überwachungsdienste auf den einzelnen Front-End-Servern entfällt die Notwendigkeit der Installation, Konfiguration und Verwaltung von Monitoring Server-Rollen.

Weitere Informationen finden Sie im Thema [Bereitstellen der Überwachung in lync Server 2013](lync-server-2013-deploying-monitoring.md) im Bereitstellungshandbuch für lync Server 2013 2013.

</div>

<span> </span>

</div>

</div>

</div>

