---
title: Quality of Service in Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: Serdars
ms.date: 12/17/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Bereiten Sie das Netzwerk Ihrer Organisation für Quality of Service (QoS) in Microsoft Teams vor.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8aa4bb6858fceb45fbf6abca8fe475ba49dbe1ba
ms.sourcegitcommit: 6205201cb1314e753f672654dade11dd4adbfe8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2019
ms.locfileid: "29742863"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>Implementieren von Quality of Service (QoS) in Microsoft-Teams

In diesem Artikel helfen Ihnen bei der Vorbereitung des Netzwerks Ihrer Organisation für Quality of Service (QoS) in Microsoft-Teams.

QoS können Sie um den Netzwerkverkehr zu priorisieren, die Beachtung von netzwerkverzögerungen über Datenverkehr befindet, die weniger beachtet wird. Eine einfache entsprechend besteht darin, dass QoS virtuellen erstellt "Fahrgemeinschaften Spuren" in den Daten also einige Datentypen nie Netzwerk oder selten Verzögerungen auftreten.
Beim Priorisieren von Datenverkehr für die Echtzeitkommunikation wie Anrufe oder freigegebenen Besprechungen in Teams Sie können bieten mehr zuverlässig ein Benutzererlebnis Business-Klasse. Ohne eine Form von QoS möglicherweise die folgenden Qualitätsprobleme in Sprach- und Videofunktionen angezeigt:

- Jitter – unterschiedlich eingehenden Media-Pakete.
- Paketverlust – Pakete, was die fehlenden Wörter oder Silbenschrift verwenden kann.
- Verzögerte Roundtripzeit (Zeit) – Media-Pakete dauert sehr lange, um ihre Ziele zu erreichen.

Um QoS tatsächlich wirksam wird müssen Sie konsistente QoS-Einstellungen auf von Anfang bis Ende in Ihrer Organisation (Benutzer PCs, Netzwerk-Switches und Router in die Cloud) angewendet werden, da die Qualität der Anrufe von jeder Teil des Pfads, der zur Unterstützung der QoS-Prioritäten fehlschlägt beeinträchtigt werden kann , Video- und Bildschirm Freigaben.

QoS ist ein Mechanismus, den Sie verwenden können, bestimmte Arten von Netzwerkverkehr priorisieren Beachtung von netzwerkverzögerungen über dem anderen Datenverkehr, der weniger beachtet wird. Eine einfache entsprechend besteht darin, dass QoS virtuellen erstellt "Fahrgemeinschaften Spuren" in den Daten Netzwerk, sodass einige Datentypen nie oder selten Verzögerungen auftreten.

Beim Priorisieren von Datenverkehr für die Echtzeitkommunikation wie Anrufe oder freigegebenen Besprechungen in Teams Sie können bieten mehr zuverlässig ein Benutzererlebnis Business-Klasse. Wenn Sie QoS nicht implementieren, freigegebenen Bildschirme in Besprechungen können fixieren, Video kann pixellate, und Farbe UMSCHALT und VoIP-Anrufe können nicht mehr abgehackte und schwierig oder unmöglich zu verstehen. Um QoS tatsächlich wirksam wird müssen Sie konsistente QoS-Einstellungen auf von Anfang bis Ende in Ihrer Organisation (Benutzer PCs, Netzwerk-Switches und Router in die Cloud) angewendet werden, da die Qualität der Anrufe von jeder Teil des Pfads, der zur Unterstützung der QoS-Prioritäten fehlschlägt beeinträchtigt werden kann , Video- und Bildschirm Freigaben.

![Die Beziehung zwischen einer Organisation Netzwerke und Office 365-Dienste: lokale Netzwerk und Geräte Kontaktaufnahme mit einem Interconnect-Netzwerk, das wiederum eine Verbindung mit Office 365-Cloud-VoIP und Audiokonferenzen Services herstellt.](media/Qos-in-Teams-Image1.png) 

Eine Option zum Beheben von End-to-End-Dienstqualität ist [Azure ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/). Dennoch wird empfohlen, dass Sie QoS auf Ihrem lokalen Netzwerk implementieren. Die Qualität der Kommunikation in Echtzeit Arbeitslasten in Ihrer Bereitstellung zu erhöhen wird und verringern so genannten Chokepunkten gewährleistet. 

In den meisten Fällen werden im Netzwerk herstellen einer Verbindung mit Ihrem Unternehmen in die Cloud Internetzugang nicht verwalteten Netzwerk, in dem kann nicht zuverlässig QoS festgelegt werden. Eine Option zum tatsächlich End-to-End-Dienstqualität zulassen ist [Azure ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/). Empfohlen, Sie QoS implementieren auf die Teile des Netzwerks End-to-End-können Sie steuern, welche, nämlich auf Ihrem lokalen Netzwerk. Die Qualität der Kommunikation in Echtzeit Arbeitslasten in Ihrer Bereitstellung zu erhöhen wird und so genannten Chokepunkten gewährleistet in Ihrer bestehenden Bereitstellung verringern.

## <a name="prioritize-teams-network-traffic-for-qos"></a>Priorisieren von Teams Netzwerkdatenverkehr für QoS 

Dieser Artikel befasst sich Teams Echtzeitkommunikation Datenverkehr zu priorisieren – nämlich Sprach- und Videofunktionen. Sie können auch andere Arten von Datenverkehr, basierend auf Ihren Anforderungen priorisieren.

Es gibt verschiedene Methoden zum Priorisieren von Verkehr, aber die am häufigsten verwendeten mithilfe von differentiated Services Code Point (DSCP) Auswahlmöglichkeiten ist. Sie können ("mit Tags") angewendet werden basierend auf Portbereiche oder über den Gruppenrichtlinienobjekten. In diesem Artikel behandelt wird. Es wird empfohlen, für die Verwendung tagging basierend auf Portbereiche, da es für alle Geräte, nicht nur die der Domäne beigetreten funktionsfähig ist.

Steuern der DSCP-Markierung über Gruppenrichtlinienobjekte wird sichergestellt, dass die Domäne eingebundenen Computer die richtigen Einstellungen erhalten und nur von einem Administrator verwaltet werden kann.

Es ist wichtig zu verstehen, dass QoS nur, funktioniert Wenn für alle Hyperlinks implementiert, die Anrufer mit einem anderen verbinden. Wenn Sie QoS auf das interne Netzwerk und ein Benutzer von einem Remotestandort aus anmeldet, können Sie nur innerhalb des internen, verwalteten Netzwerks priorisieren. Obwohl Remotestandorten eine verwaltete Verbindung durch die Implementierung eines virtuellen privaten Netzwerks (VPN) empfangen können, wird empfohlen, dass Sie vermeiden Sie die Ausführung von Real-Time Communications Datenverkehr über VPN.

> [!NOTE]
> Es wird empfohlen, dass Sie Split-tunneling für Remotebenutzer VPN-Verbindung implementieren, um die Qualität des Benutzererlebnisses zu maximieren. Herunterladen des Dokuments [Bereitstellen-Anweisungen-VPN-Split Tunnel](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9 ) aus MyAdvisor Weitere Informationen.

In einem globalen Unternehmen mit verwalteten Links, die Kontinente umfassen, wird dringend empfohlen QoS, da die Bandbreite für diese Links im Vergleich zu den LAN eingeschränkt ist.

## <a name="qos-queues"></a>QoS-Warteschlangen

Um QoS zu ermöglichen, Netzwerkgeräten benötigen eine Möglichkeit zum Klassifizieren von Datenverkehr und müssen in der Lage, VoIP oder Video von anderen Netzwerkverkehr zu unterscheiden. 

Differenzierte Dienste (DiffServ) mithilfe den Typ des Felds in der Kopfzeile der IPv4/IPv6-Paket (ToS) Dienste Netzwerkgeräten Priorität festgelegt. Die wichtigsten sechs Bits des Felds DiffServ sind die differentiated Services Code Point oder DSCP. Mit diesem, Datenverkehr kann werden als eines bestimmten Typs (beispielsweise Voice) klassifiziert, und klicken Sie dann markiert (101110 oder 46 Dezimal für VoIP-Datenverkehr), sodass Wenn Netzwerkgeräte diese Auswahlmöglichkeiten verarbeiten, der Datenverkehr entsprechend priorisiert werden kann (EF Weiterleitung In diesem Beispiel wird).

Netzwerkverkehr einen Router eingibt, wird der Datenverkehr in einer Warteschlange abgelegt. Wenn keine QoS besteht, es nur eine einzige Warteschlange wird und Daten, wie First in behandelt werden, First out. Dies bedeutet, dass VoIP-Datenverkehr (, sehr groß-und Kleinschreibung zu Verzögerungen) hinter Datenverkehr über streaming Onlinedienste Neustartzyklus möglicherweise. Wenn Sie QoS implementieren, können Sie mehrere Warteschlangen definieren, mit anderen Überlastung Management-Features (wie Cisco Reihenfolge in der Warteschlange und Klassen basierende gewichteten fair Warteschlange [CBWFQ]) und eine Überlastung Vermeidung Features (beispielsweise gewichteten zufällige frühe Erkennung [ WRED]).

![Gesamten verfügbaren Bandbreite auf mehrere Warteschlangen aufgeteilt ist – Audio-, Video- und anderen Datenverkehr – unterschiedliche Prioritäten zugewiesen wurden.] (media/Qos-in-Teams-Image2.png "Gesamten verfügbaren Bandbreite auf mehrere Warteschlangen aufgeteilt ist – Audio-, Video- und anderen Datenverkehr – unterschiedliche Prioritäten zugewiesen wurden.")

_Abbildung 2. Beispiele für die QoS-Warteschlangen_

Nachdem diese vorhanden sind, ist es möglich, vorhersehbare QoS übermittelt werden, da das Netzwerk nun weiß, wie klassifizieren, markieren und Priorisieren von Datenverkehr. Aus der Sicht Teams die wichtigsten Konfigurationsschritt ist die Klassifizierung und Kennzeichnung der Pakete, aber für End-to-End-QoS erfolgreich durchgeführt werden müssen Sie auch die Konfiguration der Anwendung mit der zugrunde liegenden Netzwerkkonfiguration sorgfältig ausrichten.

## <a name="teams-qos-scenarios"></a>Teams QoS-Szenarien

Die Anleitung für die Implementierung von QoS für Teams basiert auf vier Szenarien:

*  **Szenario 1:** Sie bereitgestellt haben oder Teams bereitstellen und Implementieren von QoS über Port-basierte markieren möchten. Port-basierte tagging ist die zuverlässigste Methode, da es universell auf allen Plattformen funktioniert und einfachste implementiert wird.  

*  **Szenario 2:** Sie bereitgestellt haben oder Teams bereitstellen und Implementieren von QoS über Gruppenrichtlinien Objekt markieren möchten. Diese Vorgehensweise wird manchmal in Verbindung mit Szenario 1 verwendet. Obwohl dieses Szenario vollständig gültig ist, funktioniert es nur für die Domäne eingebundener Windows-Clients. Jedes Gerät, das ein in die Domäne eingebundener Windows-Client wird nicht nicht aktiviert werden, für DSCP markieren.

*  **Szenario 3:** Sie haben Skype für Business Online, einschließlich QoS-tagging, bereitgestellt und sind nun Teams bereitstellen. Wenn dies auf Sie zutrifft, respektiert Microsoft Teams die vorhandene Konfiguration und verwendet die gleichen Portbereiche und Markierungen wie der Skype for Business-Client. In den meisten Fällen wird keine zusätzliche Konfiguration erforderlich sein. 

    > [!NOTE]
    > Wenn Sie Anwendung Namen QoS tagging über Gruppenrichtlinien verwenden, müssen Sie Teams.exe als den Namen der Anwendung hinzufügen.

*  **Szenario 4:** Sie bereitgestellt haben oder Teams bereitstellen und QoS über Port-basierte mithilfe einen benutzerdefinierten Portbereich tagging implementieren möchten.

## <a name="implement-qos"></a>Implementieren von QoS

Auf einer sehr hohen Ebene erfordert die Implementierung der QoS folgende Schritte aus:

1. Bestimmen der Route und Bandbreite.

2. Verwenden Sie die DSCP-Auswahlmöglichkeiten und Portbereiche zum Klassifizieren von Datenverkehr.

3. Konfigurieren Sie die Richtlinienbasierte QoS-Einstellungen in ein Gruppenrichtlinienobjekt.

4. Überprüfen Sie die Portbereiche in Group Policy Object.

5. Analysieren von Teams Datenverkehr im Netzwerk, um QoS zu überprüfen.

Als Vorbereitung der QoS zu implementieren, sollten beachten Sie die folgenden Richtlinien:

- Der kürzeste Pfad zu Office 365 ist am besten.

- Schließen von Ports wird nur zu Qualität Beeinträchtigung führen.

- Hindernisse dazwischen liegenden wie Proxys, werden nicht empfohlen.

- Grenzwert für die Anzahl von Hops:

    - Client Netzwerkgrenze – 3 bis 5 Hops.
    - Internetdienstanbieter Microsoft Netzwerkgrenze – 3 hops
    - Microsoft Netzwerkgrenze zum endgültigen Ziel – irrelevante 

Informationen zum Konfigurieren von Firewallports wechseln Sie zu [Office 365-URLs und IP-Adressbereichen](office-365-urls-ip-address-ranges.md).

## <a name="determine-bandwidth-requirements"></a>Bestimmen der Bandbreite

Bevor Sie QoS für Microsoft-Teams, konfigurieren, ist es wichtig, bereiten Sie Ihr Netzwerk für Microsoft-Teams, und bestimmen Sie Ihre bandbreitenanforderungen. QoS in Ihrem Netzwerk bereitstellen erfordert die Reservierung einer definierten Anzahl von Bandbreite für jede Verbindung für Datenverkehr in Echtzeit. (Wenn Sie, dass die Bandbreite nicht zu einem beliebigen Zeitpunkt für Real-Time-Datenverkehr erforderlich ist, kann sie für andere Datenverkehr verwendet werden.)

Überlastung über ein Netzwerk wird Medienqualität erheblich beeinträchtigen. Fehlender Bandbreite führt zu Leistungseinbußen und benutzerfreundlich, daher empfiehlt es Bandbreite, die als Ausgangspunkt für die Bereitstellung von Teams planen. Zunehmender Teams Annahme und Nutzung, Verwendung von Berichterstattung zum erforderlichen anzupassen. 

Der Netzwerk-Planner auf schnelle verfügbar ist hilfreich, wenn Sie die erforderliche Bandbreite ermitteln möchten.

### <a name="requirements-for-a-connection-from-your-network-to-microsoft-network-edge"></a>Anforderungen für die Verbindung mit Microsoft Netzwerkgrenze aus dem Netzwerk

Für die optimale Medienqualität sind die Leistungsziele Netzwerk oder in Tabelle 1 aufgeführten Schwellenwerte für des Netzwerks Ihrer Organisation eine Verbindung mit der Microsoft-Netzwerkgrenze erforderlich.

> [!IMPORTANT]
> Konnektivität zwischen einem Client Teams auf das Netzwerk Ihres Unternehmens zu Office 365-Diensten muss die folgenden Netzwerk leistungsanforderungen erfüllen.

_In Tabelle 1. Leistungsmetriken für die Netzwerk - Client zu Office 365-Diensten_

| Metrik | Target  |
|--------|--------|
| Latenz (ein Weg) | < 50 Millisekunden |
| Wartezeit (Roundtripzeit (Zeit) | < 100 Millisekunden |
| Burstverlust von Paketen | < 10 % Intervall 200 Millisekunde |
| Paketverlust | < 1 % 15 zweiten Intervall |
| Die Kommunikation zwischen hinzukommen Jitter Paket | < 30 Millisekunden 15 zweiten Intervall |
| Neuanordnung von Paketen | < 0,05 % keine Reihenfolge Pakete |

Das Ziel des Vorgangs metrischen Wartezeit wird davon ausgegangen, Ihre Unternehmensstandort oder Websites und die Microsoft-Ränder befinden sich auf dem gleichen Kontinent.

Der Website Ihres Unternehmens für die Microsoft Network-Edge-Verbindung umfasst den ersten Hop Netzwerkzugriff, WiFi oder einer anderen drahtlosen Technologie werden kann.

Das Netzwerk Leistungsziel wird davon ausgegangen erforderlichen Bandbreite und/oder QoS-Planung. Mit anderen Worten, gelten die Anforderungen direkt in Echtzeit Mediendatenverkehr Teams, wenn eine spitzenauslastung die Netzwerkschnittstelle ist.

### <a name="requirements-for-a-connection-from-your-network-edge-to-microsoft-network-edge"></a>Anforderungen für eine Verbindung von Ihrer Netzwerkgrenze an Microsoft network edge

In Tabelle 2 sind die Leistungsziele Netzwerk oder Schwellenwerte, die für die Verbindung zwischen Ihrer Netzwerkgrenze und die Microsoft-Netzwerkgrenze erforderlich sind. Dies schließt alle internen Netzwerk Ihrer Organisation oder WAN und dient als Anleitung beim Testen des Netzwerkverkehrs, die über das Internet oder über ein ExpressRoute Partner-Netzwerk gesendet wird.

> [!IMPORTANT]
> Konnektivität zwischen Netzwerkgrenze an die Ränder der Microsoft-Netzwerk Ihres Unternehmens muss die folgenden Netzwerk leistungsanforderungen erfüllen.

_In Tabelle 2. Netzwerk Leistungsmetriken - Kante zu Kante_

| Metrik | Target  |
|--------|--------|
| Latenz (ein Weg) | < 30 Millisekunden |
| Wartezeit (Roundtripzeit (Zeit) | < 60 Millisekunden |
| Burstverlust von Paketen | < 1 % Intervall 200 Millisekunde |
| Paketverlust | < 0,1 % 15 zweiten Intervall |
| Die Kommunikation zwischen hinzukommen Jitter Paket | < 15 Millisekunden 15 zweiten Intervall |
| Neuanordnung von Paketen | < 0,01 % keine Reihenfolge Pakete |


## <a name="recommended-dscp-markings"></a>Empfohlene DSCP Auswahlmöglichkeiten

Wenn Sie zum Konfigurieren von QoS bereit sind, ist der erste Schritt zum Klassifizieren der Datenverkehr fließt (wie Audio und Video) durch die eindeutige, nicht überlappende Portbereiche DSCP-Werte zuweisen. Hier zugewiesene DSCP-Wert wird die Priorität des Datenverkehrs über das Netzwerk, basierend auf der Netzwerkkonfiguration laufen bestimmen. Jede Arbeitslast eigenen DSCP-Wert, jedoch nicht unbedingt eindeutig Ruft einen Wert ab, möglicherweise möchten Sie den gleichen Wert für Sprach- und Videofunktionen Arbeitslasten, legen sie benennen die gleiche Priorität im Netzwerk.  

Der zu verwendende DSCP-Wert hängt davon ab, wie Sie die Arbeitslast priorisieren möchten. Beispielsweise die geschäftlichen möglicherweise Abläufe, dass die Anwendung geben die gleiche Priorität als Video Freigabe (und markieren Sie diese daher mit denselben DSCP-Wert wie Video). Anderen Umgebungen möglicherweise eine vorhandene QoS-Strategie an, die Hilfe Sie die Priorität der Netzwerk-Arbeitslasten zu bestimmen. 

Tabelle 3 zeigt die DSCP-Auswahlmöglichkeiten für Teams mit ExpressRoute erforderlich. Diese Auswahlmöglichkeiten können als Ausgangspunkt für Kunden verwendet werden, die sich nicht sicher sind, was für die Verwendung in ihrer eigenen Umgebung befinden. Weitere Informationen finden Sie unter [QoS-Anforderungen für ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-qos).

_Tabelle 3. DSCP Auswahlmöglichkeiten_

| Client-Quellportbereich |Protokoll|Medienkategorie|DSCP-Wert|DSCP-Klasse|
|---------|---------|---------|---------|---------|
| 50.000 – 50,019|TCP/UDP|Audio|46|Expedited Forwarding (EF)|
| 50,020 – 50,039|TCP/UDP|Video|34|Assured Forwarding (AF41)|
| 50,040 – 50,059|TCP/UDP|Anwendung/Desktopfreigabe|18|Assured Forwarding (AF21)|

Achten Sie auf Folgendes, wenn Sie die Informationen in Tabelle 3 verwenden:

-  Wenn Sie in der Zukunft ExpressRoute implementieren möchten und noch nicht noch QoS implementiert, wird empfohlen, dass Sie die Anleitung in Tabelle 3 befolgen, sodass DSCP-Werte vom Absender zum Empfänger identisch sind. 

-  Alle Clients, einschließlich mobilen Clients und Geräten von Teams, verwenden diese Portbereiche und von einer DSCP-Richtlinie, die Sie implementieren, die diese Quelle Portbereiche verwendet betroffen sind. Die nur Clients, die weiterhin dynamische Ports verwenden, sind die Clients browserbasierte (d. h., diese Clients, mit denen Teilnehmer Besprechungen beitreten, indem Sie mit ihrem Browser).

-  Obwohl der Mac-Client dieselben Portbereiche verwendet, verwendet er auch hartcodierte Werte für (Expedited FORWARDING) Audio- und Videofunktionen (AF41). Diese Werte sind nicht konfigurierbar.


## <a name="source-ports-used-by-teams"></a>Von Microsoft Teams verwendete Quellports

In Microsoft Teams sollte QoS basierend auf den Quellports konfiguriert werden, die von den verschiedenen Arbeitsauslastungen verwendet werden. Derzeit können weder serverseitige und clientseitige Portbereiche konfiguriert werden. 

Die in Tabelle 3 aufgeführten Client Quelle Portbereiche auch gelten für Teams und ihre zugehörigen QoS DSCP Auswahlmöglichkeiten verwenden.

Die empfohlene Methode implementieren dieser QoS-Richtlinien ist die Verwendung der Quelle Clientports mit einer Quell- und Ziel-IP-Adresse des "beliebigen". Dies fängt beide ein- und ausgehenden Datenverkehr im internen Netzwerk. 

> [!NOTE]
> Wenn Sie QoS basierend auf Quelle Portbereiche für Skype für Business Online bereits konfiguriert haben, gilt die gleiche Konfiguration für Teams und werden keine weiteren Änderungen erforderlich. Wenn Sie Skype für Business Server lokal bereitgestellt haben, müssen Sie die QoS-Richtlinien neu zu überprüfen, und passen sie bei Bedarf.

## <a name="set-dscp-markings"></a>Festlegen von DSCP Auswahlmöglichkeiten

Es gibt mehrere Ansätze zum Festlegen der richtigen DSCP Auswahlmöglichkeiten für Datenverkehr Klassifizierung:

-  **DSCP-Markierung am Endpunkt:** Dies ist im Allgemeinen die bevorzugte Option, da der Endpunkt selbst die richtigen Auswahlmöglichkeiten stellt. Derzeit können dazu mithilfe eines Gruppenrichtlinienobjekts, jedoch kann nur auf die Domäne eingebundener Windows-Clients verwendet werden. Mobile-Clients enthalten keinen Mechanismus zum Kennzeichnen Datenverkehr mit DSCP-Werte. Obwohl Sie nicht konfigurieren können nicht&ndash;in die Domäne eingebundener Windows-Clients für den Tag Verkehr, Clients wie Mac OS hartcodierte Tags haben und Datenverkehr immer markieren, wie oben beschrieben.

-  **Port-basierte DSCP mithilfe von Zugriffssteuerungslisten (ACLs) auf Routern tagging:** Dies ist ein sehr häufiges Option in heterogenen Windows- und Mac-Umgebungen ist aufgetreten. In diesem Szenario markiert das Netzwerkteam des Datenverkehrs an die eingehende/Ausgang Router (in der Regel befindet sich auf das WAN) basierend auf der Quelle Portbereiche für jede Modalität definiert ist. Obwohl dies plattformübergreifend funktioniert, er nur Datenverkehr an den WAN-Rand kennzeichnet – ganz nicht auf den Clientcomputer – und daher birgt Verwaltungsaufwand.

-  **Eine Kombination von DSCP Auswahlmöglichkeiten an den Endpunkt und Port-basierte ACLs für Router:** Sie sollten diese Kombination Wenn möglich in Ihrer Umgebung. Verwenden Sie ein Gruppenrichtlinienobjekt, um die meisten Clients abzufangen und auch verwenden Sie, Port-basierte DSCP-Markierung um sicherzustellen, dass diese Mobile, Mac und andere Clients weiterhin QoS-Behandlung (zumindest teilweise) relevanten Informationen erhalten.

Sie können Richtlinienbasierte QoS innerhalb der Gruppenrichtlinien verwenden, um den DSCP-Wert für den Portbereich vordefinierten Quelle im Client Teams festzulegen. Verwenden Sie die in Tabelle 3 angegebenen Portbereiche zum Erstellen einer Richtlinie für jeden Workload.

Nachdem Sie die Portbereiche identifiziert haben, besteht der nächste Schritt konfigurieren Sie die Richtlinienbasierte QoS-Einstellungen innerhalb eines Gruppenrichtlinienobjekts. Weitere Informationen zu diesen Schritten finden in [Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Clients auf Skype für Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10).

Zum Erstellen einer QoS-audio Richtlinie für Windows 10 Computer zuerst melden Sie sich an einem Computer, auf dem die Gruppenrichtlinien-Verwaltungskonsole installiert wurde. Öffnen Sie die Gruppenrichtlinien-Verwaltungskonsole (klicken Sie auf Start, zeigen Sie auf Verwaltung, und klicken Sie dann auf die Gruppenrichtlinien-Verwaltungskonsole), und führen Sie dann die folgenden Schritte aus:

1. Suchen Sie in der Gruppenrichtlinien-Verwaltungskonsole den Container, in dem die neue Richtlinie erstellt werden soll. Beispielsweise sollte alle Client-Computer in einer Organisationseinheit mit dem Namen **Clients**befinden, die neue Richtlinie in der Organisationseinheit Client erstellt werden.

2. Maustaste auf den entsprechenden Container, und klicken Sie dann auf **Erstellen Sie ein Gruppenrichtlinienobjekt in dieser Domäne, und Verknüpfen des Arbeitsbereichs hier**.

3. Klicken Sie im Dialogfeld **Neues Gruppenrichtlinienobjekt** Geben Sie im Feld **Name** einen Namen für das neue Gruppenrichtlinienobjekt ein, und klicken Sie dann auf **OK**.

4. Maustaste auf die neu erstellte Richtlinie, und klicken Sie dann auf **Bearbeiten**.

5. In den Gruppenrichtlinienverwaltungs-Editor, erweitern Sie **Computerkonfiguration**, erweitern Sie **Windows-Einstellungen**, mit der rechten Maustaste **Richtlinienbasierte QoS**, und klicken Sie dann auf **neue Richtlinie erstellen**.

6. Geben Sie im Dialogfeld **Richtlinienbasierte QoS** auf der ersten Seite einen Namen für die neue Richtlinie in das Feld **Name** ein. Wählen Sie die **DSCP-Wert angeben** , und legen Sie den Wert auf **46 fest**. Lassen Sie **Ausgehende Drosselungsrate angeben** deaktiviert, und klicken Sie dann auf **Weiter**.

7. Wählen Sie auf der nächsten Seite **nur Anwendungen mit diesem Namen ausführbare** und geben Sie den Namen **Teams.exe**, und klicken Sie dann auf **Weiter**. Diese Einstellung weist die Richtlinie nur übereinstimmenden Datenverkehr vom Client Teams priorisieren.

8. Stellen Sie auf der dritten Seite sicher, dass **alle Quell-IP-Adresse** und **einer beliebigen Ziel-IP-Adresse** ausgewählt sind, und klicken Sie dann auf **Weiter**. Diese zwei Einstellungen stellen Sie sicher, dass Pakete verwaltet werden unabhängig vom Computer (IP-Adresse), die die Pakete gesendet, und welchen Computern (IP-Adresse) wird die Pakete empfangen.

9. Wählen Sie auf Seite vier **TCP und UDP** aus der Dropdownliste **Wählen Sie das Protokoll, dem diese QoS-Richtlinie angewendet wird** . TCP (Transmission Control Protocol) und UDP (User Datagram Protocol) werden die am häufigsten verwendeten zwei Netzwerkprotokollen.

10. Wählen Sie unter der Überschrift **Geben Sie die Quellportnummer** **aus dieser Quellport oder der Bereich**. Geben Sie in das Textfeld zugehörige den Portbereich für audio Übertragungen reserviert. Angenommen, wenn Sie Ports 50000 über Ports 50019 für audio-Datenverkehr reserviert ist, geben Sie den Portbereich, der mit diesem Format: **50000:50019**. Klicken Sie auf **Fertig stellen**.

11. Wiederholen Sie die Schritte 5 bis 10, um Richtlinien für Video und Anwendung/Desktop freigeben, ersetzen die entsprechenden Werte in Schritt 6 und 10 zu erstellen.

Die neuen Richtlinien, die von die Ihnen erstellten werden nicht erst wirksam, Gruppenrichtlinien auf den Clientcomputern aktualisiert wurde. Obwohl Gruppenrichtlinien allein in regelmäßigen Abständen aktualisiert wurde, können Sie eine sofortige Aktualisierung erzwingen.

### <a name="force-group-policy-refresh"></a>Force Group Policy aktualisieren

1. Öffnen Sie auf jedem Computer, für die Sie die Gruppenrichtlinie aktualisieren möchten eine Befehlskonsole. Stellen Sie sicher, dass die Befehlskonsole festgelegt ist, als Administrator ausführen.

2. Geben Sie an der Befehlszeile
   ```
    gpupdate.exe /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>Überprüfen Sie die DSCP-Auswahlmöglichkeiten in das Gruppenrichtlinienobjekt

Führen Sie die folgenden Schritte aus, um zu überprüfen, dass die Werte aus dem Gruppenrichtlinienobjekt festgelegt wurden.

1. Öffnen Sie eine Befehlskonsole. Stellen Sie sicher, dass die Befehlskonsole festgelegt ist, als Administrator ausführen.

2. Geben Sie an der Befehlszeile 
   ```
   gpresult /R > gp.txt
   ```

   Dies einen Bericht generiert und in eine Textdatei mit dem Namen gp.txt zu senden. Alternativ können Sie den folgenden Befehl aus, um die gleichen Daten in einem besser lesbar HTML-Bericht mit dem Namen gp.html zu erzeugen eingeben:
   ```
   gpresult /H >gp.html
   ```
 ![Screenshot des Konsolenfenster des Befehls Gpresult.] (media/Qos-in-Teams-Image3.png "Screenshot des Konsolenfenster des Befehls Gpresult.")

3. Suchen Sie in der generierten Datei nach der Überschrift **Gruppenrichtlinienobjekte angewendet** , und stellen Sie sicher, dass die Namen der zuvor erstellten Gruppenrichtlinienobjekte in der Liste der Richtlinien angewendet werden. 

4. Öffnen Sie den Registrierungs-Editor, und wechseln Sie zu:

   HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\

   Überprüfen Sie die Werte für die in Tabelle 4 aufgeführten Registrierungseinträge.

   _In Tabelle 4. Werte für Windows-Registrierungseinträge für QoS_


   |          Name          |  Typ  |    Daten     |
   |------------------------|--------|-------------|
   |    Application Name    | REG_SZ |  Teams.exe  |
   |       DSCP Value       | REG_SZ |     46      |
   |        Local IP        | REG_SZ |     \*      |
   | Local IP Prefix Length | REG_SZ |     \*      |
   |       Local Port       | REG_SZ | 50000-50019 |
   |        Protokoll        | REG_SZ |     \*      |
   |       Remote IP        | REG_SZ |     \*      |
   |    Remote-IP-Präfix    | REG_SZ |     \*      |
   |      Remote Port       | REG_SZ |     \*      |
   |     Throttle Rate      | REG_SZ |     -1      |


5. Stellen Sie sicher, dass der Wert für den Anwendungsnamen-Eintrag für den Client korrekt ist, den Sie verwenden, und stellen Sie sicher, dass sowohl die DSCP-Wert und der lokalen Port Einträge die Einstellungen in das Gruppenrichtlinienobjekt aktualisiert.

## <a name="validate-qos-by-analyzing-teams-traffic-on-the-network"></a>Überprüfen von QoS durch Analysieren Teams Datenverkehr im Netzwerk

Für QoS wirksam werden, die DSCP durch das Gruppenrichtlinienobjekt festgelegter Wert müssen an beiden Enden eines Aufrufs vorhanden sein. Verfolgen Sie den Datenverkehr vom Client Teams generiert, stellen Sie sicher, dass der DSCP-Wert wird nicht geändert oder entfernt, wenn der Teams Arbeitslast Datenverkehr Verschiebungen durchläuft über das Netzwerk.

Vorzugsweise, erfassen Sie Datenverkehr am Netzwerk Austritt. Sie können Anschluss Spiegelung für eine Switch- oder Router um dabei zu unterstützen.

### <a name="use-network-monitor-to-verify-dscp-values"></a>Verwenden des Netzwerkmonitors DSCP-Werte überprüfen

Netzwerkmonitor ist ein Tool, um den Netzwerkverkehr zu analysieren [von Microsoft herunterladen](https://www.microsoft.com/download/4865) können.

1. Verbinden Sie auf dem PC Netzwerkmonitor ausgeführt wird auf den Port, der für die Spiegelung von Port und Erfassung von Paketen Start konfiguriert wurde. 

2. Tätigen eines Anrufs mit dem Teams. Stellen Sie sicher, dass Media hergestellt wurde, bevor der Anruf wird beendet. 

3. Beenden Sie die Aufzeichnung.

4. Klicken Sie im Feld **Anzeigefilter** verwenden Sie die Quell-IP-Adresse des Computers, der den Anruf getätigt hat, und verfeinern Sie den Filter, indem Sie definieren DSCP-Wert (hex-0xb8) 46 als Suchkriterien, wie im folgenden Beispiel dargestellt:

    Source == "192.168.137.201" AND IPv4.DifferentiatedServicesField == 0xb8 

    ![Screenshot des Dialogfelds in Microsoft Netzwerkmonitor mit Filter für Anzeigefilter.] (media/Qos-in-Teams-Image4.png "Screenshot des Dialogfelds in Microsoft Netzwerkmonitor mit Filter für Anzeigefilter.")

5. **Übernehmen** Sie den Filter aktivieren auswählen.

6. Wählen Sie im Fenster **Zusammenfassung Frame** das erste UDP-Paket aus.

7. In Frame im Dialogfeld **Details** der erweitern Sie das Listenelement IPv4, und notieren Sie den Wert am Ende der Zeile, die mit **DSCP**beginnt. 

    ![Screenshot des Frames im Dialogfeld Details der in Microsoft Netzwerkmonitor DSCP-Einstellungen der Hervorhebung.] (media/Qos-in-Teams-Image5.png "Screenshot des Frames im Dialogfeld Details der in Microsoft Netzwerkmonitor DSCP-Einstellungen der Hervorhebung.")

In diesem Beispiel wird der DSCP-Wert auf 46 festgelegt. Dies ist korrekt, da der verwendete Quellport 50019, ist gibt an, dass es sich um eine VoIP-Arbeitslast handelt. 

Wiederholen Sie die Überprüfung für alle Arbeitsauslastungen, die durch das GPO markiert wurden. 

## <a name="more-information"></a>Weitere Informationen

[Video: Netzwerkplanung](https://aka.ms/teams-networking)

[Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams](prepare-network.md)

[ExpressRoute QoS-Anforderungen](https://docs.microsoft.com/azure/expressroute/expressroute-qos)
