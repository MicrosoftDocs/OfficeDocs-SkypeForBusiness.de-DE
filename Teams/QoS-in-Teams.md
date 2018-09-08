---
title: Quality of Service in Microsoft-Teams - Microsoft-Teams
author: rmw2890
ms.author: MyAdvisor
manager: Serdars
ms.date: 04/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Bereiten Sie das Netzwerk Ihrer Organisation für Quality of Service (QoS) in Microsoft Teams vor.
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 640f567033b75a6d068721c0c59ef4d2a1b5f11a
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882274"
---
# <a name="quality-of-service-qos-in-microsoft-teams"></a>Quality of Service (QoS) in Microsoft Teams

In diesem Artikel helfen Ihnen bei der Vorbereitung des Netzwerks Ihrer Organisation für Quality of Service (QoS) in Microsoft-Teams.
QoS ist ein Mechanismus, mit denen Sie bestimmte Arten von Netzwerkverkehr zu priorisieren. Datenfluss für die Echtzeitkommunikation Diensten wie etwa Teams Priorisierung ist wichtig, Business-Klasse Benutzer-Erlebnis. Für QoS tatsächlich wirksam wird müssen Sie eine QoS-fähigen Verbindung von Ende zu Ende (PC, Netzwerk-Switches und Router in die Cloud) konfigurieren, da jeder Teil des Pfads, die zur Unterstützung von QoS fehlschlägt, die Qualität der gesamten Kommunikation beeinträchtigt werden kann.

![Die Beziehung zwischen einer Organisation Netzwerke und Office 365-Dienste: lokale Netzwerk und Geräte Kontaktaufnahme mit einem Interconnect-Netzwerk, das wiederum eine Verbindung mit Office 365-Cloud-VoIP und Audiokonferenzen Services herstellt.] (media/Qos-in-Teams-Image1.png "Die Beziehung zwischen einer Organisation Netzwerke und Office 365-Dienste: lokale Netzwerk und Geräte Kontaktaufnahme mit einem Interconnect-Netzwerk, das wiederum eine Verbindung mit Office 365-Cloud-VoIP und Audiokonferenzen Services herstellt.")

_Abbildung 1. Die Beziehung zwischen einer Organisation Netzwerke und Office 365-Dienste_
 

In den meisten Fällen werden im Netzwerk Interconnect einer nicht verwalteten Internet Netzwerkverbindung. Eine Option zum Beheben von End-to-End-Dienstqualität ist [Azure ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/). Empfohlen, Sie QoS implementieren auf die Teile des Netzwerks können Sie steuern, welche, nämlich auf Ihrem lokalen Netzwerk. Die Qualität der Kommunikation in Echtzeit Arbeitslasten in Ihrer Bereitstellung zu erhöhen wird und so genannten Chokepunkten gewährleistet in Ihrer bestehenden Bereitstellung verringern. 


## <a name="prioritize-teams-network-traffic-for-qos"></a>Priorisieren von Teams Netzwerkdatenverkehr für QoS 

Dieser Artikel befasst sich Teams Echtzeitkommunikation Datenverkehr zu priorisieren – nämlich Sprach- und Videofunktionen. Sie können auch andere Arten von Datenverkehr, basierend auf Ihren Anforderungen priorisieren.

Es gibt mehrere Möglichkeiten zum Priorisieren des Datenverkehrs, am häufigsten werden jedoch DSCP-Markierungen (Differentiated Services Code Point) verwendet. Sie können ("mit Tags") angewendet werden basierend auf Portbereiche und auch über den Gruppenrichtlinienobjekten. In diesem Artikel behandelt wird. Es wird empfohlen, für die Verwendung tagging basierend auf Portbereiche, da es für alle Geräte, nicht nur die der Domäne beigetreten funktionsfähig ist.

Steuern der DSCP-Markierung über Gruppenrichtlinienobjekte wird sichergestellt, dass die Domäne eingebundenen Computer die richtigen Einstellungen erhalten und nur von einem Administrator verwaltet werden kann.
 
Es ist wichtig zu verstehen, dass QoS nur, funktioniert Wenn für alle Hyperlinks implementiert, die Anrufer zum angerufenen verbinden. Wenn Sie QoS auf das interne Netzwerk und ein Benutzer von einem Remotestandort aus anmeldet, können Sie nur innerhalb des internen, verwalteten Netzwerks priorisieren. Obwohl Remotestandorten eine verwaltete Verbindung durch die Implementierung eines virtuellen privaten Netzwerks (VPN) empfangen können, wird empfohlen, dass Sie vermeiden Sie die Ausführung von Real-Time Communications Datenverkehr über VPN.

> [!NOTE]
> Es wird empfohlen, dass Sie Split-tunneling für Remotebenutzer VPN-Verbindung implementieren, um die Qualität des Benutzererlebnisses zu maximieren. Herunterladen des Dokuments [Bereitstellen-Anweisungen-VPN-Split Tunnel](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9 ) aus MyAdvisor Weitere Informationen.

In einem globalen Unternehmen mit verwalteten Links, die Kontinente erstrecken wird QoS dringend empfohlen, da Bandbreite für diese Links im Vergleich zu den LAN beschränkt ist.

## <a name="qos-queues"></a>QoS-Warteschlangen

Um eine garantierter Ebene des Diensts für eine Anwendung im Netzwerk bereitstellen, benötigen die zugrunde liegenden Netzwerkgeräte eine Möglichkeit zum Klassifizieren unterschiedliche Arten von Datenverkehr. Wenn Ihre Organisation VoIP-Datenverkehr Priorität über andere Datenverkehr übergeben möchte, muss ein Router (z. b) VoIP und normalen Browsen Datenverkehr unterscheiden können. 

Differenzierte Dienste (DiffServ) stellt einen Rahmen in der Datenverkehr von Netzwerkgeräten basierend auf den Typ des Felds in der Kopfzeile der IPv4/IPv6-Paket (ToS) Dienste andere Priorität zugewiesen ist. Die wichtigsten sechs Bits des Felds DiffServ sind die differentiated Services Code Point oder DSCP. Durch die Verwendung dieses Frameworks Datenverkehr kann werden als einen bestimmten Typ Datenverkehr (beispielsweise Voice) klassifiziert, und klicken Sie dann markiert (101110 oder 46 Dezimal für VoIP-Datenverkehr), sodass Wenn Netzwerkgeräte diese Auswahlmöglichkeiten verarbeiten, der Datenverkehr werden kann priorisiert entsprechend () Expedited Forwarding, in diesem Beispiel).

Netzwerkverkehr einen Router eingibt, wird der Datenverkehr in einer Warteschlange platziert – Wenn keine QoS besteht im Wesentlichen nur eine einzige Warteschlange vorhanden ist und Daten, wie First in behandelt werden, First out. Dies bedeutet, dass VoIP-Datenverkehr (, sehr groß-und Kleinschreibung zu Verzögerungen) hinter Datenverkehr über streaming Onlinedienste Neustartzyklus möglicherweise. Wenn Sie QoS zu implementieren, können Sie mehrere Warteschlangen definieren, mit anderen Überlastung Management-Features (wie Cisco Reihenfolge in der Warteschlange und Klassen basierende gewichteten fair Warteschlange [CBWFQ]) und eine Überlastung Vermeidung Features (beispielsweise gewichteten zufällige frühe Erkennung [ WRED]).

![Gesamten verfügbaren Bandbreite auf mehrere Warteschlangen aufgeteilt ist – Audio-, Video- und anderen Datenverkehr – unterschiedliche Prioritäten zugewiesen wurden.] (media/Qos-in-Teams-Image2.png "Gesamten verfügbaren Bandbreite auf mehrere Warteschlangen aufgeteilt ist – Audio-, Video- und anderen Datenverkehr – unterschiedliche Prioritäten zugewiesen wurden.")

_Abbildung 2. Dargestellte QoS-Warteschlangen_

Nachdem diese vorhanden sind, ist es möglich, vorhersehbare QoS übermittelt werden, da die zugrunde liegenden verwalteten Netzwerks nun weiß, wie klassifizieren, markieren und Priorisieren von Datenverkehr. Aus der Sicht Teams die wichtigsten Konfigurationsschritt ist die Klassifizierung und Kennzeichnung der Pakete, aber für End-to-End-QoS erfolgreich durchgeführt werden müssen Sie auch die Konfiguration der Anwendung mit der zugrunde liegenden Netzwerkkonfiguration sorgfältig ausrichten.

## <a name="teams-qos-scenarios"></a>Teams QoS-Szenarien

Die Anleitung für die Implementierung von QoS für Teams basiert auf vier Szenarien:

*  **Szenario 1:** Sie bereitgestellt haben, oder bereitstellen, Teams und zum Implementieren von QoS über Port-basierte tagging planen. Port-basierte tagging ist die zuverlässigste-Methode, da es universell in der gesamten alle Plattformen funktioniert und einfachste besteht darin zu implementieren.  

*  **Szenario 2:** Sie bereitgestellt haben, oder bereitstellen, Teams und planen, implementieren Sie QoS über tagging Group Policy Object. Diese Vorgehensweise wird manchmal in Verbindung mit Szenario 1 verwendet. Obwohl dieses Szenario vollständig gültig ist, ist es wichtig zu verstehen, dass es nur für die Domäne eingebundener Windows-Clients eingesetzt wird. Jedes Gerät, das ein in die Domäne eingebundener Windows-Client wird nicht nicht aktiviert werden, für DSCP markieren.

*  **Szenario 3:** Sie haben Skype für Business Online, einschließlich QoS-tagging, bereitgestellt und sind nun Teams bereitstellen. Wenn dies auf Sie zutrifft, respektiert Microsoft Teams die vorhandene Konfiguration und verwendet die gleichen Portbereiche und Markierungen wie der Skype for Business-Client. In den meisten Fällen wird keine zusätzliche Konfiguration erforderlich sein. 
 
    > [!NOTE]
    > Wenn Sie Anwendung Namen QoS tagging über Gruppenrichtlinien verwenden, müssen Sie Teams.exe als den Namen der Anwendung hinzufügen.

*  **Szenario 4:** Sie bereitgestellt haben, oder bereitstellen, Teams und QoS über Port-basierte mithilfe einen benutzerdefinierten Portbereich tagging implementieren möchten.

## <a name="recommended-dscp-markings"></a>Empfohlene DSCP Auswahlmöglichkeiten

Der erste Schritt besteht zum Klassifizieren der Datenverkehr fließt (wie Audio und Video), indem Sie die eindeutige, nicht überlappende Portbereiche DSCP-Werte zuweisen. Hier zugewiesene DSCP-Wert wird die Priorität des Datenverkehrs über das Netzwerk, basierend auf der Netzwerkkonfiguration laufen bestimmen. Jede Arbeitslast eigenen DSCP-Wert, jedoch nicht unbedingt eindeutig Ruft einen Wert ab, einige Kunden möglicherweise den gleichen Wert für Sprach- und Videofunktionen Arbeitslasten festlegen die gleiche Priorität im Netzwerk gewähren.  

Der zu verwendende DSCP-Wert hängt davon ab, wie Sie die Arbeitslast priorisieren möchten. Beispielsweise die geschäftlichen möglicherweise Abläufe, dass die Anwendung geben die gleiche Priorität als Video Freigabe (und markieren Sie diese daher mit denselben DSCP-Wert wie Video). Anderen Umgebungen möglicherweise eine vorhandene QoS-Strategie an, die Hilfe Sie die Priorität der Netzwerk-Arbeitslasten zu bestimmen. 

Tabelle 1 zeigt die DSCP-Auswahlmöglichkeiten bei der Verwendung von Teams mit ExpressRoute erforderlich. Diese Auswahlmöglichkeiten können als Ausgangspunkt für Kunden verwendet werden, die sich nicht sicher sind, was für die Verwendung in ihrer eigenen Umgebung befinden. Weitere Informationen finden Sie unter [QoS-Anforderungen für ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-qos).


_In Tabelle 1. DSCP Auswahlmöglichkeiten_
    
| Client-Quellportbereich |Protokoll|Medienkategorie|DSCP-Wert|DSCP-Klasse|
|---------|---------|---------|---------|---------|
| 50.000 – 50,019|TCP/UDP|Audio|46|Expedited Forwarding (EF)|
| 50,020 – 50,039|TCP/UDP|Video|34|Assured Forwarding (AF41)|
| 50,040 – 50,059|TCP/UDP|Anwendung/Desktopfreigabe|18|Assured Forwarding (AF21)|

Hier sind ein paar Bedingungen, die Sie verstehen müssen, wenn Sie die Informationen in Tabelle 1 verwenden:
    
-  Wenn Sie in der Zukunft ExpressRoute implementieren möchten und noch nicht noch QoS implementiert, wird empfohlen, dass Sie die Anleitung in Tabelle 1 befolgen, sodass DSCP-Werte vom Absender zum Empfänger identisch sind. 

-  Alle Clients, einschließlich mobilen Clients und Geräten von Teams, verwenden diese Portbereiche und von einer DSCP-Richtlinie, die Sie implementieren, die diese Quelle Portbereiche verwendet betroffen sind. Die nur Clients, die weiterhin dynamische Ports verwenden, sind die Clients browserbasierte (d. h., diese Clients, mit denen Teilnehmer Besprechungen beitreten, indem Sie mit ihrem Browser).

-  Auch wenn der Mac-Client dieselben Portbereiche verwendet wird, verwendet der Mac-Client auch hartcodierte Werte für (Expedited FORWARDING)-Audio und Video (AF41). Diese Werte sind nicht konfigurierbar.
 
    
## <a name="source-ports-used-by-teams"></a>Von Microsoft Teams verwendete Quellports

In Microsoft Teams sollte QoS basierend auf den Quellports konfiguriert werden, die von den verschiedenen Arbeitsauslastungen verwendet werden. Weder serverseitige und clientseitige Portbereiche können derzeit konfiguriert werden. 

Beachten Sie die in Tabelle 2 aufgelisteten Client Quelle Portbereiche und verwenden Sie deren zugeordneten QoS DSCP Auswahlmöglichkeiten.

_In Tabelle 2. Quelle clientportbereiche_

| Client-Quellportbereich |Protokoll|Medienkategorie|DSCP-Wert|DSCP-Klasse|
|---------|---------|---------|---------|---------|
| 50.000 – 50,019|TCP/UDP|Audio|46|Expedited Forwarding (EF)|
| 50,020 – 50,039|TCP/UDP|Video|34|Assured Forwarding (AF41)|
| 50,040 – 50,059|TCP/UDP|Anwendung/Desktopfreigabe|18|Assured Forwarding (AF21)|

Die empfohlene Methode implementieren dieser QoS-Richtlinien ist die Verwendung der Quelle Clientports mit einer Quell- und Ziel-IP-Adresse des "beliebigen". Dies fängt beide ein- und ausgehenden Datenverkehr im internen Netzwerk. 

> [!NOTE]
> Wenn Sie QoS basierend auf Quelle Portbereiche für Skype für Business Online bereits konfiguriert haben, gilt die gleiche Konfiguration für Teams und werden keine weiteren Änderungen erforderlich. Wenn Sie Skype für Business Server lokal bereitgestellt haben, müssen Sie die QoS-Richtlinien Umgestalten.

## <a name="setting-dscp-markings"></a>Festlegen von DSCP Auswahlmöglichkeiten

Es gibt mehrere Ansätze zum Festlegen der richtigen DSCP Auswahlmöglichkeiten für Datenverkehr Klassifizierung:

-  **DSCP-Markierung am Endpunkt:** Dies ist im Allgemeinen die bevorzugte Option, da der Endpunkt selbst die richtigen Auswahlmöglichkeiten stellt. Derzeit können dazu mithilfe eines Gruppenrichtlinienobjekts, jedoch kann nur auf die Domäne eingebundener Windows-Clients verwendet werden. Mobile-Clients enthalten keinen Mechanismus zum Kennzeichnen Datenverkehr mit DSCP-Werte. Obwohl Sie nicht konfigurieren können nicht&ndash;in die Domäne eingebundener Windows-Clients für den Tag Verkehr, Clients wie Mac OS hartcodierte Tags haben und Datenverkehr immer markieren, wie oben beschrieben.

-  **Port-basierte DSCP mithilfe von Zugriffssteuerungslisten (ACLs) auf Routern tagging:** Dies ist ein sehr häufiges Option in heterogenen Windows- und Mac-Umgebungen ist aufgetreten. In diesem Szenario markiert das Netzwerkteam des Datenverkehrs an die eingehende/Ausgang Router (in der Regel befindet sich auf das WAN) basierend auf der Quelle Portbereiche für jede Modalität definiert ist. Obwohl dies plattformübergreifend funktioniert, er nur Datenverkehr an den WAN-Rand kennzeichnet – ganz nicht auf den Clientcomputer – und daher birgt Verwaltungsaufwand.
    
-  **Eine Kombination von DSCP Auswahlmöglichkeiten an den Endpunkt und Port-basierte ACLs für Router:** Sie sollten diese Kombination Wenn möglich in Ihrer Umgebung. Verwenden Sie ein Gruppenrichtlinienobjekt, um die meisten Clients abzufangen und auch verwenden Sie, Port-basierte DSCP-Markierung um sicherzustellen, dass diese Mobile, Mac und andere Clients weiterhin QoS-Behandlung (zumindest teilweise) relevanten Informationen erhalten.
    
Sie können Richtlinienbasierte QoS innerhalb der Gruppenrichtlinien verwenden, um den DSCP-Wert für den Portbereich vordefinierten Quelle im Client Teams festzulegen. Verwenden Sie die in Tabelle 3 angegebenen Portbereiche zum Erstellen einer Richtlinie für jeden Workload.

_Tabelle 3. Portbereiche nach Datenverkehrstyp_
| Datenverkehrstyp des Clients|Anfang des Portbereichs|Ende des Portbereichs|DSCP-Wert|
|---------|---------|---------|--------|
| Audio|50000|50019|46|
| Video|50020|50039|34|
| Anwendungsfreigabe|50040|50059|18|

> [!NOTE]
> Festlegen von Teams, die die Portbereiche können nicht geändert werden. Lesen Sie [in diesem Artikel Unterstützung](https://support.microsoft.com/kb/2409256) für die neuesten Informationen. 

Nachdem Sie die Portbereiche identifiziert haben, besteht der nächste Schritt konfigurieren Sie die Richtlinienbasierte QoS-Einstellungen innerhalb eines Gruppenrichtlinienobjekts. Weitere Informationen zu diesen Schritten finden Sie im [TechNet-Artikel](https://technet.microsoft.com/library/jj205371(v=ocs.15).aspx). 

Die neuen Richtlinien, die von die Ihnen erstellten werden nicht erst wirksam, Gruppenrichtlinien auf den Clientcomputern aktualisiert wurde. Obwohl Gruppenrichtlinien allein in regelmäßigen Abständen aktualisiert wurde, können Sie eine sofortige Aktualisierung erzwingen.

### <a name="force-group-policy-refresh"></a>Force Group Policy aktualisieren

1. Öffnen Sie auf jedem Computer, für die Sie die Gruppenrichtlinie aktualisieren möchten eine Befehlskonsole. Stellen Sie sicher, dass die Befehlskonsole festgelegt ist, als Administrator ausführen.

2. Geben Sie an der Befehlszeile
```
    gpudate.exe /force
```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>Überprüfen Sie die DSCP-Auswahlmöglichkeiten in das Gruppenrichtlinienobjekt

Führen Sie die folgenden Schritte aus, um zu überprüfen, dass die Werte aus dem Gruppenrichtlinienobjekt festgelegt wurden.

1.  Öffnen Sie eine Befehlskonsole. Stellen Sie sicher, dass die Befehlskonsole festgelegt ist, als Administrator ausführen.

2.  Geben Sie an der Befehlszeile 
    ```
    gpresult /R >gp.txt
    ```

    Dies einen Bericht generiert und in eine Textdatei mit dem Namen gp.txt zu senden. Alternativ können Sie den folgenden Befehl aus, um die gleichen Daten in einem besser lesbar HTML-Bericht mit dem Namen gp.html zu erzeugen eingeben:
    ```
    gpresult /H >gp.html
    ```
 
   ![Screenshot des Konsolenfenster des Befehls Gpresult.] (media/Qos-in-Teams-Image3.png "Screenshot des Konsolenfenster des Befehls Gpresult.")

3.  Suchen Sie in der generierten Datei nach der Überschrift **Gruppenrichtlinienobjekte angewendet** , und stellen Sie sicher, dass die Namen der zuvor erstellten Gruppenrichtlinienobjekte in der Liste der Richtlinien angewendet werden. 

4.  Öffnen Sie den Registrierungs-Editor, und wechseln Sie zu:

    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\

    Überprüfen Sie die Werte für die in Tabelle 3 aufgeführten Registrierungseinträge.

    _Tabelle 3. Werte für Windows-Registrierungseinträge für QoS_
    
    | Name | Typ | Daten|
    |---------|---------|---------
    | Application Name|REG_SZ|Teams.exe|
    | DSCP Value|REG_SZ|46|
    | Local IP|REG_SZ|*|
    | Local IP Prefix Length|REG_SZ|*|
    | Local Port|REG_SZ|50000-50019|
    | Protokoll|REG_SZ|*|
    | Remote IP|REG_SZ|*|
    | Remote-IP-Präfix|REG_SZ|*|
    | Remote Port|REG_SZ|*|
    | Throttle Rate|REG_SZ|-1|
    
5.  Stellen Sie sicher, dass der Wert für den Anwendungsnamen-Eintrag für den Client korrekt ist, den Sie verwenden, und stellen Sie sicher, dass sowohl die DSCP-Wert und der lokalen Port Einträge die Einstellungen in das Gruppenrichtlinienobjekt aktualisiert.

## <a name="validate-qos-by-analyzing-teams-traffic-on-the-network"></a>Überprüfen von QoS durch Analysieren Teams Datenverkehr im Netzwerk

Die DSCP-Wert festlegen, indem die Gruppenrichtlinien-Objekt muss vom Anrufer zum angerufenen in Reihenfolge für QoS effektiv vorhanden sein. Verfolgen Sie den Datenverkehr vom Client Teams generiert, stellen Sie sicher, dass der DSCP-Wert wird nicht geändert oder entfernt, wenn der Teams Arbeitslast Datenverkehr im Netzwerk durchläuft. 

Vorzugsweise, erfassen Sie Datenverkehr am Netzwerk Austritt. Sie können Anschluss Spiegelung für eine Switch- oder Router um dabei zu unterstützen.

### <a name="use-network-monitor-to-verify-dscp-values"></a>Verwenden des Netzwerkmonitors DSCP-Werte überprüfen

Netzwerkmonitor ist ein Tool, um den Netzwerkverkehr zu analysieren [von Microsoft herunterladen](https://www.microsoft.com/download/4865) können.

1.  Verbinden Sie auf dem PC Netzwerkmonitor ausgeführt wird auf den Port, der für die Spiegelung von Port und Erfassung von Paketen Start konfiguriert wurde. 

2.  Tätigen eines Anrufs mithilfe der Skype für Business-Client. Stellen Sie sicher, dass Media hergestellt wurde, bevor der Anruf wird beendet. 

3.  Beenden Sie die Aufzeichnung.

4. Klicken Sie im Feld **Anzeigefilter** verwenden Sie die Quell-IP-Adresse des Computers, der den Anruf getätigt hat, und verfeinern Sie den Filter, indem Sie definieren DSCP-Wert (hex-0xb8) 46 als Suchkriterien, wie im folgenden Beispiel dargestellt:

    Source == "192.168.137.201" AND IPv4.DifferentiatedServicesField == 0xb8 

    ![Screenshot des Dialogfelds in Microsoft Netzwerkmonitor mit Filter für Anzeigefilter.] (media/Qos-in-Teams-Image4.png "Screenshot des Dialogfelds in Microsoft Netzwerkmonitor mit Filter für Anzeigefilter.")

5.  **Übernehmen** Sie den Filter aktivieren auswählen.

6.  Wählen Sie im Fenster **Zusammenfassung Frame** das erste UDP-Paket aus.

7.  In Frame im Dialogfeld **Details** der erweitern Sie das Listenelement IPv4, und notieren Sie den Wert am Ende der Zeile, die mit **DSCP**beginnt. 

    ![Screenshot des Frames im Dialogfeld Details der in Microsoft Netzwerkmonitor DSCP-Einstellungen der Hervorhebung.] (media/Qos-in-Teams-Image5.png "Screenshot des Frames im Dialogfeld Details der in Microsoft Netzwerkmonitor DSCP-Einstellungen der Hervorhebung.")

In diesem Beispiel wird der DSCP-Wert auf 46 festgelegt. Dies ist korrekt, da der verwendete Quellport 50019, ist gibt an, dass es sich um eine VoIP-Arbeitslast handelt. 

Wiederholen Sie die Überprüfung für alle Arbeitsauslastungen, die durch das GPO markiert wurden. 
