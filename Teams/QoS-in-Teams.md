---
title: Quality of Service (QoS) in Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: Serdars
ms.date: 02/16/2018
ms.topic: article
ms.service: msteams
description: "Bereiten Sie das Netzwerk Ihrer Organisation für Quality of Service (QoS) in Microsoft Teams vor."
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 61bebd64c7d1478c16e114631b696dee2bf59625
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2018
---
<a name="quality-of-service-qos-in-microsoft-teams"></a>Quality of Service (QoS) in Microsoft Teams
==========================================
Dieses Handbuch soll Sie beim Vorbereiten des Netzwerks Ihrer Organisation für Quality of Service (QoS) in Microsoft Teams unterstützen.


Quality of Service (QoS) ist ein Mechanismus, mit dem Sie bestimmte Typen von Netzwerkdatenverkehr priorisieren können. Die Priorisierung des Datenverkehrs für Echtzeitkommunikationsdienste wie Microsoft Teams spielt eine wichtige Rolle dabei, Geschäftsbenutzern optimales Arbeiten zu ermöglichen. Damit QoS wirklich effektiv ist, muss eine QoS-fähige End-to-End-Verbindung konfiguriert werden (PC, Netzwerkswitches und Router für die Cloud), da Pfadbestandteile ohne QoS-Unterstützung die Qualität des gesamten Anrufs beeinträchtigen können.


![Screenshot eines Diagramms, das die Beziehung zwischen den Netzwerken einer Organisation und Office 365-Diensten veranschaulicht](media/Qos-in-Teams-Image1.png)

 

In den meisten Fällen ist das Verbindungsnetzwerk ein nicht verwaltetes Netzwerk oder eine Internetverbindung. [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/) ist eine der verfügbaren Optionen für End-to-End-QoS. Wir empfehlen, QoS auch in den Teilen des Netzwerks zu implementieren, über die Sie die Kontrolle haben, also in Ihrem lokalen Netzwerk. Dadurch können Sie die Qualität der Arbeitsauslastungen für Echtzeitkommunikation in der gesamten Bereitstellung erhöhen und Engpässe in der vorhandenen Bereitstellung abschwächen. 

## <a name="objectives"></a>Ziele 

Schwerpunkt des Handbuchs ist die Priorisierung des Datenverkehrs für die Echtzeitkommunikation von Microsoft Teams, das heißt Sprache und Video. Andere Datenverkehrstypen können ebenfalls gemäß Ihren Anforderungen priorisiert werden.

Es gibt mehrere Möglichkeiten zum Priorisieren des Datenverkehrs, am häufigsten werden jedoch DSCP-Markierungen (Differentiated Services Code Point) verwendet. Sie können basierend auf Portbereichen, aber auch über Gruppenrichtlinienobjekte angewendet werden. Wir gehen in diesem Dokument auf beide Möglichkeiten ein.

Durch Steuern der DSCP-Markierungen mithilfe von Gruppenrichtlinienobjekten (Group Policy Objects, GPOs) stellen Sie sicher, dass in eine Domäne eingebundene Computer die richtigen Einstellungen erhalten und dass diese Einstellungen nur von einem Administrator verwaltet werden können. 

Sie müssen sich dessen bewusst sein, dass QoS nur funktioniert, wenn sie für alle Verbindungen zwischen Anrufer und Angerufenem implementiert ist. Wenn Sie QoS im internen Netzwerk verwenden und Benutzer sich von einem Remotestandort aus anmelden, können Sie nur innerhalb des internen verwalteten Netzwerks Prioritäten festlegen. Verwaltete Verbindungen mit Remotestandorten durch Implementierung eines VPNs sind zwar möglich, aber es wird nicht empfohlen, Datenverkehr für Echtzeitkommunikation über das VPN zu übertragen.

> [!NOTE]
> Wir empfehlen, für über ein VPN verbundene Remotebenutzer getrenntes Tunneln zu implementieren, um die Benutzerfreundlichkeit zu maximieren. Weitere Informationen finden Sie im [Bereitstellungsleitfaden für geteilte Tunnel für VPN-Verbindungen](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9 ).

In einer globalen Organisation mit verwalteten Verbindungen über mehrere Kontinente hinweg wird QoS dringend empfohlen, da die Bandbreite im Vergleich zum lokalen Netzwerk (LAN) begrenzt ist.

## <a name="quality-of-service"></a>Quality of Service

Um ein garantiertes Dienstniveau für eine Anwendung im Netzwerk zu gewährleisten, müssen die zugrunde liegenden Netzwerkgeräte in der Lage sein, verschiedene Datenverkehrstypen zu klassifizieren. So muss zum Beispiel ein Router zwischen Sprachdatenverkehr und normalem Datenverkehr für Webbrowsen unterscheiden können, wenn der Sprachdatenverkehr vorrangig behandelt werden soll. 

Differenzierte Dienste (DiffServ) stellen ein Framework bereit, in dem der Datenverkehr von Netzwerkgeräten mit Prioritäten behandelt wird, die auf dem Feld für den Diensttyp (Type of Service, ToS) im Header von IPv4-/IPv6-Paketen basieren. Die sechs wichtigsten Bits des DiffServ-Felds werden als Differentiated Services Code Point oder DSCP bezeichnet. Mithilfe dieses Frameworks kann Datenverkehr als ein bestimmter Typ (Sprache) klassifiziert und dann markiert werden (101110 oder in Dezimalschreibweise 46). Wenn dann Netzwerkgeräte diese Markierungen verarbeiten, kann der Datenverkehr entsprechend priorisiert werden (in diesem Beispiel als „Expedited Forwarding“).

Wenn Netzwerkdatenverkehr einen Router erreicht, wird er in einer Warteschlange platziert. Wenn QoS nicht implementiert ist, ist im Wesentlichen nur eine Warteschlange vorhanden, und die Daten werden nach dem FIFO-Prinzip (First In, First Out) behandelt. Das heißt, Sprachdatenverkehr (bei dem sich Verzögerungen sehr deutlich bemerkbar machen) könnte durch Datenverkehr von Onlinestreamingdiensten ausgebremst werden. Bei der Implementierung von QoS können mehrere Warteschlangen mit unterschiedlichen Funktionen für die Verwaltung von Überlastungen (z. B. Priority Queuing (PQ) und Class Based Weighted Fair Queue (CBWFQ) von Cisco) und die Vermeidung von Überlastungen (z. B. Weighted Random Early Detection (WRED)) definiert werden.

![Screenshot eines Diagramms, das QoS-Warteschlangen in Microsoft Teams veranschaulicht](media/Qos-in-Teams-Image2.png)

Abbildung 1: Visualisierung von QoS-Warteschlangen

Wenn diese Elemente implementiert sind, kann eine vorhersagbare Quality of Service bereitgestellt werden, da jetzt im zugrunde liegenden verwalteten Netzwerk festgelegt ist, wie der Datenverkehr klassifiziert, markiert und priorisiert werden soll. Im Hinblick auf Microsoft Teams ist das wichtigste Konfigurationselement die Klassifizierung und Markierung von Paketen. Um die Konfiguration der Anwendung mit der zugrunde liegenden Netzwerkkonfiguration in Einklang zu bringen und eine erfolgreiche End-to-End-QoS zu implementieren, ist jedoch sorgfältige Planung erforderlich.

## <a name="qos-scenarios"></a>QoS-Szenarien

Unsere Ratschläge für die Implementierung von QoS für Microsoft Teams basieren auf vier Ausgangsszenarien:

1.  Sie haben Microsoft Teams bereitgestellt oder nehmen die Bereitstellung gerade vor, und Sie planen die Implementierung von QoS über portbasierte Markierungen. Portbasierte Markierungen stellen die zuverlässigste Methode dar, da sie universell auf allen Plattformen funktionieren und sich am einfachsten implementieren lassen. 

2.  Sie haben Microsoft Teams bereitgestellt oder nehmen die Bereitstellung gerade vor, und Sie planen die Implementierung von QoS über Markierungen durch Gruppenrichtlinienobjekte. Diese Vorgehensweise wird manchmal in Verbindung mit Szenario 1 verwendet. Dieses unten beschriebene Szenario ist zwar absolut zulässig, aber Sie müssen sich dessen bewusst sein, dass es nur für Windows-Clients funktioniert, die in eine Domäne eingebunden sind. Geräte, die nicht als Windows-Clients in eine Domäne eingebunden sind, sind nicht für QoS-/DSCP-Markierungen aktiviert. 

3.  Sie haben Skype for Business Online einschließlich QoS-Markierungen bereitgestellt und stellen jetzt Microsoft Teams bereit. Wenn dies auf Sie zutrifft, respektiert Microsoft Teams die vorhandene Konfiguration und verwendet die gleichen Portbereiche und Markierungen wie der Skype for Business-Client. Es sollte keine zusätzliche Konfiguration erforderlich sein. 
    > [!NOTE]
    > Wenn Sie QoS-Markierungen mit Anwendungsnamen über Gruppenrichtlinien verwenden, sollten Sie „Teams.exe“ als Anwendungsnamen hinzufügen.
4.  Sie haben Microsoft Teams bereitgestellt oder nehmen die Bereitstellung gerade vor, und Sie möchten QoS über portbasierte Markierungen mit einem benutzerdefinierten Portbereich implementieren.

## <a name="recommended-differentiated-services-code-point-dscp-markings"></a>Empfohlene DSCP-Markierungen (Differentiated Services Code Point)

Im ersten Schritt klassifizieren Sie die Datenverkehrsflüsse (beispielsweise Audio und Video). Dazu nutzen Sie die eindeutigen, nicht überlappenden Portbereiche mit einem DSCP-Wert. Der hier zugewiesene DSCP-Wert bestimmt die Priorität des Datenverkehrs im Netzwerk (basierend auf der Netzwerkkonfiguration). Jede Arbeitsauslastung erhält einen eigenen DSCP-Wert. Manche Kunden legen möglicherweise für Sprache und Video den gleichen Wert fest, sodass beide im Netzwerk die gleiche Priorität haben. 

Welchen DSCP-Wert Sie verwenden sollten, hängt von der Priorität der Arbeitsauslastung ab. Beispielsweise kann es aufgrund von Geschäftsanforderungen notwendig sein, die Anwendungsfreigabe mit der gleichen Priorität wie Video zu behandeln (und sie entsprechend mit dem gleichen DSCP-Wert wie Video zu markieren). In anderen Umgebungen ist möglicherweise bereits eine QoS-Strategie vorhanden. 

Tabelle 1 zeigt die erforderlichen DSCP-Markierungen bei Nutzung von Microsoft Teams mit ExpressRoute. Dies kann ein guter Ausgangspunkt für Kunden sein, die nicht sicher sind, welche Markierungen sie in ihrer eigenen Umgebung verwenden sollen. Weitere Informationen finden Sie unter [QoS-Anforderungen für ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-qos).


| Clientquellport|Protokoll|Medienkategorie|Allgemeiner DSCP-Wert|DSCP-Klasse|
|---------|---------|---------|---------|---------|
| 50000–50019|TCP/UDP|Audio|46|Expedited Forwarding (EF)|
| 50020–50039|TCP/UDP|Video|34|Assured Forwarding (AF41)|
| 50040–50059|TCP/UDP|Anwendungs-/Desktopfreigabe und Dateiübertragung|18|Klassenauswahl (CS3)|

Tabelle 1: DSCP-Markierungen

Hier sind ein paar Bedingungen, die Sie verstehen müssen, wenn Sie die Informationen in Tabelle 1 verwenden:

- Dateifreigabe und Anwendungsfreigabe verwenden den gleichen Quellportbereich und würden daher bei Verwendung von portbasierten Markierungen die gleichen DSCP-Markierungen verwenden. Aus diesem Grund sollten Sie ermitteln, welche Priorität für *beide* Modalitäten am besten geeignet ist („Interactive“ oder „Default“).
    
- Wenn Sie für die Zukunft die Implementierung von ExpressRoute planen und QoS noch nicht implementiert ist, empfehlen wir, den oben genannten Ratschlägen zu folgen, sodass die DSCP-Werte vom Absender bis zum Empfänger identisch sind. 
    
## <a name="source-ports-used-by-teams"></a>Von Microsoft Teams verwendete Quellports

In Microsoft Teams sollte QoS basierend auf den Quellports konfiguriert werden, die von den verschiedenen Arbeitsauslastungen verwendet werden. Die serverseitigen und clientseitigen Portbereiche sind an dieser Stelle nicht konfigurierbar. 

Verwenden Sie zum Bereitstellen von QoS die Clientquellportbereiche aus Tabelle 2 mit den zugehörigen QoS-DSCP-Markierungen.

| Clientquellport|Protokoll|Medienkategorie|Allgemeiner DSCP-Wert|DSCP-Klasse|
|---------|---------|---------|---------|---------|
| 50000–50019|TCP/UDP|Audio|46|Expedited Forwarding (EF)|
| 50020–50039|TCP/UDP|Video|34|Assured Forwarding (AF41)|
| 50040–50059|TCP/UDP|Anwendungs-/Desktopfreigabe und Dateiübertragung|18|Klassenauswahl (CS3)|

Tabelle 2: Clientquellportbereiche

> [!NOTE]
> Wenn Sie QoS bereits basierend auf den Quellportbereichen für Skype for Business Online konfiguriert haben, gilt die gleiche Konfiguration auch für Microsoft Teams. Sie müssen keine weiteren Änderungen vornehmen. Wenn Sie Skype for Business Server (lokal) bereitgestellt haben, müssen Sie Ihre QoS-Richtlinien überarbeiten.

## <a name="setting-differentiated-services-code-point-dscp-markings"></a>Festlegen von DSCP-Markierungen (Differentiated Services Code Point)

Es gibt mehrere Methoden zum Festlegen der richtigen DSCP-Markierungen für die Klassifizierung des Datenverkehrs.

- DSCP-Markierungen am Endpunkt: Diese Option wird im Allgemeinen bevorzugt, da der Endpunkt selbst die richtigen Markierungen bereitstellt. Zurzeit können Sie dazu ein GPO verwenden. Dies ist aber nur auf Windows-Clients möglich, die in eine Domäne eingebunden sind. Mac OS X-Clients oder mobile Clients zum Beispiel stellen keinen Mechanismus zum Markieren des Datenverkehrs mit DSCP-Werten bereit.

- Portbasierte Markierungen mithilfe von ACLs in Routern: Diese Option wird sehr häufig verwendet, vor allem in heterogenen Umgebungen mit Windows- und Mac-Computern. In diesem Szenario markiert das Netzwerkteam den Datenverkehr an den Routern für eingehenden/ausgehenden Datenverkehr (normalerweise im WAN (Wide Area Network, Fernnetz)) basierend auf den für die einzelnen Modalitäten definierten Quellportbereichen. Diese Vorgehensweise funktioniert zwar plattformübergreifend, allerdings wird dabei nur der WAN-Edge markiert (nicht die gesamte Strecke bis zum Clientcomputer). Außerdem entsteht Verwaltungsaufwand.
    
- Eine Kombination aus DSCP-Markierungen auf dem Client und portbasierten ACLs in Routern
    
Wir empfehlen nach Möglichkeit eine Kombination aus beiden, das heißt die Verwendung eines GPOs für die Mehrheit der Clients sowie die Verwendung von portbasierten Markierungen. Dadurch können Sie sicherstellen, dass QoS zumindest teilweise auf mobile Clients, Macs und andere Clients angewendet wird.

Zum Festlegen des DSCP-Werts für den vordefinierten Quellportbereich im Microsoft Teams-Client können Sie richtlinienbasierte QoS innerhalb von Gruppenrichtlinien verwenden. In der folgenden Tabelle wird anhand der genannten Portbereiche für jede Arbeitsauslastung eine Richtlinie erstellt.

| Datenverkehrstyp des Clients|Anfang des Portbereichs|Ende des Portbereichs|DSCP-Wert|
|---------|---------|---------|--------|
| Audio|50000|50019|46|
| Video|50020|50039|34|
| Anwendungsfreigabe|50040|50059|18|
| Dateiübertragung|50040|50059|18|

Tabelle 3: Portbereiche nach Datenverkehrstyp

Hinweis: Die von Microsoft Teams festgelegten Portbereiche können nicht geändert werden. Die neuesten Informationen finden Sie auf dieser Seite: https://support.microsoft.com/kb/2409256.

Wenn Sie die Portbereiche festgelegt haben, konfigurieren Sie im nächsten Schritt die Einstellungen für richtlinienbasierte QoS in einem Gruppenrichtlinienobjekt (Group Policy Object, GPO). Details zu diesen Schritten finden Sie auf [TechNet](https://technet.microsoft.com/library/jj205371(v=ocs.15).aspx). 

Die neuen Richtlinien, die Sie erstellt haben, werden erst nach einer Aktualisierung der Gruppenrichtlinien auf den Clientcomputern wirksam. Die Gruppenrichtlinien werden zwar automatisch regelmäßig aktualisiert, aber Sie können die sofortige Aktualisierung erzwingen. Dazu führen Sie auf allen Computern, auf denen die Gruppenrichtlinien aktualisiert werden sollen, den folgenden Befehl aus:

        gpudate.exe /force

Diesen Befehl können Sie über ein beliebiges Befehlsfenster ausführen, das mit Administratoranmeldeinformationen ausgeführt wird. Um ein Befehlsfenster mit Administratoranmeldeinformationen auszuführen, klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.

## <a name="verifying-the-dscp-markings-in-gpo"></a>Überprüfen der DSCP-Markierungen aus dem GPO

Um zu überprüfen, ob die Werte aus dem GPO festgelegt wurden, führen Sie die folgenden Schritte aus:

1.  Überprüfen Sie mit „gpresult“, ob der lokale PC die Einstellungen aus dem GPO erhalten hat. Mit „gpresult /R >gp.txt“ generieren Sie einen Bericht und senden ihn an eine Textdatei („gp.txt“).

    ![Screenshot der Administratoreingabeaufforderung, in der der Befehl „gpresult“ ausgeführt wird](media/Qos-in-Teams-Image3.png)

    Abbildung 2: Überprüfen der angewendeten Gruppenrichtlinienobjekte
    > [!NOTE]
    > Alternativ können Sie „gpresult /H gp.html“ ausführen, um die gleichen Daten in Form eines benutzerfreundlicheren HTML-Berichts zu erzeugen. 
2.  Suchen Sie in der generierten Datei nach der Überschrift „Angewendete Gruppenrichtlinienobjekte“, und vergewissern Sie sich, dass die Namen der zuvor erstellten GPOs in der Liste der angewendeten Richtlinien enthalten sind. 

3.  Öffnen Sie den Registrierungs-Editor, und navigieren Sie zu:

    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\

    Überprüfen Sie die unten in Tabelle 3 aufgeführten Registrierungswerte.
    
    | Name | Typ | Daten|
    |---------|---------|---------
    | Application Name|REG_SZ|Teams.exe|
    | DSCP Value|REG_SZ|46|
    | Local IP|REG_SZ|*|
    | Local IP Prefix Length|REG_SZ|*|
    | Local Port|REG_SZ|50000-50019|
    | Protokoll|REG_SZ|*|
    | Remote IP|REG_SZ|*|
    | Remote Ip Prefix|REG_SZ|*|
    | Remote Port|REG_SZ|*|
    | Throttle Rate|REG_SZ|-1|
    
    Tabelle 3: Windows-Registrierungswerte für QoS

4.  Vergewissern Sie sich, dass die Angabe für „Application Name“ für den verwendeten Client richtig ist, und dass „DSCP Value“ und „Local Port“ den Einstellungen im GPO entsprechen.

## <a name="validating-qos-analyzing-teams-traffic-on-the-network"></a>Validieren von QoS: Analysieren des Microsoft Teams-Datenverkehrs im Netzwerk

QoS ist nur wirksam, wenn der durch das GPO festgelegte DSCP-Wert vom Anrufer bis zum Angerufenen vorhanden ist. Durch Untersuchen des vom Microsoft Teams-Client generierten Datenverkehrs können wir sicherstellen, dass der DSCP-Wert beim Durchqueren des Netzwerks nicht geändert oder entfernt wird. 

Am besten wäre es, den Datenverkehr an der Stelle aufzuzeichnen, an der er das Netzwerk verlässt. Sie können Portspiegelung in einem Switch oder Router verwenden, um die Aufzeichnung des Datenverkehrs im Netzwerk zu erleichtern. 

### <a name="looking-at-network-traffic-using-network-monitor"></a>Untersuchen des Netzwerkdatenverkehrs mit dem Netzwerkmonitor

Der Netzwerkmonitor ist ein Tool von Microsoft, das Sie herunterladen können, um den Netzwerkdatenverkehr zu analysieren. Laden Sie [Netzwerkmonitor 3.4](https://www.microsoft.com/download/4865) herunter.

Stellen Sie eine Verbindung mit dem PC her, auf dem der Netzwerkmonitor ausgeführt wird, und zwar an dem Port, der für Portspiegelung konfiguriert ist. Starten Sie die Aufzeichnung von Paketen. Tätigen Sie einen Anruf mit dem Skype for Business-Client. Stellen Sie vor dem Auflegen sicher, dass die Medienverbindung hergestellt wurde. Beenden Sie die Aufzeichnung, und erstellen Sie einen Anzeigefilter, der der Quell-IP des PCs entspricht, von dem aus der Anruf getätigt wurde. Optimieren Sie den Filter, indem Sie den DSCP-Wert 46 (in Hexadezimalschreibweise 0xb8) als Suchkriterium definieren:

Source == "192.168.137.201" AND IPv4.DifferentiatedServicesField == 0xb8 

![Screenshot des Dialogfelds „Display Filter“ im Netzwerkmonitor mit den Filtern, die angewendet werden können](media/Qos-in-Teams-Image4.png)


Klicken Sie auf **Apply** (Anwenden), um den Filter zu aktivieren. Wählen Sie im Fenster **Frame Summary** (Framezusammenfassung) das erste UDP-Paket aus, und betrachten Sie die Framedetails:

![Screenshot des Dialogfelds „Frame Details“ (Framedetails) im Netzwerkmonitor mit hervorgehobenen DSCP-Einstellungen](media/Qos-in-Teams-Image5.png)

Erweitern Sie „IPv4“, und betrachten Sie den Wert am Ende der Zeile „DSCP“. In diesem Beispiel ist der DSCP-Wert auf „46“ festgelegt. Das ist richtig, da der Quellport 50019 verwendet wird, das heißt, bei der Arbeitsauslastung handelt es sich um Sprache. 

Wiederholen Sie die Überprüfung für alle Arbeitsauslastungen, die durch das GPO markiert wurden. 

> [!NOTE]
> Vergewissern Sie sich, dass die Markierungen auch für Peer-zu-Peer-Datenverkehr berücksichtigt werden. Dazu können Sie den Netzwerkmonitor auf zwei Clients installieren und Anrufe zwischen den beiden Clients tätigen. Untersuchen Sie den zwischen den Clients fließenden Mediendatenverkehr auf die gleiche Weise wie oben beschrieben.

### <a name="sample-filters-to-use-for-network-monitor-or-wireshark"></a>Beispielfilter zur Verwendung mit dem Netzwerkmonitor oder mit Wireshark

|Verwendung  |Beispielfilter  |
|---------|---------|
|Sprache (Hinweis: Multiplexing muss deaktiviert sein.)     |   udp.port==3479 AND Ipv4.DifferentiatedServicesField.DSCP==46      |
|Video     | udp.port==3480 AND Ipv4.DifferentiatedServicesField.DSCP==34        |
|Bildschirmübertragung     |  udp.port==3481 AND Ipv4.DifferentiatedServicesField.DSCP==18       |

### <a name="filter-media-traffic-from-microsoft-relays-requires-azure-expressroutehttpsazuremicrosoftcomservicesexpressroute"></a>Filter: Mediendatenverkehr von Microsoft-Relays (Erfordert [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/).)

ip.src in {52.114.188.0/22 52.114.220.0/22 52.114.124.0/22 52.114.60.0/22} and (udp.srcport in {3479 3480 3481} or (udp.srcport ge 50000 and udp.srcport lt 60000))

### <a name="filter-media-traffic-to-microsoft-relays"></a>Filter: Mediendatenverkehr zu Microsoft-Relays

ip.dst in {52.114.188.0/22 52.114.220.0/22 52.114.124.0/22 52.114.60.0/22} and (udp.dstport in {3479 3480 3481} or (udp.dstport ge 50000 and udp.dstport lt 60000))


Sie sollten Datenverkehr zu und von den Microsoft-Relays sehen. Sie können wie im nächsten Abschnitt gezeigt die DSCP-Markierungen auf der IP-Ebene in Wireshark überprüfen.

### <a name="expected-dscp-markings"></a>Erwartete DSCP-Markierungen

Audiodatenströme: 46

Videodatenströme: 34

Datenströme: 18

### <a name="filter-dscp-condition-to-network"></a>Filter: DSCP-Bedingung für Netzwerk

ip.dsfield.dscp in {46 34 18}



### <a name="looking-at-network-traffic-using-wireshark"></a>Untersuchen des Netzwerkdatenverkehrs mit Wireshark

Wireshark (https://www.wireshark.org/) ist ein leistungsstarkes Tool, mit dem Sie Netzwerkdaten zur weiteren Analyse filtern und aufzeichnen können. Stellen Sie eine Verbindung mit einem PC her, auf dem Wireshark ausgeführt wird, und zwar an dem Port, der für Portspiegelung konfiguriert ist. Starten Sie die Aufzeichnung von Paketen. Tätigen Sie einen Anruf mit dem Microsoft Teams-Client. Stellen Sie vor dem Auflegen sicher, dass die Medienverbindung hergestellt wurde.

Beenden Sie die Paketablaufverfolgung, und erstellen Sie einen Filter, der nur die Quell-IP des PCs anzeigt, auf dem der Microsoft Teams-Client installiert ist (z. B. *ip.src_host == 192.168.137.201*). Außerdem soll der Filter nach Paketen suchen, die einen Quellport aus dem für Sprache angegebenen Bereich verwenden (50000–50019):

![Screenshot von Wireshark mit Filtereinstellungen](media/Qos-in-Teams-Image6.png)
 

Markieren Sie das Paket, und erweitern Sie den IPv4-Header (Internetprotokoll, Version 4) im Detailbereich für das Paket:

![Screenshot von Wireshark mit hervorgehobenen DSCP-Einstellungen](media/Qos-in-Teams-Image7.png)
 

Vergewissern Sie sich, dass der Wert für *Differentiated Services Code Point* mit dem Wert für die entsprechende Arbeitsauslastung übereinstimmt, in diesem Fall „46“ (in Binärschreibweise 101110) für Sprache.

Wiederholen Sie die Überprüfung für alle Arbeitsauslastungen, die durch das GPO markiert wurden.

> [!NOTE]
> Vergewissern Sie sich, dass die Markierungen für Peer-zu-Peer-Datenverkehr berücksichtigt werden. Dazu können Sie Wireshark oder den Netzwerkmonitor auf zwei Clients installieren und Anrufe zwischen den beiden Clients tätigen. Untersuchen Sie den zwischen den Clients fließenden Mediendatenverkehr auf die gleiche Weise wie oben beschrieben.

## <a name="summary"></a>Zusammenfassung

Quality of Service spielt bei der Bereitstellung von Funktionen auf Unternehmensniveau mit Microsoft Teams eine wichtige Rolle. Dabei müssen Sie jedoch immer bedenken, dass QoS nur in ordnungsgemäß verwalteten Netzwerken effektiv ist. Daher muss das Bereitstellungsteam eng mit den Netzwerkteams zusammenarbeiten, um sicherzustellen, dass in der Vermittlungsschicht die richtigen Informationen übergeben werden, idealerweise mit End-to-End-Verwaltung.

