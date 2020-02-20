---
title: 'Lync Server 2013: Mobilitätsfeatures und-Funktionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility features and capabilities
ms:assetid: 12517a88-2531-44a5-bea5-d8884aff53eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689983(v=OCS.15)
ms:contentKeyID: 48183457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a001a6fb76a0612f7f650a31de5cf788a7f69327
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149584"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mobility-features-and-capabilities-in-lync-server-2013"></a>Mobilitätsfeatures und-Funktionen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-19_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Das in den kumulativen Updates für lync Server 2013:2013. Februar eingeführte Mobilitätsfeature unterstützt lync 2010 Mobile-und lync 2013-Funktionen für mobile Clients. Wenn Sie den lync Server 2013 Mobilitätsdienst bereitstellen, können Benutzer unterstützte Apple IOS-, Android-und Windows Phone-oder Nokia Symbian-Mobilgeräte verwenden, um Aktivitäten wie senden und empfangen von Chatnachrichten, Anzeigen von Kontakten und Anzeigen der Anwesenheit durchzuführen. Zudem unterstützen mobile Geräte einige Enterprise-VoIP-Features, beispielsweise die Teilnahme an einer Besprechung durch Klicken, Geschäftlich anrufen, Erreichbarkeit unter einer Nummer, Voicemail und Anrufe in Abwesenheit. Zu den neuen Features, die in den kumulativen Updates für lync Server 2013:2013. Februar eingeführt wurden, gehören Voice over IP (VoIP)-Funktionen und Video (H. 264) für Besprechungsteilnehmer.

Das in den kumulativen Updates für lync Server 2013:2013. Februar eingeführte Mobilitätsfeature unterstützt lync 2013 Mobile Clientfunktionalität. Die kumulativen Updates für lync Server 2013:2013 Februar installieren Unified Communications-WebAPI oder UCWA. UCWA ist die Komponente, die für lync 2013 Mobile Clients verwendet wird. In lync Server 2013 wird MCX für lync 2010 Mobile-Clients verwendet. Kumulative Updates für lync Server 2013: Februar 2013 Einführung von UCWA als neuen Einstiegspfad für Mobilitätsdienste. Lync Server 2013 implementiert gleichzeitig den Mobilitätsdienst (MCX), der in den kumulativen Updates für lync Server 2010: November 2011 eingeführt wurde, und bietet Unterstützung für lync 2010 Mobile. Wenn Sie die kumulativen Updates für lync Server 2013: Februar 2013 bereitstellen, können Benutzer unterstützte Apple IOS-, Android-und Windows Phone-Mobilgeräte verwenden, um folgende Aktivitäten auszuführen:

<div>


> [!IMPORTANT]  
> Vom Mobilitätsdienst unterstützte Features aus den kumulativen Updates für lync Server 2010: November 2011 werden mit (MCX) notiert. Alle aufgeführten Features werden von der UCWA unterstützt, die in den kumulativen Updates für lync Server 2013:2013. Februar eingeführt wurde.



</div>

  - Senden und empfangen von Chatnachrichten (MCX)

  - Anwesenheit anzeigen (MCX)

  - Kontakte anzeigen (MCX)

  - Klicken Sie, um an einer Konferenz teilzunehmen (MCX)

  - Anruf über Arbeit (MCX)

  - Reichweite für einzelne Nummern (MCX)

  - Voicemail (MCX)

  - Benachrichtigung über verpasste Anrufe (MCX)

  - VoIP (Voice over IP)

  - Teilnehmer Video (H. 264)

<div>


> [!NOTE]  
> Lync 2010 Mobile einen Client für Nokia Symbian-Geräte bereitgestellt. Lync 2013 Mobile verfügt über keinen Client für Nokia Symbian-basierte Geräte.



</div>

Apple iPad-Benutzer haben Zugriff auf erweiterte Fähigkeiten. Nachdem ein iPad-Benutzer eine Besprechung mit dem audiorückruf durchführen konnte, kann er hochgeladene Microsoft PowerPoint Präsentationen in einer Besprechung anzeigen, Anwendungen und Desktops freigeben, die Teilnehmerliste der Besprechung anzeigen und Benachrichtigungen über andere Inhaltstypen empfangen. , die in der Besprechung freigegeben werden.

<div>


> [!TIP]  
> Bei einer einzelnen Rufnummer erhält ein Benutzer Anrufe auf einem Mobiltelefon, die zur Arbeitsnummer gewählt wurden. Bei der Funktion "Anruf über Arbeit" platziert der Benutzer einen ausgehenden Anruf vom mobilen lync-Client mithilfe einer geschäftlichen Telefonnummer anstelle der Mobiltelefonnummer. Mit "Dial-Out" sendet der Client eine Anforderung an MCX oder UCWA (basierend auf der mobilen lync-Version), um den Anruf zu tätigen. Der Server initiiert den Anruf und ruft dann den Benutzer wieder auf dem Mobiltelefon an. Wenn der Benutzer antwortet, beendet der Server den Anruf, indem er den anderen Teilnehmer anwählt. Mithilfe der Funktion "Anruf über Arbeit" können Benutzer ihre Arbeitsidentität während eines Anrufs aufrecht erhalten, was bedeutet, dass der Anrufempfänger die Mobiltelefonnummer des Anrufers nicht erkennt und der Anrufer keine ausgehenden Gebühren mehr annimmt.



</div>

<div>


> [!NOTE]  
> Nicht alle Features werden auf sämtlichen Mobiltelefonen genau gleich ausgeführt. Ausführliche Informationen zu den auf mobilen Geräten unterstützten Features finden Sie in <A href="https://go.microsoft.com/fwlink/p/?linkid=234777">https://go.microsoft.com/fwlink/p/?LinkId=234777</A>den Vergleichstabellen für mobile Clients unter. Ausführliche Informationen zu unterstützten Geräten und Betriebssystemen finden Sie in den Anforderungen unter <A href="lync-server-2013-planning-for-mobile-clients.md">Planung für mobile Clients in lync Server 2013</A>.



</div>

Wenn Sie das Feature lync Server 2013 AutoErmittlung verwenden, können mobile Anwendungen automatisch lync Server 2013 Webdienste finden, ohne dass Benutzer die URLs in ihren Geräteeinstellungen manuell eingeben müssen. Die manuelle Eingabe von URLs in den Einstellungen des mobilen Geräts wird auch unterstützt, hauptsächlich zu Problembehandlungszwecken.

<div>


> [!IMPORTANT]  
> Die MCX und UCWA sind ﻿kostenlose Dienste, und beide werden bereitgestellt, um lync 2010 Mobile und lync 2013 Mobile Clients zu unterstützen. Lync 2013 Mobile kann sich nicht bei lync Server 2010-Bereitstellungen anmelden. Lync 2010 Mobile und lync 2013 Mobile können eine lync Server 2013-Bereitstellung mit den kumulativen Updates für lync Server 2013 verwenden: 2013. Februar: wird angewendet.



</div>

Das Mobilitätsfeature unterstützt auch *Pushbenachrichtigungen* für mobile Geräte, die das Ausführen von Anwendungen im Hintergrund nicht unterstützen. Eine Pushbenachrichtigung ist eine an ein mobiles Gerät gesendete Benachrichtigung über ein Ereignis, das auftritt, wenn eine mobile Anwendung inaktiv ist. Beispielsweise kann eine verpasste sofortnachrichteneinladung zu einer Push-Benachrichtigung führen.

MCX, UCWA, AutoErmittlungsdienst und Unterstützung für Push-Benachrichtigungen werden in lync Server 2013 bereitgestellt. Aktualisierte Clientfeatures, Funktionen und die Verwendung von UCWA als Mobilitäts Einstiegspunkt werden in den kumulativen Updates für lync Server 2013:2013. Februar eingeführt.

</div>

<span> </span>

</div>

</div>

</div>

