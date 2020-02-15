---
title: 'Lync Server 2013: häufig gestellte Fragen zur großen Besprechungs Unterstützung'
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
ms.openlocfilehash: 4c8d834bbd38cbfeeccc74e90bad6f11e47cc805
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-support-faq-for-lync-server-2013"></a>FAQ für umfangreiche Besprechungs Unterstützung für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-22_

Die folgenden Abschnitte enthalten Antworten auf häufige Fragen zum Erstellen und Ausführen großer Besprechungen.

<div>

## <a name="q-how-many-users-can-participate-in-a-large-meeting"></a>Frage: Wie viele Benutzer können an einer großen Besprechung teilnehmen?

Das lync Server Benutzermodell gibt die Begrenzungen von 250 Benutzern in einem freigegebenen Pool oder 1000-Benutzern in einem Pool an, der für große Besprechungen reserviert ist, aber diese Zahlen stellen nur die Anzahl der getesteten Benutzer dar und nur für die spezifische Hardware, die wir in unseren Tests verwendet haben. Basierend auf unseren Tests empfehlen wir diese Grenzwerte für maximale Größe. Sie steuern jedoch die tatsächliche Anzahl von Teilnehmern, die in Besprechungen in Ihrer Organisation zulässig sind, indem Sie eine oder mehrere Konferenzrichtlinien konfigurieren (die Sie mit Windows PowerShell-Cmdlets im lync Server-Verwaltungsshell oder mithilfe der lync Server Systemsteuerung). Die Nummer, die Sie in einer konferenzrichtlinie angeben, kann eine beliebige 32-Bit-ganze Zahl zwischen 1 und 4.294.967.295 sein, die empfohlene Größe liegt jedoch zwischen 2 und 250 Teilnehmern, einschließlich; der Standardwert lautet 250.

</div>

<div>

## <a name="q-how-many-meetings-or-other-workloads-can-i-have-in-a-pool-that-is-dedicated-to-large-meetings"></a>Frage: Wie viele Besprechungen oder andere Arbeitsauslastungen sind für einen dedizierten Pool für große Besprechungen zulässig?

Um bei großen Besprechungen mit bis zu 1000 Teilnehmern die beste Benutzererfahrung zu erzielen, wird empfohlen, in einem dedizierten Pool für große Besprechungen jeweils immer nur eine große Besprechung zu hosten. Zudem wird empfohlen, keine anderen Arbeitsauslastungen im Pool auszuführen, während eine große Besprechung stattfindet.

</div>

<div>

## <a name="q-should-the-organizers-of-large-meeting-be-homed-on-the-dedicated-pool"></a>Frage: Sollten die Organisatoren großer Besprechungen auf dem dedizierten Pool verwaltet werden?

Nein. Es wird empfohlen, auf dem dedizierten Pool nur die Mitarbeiter zu verwalten, die für die Planung großer Besprechungen verantwortlich sind, und keine anderen Benutzer. Hierdurch wird verhindert, dass anderer Datenverkehr aus Echtzeitkommunikationen zu Problemen bei großen Besprechungen führt, die im Pool gehostet werden. Große Besprechungen im dedizierten Pool sollten mit einem Benutzerkonto geplant werden, das dem für die Planung großer Besprechungen zuständigen Personal zugewiesen ist. Sie sollten das Benutzerkonto des Besprechungsorganisators (der Benutzer, der eine große Besprechung anfordert) als Referenten für die große Besprechung hinzufügen.

</div>

<div>

## <a name="q-what-media-modalities-can-i-use-in-a-large-meeting"></a>Frage: Welche Medienmodalitäten können in einer großen Besprechung verwendet werden?

Große Besprechungen mit bis zu 1000 Benutzern können Audio, Video, PowerPoint-Freigabe, Whiteboards und den Abruf von Anwesenheitsinformationen umfassen.

</div>

<div>

## <a name="q-can-i-use-group-instant-messaging-im-in-large-meetings"></a>Frage: Kann ich in großen Besprechungen einen Gruppenchat verwenden?

Ja. Jedoch kann eine große Anzahl von Chatnachrichten, insbesondere wenn diese von sehr vielen Besprechungsteilnehmern gesendet werden, die Benutzerfreundlichkeit beeinträchtigen, da es Probleme mit dem schnellen Textbildlauf im Chatfester geben kann. Durch das Senden einer großen Anzahl von Chatnachrichten an bis zu 1000 Benutzer kann zudem eine beträchtliche Serverlast entstehen, die zu einer Leistungsbeeinträchtigung führen kann. Im Allgemeinen ist Chat nur für Fragen und Antworten erforderlich (Q\&as).

</div>

<div>

## <a name="can-users-join-large-meetings-by-dialing-in-from-a-phone"></a>Können Benutzer an einer großen Besprechung teilnehmen, indem sie sich über ein Telefon einwählen?

Ja. Wenn der lync Server 2013 Pool ordnungsgemäß bereitgestellt und für Einwahlkonferenzen aktiviert ist, können Benutzer an den großen Besprechungen teilnehmen, indem Sie sich einwählen. Unsere Tests haben ergeben, dass sich in einem Zeitraum von 10 Minuten bis zu 15 % der 1000 Benutzer einwählen konnten.

</div>

<div>

## <a name="q-can-i-host-large-meetings-in-a-virtual-topology"></a>Frage: Kann ich große Topologien in einer virtuellen Topologie hosten?

Wir haben keine großen Besprechungen in einer virtuellen Topologie gehostet. Daher wird die Verwendung virtueller Computer zum Hosten eines dedizierten Pools für große Besprechungen nicht unterstützt.

</div>

</div>

<span> </span>

</div>

</div>

</div>

