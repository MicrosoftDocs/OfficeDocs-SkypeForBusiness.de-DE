---
title: 'Lync Server 2013: Mobilitätsfeatures und -funktionen'
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
ms.openlocfilehash: 3e00274e62cc0fe7cf55c45e11a49670c7f1e6a0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758697"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-features-and-capabilities-in-lync-server-2013"></a>Mobilitätsfeatures und -funktionen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-19_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Das Mobilitätsfeature, das in den kumulativen Updates für lync Server 2013: Februar 2013 unterstützt die lync 2010 Mobile-und lync 2013-Funktionen für mobile Clients. Wenn Sie den lync Server 2013-Mobilitätsdienst bereitstellen, können Benutzer unterstützte Apple IOS-, Android-und Windows Phone-oder Nokia Symbian-Mobilgeräte verwenden, um Aktivitäten wie das Senden und empfangen von Sofortnachrichten, das Anzeigen von Kontakten und das Anzeigen von Anwesenheitsfunktionen auszuführen. Darüber hinaus unterstützen Mobile Geräte einige Enterprise-VoIP-Features, wie beispielsweise klicken, um an einer Konferenz teilzunehmen, über Arbeit anzurufen, eine Rufnummer zu erreichen, Voicemail und verpasste Anrufe zu tätigen. Neue Features, die in den kumulativen Updates für lync Server 2013: Februar 2013 eingeführt wurden, umfassen VoIP-Funktionen und Video (H. 264) für Besprechungsteilnehmer.

Das Mobilitätsfeature in den kumulativen Updates für lync Server 2013: Februar 2013 unterstützt die lync 2013-Funktionalität für mobile Clients. Die kumulativen Updates für lync Server 2013: Februar 2013 Installieren der Unified Communications Web-API oder UCWA. UCWA ist die Komponente, die für Mobile lync 2013-Clients verwendet wird. In lync Server 2013 wird MCX für Mobile lync 2010-Clients verwendet. Kumulative Updates für lync Server 2013: Februar 2013 Einführung von UCWA als neuen Einstiegspunkt für Mobilitätsdienste. Lync Server 2013 implementiert gleichzeitig den Mobilitätsdienst (Mobility Service, MCX), der in den kumulativen Updates für lync Server 2010: November 2011 eingeführt wurde, und bietet Unterstützung für lync 2010 Mobile. Wenn Sie die kumulativen Updates für lync Server 2013: Februar 2013 bereitstellen, können Benutzer unterstützte Apple IOS-, Android-und Windows Phone-Mobilgeräte verwenden, um folgende Aktionen auszuführen:

<div>


> [!IMPORTANT]  
> Vom Mobilitätsdienst unterstützte Features aus den kumulativen Updates für lync Server 2010: November 2011 sind mit (MCX) gekennzeichnet. Alle aufgelisteten Features werden vom UCWA unterstützt, das in den kumulativen Updates für lync Server 2013: Februar 2013 eingeführt wurde.



</div>

  - Senden und empfangen von Sofortnachrichten (MCX)

  - Anzeigen von Anwesenheitsinformationen (MCX)

  - Anzeigen von Kontakten (MCX)

  - Klicken Sie, um an einer Konferenz teilzunehmen (MCX)

  - Anruf über Arbeit (MCX)

  - Erreichbarkeit einer Rufnummer (MCX)

  - Voicemail (MCX)

  - Benachrichtigung über verpasste Anrufe (MCX)

  - Voice over IP (VoIP)

  - Teilnehmervideo (H.264)

<div>


> [!NOTE]  
> Lync 2010 Mobile hat einen Client für Nokia Symbian-Geräte bereitgestellt. Lync 2013 Mobile hat keinen Client für Nokia Symbian-basierte Geräte.



</div>

Apple iPad-Benutzer erhalten Zugriff auf Erweiterte Funktionen. Nach dem teilnehmen an einer Besprechung mithilfe des audiorückrufs kann ein iPad-Benutzer hochgeladene Microsoft PowerPoint-Präsentationen in einer Besprechung anzeigen, Anwendungen und Desktops freigeben, die Teilnehmerliste der Besprechung anzeigen und Benachrichtigungen zu anderen Inhaltstypen empfangen. , die in der Besprechung freigegeben werden.

<div>


> [!TIP]  
> Mit einer einzelnen Rufnummer erhält ein Nutzer Anrufe auf einem Mobiltelefon, das in die geschäftliche Rufnummer gewählt wurde. Bei Anrufen über Arbeit platziert der Benutzer einen ausgehenden Anruf vom lync Mobile-Client unter Verwendung einer geschäftlichen Telefonnummer anstelle der Mobiltelefonnummer. Beim Einwählen sendet der Client eine Anforderung an MCX oder UCWA (basierend auf der lync Mobile-Version), um den Anruf zu tätigen. Der Server initiiert den Anruf und ruft den Benutzer dann wieder auf dem Mobiltelefon an. Wenn der Benutzer antwortet, schließt der Server den Anruf ab, indem er die andere Partei anwählt. Durch die Verwendung von Anruf über die Arbeit können Benutzer Ihre geschäftliche Identität während eines Anrufs aufrecht erhalten, was bedeutet, dass der Anrufempfänger die Handynummer des Anrufers nicht sieht, und der Anrufer die Gebühren für ausgehende Anrufe vermeidet.



</div>

<div>


> [!NOTE]  
> Nicht alle Features funktionieren auf allen mobilen Geräten genau gleich. Details zu den auf mobilen Geräten unterstützten Features finden Sie in <A href="http://go.microsoft.com/fwlink/p/?linkid=234777">http://go.microsoft.com/fwlink/p/?LinkId=234777</A>den Vergleichstabellen für mobile Clients unter. Ausführliche Informationen zu unterstützten Geräten und Betriebssystemen finden Sie in den Anforderungs Themen unter <A href="lync-server-2013-planning-for-mobile-clients.md">Planen für mobile Clients in lync Server 2013</A>.



</div>

Wenn Sie das Feature für die AutoErmittlung in lync Server 2013 verwenden, können mobile Anwendungen lync Server 2013-Webdienste automatisch finden, ohne dass die Benutzer die URLs manuell in Ihre Geräteeinstellungen eingeben müssen. Die manuelle Eingabe von URLs in Einstellungen für mobile Geräte wird ebenfalls unterstützt, hauptsächlich zur Problembehandlung.

<div>


> [!IMPORTANT]  
> MCX und UCWA sind ﻿kostenlose Dienste, die beide zur Unterstützung von lync 2010 Mobile-und lync 2013-mobilen Clients bereitgestellt werden. Lync 2013 Mobile kann sich bei lync Server 2010-Bereitstellungen nicht anmelden. Lync 2010 Mobile und lync 2013 Mobile können eine lync Server 2013-Bereitstellung mit den kumulierten Updates für lync Server 2013 verwenden: Februar 2013 angewendet.



</div>

Die Mobilitätsfunktion unterstützt auch *Pushbenachrichtigungen* für mobile Geräte, die das Ausführen von Anwendungen im Hintergrund nicht unterstützen. Eine Pushbenachrichtigung ist eine an ein mobiles Gerät gesendete Benachrichtigung über ein Ereignis, das auftritt, wenn eine mobile Anwendung inaktiv ist. So kann beispielsweise eine verpasste sofortnachrichteneinladung zu einer Push-Benachrichtigung führen.

MCX, UCWA, AutoErmittlungsdienst und Support für Push-Benachrichtigungen werden in lync Server 2013 bereitgestellt. Aktualisierte Clientfeatures, Funktionen und die Verwendung von UCWA als Mobilitäts Einstiegspunkt werden in den kumulativen Updates für lync Server 2013: Februar 2013 vorgestellt.

</div>

<span> </span>

</div>

</div>

</div>

