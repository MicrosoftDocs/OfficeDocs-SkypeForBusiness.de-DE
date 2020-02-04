---
title: 'Lync Server 2013: häufig gestellte Fragen zum Support für große Besprechungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server large meeting support FAQ
ms:assetid: 34b4fb6a-e35c-47e8-8ab1-f8331741fed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204804(v=OCS.15)
ms:contentKeyID: 48183837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f5a8d63fddf3b8633ebf31651d501458eaf4893
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-support-faq-for-lync-server-2013"></a>Häufig gestellte Fragen zu Besprechungs Support für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-22_

Die folgenden Abschnitte enthalten Antworten auf häufig gestellte Fragen zum Erstellen und Ausführen großer Besprechungen.

<div>

## <a name="q-how-many-users-can-participate-in-a-large-meeting"></a>F: wie viele Benutzer können an einer großen Besprechung teilnehmen?

Das lync Server-Benutzermodell gibt Grenzwerte für 250-Benutzer in einem freigegebenen Pool oder 1000-Benutzern in einem Pool an, die für große Besprechungen reserviert sind, aber diese Zahlen stellen nur die Anzahl der getesteten Benutzer und nur für den spezifischen Satz von Hardware dar, den wir in unseren Tests verwendet haben. Basierend auf unseren Tests empfehlen wir diese Grenzwerte für maximale Größen. Sie steuern jedoch die tatsächliche Anzahl der Teilnehmer, die in Besprechungen in Ihrer Organisation zulässig sind, indem Sie eine oder mehrere Konferenzrichtlinien konfigurieren (die Sie mithilfe von Windows PowerShell-Cmdlets in der lync Server-Verwaltungsshell oder mithilfe von lync Server konfigurieren. Control Panel). Die Zahl, die Sie in einer konferenzrichtlinie angeben, kann eine beliebige 32-Bit-Ganzzahl zwischen 1 und 4.294.967.295 sein, aber die empfohlene Größe liegt zwischen 2 und 250 Teilnehmern inklusive; der Standardwert ist 250.

</div>

<div>

## <a name="q-how-many-meetings-or-other-workloads-can-i-have-in-a-pool-that-is-dedicated-to-large-meetings"></a>F: wie viele Besprechungen oder andere Arbeitslasten kann ich in einem Pool haben, der großen Besprechungen gewidmet ist?

Um eine optimale Benutzererfahrung in umfangreichen Besprechungen mit bis zu 1000 Teilnehmern zu gewährleisten, empfehlen wir, nur eine einzige große Besprechung in einem Pool zu hosten, der für große Besprechungen reserviert ist. Wir empfehlen auch, keine anderen Arbeitsauslastungen für diesen Pool auszuführen, wenn die große Besprechung gerade ausgeführt wird.

</div>

<div>

## <a name="q-should-the-organizers-of-large-meeting-be-homed-on-the-dedicated-pool"></a>F: sollten sich die Organisatoren großer Besprechungen im dedizierten Pool befinden?

Nummer Es wird empfohlen, keine anderen Benutzer als die dedizierten Mitarbeiter zu unterhalten, die die Planung von umfangreichen Besprechungen im dedizierten Pool verwalten. Dadurch wird verhindert, dass der andere Echt Zeit Kommunikationsverkehr Probleme mit umfangreichen Besprechungen verursacht, die im Pool gehostet werden. Sie sollten große Besprechungen im dedizierten Pool mithilfe eines Benutzerkontos des umfangreichen Besprechungs Planungs Personals planen. Sie sollten das Benutzerkonto des Besprechungsorganisators (der Benutzer, der eine große Besprechung anfordert) als Referent für die große Besprechung hinzufügen.

</div>

<div>

## <a name="q-what-media-modalities-can-i-use-in-a-large-meeting"></a>F: welche Medien Modalitäten kann ich in einer umfangreichen Besprechung verwenden?

Große Besprechungen mit bis zu 1000 Benutzern können Audio, Video, PowerPoint-Freigabe, Whiteboards und Anwesenheits Abfragen umfassen.

</div>

<div>

## <a name="q-can-i-use-group-instant-messaging-im-in-large-meetings"></a>F: kann ich Gruppen-Instant Messaging (im) in umfangreichen Besprechungen verwenden?

Ja. Eine große Anzahl von Sofortnachrichten, vor allem, wenn Sie von einer Vielzahl von Besprechungsteilnehmern gesendet werden, kann sich aufgrund von Problemen mit dem schnellen Text Bildlauf im Chatfenster auf die Benutzerfreundlichkeit auswirken. Durch die Bereitstellung einer großen Anzahl von Sofortnachrichten an bis zu 1000-Benutzer können auch signifikante Serverlasten eingeführt werden, die sich auf die Leistung auswirken können. Im Allgemeinen ist Chatnachrichten nur für Fragen und Antworten (Q\&as) erforderlich.

</div>

<div>

## <a name="can-users-join-large-meetings-by-dialing-in-from-a-phone"></a>Können Benutzer an umfangreichen Besprechungen teilnehmen, indem Sie sich über ein Telefon einwählen?

Ja. Wenn der lync Server 2013-Pool ordnungsgemäß bereitgestellt und für Einwahlkonferenzen aktiviert ist, können Benutzer an den umfangreichen Besprechungen teilnehmen, indem Sie sich einwählen. Unsere Tests haben gezeigt, dass bis zu 15% der 1000-Nutzer über einen Zeitraum von 10 Minuten an der groß Besprechung teilnehmen können.

</div>

<div>

## <a name="q-can-i-host-large-meetings-in-a-virtual-topology"></a>F: kann ich große Besprechungen in einer virtuellen Topologie hosten?

Wir haben keine umfangreichen Besprechungen in einer virtuellen Topologie getestet, daher unterstützen wir nicht die Verwendung virtueller Computer, um einen dedizierten Pool für große Besprechungen zu hosten.

</div>

</div>

<span> </span>

</div>

</div>

</div>

