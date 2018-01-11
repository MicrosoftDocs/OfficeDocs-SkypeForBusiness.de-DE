---
title: "ExpressRoute und QoS in Skype für Unternehmen Online"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 20c654da-30ee-4e4f-a764-8b7d8844431d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "Informationen Sie zum Verwenden von Azure ExpressRoute ein Netzwerk mit bandbreitenanforderungen und Quality of Service-Funktionalität für eine geschäftsbenutzererfahrungen-Klasse. "
ms.openlocfilehash: 7073840031013d41013762b190ccdc568840cceb
ms.sourcegitcommit: 61127a5723fe58545b0b19edb2e2d4260965eb4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="expressroute-and-qos-in-skype-for-business-online"></a>ExpressRoute und QoS in Skype für Unternehmen Online

Verbinden Sie mit Office 365 über eine dedizierte Netzwerkverbindung von Azure ExpressRoute für Office 365 und Skype für Business Online. Die dedizierte Verbindung für Ihre Skype für Business apps erhalten verlässliche und vorhersehbare Leistung sowie Privacy Weg das öffentliche Internet Sie. Sie können nun eine bessere Netzwerkverbindung zu Office 365 und Skype für Business Online kaufen, die Vorhersagbarkeit Business höchste Zuverlässigkeit hinzugefügt und mit einer Betriebszeit SLA kommt.
  
> [!NOTE]
> Eine neue Version des Rechners Bandbreite verfügbar ist: [Skype für Unternehmen, Bandbreite Rechner](https://go.microsoft.com/fwlink/?LinkId=715766). Die Anweisungen in diesem Dokument werden jedoch die Lync 2010 und 2013 Bandbreite Rechner verwenden. 
  
## <a name="skype-for-business-online-and-expressroute"></a>Skype für Unternehmen Online und ExpressRoute

Arbeiten mit einem Microsoft ExpressRoute Partner, können Sie eine Vielzahl von Office 365-Anwendungen, einschließlich Skype für Business Online in der Cloud über eine dedizierte Verbindung herstellen. Der Real-Time Sprach- und Videokommunikation Funktionen für Skype für Unternehmen erfordern jedoch Netzwerkdienste, die speziell für die Unterstützung von diese Office 365 in Echtzeit Arbeitslasten konfiguriert sind. Dazu gehören ein Netzwerk mit ausreichend Bandbreite zum Ausführen der erforderlichen Umfang des Datenverkehrs und Quality of Service (QoS) zu einer Business-Klasse Erlebnis für Ihre Benutzer unterstützt werden.
  
Dieses Dokument dient Sie Administratoren und verstehen, die spezielle Probleme, die zur Unterstützung von Real-Time Communications, die Tools von Microsoft unterstützen Sie beim Entwerfen eines Netzwerks unterstützen die Netzwerkdesigner Anforderungen, und Sie den Entwurfsprozess anhand einer Fallstudie durchlaufen. 
  
Der erste Teil dieses Dokuments durchlaufen einer Fallstudie, die Sie mit dem Netzwerkentwurf mit dem [Lync 2010 und 2013 Bandbreite Rechner](https://go.microsoft.com/fwlink/?LinkId=690282) schätzen Sie die netzwerkanforderungen für eine große, mehrere Standorte Skype für Business ExpressRoute-Bereitstellung unterstützen. Im zweite Teil dieses Dokuments können Sie mit den grundlegenden Konzepten der Quality of Service (QoS), eine im-Detail für bestimmte technische Details zur Unterstützung von Skype für Real-Time Communications Business und der spezifischen Typen von Netzwerkdienste, die sind erforderlich.
  
Alle Informationen hier finden Sie technische Details und Verständnis für QoS und ExpressRoute, einen Überblick über die besondere Aspekte werden werden facing, und weisen Sie Kenntnisse der Tools und Techniken, die Sie zum erfolgreichen zulassen Bereitstellen einer ExpressRoute über Ihre Skype für Unternehmensnetzwerk. 
  
## <a name="getting-started"></a>Erste Schritte

Wenn Sie bereit für ExpressRoute für Skype für Unternehmen erhalten, ist es ratsam, sehen Sie sich die verschiedenen ExpressRoute Verbindung Modelle und die verschiedenen Wahl mit Partnern und Standorten und hier erhalten Sie Informationen zum erwerben und ExpressRoute in Ihrem Unternehmen bereitstellen. Hier sind einige Ressourcen für die ersten Schritte aus: 
  
- [Azure ExpressRoute]( https://go.microsoft.com/fwlink/?LinkId=690283)
    
- [ExpressRoute Preise](https://go.microsoft.com/fwlink/?LinkId=690284)
    
- [ExpressRoute-Dokumentation](https://go.microsoft.com/fwlink/?LinkId=690285)
    
## <a name="part-1-case-study---expressroute-for-dewey-law-llc"></a>Teil 1: Fallstudie - ExpressRoute für Dewey Law, LLC.

Diese Fallstudie für Dewey Law, LLC. Erfahren Sie, wie Sie Einrichten eines Netzwerks, Reihenfolge Network Access Services, und ermitteln Sie die bandbreitenanforderungen zur Unterstützung von ExpressRoute für Skype für Business Online.
  
 **Hintergrund** Dewy Recht LLC. eine große national Anwaltskanzlei mit 790 Anwälte und einem Gesamtabstand von 5,580 Mitarbeiter ist über 78 Standorte verteilt werden. Das Unternehmen verfügt über eine zentrale in New York, drei regionale Büros in Chicago, San Francisco (engl.) und Dallas, zusammen mit 24 große und 50 kleinen Zweigstellen, um das Land verteilt sind. Das Unternehmen behandelt komplexen Fälle der Arbeitslast, die in der Regel mindestens zwei Büros verteilt. Mit dieser Netzwerk-Design-Ergebnisse in einem beträchtliche Netzwerkverkehr zwischen den Büros.
  
Dewy Recht LLC. ist ein relativ kleines Unternehmen und die Anwälte und andere Mitarbeiter mit der Technologie sehr vertraut sind und erheblich hängen sie bei ihrer täglichen Arbeit. 
  
 **Verteilung von Benutzern von Standorten und Position**
  
||**Zentrale (Nynorsk)**|**Regionale Büros (3)**|**Große Zweigstellen (24)**|**Kleinen Zweigstellen (50)**|
|:-----|:-----|:-----|:-----|:-----|
|Führungskräfte  <br/> |20  <br/> |10  <br/> |1  <br/> |1  <br/> |
|Partner (engl.)  <br/> |150  <br/> |50  <br/> |10  <br/> |5  <br/> |
|Ordnet  <br/> |300  <br/> |100  <br/> |20  <br/> |10  <br/> |
|Paralegal  <br/> |400  <br/> |125  <br/> |30  <br/> |15  <br/> |
|Executive-admins  <br/> |100  <br/> |35  <br/> |6  <br/> |3  <br/> |
|IT und allgemeine Administrative  <br/> |100  <br/> |25  <br/> |3  <br/> |2  <br/> |
|Insgesamt pro Website  <br/> |1,070  <br/> |345  <br/> |70  <br/> |36  <br/> |
|Insgesamt pro Website-Klasse  <br/> |1,070  <br/> |1,035  <br/> |1,680  <br/> |1.800  <br/> |
   
### <a name="setting-up-the-network"></a>Einrichten des Netzwerks

Um konsistent und qualitativ hochwertige Real-Time Services für Dewey Law LLC. zu übermitteln, sind einige Grundlagen Anforderungen, die erfüllt sein müssen:
  
- Sie möchten während Stromausfall VoIP-Dienste bereitstellen, damit ihre Verteilung Netzwerkswitches und Router Power over Ethernet (PoE) IEEE 802.3af oder 802.3at angeben müssen.
    
- Die Netzwerk-Switches und Router müssen Sie auch unterbrechungsfreie Stromversorgung (USV) verwenden, damit sie weiterhin können wegen eines Stromausfalls Betrieb.
    
    Sie müssen eine Wi-Fi-Verbindungen ihre Büros LAN, sodass es wird dringend empfohlen, mit denen sie eine zertifizierten Skype für Business Wi-Fi-Infrastruktur Partner von [Skype für Business Solutions](https://go.microsoft.com/fwlink/?LinkId=690281).
    
    > [!TIP]
    >  802. 11n und 802.11ac drahtlosen Zugriffspunkte werden empfohlen.
  
- Und vor allem alle LAN Netzwerke in allen Büros muss eingerichtet sein Quality of Service (QoS) bereitstellen. Dazu gehören PCs, Notebooks und Netzwerkhardware wie Switches und Router.
    
Nun, da Sie die Grundlagen behandelt haben, sollten zur Erbringung geschäftlicher Note VoIP Services für Dewey Law LLC. Multi-Protocol Label wechseln (MPLS) IP-Service von einem Netzwerk Servicepartner, der mit dem Azure ExpressRoute-Dienst hergestellt wird. MPLS bietet einen IP mit Leistung Garantien für Verzögerungen, Jitter und Paketverlust. Aber wenn MPLS nicht verfügbar ist, verbunden Ethernet eines unsere ExpressRoute Daten Exchange Partner auch verwendet werden können.
  
MPLS-Anbieter bieten verschiedene Servicelevel-Klasse, aber jede verwenden unterschiedliche Begriffe identifizieren. Sie müssen arbeiten eng mit Ihrem Anbieter um sicherzustellen, dass sie die Daten verstehen, die Sie in [Lync 2010 und 2013 Bandbreite Rechner](https://go.microsoft.com/fwlink/?LinkID=690282) und die verfügbaren Optionen eingegeben haben, und werden empfohlen, für die verschiedenen Office 365 Arbeitslast in Echtzeit zu Applications.
  
Es gibt zwei Optionen für die wie Daten von Skype für Geschäftsanwendungen in die entsprechenden MPLS-Klassen des Diensts zugeordnet werden können:
  
- Endpunkt-Kennzeichnung des Datenverkehrs mit DiffServ Steuerelement Point (DSCP)
    
- Netzwerk Zugriffssteuerungsliste (ACL) basierte
    
Zum Implementieren der Endpunkt zu kennzeichnen, müssen Sie alle Domäne beitreten Windows-Computern für Dewey Recht LLC konfigurieren. Markieren jedes Paket mit der entsprechenden DiffServ Steuerelement Point (DSCP) Kennzeichnung und implementieren Sie QoS auf allen Netzwerk-Switches und Router in allen ihrer Office-Websites, um sicherzustellen, dass der QoS Auswahlmöglichkeiten verwaltet werden und werden nicht entfernt. DSCP Auswahlmöglichkeiten auf Netzwerkpakete Teilen Sie den Dienstanbieter wie des Netzwerkpakets priorisiert ist. **Weitere Informationen zu DSCP im Abschnitt QoS in Teil 2 ist vorhanden.**
  
Für Netzwerk ACL-basierte Zuordnung die DSCP Priorität Auswahlmöglichkeiten an einem Upstream-Router implementiert werden und basieren auf der Quelle UDP-Port. Die empfohlene Portbereiche für jede Anwendung werden im Abschnitt 2.6.1.1 der [Netzwerk-Planung, Überwachung und Problembehandlung von Lync Server](https://go.microsoft.com/fwlink/?LinkId=690286)aufgelistet. Es ist wichtig, dass Sie dies mit QoS-Implementierung und das Design Dewey Recht LLC Koordinierung des Projekts, und achten verschiedene QoS-Richtlinien und dem Potenzial für die Markierung Konflikte Paket.
  
Jeder ExpressRoute Netzwerk-Dienstanbieter müssen Service (QoS) eine Klasse, die für in Echtzeit Sprach- und Videofunktionen geeignet ist. Diese COS wird 'Expedited Forwarding' (EF) für Sprach- und 'Assured Forwarding' (AF) für Video aufgerufen. Achten Sie sehr in Größe Bandbreite, die Sie für VoIP EF Datenverkehr erwerben. Der Grund dafür besteht, dass die VoIP-Klasse des Diensts sehr fehleranfällig ist, im Ereignisprotokoll Sie senden weitere VoIP-Datenverkehr als die Dienstklasse für eingerichtet ist.
  
> [!TIP]
>  Datenverkehr, der auf der VoIP-Klasse des Diensts mehr als Verpflichtung des Dienstanbieters gesendet wird wird sofort die Sprachqualität Effekt anweisen wird verworfen.
  
Wenn der Gesamtentwurf für Dewey Recht LLC betrachten. Es ist wichtig, dass Sie genau die Menge der Netzwerkbandbreite bestimmen, die sie benötigen, zur Unterstützung von VoIP-Datenverkehr über das Netzwerk und werden durch die Markierung jedes VoIP-Paket (und nur VoIP-Pakete) mit der Einstellung DSCP für VoIP (d. h. DSCP EF 46).
  
Zum Implementieren der QoS in ihren Unternehmen Netzwerk, die Endpunkte oder Router muss jedes Paket mit den entsprechenden Layer 3 Priorität Indikator (d. h., DSCP) markieren. Entlang des Pfads gesamte Netzwerk muss alle Switch und Router die QoS-Option aktiviert haben. Müssen auch nur ein Netzwerk-Switch oder dem Router, für das QoS aktiviert ist, entfernt die QoS Auswahlmöglichkeiten für Sprach- oder Videokonferenz Pakete passieren, Switch- oder Router werden konnte. Dadurch wird effektiv QoS in alle downstream Switches und Router, die die Vorteile der Nutzung ExpressRoute beeinträchtigt wird deaktiviert.
  
Dies erfordert auch, dass die Zuordnung der Layer 3 und der Ebene 2 QoS-Prioritäten zu jedem Zeitpunkt definiert werden. Die Ebene 2 Priorität Mechanismen werden in IEEE 802. 1p für verdrahtete Netzwerke und 802.11e definiert / WMM für Wi-Fi-Netzwerke. Netzwerk-Routers mit dem Netzwerk des Dienstanbieters MPLS-Netzwerk wichtiger ist, muss die DSCP-Einstellungen für alle ausgehenden Pakete verwaltet werden, damit sie die entsprechende MPLS-Klasse des Diensts bewahren. 
  
> [!TIP]
>  Die Details zu im Zusammenhang mit QoS-Einrichtung finden Sie im Abschnitt 2,6 [Netzwerkplanung, Überwachung und Problembehandlung von Lync Server]( https://go.microsoft.com/fwlink/?LinkId=760669). Sie können auch für weitere Netzwerk planungsanforderungen [netzwerkanforderungen für die Skype für Business 2015 planen](https://go.microsoft.com/fwlink/?LinkId=690287) sehen.
  
### <a name="ordering-network-access-services"></a>Sortierung Network Access Services

Nachdem Sie die QoS-Netzwerk erforderlichen Komponenten und Mechanismen zur Unterstützung von ExpressRoute verfügen, besteht der nächste Schritt für die ExpressRoute Network Access Services bestellen. Bei Bestellung ExpressRoute Access Services für Dewey Recht LLC über das Microsoft Network Services Anbieter Partner benötigen Sie zwei Dinge bereitstellen:
  
- Die Gesamtgröße der Bandbreite, die zum Verbinden von jedem Standort mit ExpressRoute und Office 365 erforderlich.
    
- Das erforderliche Gesamtbandbreite in für jede Klasse des Diensts, die erforderlich sind, um Skype für Geschäfts-apps zu unterstützen, die unter Dewey Recht LLC verwendet werden. Die Klasse der Dienst bandbreitenanforderung wird gesteuert, die von der Umfang des Datenverkehrs Sie erwarten von jedem der verschiedenen Skype für Geschäftsanwendungen wie VoIP, video, Sofortnachrichten, Anwesenheit und Bildschirmfreigabe.
    
### <a name="determining-bandwidth-requirements-for-skype-for-business-applications"></a>Bestimmen der Bandbreitenanforderungen für Skype für Geschäftsanwendungen

Für Dewey Law LLC. nachdem Sie die erforderliche Gesamtbandbreite bestimmt haben müssen Sie nun wissen, wie Gesamtbetrag Bandbreite in den verschiedenen Klassen des Diensts aufgeteilt werden soll. Angenommen, wie viel Bandbreite für jede Skype für Business-Anwendung.
  
Um diese Anforderungen an jedem der Dewey Recht LLC zu bestimmen. Websites, verwenden Sie die [Lync 2010 und 2013 Bandbreite Rechner](https://go.microsoft.com/fwlink/?LinkID=690282). Mit diesem Rechner ist ein Excel-basiertes Programm, das Sie die erwartete Verwendung von den verschiedenen Skype für Geschäftsanwendungen, einschließlich Sprache, Video, Konferenzen und Bildschirmfreigabe angeben kann. Der Rechner generiert automatisch eine Schätzung der Bandbreite und CoS Anforderungen für jeden Standort in ihrem Netzwerk. Wenn Sie die Lync 2010 und 2013 Bandbreite Rechner herunterladen, wird ein Benutzerhandbuch auch die Details zur Verwendung übergeben wird heruntergeladen werden. 
  
Damit Sie mit der Kalkulationstabelle gewährleistet ist, sind die verschiedenen Zellen in der Kalkulationstabelle farbcodierten:
  
- **Grün** Dies sind die allgemeinen Daten input Bereiche.
    
- **Gelb** Diese werden input Datenbereich erweitert. Sie können diese ändern, aber sorgfältig tun.
    
- **Rot** Diese werden schreibgeschützte Bereiche und sind gesperrte Eingabewerten und können nicht geändert werden.
    
- **Grau** Hierbei handelt es sich um reine Bereiche. Sie sind die Ergebnisse oder Daten, die aus den allgemeinen input Bereichen.
    
Den Entwurfsprozess für Dewey Recht LLC. zunächst erstellt die Benutzer in unterschiedlichen "Rollen". Für jede Rolle, die Sie definieren, können Sie ihre erwartete Verwendung von den verschiedenen Skype für Geschäftsanwendungen ("None", "Niedrig", "Mittel", 'Hoch' oder eine der drei definierte 'Benutzerdefiniert' Einstellungen) angeben. Diese Optionen befinden sich im Arbeitsblatt 'Persona'. Die Verwendung für jede Auswahl ('Niedrig', ' Mittel' oder 'Hoch') bereitgestellt, aber die Standardeinstellungen für jede Auswahl geändert werden können. Durch die Ermittlung der Anzahl der Benutzer für jede Rolle, die an den einzelnen Standorten gespeichert ist, kann der Rechner die für jeden Standort erforderliche Gesamtbandbreite berechnen.
  
Sie können auch angeben, die Audio- und video-Codecs, die verwendet werden, ob vorwärtsfehlerkorrektur verwendet wird und auch andere Systemparameter, die erforderliche Netzwerkbandbreite auswirkt. Sie verwenden die Standardeinstellungen in der Lync 2010 und 2013 Bandbreite Rechner oder anderen Codecs und andere Systemparameter auswählen. Für Dewey Recht LLC Website entwerfen können die Standardeinstellungen verwendet werden. Zum Ändern eines Standard Settings es ist jedoch ein Dropdownmenü mit allen verfügbaren Optionen. Die Bandbreiten, die für jede Auswahl verwendet werden, sind im Arbeitsblatt "Codecs" enthalten. Wenn Sie ändern (CoS) Mix an jedem Standort aktualisiert wird eine beliebige Einstellung, die Änderung Bandbreite und Klasse des Diensts. Mit dieser Funktion können Sie testen verschiedene potenzielle Konfigurationen für diese und überprüfen die Auswirkungen die Änderungen auf bandbreitenanforderungen für diese haben.
  
Wir haben drei Rollen ' Executive/Partner', ' Zuordnen/Paralegal' und "IT Admins" für Dewey Law LLC. definiert. Die nachstehende Tabelle zeigt, wie wir die Verwendungsprofile für die verschiedenen Skype für Geschäfts-apps für jede Rolle festgelegt haben.
  
 **Rollen und Verwendungsprofile ('Persona' Arbeitsblatt - Spalten A bis P)**
  
|**Rolle**|**Sofortnachrichten/Anwesenheitsinformationen**|**P2P-audio**|**P2P-video**|**Audiokonferenzen**|**Video Conferencing**|**Desktopfreigabe**|**Audiokonferenzen**|**Lync 2010 RTV_Type**|**Remotebenutzer**|**Lync 2013 Stereo-audio**|**Lync 2013 Videoqualität**|**Lync 2013 Benutzer Verhalten für P2P Videofenster**|**Verwendung von Lync 2013 mit mehreren Ansichten**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Executive / Partner  <br/> |Hoch  <br/> |Mittel  <br/> |Niedrig  <br/> |Mittel  <br/> |Mittel  <br/> |Keine  <br/> |Mittel  <br/> |CIF  <br/> |0%  <br/> |0%  <br/> |Am besten  <br/> |Typische  <br/> |Typische  <br/> |
|Zuordnen / Paralegal  <br/> |Hoch  <br/> |Mittel  <br/> |Niedrig  <br/> |Mittel  <br/> |Hoch  <br/> |Hoch  <br/> |Mittel  <br/> |CIF  <br/> |0%  <br/> |0%  <br/> |Mittel  <br/> |Typische  <br/> |Typische  <br/> |
|IT-Administratoren  <br/> |Hoch  <br/> |Mittel  <br/> |Keine  <br/> |Niedrig  <br/> |Keine   <br/> |Keine  <br/> |Mittel  <br/> |CIF  <br/> |0%  <br/> |0%  <br/> |Mittel  <br/> |Typische  <br/> |Typische  <br/> |
   
Sie müssen die Informationen in der Tabelle **Verteilung von Benutzern von Standorten und Position** oben im Arbeitsblatt "Websites" von der Lync 2010 und 2013 Bandbreite Rechner eingeben. Die Anzahl der Benutzer in den regionalen Büros identisch ist, werden sie für einen "Standort" definiert und angegeben, dass es drei Instanzen des wurden. Die gleichen für großen und kleinen Zweigstellen durchgeführt wurde, in denen wurden 24 und 50 Benutzer jeweils in Websites.
  
Nach dem Festlegen der Einstellungen für jede Rolle, müssen Sie die Anzahl der Benutzer in den einzelnen Rollen an jedem Standort im Arbeitsblatt "Websites" eingeben. Die Gesamtzahl Benutzer für alle Websites wird automatisch aktualisiert. Da Benutzer nicht an der Position von Office 365, sollten sie alle in den Zeilen "In den Zweigstellen" des Arbeitsblatts eingegeben werden. Die Lync 2010 und 2013 Bandbreite Rechner füllt dann die "Best-Effort-Klasse", "Daten Datenverkehr-Klasse" und "Datenverkehr in Echtzeit-Klasse" Spalten in der Tabelle 'WAN BW pro QoS-Datenverkehrsklasse'. Dies ist in den Daten in der folgenden Tabelle dargestellt.
  
> [!TIP]
>  Die vollständige Kalkulationstabelle enthält außerdem die maximale Anzahl von gleichzeitigen Sitzungen für jede Anwendung, aber wir diese Spalten, um Speicherplatz einzusparen gelöscht.
  
 **Rollen von Website - ("Websites" Arbeitsblatt - Spalten A, D, ich und AI über AX)**
  
|**Websitename**|**Gesamtzahl von Benutzern in der Website**|**Insgesamt Websites wie folgt**|**Benutzerprofil 1**|**Benutzer von Profil 1**|**Benutzerprofil 2**|**Benutzer des Profils 2**|**Benutzerprofil 3**|**Benutzer des Profils 3**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Zentrale  <br/> |1070  <br/> |1  <br/> |Executive-Partner  <br/> |170  <br/> |Zuordnen/Paralegal  <br/> |700  <br/> |IT-Administratoren  <br/> |200  <br/> |
|Regionale Büros  <br/> |345  <br/> |3  <br/> |Executive-Partner  <br/> |60  <br/> |Zuordnen/Paralegal  <br/> |225  <br/> |IT-Administrator  <br/> |60  <br/> |
|Große Zweigstellen  <br/> |70  <br/> |24  <br/> |Executive-Partner  <br/> |11  <br/> |Zuordnen/Paralegal  <br/> |50  <br/> |IT-Administrator  <br/> |9  <br/> |
|Kleinen Zweigstellen  <br/> |36  <br/> |50  <br/> |Executive-Partner  <br/> |6  <br/> |Zuordnen/Paralegal  <br/> |25  <br/> |IT-Administrator  <br/> |1  <br/> |
   
 **Bandbreite pro Anwendung nach Standort in Kbit/s ('Websites Arbeitsblatt'-Spalten A und BQ über LF)**
  
|**Website**|**Spitzen SIP / Instant Messaging-Bandbreite**|**Maximale standortübergreifende Peer-Audio-Bandbreite**|**Maximale standortübergreifende Peer-Video-Bandbreite**|**Maximale Audiokonferenzen Bandbreite**|**Peak-Video-Konferenzen Bandbreite**|**Maximale freigeben WAN-Bandbreite**|**Maximale WAN-Bandbreite für PSTN-Anrufe**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Zentrale  <br/> |1070  <br/> |525.30  <br/> |560.00  <br/> |739.50  <br/> |2640.00  <br/> |4224.00  <br/> |2688.30  <br/> |
|Regionale Büros  <br/> |345  <br/> |185.40  <br/> |560.00  <br/> |255.00  <br/> |1320.00  <br/> |1536.00  <br/> |896.10  <br/> |
|Große in den Zweigstellen  <br/> |70  <br/> |92.70  <br/> |560.00  <br/> |102.00  <br/> |600,00  <br/> |384.00  <br/> |216.30  <br/> |
|Kleine in den Zweigstellen  <br/> |36  <br/> |119.40  <br/> |560.00  <br/> |76.50  <br/> |600,00  <br/> |384.00  <br/> |123.60  <br/> |
   
Wahrscheinlich sind die wichtigsten Spalten in der Kalkulationstabelle für die WAN-Bandbreite von QoS-Klasse beschreiben. Dies ist in der folgenden Tabelle dargestellt. Diese Daten sind die Informationen, die Sie benötigen, um mit dem Netzwerk-Dienstanbieter, die Access-Verbindung an jedem Standort bestellen bereitzustellen zusammengefasst. Bei der Berechnung Gesamtbandbreite Bitte beachten Sie die Bandbreite für jede Art von Zweigniederlassungen, um die Anzahl von Websites des gleichen Typs multipliziert werden soll. Zum Verbinden mit Ihrem ExpressRoute Netzwerk Services Partner können Sie [Azure ExpressRoute]( https://go.microsoft.com/fwlink/?LinkId=690283)finden Sie unter.
  
Es ist sehr wichtig, dass Sie die Bandbreite in das Voice- oder Dienstklasse 'Expedited Forwarding' (EF) nicht überschreiten. Eine zufällige Reihe von Pakete verworfen also statt verringern die Qualität der einen einzigen Anruf oder eine Gruppe von Anrufen, alle Aufrufe in Bearbeitung kann beeinträchtigt werden. Außerdem ist es wichtig, dass nur VoIP mit dem DSCP für EF gekennzeichnet werden (d. h. DSCP 46 =) oder die VoIP-Warteschlange konnte Überlauf, wenn der nicht-Sprachdatenverkehr hinzugefügt wird.
  
> [!TIP]
>  Erneut, während die EF-Klasse des Diensts die beste Leistung Garantie bietet, wenn Sie die definierte Bandbreite überschreiten, werden alle zusätzlichen Pakete sofort verworfen.
  
 **Aggregierte Bandbreite pro Website von QoS-Datenverkehrsklasse - ("Websites" Arbeitsblatt Spalten A und ML über MR)**
  
|**Websitename**|**Best Effort-Klasse (DSCP 0)**|**Daten (benutzerdefinierte DSCP) Datenverkehr-Klasse**|**Datenverkehr in Echtzeit-Klasse (DSCP 34, AF41)**|**Priorität Datenverkehr Class (DSCP 46, Expedited FORWARDING)**|
|:-----|:-----|:-----|:-----|:-----|
|Zentrale  <br/> |0,00  <br/> |5764.80  <br/> |3200.00  <br/> |3953.10  <br/> |
|Regionale Büros  <br/> |0,00  <br/> |2033.60  <br/> |1880.00  <br/> |1336.50  <br/> |
|Große in den Zweigstellen  <br/> |0,00  <br/> |486.40  <br/> |1160.00  <br/> |411.00  <br/> |
|Kleine in den Zweigstellen  <br/> |0,00  <br/> |438.40  <br/> |1160.00  <br/> |319.50  <br/> |
   
### <a name="putting-your-plan-into-action"></a>Aktion Inbetriebnahme des Plans

Wir die gesamte Bandbreite berechnen können, die durchlaufen werden, das WAN und Bandbreite, die ExpressRoute durchlaufen wird, schätzt aus der Tabelle **pro Anwendung pro Website** oben Nutzung der Bandbreite. Der Teil-Datenverkehr, der ExpressRoute durchläuft schließt die standortübergreifende Peer Bandbreite.

 
|**Website**|**Spitzen SIP / Instant Messaging-Bandbreite**|**Maximale Audiokonferenzen Bandbreite**|**Peak-Video-Konferenzen Bandbreite**|**Maximale freigeben WAN-Bandbreite**|**Maximale WAN-Bandbreite für PSTN-Anrufe**|**Insgesamt ExpressRoute<br/>Datenverkehr pro Website Klasse<br/>(d. h. insgesamt<br/>Zeit # Websites)**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**Zentrale** <br/> |1,070  <br/> |739.50  <br/> |2640.00  <br/> |4224.00  <br/> |2688.30  <br/> |11361.80  <br/> |
|**Regionale Büros** <br/> |345  <br/> |255.00  <br/> |1320.00  <br/> |1536.00  <br/> |896.10  <br/> |8704.20  <br/> |
|**Große in den Zweigstellen** <br/> |70  <br/> |102.00  <br/> |600,00  <br/> |384.00  <br/> |216.30  <br/> |32935.20  <br/> |
|**Kleine in den Zweigstellen** <br/> |36  <br/> |76.50  <br/> |600,00  <br/> |384.00  <br/> |123.60  <br/> |61005.00  <br/> |
   
Dies bedeutet, dass Skype für Business Online-Datenverkehr der durchlaufen die express Route wird ungefähr 114 Mbit/s werden, damit Dewey mindestens 200 Mbit/s-Abonnement für ExpressRoute benötigen. Mehrere ExpressRoute Circuits können an unterschiedlichen ExpressRoute Peers Standorten erworben werden. Dies konnte empfohlen werden, wenn Dewey Websites sind in unterschiedlichen geografischen Regionen oder Resiliency bereitzustellen, falls bei der Verbindung mit der Netzfrequenz ExpressRoute fehlschlägt. Wenn Sie ExpressRoute Circuits mehrere Azure Regionen erworben haben, wird das ExpressRoute Premium Add-on müssen globale Konnektivität über ExpressRoute empfangen.
  
Nun, Sie die Gesamtmenge des erforderliche Bandbreite und Dienstklasse (CoS haben) service Bandbreite Zahlen Sie Ihre Aufträge mit dem ausgewählten Netzwerk tätigen können Anbieter. Vergessen Sie nicht Schätzungen für Datenverkehr für andere Anwendungen und Dienste eingeschlossen. Wir bieten planungsanleitung für andere Office 365-Dienste, einschließlich bandbreitenrechnern für Exchange und OneDrive Netzwerk. Bandbreite Abonnement für die Netzwerk-Dienstanbieter wird höher sein, da Standorts Datenverkehr wieder hinzugefügt werden muss. Die Lync 2010 und 2013 Bandbreite Rechner enthält nur eine Schätzung der den erwarteten Datenverkehr, daher wird empfohlen, im Netzwerk Fähigkeit zur Unterstützung von diesem Volumes Durchführen eines Leistungstests Verkehr bestätigen. 
  
> [!TIP]
> Belastungstests Ihr Netzwerk wird dringend empfohlen Wenn Sie eine Netzwerk vor Bewertung durchgeführt werden. 
  
Ein Leistungstests umfasst das Erstellen und Konfigurieren der Infrastruktur, und klicken Sie dann mit der erwarteten Menge der simulierter Datenverkehr bei der Überwachung der Leistung ausgeführt. Die geschätzten Datenverkehr möglicherweise in einigen Bereichen unrichtige, aber mindestens Sie sicher, dass es unterstützen der Umfang des Datenverkehrs der Lync 2010 und 2013 Bandbreite Rechner vorhergesagt werden können. Es wird empfohlen, dass Sie der Leistungstests für mindestens einen Moment ausführen, aber für längere Zeit ausführen, helfen Ihnen bei Nummern zu optimieren. Allerdings muss Verlängerung des Zeitraums Belastungstests gegen die Kosten für die Netzwerkdienste, denen Sie für bezahlen abgewogen werden, die echte Benutzer Netzwerkdatenverkehr befördern sind nicht. Microsoft zertifiziert eine Anzahl von Anbietern im Rahmen seines Programms IT Pro-Tools, Verwaltung und Vorgänge Netzwerktools einschließlich vor Assessment Stress Netzwerktools bereitzustellen. Skype für Unternehmen bietet auch ein System Systemintegratoren (SI), die die zertifizierten IT Pro-Tools dauert und Möglichkeiten, die das Netzwerk Assessment für Sie. Weitere Informationen finden Sie unter [Skype für Business Solutions: IT Pro Tools](https://go.microsoft.com/fwlink/?LinkID=690307).
  
Belastungstests enthält einige sein können, dass das Netzwerk unterstützen die Datenvolumen, die benötigt werden, aber in der Realität der Lync 2010 und 2013 Bandbreite Rechner Daten für eine beliebige Anzahl von Gründe deaktiviert sind. Sie sollten auch Überwachung des Netzwerks Websites durch Ausführen eine laufenden Bewertung, sobald sie bereitgestellt wird, um die Bandbreite sicherzustellen ist ausreichend und, die die QoS-Mechanismen ordnungsgemäß arbeiten. Es ist wichtig, um den Vorgang fortzusetzen, Überwachung der Leistung des Netzwerks, wie mehr echte Benutzer online sind.
  
## <a name="part-2-expressroute-skype-for-business-qos"></a>Teil 2: ExpressRoute Skype für Business QoS

Microsofts ExpressRoute Service bietet eine dedizierte Verbindung mit der Azure-Cloud, aber Office 365 Echtzeit Arbeitslast Kommunikationsdienste erfordern die Netzwerkdienste mit ausreichend Bandbreite, der Umfang des Datenverkehrs auszuführen und unterstützen Erleben Sie die Dienstqualität (QoS) Note Geschäftsbenutzer übermitteln. Eine QoS sein muss, kann Verbindung konfiguriert End-to-End (PC, Netzwerk-Switches und Router in die Cloud) an, wie ein Teil in den Pfad, der ein Fehler, zur Unterstützung von QoS auftritt die Qualität der gesamten Kommunikation beeinträchtigt werden könnte.
  
Der Zweck dieses Abschnitts werden die Probleme bei der Unterstützung von Datenverkehr in Echtzeit in einem IP-Netzwerk und Konfiguration und Unterstützung für eine erfolgreiche ExpressRoute Bereitstellung von Office 365 Echtzeit Arbeitslasten mit einer Microsofts ExpressRoute Exchange Verständnis der Partner-Anbieter oder Netzwerk-Dienstanbieter.
  
QoS wird ausschließlich über ExpressRoute Netzwerk Circuits aus Ihren Netzwerken akzeptiert und für Skype innerhalb des Netzwerks Microsoft für Business-Datenverkehr verwendet. Heute haben Teile des einige ausgehenden Verbindungen von Microsoft fehlende DSCP-Werte für Skype für Unternehmen. Bis ausgehender Datenverkehr vollständig mit DSCP-Werte gekennzeichnet ist, werden Sie aufgefordert, befolgen die Richtlinien für das Hinzufügen von QoS Auswahlmöglichkeiten Datenverkehr an der Netzwerkgrenze wie im Abschnitt **Implementieren QoS mit Netzwerk Zugriffssteuerungsliste (ACL)** dieses beschrieben Artikel.
  
### <a name="the-real-time-problem"></a>Der Echtzeit-problem

Bereitstellung von Business Qualität der Sprach- und Videofunktionen Diensten platziert spezielle optimierte in einem IP-Netzwerk. Real-Time-Datenverkehr verwendet Real-Time Transport Protocol (RTP), die mit User Datagram Protocol (UDP) ausgeführt wird. Im Gegensatz zu Protokoll TCP (Transmission Control), die Zahlen und jede Nachricht auf Fehler überprüft und andere Mechanismen zum Erkennen und sind fehlen oder falsch empfangene Nachrichten enthält, zur nicht für dieses Typs Zuverlässigkeit UDP Verfügung. Nachrichten werden durch Fehler beschädigt oder aufgrund von Pufferüberläufe gehen verloren, werden sie verloren. UDP wurde für die Verwendung mit RTP ausgewählt wurde, da die Art des Datenverkehrs in Echtzeit besteht darin, dass auch wenn die verlorenen Nachrichten gesendet wurden, ganz so spät Ankunft würde, um eine beliebige positive Auswirkung auf den Ablauf des Sprachnachricht haben.
  
Kennen die Auswirkungen der verlorenen Voice-Paketen, Lieferumfang Designern von zwei Ansätze zur Verbesserung der Leistung von Sprach- und Videodaten über IP:
  
- Stellen Sie die Codierung/Decodierung weitere VoIP ausfallsichere, wenn Pakete verloren. Dies kann entweder durch mit vorwärtsfehlerkorrektur (Correction, FEC) an den richtigen Prozentsatz der aufgetretenen Fehler die ist eine Funktion in Office 365 Real Time Transport oder von Entwerfen von VoIP-Systeme, die versuchen, den Effekt verlorenen Paketen maskieren Decodierung gefunden, ist ein Merkmal des Microsoft-Codecs. 
    
- Verwenden Sie-Transport-Dienste, die Qualität der Dienst Mechanismen verwenden, um die Leistung im Hinblick auf die Verzögerung, Paketverlust und Jitter und die Variation Verzögerung zwischen Pakete im Netzwerk zu gewährleisten.
    
Ausfallsichere VoIP codieren beschäftigt sich nur Paketverlust, damit es wichtig ist, dass ein Netzwerk verwendet, in Echtzeit VoIP auszuführen und Video Mechanismen, die Verzögerung und Jitter minimieren. Wenn zu viele Pakete verloren, muss auch mit ausfallsichere codieren, nicht die empfangende Station ausreichend Informationen zum Wiederherstellen einer erkennbaren Version des Signals VoIP. Der Prozentsatz der verlorenen Pakete, die eine bedeutende Verschlechterung Sprachqualität führen würde die variiert je nach der VoIP-Codierung Technik, die verwendet wird. In allen Fällen ist jedoch, dass Zeichenfolgen der aufeinander folgende Pakete verloren gehen sehr problematisch.
  
Minimieren der Verzögerung ist wichtig, da übermäßige Verzögerung den Ablauf der Unterhaltung auswirken und eine Belästigung für Lautsprecher erstellen kann. Bewährte Methoden Teilen Sie uns, die End-to-End-Verzögerung für VoIP (was wir als 'Mund Ohr' Verzögerung bezeichnen) unter 150 Millisekunden (ms) aufbewahrt werden muss. unidirektionale, nicht 'round-Trip' Verzögerung. Natürlich erhöht die Verzögerung auf länger Übertragung Links wie die, die über auf verschiedenen Kontinenten, erhält die Verteilung Verzögerung oder der Zeitaufwand für das Signal physisch über das Kabel Reisen wechseln.
  
Wenn die Verzögerung höher ist als 150 ms wechselt. unidirektionale, er hat eine ungewöhnliche Auswirkung des Lautsprechers. Psychologically, geht in den Lautsprecher Brain, die sie der Meinung, dass der Empfänger noch nicht sie hören und sie wiederholt das letzte, was, das Sie sagten, macht eine Uhr deaktiviert ein. Dies hat einen Konflikt mit der verzögerten Antwort, die von der äußersten Ende. Wenn Sie jemals über einen Satelliten Kanal gesprochen haben, werden Sie dieser Effekt erkennen. Über einen Satelliten Kanal ist die unidirektionale Verzögerung ungefähr 250 MS; die weit über die zulässige Verzögerung ist.
  
 **Empfohlene Netzwerkparameter für Business Note-VoIP**
  
|**Parameter**|**Empfohlene Wert**|
|:-----|:-----|
|Inter hinzukommen Paket Jitter (Durchschnitt)  <br/> |≤ 5 MS  <br/> |
|Inter hinzukommen Paket Jitter (Maximum)  <br/> |≤ 40MS  <br/> |
|Paketverlustrate (Durchschnitt)  <br/> |0 % bald ausgeschöpft  <br/> |
|Netzwerklatenz unidirektional  <br/> |≤ 100 ms (sollte auf Verzögerung im Vergleich zu geografische Entfernung Überprüfungen enthalten)  <br/> |
   
### <a name="expressroute-as-part-of-a-business-grade-voice-network"></a>ExpressRoute als Teil einer Business Note VoIP-Netzwerk

ExpressRoute bietet eine dedizierte Verbindung über ein Netzwerk Service Provider (NSP) oder ein Exchange-Anbieter (EXP) in einem der 3 Verbindungsoptionen: 
  
- Cloud Exchange Colocation
    
- Point-Ethernet-Verbindung
    
- N: N-(IPVPN) Verbindung
    
Dadurch wird die Vorteile von hoher Verfügbarkeit (99,9 % Betriebszeit SLA) und (keine Internet während der Übertragung), d. h. verlässliche routing Sichern von Variationen in Internet-Datenverkehr und Hinsicht Quality of Service Auswahlmöglichkeiten für die Priorisierung von Datenverkehr (QoS wird unten erläutert) nicht betroffen . ExpressRoute, zusammen mit einem durchdachte WAN können Sie mit einem Business Note VoIP-Netzwerk bereitstellen.
  
Sie können ExpressRoute für während der Datenübertragung von Büros oder Rechenzentren verwenden (wenn hybridtopologie), die mit der Netzfrequenz verbunden sind. Daten für externe Benutzer (z. B. von Büros zu Hause oder unterwegs usw.) werden nicht der Netzfrequenz ExpressRoute nutzen, es sei denn, die Benutzer sind VPN-Verbindung, und müssen nicht in Bandbreite Einschätzung zum Anpassen der Netzfrequenz ExpressRoute enthalten sein. Wenn Sie einen multinationale Kunden sind, können Sie ExpressRoute Stromkreise in jeder Region erwerben und BGP gemeinschaftlichen Tags verwenden, um Routingregeln zu informieren, sodass Datenverkehr an der bevorzugten ExpressRoute Netzfrequenz (normalerweise nächstgelegenen demjenigen, der für die einzelnen Standorte), während die andere gerichtet ist Stromkreise bieten Redundanz bei einem Ausfall einer einzelnen Netzfrequenz beeinflussen. 
  
### <a name="if-expressroute-isnt-an-option"></a>Wenn ExpressRoute eine Option nicht zur Verfügung

Es kann nicht möglich, alle Websites Herstellen einer Verbindung ExpressRoute, entweder aufgrund von Kosten, können nicht eingehalten werden ExpressRoute erforderliche Komponenten oder Einschränkungen von Ihrer aktuellen NSP sein. Wenn Sie die ExpressRoute nicht nutzen können Sie weiterhin, befolgen die Anleitung unter zum Markieren von QoS innerhalb des Netzwerks und Planung der Verträge mit Ihr NSP, um sicherzustellen, dass genügend Bandbreite und Unterstützung für Datenverkehr Priorisierung basierend auf QoS empfohlen werden.
  
Darüber hinaus Wenn Büros mehrere Regionen, aber keinen sollten ExpressRoute Stromkreise in allen Regionen die Region BGP gemeinschaftlichen Tags verwenden beim Konfigurieren von routing für den Datenverkehr in Zweigstellen, damit unnötige langer Transport während der Übertragung vermieden werden kann. Angenommen, ein Unternehmen, das einen Skype für Business Online-Organisation in den USA, jedoch mit Zweigstellen in Europa gehostet hat, und das Unternehmen hat nur ein einzelnes ExpressRoute Netzfrequenz im Silicon Valley. Die meisten der Skype für Business Online-Verkehr an einem Rechenzentrum weitergeleitet werden, in die Organisation (beispielsweise Telefonkonferenzen mit anderen Benutzern innerhalb des Unternehmens) gehostet wird, mithilfe der Netzfrequenz ExpressRoute möglicherweise für die meisten Datenverkehr bevorzugt. Jedoch würde ein Benutzer in Europa teilnehmen an einer Telefonkonferenz, die von einem anderen Unternehmen, deren Organisation sich in Europa befindet, gehostet, wäre das Ziel für Medien in dieses Aufrufs der Europäischen Datacenter zweites Unternehmen gespeichert ist. Den Datenverkehr der Netzfrequenz ExpressRoute im Silicon Valley Routing wäre eine weniger direkte Route als über das Internet möglich wäre. In diesem Fall sollten Sie Router in Ihrem Netzwerk (beispielsweise in der Europäischen Büros) konfigurieren, um untersuchen Sie die Community-Tags beim tätigen routing für Regeln und Weiterleiten per Internet statt Silicon Valley ExpressRoute Netzfrequenz für Datenverkehr, der hat Europäische Region-Tags.
  
### <a name="basic-concepts-of-quality-of-service-qosclass-of-service-cos"></a>Grundlegende Konzepte der Quality of Service (QoS) / Klasse Quality of Service (CoS)

In IP beschreibt Quality of Service (QoS) einen Mechanismus, mit der Behandlung von Priorität für einige Pakete über andere Personen bereitstellen. Gemäß der Definition der International Telecommunications Union (ITU) umfasst QoS alle Qualitätsaspekte einer Verbindung einschließlich Verzögerung, Verlust, Signal-Rausch-Verhältnis, übersprechen, Echo, Interrupts, Bandbreite, Lautstärke Ebenen und So weiter. Was wir als Referenz QoS in Paket Netzwerken ist mehr ordnungsgemäß bezeichnet Klasse Quality of Service (CoS), die zur Verbesserung der Leistung für Verzögerungen, Jitter und Paketverlust konzentriert sich, aber es wird weiterhin den QoS-Begriff verwenden, wie sie die am häufigsten verwendet wird.
  
Bereitstellen von QoS in einer IP-Adresse von Anrufen Netzwerk für zwei Hauptkomponenten:
  
- Die Reservierung einer definierten Anzahl von Bandbreite für Links für Real-Time-Datenverkehr ggf., dass die Bandbreite für Real-Time-Datenverkehr zu einem beliebigen Zeitpunkt nicht zur Verfügung, kann sie für andere Datenverkehr verwendet werden. Die allgemeine Anleitung ist, dass nicht mehr als 30 % der Kapazität eines Links für Sprachdatenverkehr zugewiesen werden soll.
    
- Markieren die Pakete mit einer Priorität Symbol in der Kopfzeile, die die Switches weist und Router im Pfad die Priorität des Pakets, die zugewiesen werden soll.
    
Wenn ein Paket an einen Switch oder Router empfangen wird, wird für den nächsten Abschnitt oder Hop eine Ausgabewarteschlange verschoben. Es gibt verschiedene Ausgabe Warteschlangen für die verschiedenen Prioritätsebenen. Ein Switch oder dem Router wird einen Algorithmus, der die Warteschlange mit hoher Priorität häufiger als die niedrigeren Priorität Warteschlangen services verwendet.
  
Die Herausforderung ist, dass es gibt verschiedene QoS-Methoden, die auf Ebene 2 (d. h. die Ethernet oder Wi-Fi-Ebene) und Layer 3 (d. h. die IP-Schicht) implementiert werden. Diese unterschiedlichen QoS Implementierungen möglicherweise in jeder Switch und Router in das Netzwerk als auch die Schnittstelle zwischen dem Netzwerk und dem Netzwerk des Dienstanbieters Netzwerk konfiguriert werden.
  
Es gibt zwei Optionen für die Art Daten aus den verschiedenen Skype für Geschäftsanwendungen in die entsprechenden Klassen des Diensts zugeordnet werden können:
  
- Endpunkt-Kennzeichnung des Datenverkehrs mit Differentiated Services Steuerelement zeigen (DSCP) 
    
- Netzwerk-Zugriffssteuerungsliste (ACL)-basierte
    
### <a name="end-point-traffic-marking--differentiated-services-control-point-dscp"></a>Endpunkt Datenverkehr Markierung - Differentiated Services Kontrollpunkts (DSCP)

Differenzierte Dienste (DiffServ) wird als "grobkörnig" Mechanismus zum Klassifizieren und Verwalten von Netzwerkdatenverkehr sowie zum Bereitstellen von QoS in IP-Netzwerken bezeichnet. Router und andere Geräte, die implementiert werden Layer 3-Funktionen verwenden DiffServ Steuerelement Point (DSCP), um das Paket Priorität definieren. QoS ist durch Einfügen eines 6-Bit-DSCP-Werts im Feld Differentiated Services (früher das Feld "Type of Service") im IP-Header implementiert. 6 Bits ermöglicht 64 unterschiedliche Prioritätsebenen zuweisen. Die Prioritätsebenen werden normalerweise definiert, wie hier gezeigt.
  
 **Empfohlene DSCP-Wert**
  
|**Datenverkehrsklasse**|**Behandlung (DSCP-Markierung)**|**Skype für Arbeitslasten in Ihrem Unternehmen**|
|:-----|:-----|:-----|
|**VoIP** <br/> |EXPEDITED FORWARDING (46)  <br/> |Skype für Geschäfts- und Lync-VoIP  <br/> |
|**Interaktive** <br/> |AF41 (34)  <br/> |Video  <br/> |
||AF21 (18)  <br/> |Anwendungsfreigabe  <br/> |
|**Standardwert** <br/> |AF11 STELLT (10)  <br/> |Dateiübertragung  <br/> |
||CS0 (0)  <br/> |Irgendetwas anderes  <br/> |
   
 **IP-Version 4-header**
  
![IPv4-header](../images/c8a6a714-2784-4328-8297-2e62706f302d.png)
  
### <a name="layer-2-qos-ieee-8021pwi-fi-multi-media-ieee-80211e"></a>Ebene 2 QoS: IEEE 802.1 p/Wi-Fi Multimedia (IEEE 802.11e)

Zwar DSCP standard Mechanismus für die Implementierung der QoS in Schicht 3, Mechanismen vorhanden sind verschiedene Layer 2 QoS für (d. h. Ethernet) verkabelt und Wireless (d. h. Wi-Fi-Netzwerke). IEEE 802. 1p-Standard ist der QoS-Mechanismus für verdrahtete Netzwerke definiert. der WLAN-QoS-Mechanismus wird definiert, in IEEE 802.11e, was die Wi-Fi-Allianz als "Wi-Fi Multimedia Certified" (WMM zertifiziert) identifiziert.
  
IEEE 802. 1p verwendet einen 3-Bit-Priorität Code Point (PCP), um die Priorität der Nachricht zu identifizieren; die PCP ist Bestandteil eines 32-Bit-Felds im Ethernet-Header, die auch die VLAN-ID wird ausgeführt. Die Definitionen für die PCP Werte sind unten aufgeführt.
  
 **IEEE 802. 1p PCP Werte**
  
|**PCP-Wert**|**Priorität**|**Akronym**|**Typen von Datenverkehr**|
|:-----|:-----|:-----|:-----|
|7  <br/> |7  <br/> |NC  <br/> |Netzwerk-Steuerelement  <br/> |
|6  <br/> |6  <br/> |IC  <br/> |Internetwork-Steuerelement  <br/> |
|5  <br/> |5  <br/> |VO  <br/> |VoIP  <br/> |
|4  <br/> |4  <br/> |VI  <br/> |Video  <br/> |
|3  <br/> |3  <br/> |ZERTIFIZIERUNGSSTELLE  <br/> |Kritische Applikationen  <br/> |
|2  <br/> |2  <br/> |EE  <br/> |Exzellente Leistung  <br/> |
|0  <br/> |1  <br/> |WERDEN  <br/> |Beste Leistung  <br/> |
|1  <br/> |0  <br/> |BK  <br/> |Hintergrund  <br/> |
   
In andere Priorität Warteschlangen für jede Prioritätsebene, aber die Art der freigegebenen Medien WLANs Anrufe für ein anderer Ansatz sortiert, in dem IEEE 802. 1p in die gleiche Weise wie DSCP mit Datenverkehr implementiert wird. Während der Zugriffspunkt und der Client separate Ausgabe Warteschlangen für die verschiedenen Prioritätsebenen beibehalten möchten, sind auch Unterschiede bei wie die Frames auf dem Radiofrequenzkanal versendet werden.
  
In einem Netzwerk Wi-Fi alle Clients zugeordneten Zugriffspunkt einen einzelnen, Halbduplex-Kanal freigeben (d. h. nur eine Client-Station oder dem Zugriffspunkt zu einem Zeitpunkt senden kann). Minimieren Sie das Potenzial der Konflikte im Kanal Radio vor dem Senden eines Frames, den die Station für den Kanal im Leerlauf für einen definierten Zeitraum ein "zwischen Frameabstand" aufgerufen wartet, wenn der Kanal ausgelastet ist, wenn eine Station zum Senden wechselt, sichert sie deaktiviert eine Verzögerungszeit peri auf. Nachdem der Frame, gesendet wird Wenn der Absender keine Bestätigung vom Empfänger erhält, angenommen, dass einen Konflikt oder andere Fehler ist aufgetreten und es Schritte zurück einer zufällig ausgewählten Intervall beim Zugriff auf den Radiofrequenzkanal zu senden. Das Intervall Back deaktiviert ist, verringert sich die Wahrscheinlichkeit, dass die gleichen zwei Stationen erneut kollidieren werden zufällig.
  
Zugriff auf den Sender priorisieren channel IEEE 802.11e / WMM definiert verschiedene vor Übertragung wartenden Intervallen namens "Arbitrated zwischen Frames Spacings" (AFIS) und verschiedene Back-off Bereiche für die verschiedenen Datenverkehrsklassen; vier Prioritätsebenen "Kategorien" aufgerufen werden definiert.
  
Priorität von einer höheren Priorität Frames kürzeren AFIS Werte zuweisen. Wenn eine Station wartet darauf, einen VoIP-Frame senden und eine andere wartet darauf, einen Frame Daten senden, der VoIP-Frame immer zuerst gesendet wird. Technisch gesehen Sprach- und Videoframes den gleichen Wert AFIS zugewiesen sind, jedoch ist des Bereichs der Back-off Intervalle für Videoframes höher. So während einer Sprach- und Videoframes beim ersten Versuch kollidieren können, wird der VoIP-Frame immer schneller weitergeleitet werden. Die Korrelation zwischen IEEE 802. 1p und IEEE 802.11e sieht folgendermaßen aus:
  
 **IEEE 802.11e / Wi-Fi Multimedia (WMM) zu 802. 1p zuordnen**
  
|**WMM Access Kategorie**|**WMM Beschreibung**|**802. 1p PCP Wert**|**802. 1p-Bezeichnung**|
|:-----|:-----|:-----|:-----|
|1 (AC_VO)  <br/> |VoIP  <br/> |7 (111)  <br/> |NC  <br/> |
|6 (110)  <br/> |VO  <br/> |
|2 (AC_VI)  <br/> |Video  <br/> |5 (101)  <br/> |VI  <br/> |
|4 (100)  <br/> |CL  <br/> |
|3 (AC_BE)  <br/> |Best-Effort-Daten  <br/> |3 (011)  <br/> |EE  <br/> |
|0 (000)  <br/> |WERDEN  <br/> |
|4 (AC_BK)  <br/> |Hintergrund-Daten  <br/> |1 (001)  <br/> |BK  <br/> |
|2 (010)  <br/> |---  <br/> |
   
Die empfohlene Zuordnung von Layer 3 zu Layer 2 Prioritäten lautet:
  
 **Layer 3 auf Ebene 2 Priorität Zuordnungen empfohlen**
  
||**Schicht 3 Auswahlmöglichkeiten**|**Ebene 2 (PCP Wert)**|**Wi-Fi (Kategorie Zugriff)**|
|:-----|:-----|:-----|:-----|
|Netzwerk-Steuerelement  <br/> |Pro Hop-Behavior (PHB) - Klassenselektor (CS) 6  <br/> |6  <br/> |1 (AC_VO)  <br/> |
|DSCP-Wert-48  <br/> |
|VoIP  <br/> |Pro Hop-Behavior (PHB)-Expedited Forwarding (EF)  <br/> |5  <br/> |1 (AC_VO)  <br/> |
|DSCP-Wert - 46  <br/> |
|Videokonferenzen  <br/> |Pro Hop-Behavior (PHB) - Assured Forwarding (AF) 41  <br/> |4  <br/> |2 (AC_VI)  <br/> |
|DSCP-Wert - 34  <br/> |
|Rufen Sie die Signale  <br/> |Pro Hop-Behavior (PHB) - Klassenselektor (CS) 3  <br/> |3  <br/> |2 (AC_VI)  <br/> |
|DSCP-Wert - 24  <br/> |
|Daten mit geringer Latenz  <br/> |Pro Hop-Behavior (PHB)-Assured Forwarding (AF) 21  <br/> |2  <br/> |3 (AC_BE)  <br/> |
|DSCP-Wert-18  <br/> |
|Hohe Durchsatzdaten  <br/> |Pro Hop-Behavior (PHB) - Assured Forwarding (AF) 11  <br/> |1  <br/> |3 (AC_BE)  <br/> |
|DSCP-Wert - 10  <br/> |
|Beste Leistung  <br/> |Pro Hop-Behavior (PHB) - 0  <br/> |0  <br/> |4 (AC_BK)  <br/> |
|DSCP-Wert - 0  <br/> |
   
Es ist wichtig, beachten Sie, dass es ein Konflikt besteht in der Priorität, die für IEEE 802. 1p und WMM codieren. Die 802. 1p-Wert der PCP für VoIP 5 ist, jedoch in der Zuordnung standard Äquivalenzvergleich an WMM PCP 5 übersetzt Access Kategorie 2 die Kategorie WMM Zugriff für Video (AC_VI). Sie sollten möglichst außer Kraft setzen, zuordnen, damit in Access Kategorie 1 PCP 5 übersetzt oder einfach vermeiden der Verwendung von Sprach- und Videofunktionen im gleichen Netzwerk Wi-Fi, bis der Wi-Fi-Allianz dieses Problem behandelt. Weitere Informationen zu Wi-Fi finden Sie unter [Wi-Fi Katalogelemente]( https://go.microsoft.com/fwlink/?LinkId=690322).
  
### <a name="implementing-qos-using-network-access-control-list-acl"></a>Implementieren von QoS mit Netzwerk Zugriffssteuerungsliste (ACL)

Implementieren von QoS in einer ExpressRoute Konfiguration die alternative Methode ist die Verwendung von Netzwerk Zugriffssteuerungsliste (ACL). Insofern Ansatz, anstatt die Endpunkte die entsprechende DSCP-Markierung in der Kopfzeile der einzelnen Pakete einfügen, kann die Markierung durch einen Upstream-Router, basierend auf den UDP-Quellport erfolgen. Alle Switches und Router muss weiterhin konfiguriert werden, zur Unterstützung der QoS, um sicherzustellen, dass die DSCP-Einstellungen verwaltet werden. Wichtiger ist, muss der Verbindung mit Netzwerk des Dienstanbieters Router den DSCP in der Kopfzeile der einzelnen Pakete verwalten, wie diese DSCP-Einstellung im Wesentlichen Ihre Anweisung zum Netzwerk-Dienstanbieter ist für die Behandlung des Pakets.
  
Die empfohlene Portbereiche für jede Skype für Business-Anwendung werden im Abschnitt 2.6.1.1 des [Netzwerks, Überwachung und Problembehandlung von Lync Server](https://go.microsoft.com/fwlink/?LinkId=690286) Planungshandbuchs aufgelistet. Es ist wichtig, dass dies mit der Organisation insgesamt Ansatz mit QoS koordiniert werden und Sie sollte der Tabellenstrukturen auf verschiedene QoS-Richtlinien und potenzielle Paket remarking Unterschiede.
  
Während der Hauptgrund verwendeten QoS und MPLS-Netzwerk-Services ist, um sicherzustellen, dass eine gute benutzererfahrung für in Echtzeit Sprach- und Videofunktionen, können diese Features auch für Clientanwendungen Daten angewendet werden. Statt behandeln gleichermaßen alle Programme, können MPLS-Netzwerke Organisationen Anwendungsbeispiele Daten über andere Priorität zugewiesen. Echtzeitanwendungen wie Kreditkartentransaktionen oder Bildschirmfreigabe können mit MPLS Priorität über weniger Zeit vertraulichen Datenverkehr wie e-Mail angegeben sein.
  
### <a name="understanding-the-types-of-ip-network-services--basic-ip-and-mpls"></a>Grundlegendes zu den Arten von IP-Netzwerk Services - grundlegende IP und MPLS

Das ursprüngliche IP-Paket weiterleiten betrieben, dem Prinzip der "best Effort". Dies bedeutete, dass die Router dieser IP-Pakete weiterleiten die bestmöglichen führen Sie würde sie an ihre Ziele zu übermitteln, aber es ist absolut keine Garantie dafür gibt bei, oder wenn sie am Ziel eintreffen würde. Das ist wie grundlegende Internetdienste, einschließlich Ihrer privaten Internetzugang heutigen. Die Vorstellung, dass das war Wenn Zuverlässigkeit für eine bestimmte Anwendung erforderlich war, würden sie auf einer höheren Ebene im Protokollstapel bereitgestellt werden. Der zuverlässige Bereitstellungsmechanismus ist das Protokoll TCP (Transmission Control). Das Protokoll UDP (User Datagram), die für in Echtzeit Sprach- und Videofunktionen verwendet wird, ist die unzuverlässig (d. h. "best-Effort") Übermittlung Mechanismus. 
  
Multi-Protokoll Label wechseln (MPLS) wurde als Mittel für die Netzwerk-Dienstanbieter bietet eine IP-Adresse mit Leistung garantiert für Verzögerungen, jitter und Paketverlust entwickelt. Um diese Leistung Garantien zu übermitteln, dauert MPLS einiger nicht vorhersagbar sind nicht genügend herkömmlichen IP. Jedes Paket finden Sie zuerst statt dessen Weg Router-zu-Router zum Ziel (das Ergebnis der möglicherweise, dass jedes Paket eine andere Route aus der Quelle an das Ziel dauert) – MPLS leitet alle Pakete für eine "virtuelle Verbindung" Verbindung mit einer feste Route bezeichnet ein Label Switched-Pfad (LSP). Wenn Sie einen der Links in diesem Pfad ein Fehler auftritt, werden alle der LSPs, wobei dieser Link schnell umgeleitet.
  
Beim Senden eines Pakets in MPLS-Netzwerk fügt der Netzwerk-Dienstanbieter Edge-Router eine zusätzliche Kopfzeile an das Paket, das eine Beschriftung, die verwendet wird enthält, über die entsprechenden LSP weiterleiten. Die Beschriftung wird vom Edge-Router an das andere Ende des MPLS-Netzwerk entfernt.
  
Neben vereinfacht den Weiterleitungsprozess und ist ein weiterer Vorteil MPLS gewährleistete, dass das Netzwerk Managementsystem wissen, welche Verbindungen auf jedem Link im Netzwerk ausgeführt werden. Kontrolliert die Möglichkeit, den Datenverkehr über das Netzwerk weitergeleitet wird, kann der Operator der QoS garantieren jeder Pfad bereitgestellt werden. So können MPLS-Operatoren anders als die optimale Leistung Aufwand von traditionellen oder grundlegende IP einen IP-Dienst mit vorhersehbare Leistung bereitstellen. LSP MPLS grundsätzlich zugleich eine sichere mehr als herkömmliche Internetdienste. Mit grundlegenden IP-Dienst können wir also hoffen, dass das Netzwerk führt auch genügend guter Qualität VoIP bereitstellen und Verwenden von Techniken wie FEC und weitere ausfallsichere VoIP codieren zur Verbesserung der wahrscheinlich ist, aber mit MPLS, können wir es sicher sein.
  
MPLS-Anbieter bieten verschiedene Klasse von Dienst Verläufe, die unterschiedliche Begriffe leider verwendet, um sie zu identifizieren. Sie müssen eng mit Ihrem Anbieter um sicherzustellen, dass sie die Ausgaben aus [Lync 2010 und 2013 Bandbreite Rechner](https://go.microsoft.com/fwlink/?LinkID=690282) und die empfohlenen Optionen für verschiedene Office 365 Echtzeit Arbeitslasten Applikationen vertraut sind.
  
## <a name="conclusion"></a>Fazit

Skype für Unternehmen verbessert die Möglichkeit, die geschäftliche Kommunikation durchgeführt werden. Statt einer Nebenstellenanlage, einer eigenständigen-Videokonferenzsystem, eine separate Plattform für e-Mail, einen externen Dienst für Audiokonferenzen und einige Fahrzeug für Sofortnachrichten und Anwesenheit, ein herkömmliches kann Skype für Unternehmen alle diese Funktionen zusammen in einer einzigen Benutzeroberfläche.
  
Konsistente Bereitstellung von Business Note in Echtzeit Sprach- und Videofunktionen Services erfordert eine End-to-End-Netzwerkinfrastruktur, die QoS bereitstellen kann. Würde LAN und die WAN-Dienste enthalten. Microsoft bietet Tools wie die [Lync 2010 und 2013 Bandbreite Rechner](https://go.microsoft.com/fwlink/?LinkID=690282) um die Netzwerkkapazität schätzen, die Sie für die verschiedenen Dienste erforderlich ist. Außerdem sind Partner in der Anwendung IT Pro Tools [Skype für Business Solutions: IT Pro Tools](https://go.microsoft.com/fwlink/?LinkID=690307) , die Tools zur Überprüfung vor dem Bewerten der Netzwerkinfrastruktur und monitoring, reporting und Problembehandlung unterstützen anbieten. Ohne ordnungsgemäß Größe und konfigurierten Netzwerkinfrastruktur führen Sie das Risiko, dass ein ExpressRoute Skype Business-Bereitstellung, die nicht des Benutzers Ziele für die Qualität und Konsistenz erfüllen.
  
Effektiven Business-Tools müssen zuverlässig, konsistent, ausführen und eine Benutzeroberfläche zur Verfügung, die Benutzerakzeptanz zu liefern. Aus Sicht der Netzwerke, die bedeutet, dass müssen einer Netzwerkinfrastruktur lokale und breiten Bereich Festnetz- und, mit denen, die auftreten können, können. Planen, entwerfen, implementieren und verwalten, Infrastruktur ist nicht immer eine einfache Feat. Hardware, Tools und Netzwerkdienste zur Erreichung dieses Ziels sind heute verfügbar, aber es ist Aufgabe der IT-Spezialisten zu sehen, dass entworfen, implementiert und verwaltet werden, in eine Möglichkeit, die wird sichergestellt, dass die Benutzer eine Reihe von Communications und Collaboration-Dienste abrufen ermöglichen sie effizienter und effektiver arbeiten und die Organisation profitieren alle Vorteile der diese Technologie zu bieten hat. 
  
## <a name="related-topics"></a>Verwandte Themen

[ExpressRoute-Dokumentation](https://go.microsoft.com/fwlink/?LinkId=690285)

