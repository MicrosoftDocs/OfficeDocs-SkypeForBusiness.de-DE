---
title: 'Lync Server 2013: Mobilitätsfeatures und -funktionen'
TOCTitle: Mobilitätsfeatures und -funktionen
ms:assetid: 12517a88-2531-44a5-bea5-d8884aff53eb
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh689983(v=OCS.15)
ms:contentKeyID: 49293233
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Mobilitätsfeatures und -funktionen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Das Mobilitätsfeature wurde mit den kumulativen Updates für Lync Server 2013: Februar 2013 eingeführt und unterstützt Lync 2010 Mobile- und Lync 2013 Mobile-Clientfunktionen. Wenn Sie den Lync Server 2013-Mobilitätsdienst bereitstellen, können Benutzer unterstützte mobile Apple iOS-, Android-, Windows Phone oder Nokia Symbian-Geräte verwenden, um Aktivitäten wie z. B. Versenden und Empfangen von Chatnachrichten und Anzeigen von Kontakt- und Anwesenheitsinformationen auszuführen. Zudem unterstützen mobile Geräte einige Enterprise-VoIP-Funktionen wie etwa Klicken, um an einer Besprechung teilzunehmen, "Geschäftlich anrufen", Erreichbarkeit unter einer Nummer, Voicemail und entgangene Anrufe. Neue Features in den kumulativen Updates für Lync Server 2013: Februar 2013 umfassen die VoIP (Voice over IP)-Funktion und Video (H.264) für Konferenzteilnehmer.

Das Mobilitätsfeature wurde mit den kumulativen Updates für Lync Server 2013: Februar 2013 eingeführt und unterstützt Lync 2013 Mobile-Clientfunktionen. Mit den kumulativen Updates für Lync Server 2013: Februar 2013 wird die Unified Communications-Web-API bzw. UCWA installiert. UCWA ist die für Lync 2013 Mobile-Clients verwendete Komponente. In Lync Server 2013 wird Mcx für Lync 2010 Mobile-Clients verwendet. Mit den kumulativen Updates für Lync Server 2013: Februar 2013 wird die UCWA als neuer Einstiegspunkt für Mobilitätsdienste eingeführt. Gleichzeitig werden in Lync Server 2013 die Mobilitätsdienste (Mcx) implementiert, die mit den kumulativen Updates für Lync Server 2010: November 2011 eingeführt wurden; Lync 2010 Mobile wird unterstützt. Wenn Sie die kumulativen Updates für Lync Server 2013: Februar 2013 bereitstellen, können mit unterstützten mobilen Geräten (Apple iOS, Android und Windows Phone) folgende Aktionen ausführen


> [!IMPORTANT]
> Features, die vom Mobilitätsdienst aus den kumulativen Updates für Lync Server&nbsp;2010: November&nbsp;2011 unterstützt werden, sind mit "(Mcx)" gekennzeichnet. Alle aufgeführten Features werden von der UCWA unterstützt, die mit den kumulativen Updates für Lync Server&nbsp;2013: Februar&nbsp;2013 eingeführt wurde.



  - Senden und Empfangen von Chatnachrichten (Mcx)

  - Anzeigen von Anwesenheitsinformationen (Mcx)

  - Anzeigen von Kontakten (Mcx)

  - Klicken, um an einer Konferenz teilzunehmen (Mcx)

  - Geschäftlich anrufen (Mcx)

  - Erreichbarkeit unter einer Nummer (Mcx)

  - Voicemail (Mcx)

  - Benachrichtigung über einen entgangenen Anruf (Mcx)

  - Voice over IP (VoIP)

  - Teilnehmervideo (H.264)


> [!NOTE]
> Lync 2010 Mobile stellte einen Client für Nokia Symbian-Geräte bereit. In Lync 2013&nbsp;Mobile ist kein Client für Nokia Symbian-basierte Geräte verfügbar.



Apple iPad-Benutzer haben Zugriff auf erweiterte Funktionen. Nach dem Beitritt zu einer Besprechung mittels Audiorückruf kann ein iPad-Benutzer hochgeladene Microsoft PowerPoint-Präsentationen in einer Besprechung anzeigen, die Anwendungs- und Desktopfreigabe nutzen sowie die Teilnehmerliste der Besprechung anzeigen und Benachrichtigungen zu anderen Inhaltstypen erhalten, die in der Besprechung freigegeben werden.


> [!TIP]
> Mit dem Feature "Erreichbarkeit unter einer Nummer" kann der Benutzer die Anrufe, die unter seiner geschäftlichen Telefonnummer eingehen, auf einem Mobiltelefon entgegennehmen. Mit dem Feature "Geschäftlich anrufen" des Lync Mobile-Clients kann der Benutzer einen ausgehenden Anruf tätigen und hierzu eine geschäftliche Telefonnummer anstelle der Mobiltelefonnummer verwenden. Zum Verwenden dieses Features kann ein Benutzer entweder direkt vom Mobiltelefon aus wählen oder die Dial-Out-Konferenz verwenden. Bei der ausgehenden Verbindung fordert der Client Mcx oder UCWA ( Lync Mobile-Version) auf, den Anruf zu tätigen. Der Server initiiert den Anruf und ruft dann den Benutzer auf dem Mobiltelefon zurück. Wenn der Benutzer antwortet, beendet der Server den Anruf, indem der andere Teilnehmer angerufen wird. Mithilfe des Features "Geschäftlich anrufen" können Benutzer einen Anruf unter ihrer geschäftlichen Identität tätigen. Der Anrufempfänger sieht also nicht die Mobiltelefonnummer des Anrufers, und für den Anrufer fallen keine Gebühren für ausgehende Anrufe an.




> [!NOTE]
> Nicht alle Features werden auf sämtlichen Mobiltelefonen genau gleich ausgeführt. Detaillierte Informationen zu den auf mobilen Geräten unterstützten Features finden Sie in den Tabellen zum Vergleich mobiler Clients unter <A href="http://go.microsoft.com/fwlink/p/?linkid=234777">http://go.microsoft.com/fwlink/p/?LinkId=234777</A>. Detaillierte Informationen zu unterstützten Geräten und Betriebssystemen finden Sie unter <A href="lync-server-2013-planning-for-mobile-clients.md">Planung für mobile Clients</A> in den Themen, die sich mit den Anforderungen befassen.



Wenn Sie das Lync Server 2013-AutoErmittlungsfeature verwenden, können mobile Anwendungen automatisch die Lync Server 2013-Webdienste ermitteln, ohne dass Benutzer in den Geräteinstellungen manuell die URLs eingeben müssen. Die manuelle Eingabe von URLs in den Einstellungen des mobilen Geräts wird auch unterstützt, hauptsächlich zu Problembehandlungszwecken.


> [!IMPORTANT]
> Mcx und UCWA sind kostenlose Dienste und werden für die Unterstützung von Lync 2010 Mobile- und Lync 2013&nbsp;Mobile-Clients bereitgestellt. Mit Lync 2013&nbsp;Mobile ist keine Anmeldung an Lync Server 2010-Bereitstellungen möglich. Mit Lync 2010 Mobile- und Lync 2013&nbsp;Mobile ist die Verwendung einer Lync Server 2013-Bereitstellung möglich, wenn die kumulativen Updates für Lync Server&nbsp;2013: Februar&nbsp;2013 installiert wurden.



Das Mobilitätsfeature unterstützt auch *Pushbenachrichtigungen* für mobile Geräte, die das Ausführen von Anwendungen im Hintergrund nicht unterstützen. Eine Pushbenachrichtigung ist eine an ein mobiles Gerät gesendete Benachrichtigung über ein Ereignis, das auftritt, wenn eine mobile Anwendung inaktiv ist. Beispielsweise kann eine Chateinladung in Abwesenheit eine Pushbenachrichtigung auslösen.

Mcx, UCWA, der AutoErmittlungsdienst und Unterstützung für Pushbenachrichtigungen werden in Lync Server 2013 bereitgestellt. Aktualisierte Clientfeatures, -funktionen und die Verwendung der UCWA als Mobilitätseinstiegspunkt werden mit den kumulativen Updates für Lync Server 2013: Februar 2013 eingeführt.

