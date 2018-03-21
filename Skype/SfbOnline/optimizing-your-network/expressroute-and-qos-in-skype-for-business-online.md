---
title: ExpressRoute und QoS in Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 20c654da-30ee-4e4f-a764-8b7d8844431d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: 'Learn about using Azure ExpressRoute to have a network with bandwidth requirements and Quality of Service capability for a business class user experience. '
ms.openlocfilehash: 9c339905dc23df15b5e5a8e6569fafb78524d39e
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2018
---
# <a name="expressroute-and-qos-in-skype-for-business-online"></a>ExpressRoute und QoS in Skype for Business Online

Stellen Sie mithilfe von Azure ExpressRoute für Office 365 und Skype for Business Online eine Verbindung zu Office 365 über eine dedizierte Netzwerkverbindung her. Mit Ihrer dedizierten Verbindung für Ihre Skype for Business-Anwendungen profitieren Sie von einer zuverlässigen und vorhersehbaren Leistung sowie Privatsphäre außerhalb des öffentlichen Internets. Sie können jetzt eine bessere Netzwerkverbindung mit Office 365 und Skype for Business Online erwerben, die Vorhersehbarkeit, Zuverlässigkeit der Unternehmensklasse und eine SLA zur Verfügbarkeit bietet.
  
> [!NOTE]
> Eine neue Version des Bandbreiten-Rechners ist verfügbar: [Skype for Business, Bandbreiten-Rechner ](https://go.microsoft.com/fwlink/?LinkId=715766). Die Anweisungen in diesem Dokument verwenden jedoch den Lync 2010- und 2013-Bandbreiten-Rechner. 
  
## <a name="skype-for-business-online-and-expressroute"></a>Skype for Business Online und ExpressRoute

Durch die Zusammenarbeit mit einem Microsoft ExpressRoute-Partner können Sie eine Vielzahl von Office 365-Anwendungen, einschließlich Skype for Business Online, in der Cloud über eine dedizierte Verbindung verbinden. Für die Echtzeit-VoIP- und -Videokommunikationsfunktionen von Skype for Business sind jedoch Netzwerkdienste erforderlich, die speziell für die Unterstützung dieser Office 365-Echtzeitarbeitsauslastungen konfiguriert sind. Dazu gehören ein Netzwerk mit ausreichend Bandbreite für die Übertragung des erforderlichen Datenverkehrsvolumens und Unterstützung für eine Dienstqualität (Quality of Service, QoS), die Ihren Benutzern eine Erfahrung der Unternehmensklasse bietet.
  
Dieses Dokument soll dazu beitragen, dass Sie, Administratoren und Netzwerkdesigner die speziellen Herausforderungen verstehen, die mit der Unterstützung der Echtzeitkommunikation einhergehen. Sie erfahren außerdem mehr über die von Microsoft bereitgestellten Tools, die Sie beim Entwerfen eines Netzwerks unterstützen, das diese Anforderungen unterstützen kann, und werden anhand einer Fallstudie durch den Entwurfsprozess geführt. 
  
Im ersten Teil dieses Dokuments werden Sie durch eine Fallstudie geführt, die Sie beim Entwerfen Ihres Netzwerks unterstützt. Sie erfahren, wie Sie den [Lync 2010- und 2013-Bandbreiten-Rechner](https://go.microsoft.com/fwlink/?LinkId=690282) verwenden, um die Netzwerkanforderungen für eine umfangreiche Skype for Business ExpressRoute-Bereitstellung mit mehreren Standorten abzuschätzen. Im zweiten Teil dieses Dokuments erfahren Sie mehr über die grundlegenden QoS-Konzepte und erhalten eine umfassende Übersicht über die speziellen technischen Details für die Unterstützung der Skype for Business-Echtzeitkommunikation sowie die speziellen Arten von Netzwerkdiensten, die erforderlich sind.
  
Alle hier enthaltenen Informationen bieten Ihnen technische Details und Grundlegendes zu QoS und ExpressRoute sowie ein grundlegendes Verständnis für die speziellen Herausforderungen, vor denen Sie stehen werden. Die Informationen vermitteln außerdem ausreichende praktische Kenntnisse zu den Tools und Techniken, die Ihnen ermöglichen, ExpressRoute erfolgreich in Ihrem Skype for Business-Netzwerk bereitzustellen. 
  
## <a name="getting-started"></a>Erste Schritte

Bei der Vorbereitung auf den Einsatz von ExpressRoute für Skype for Business ist es sinnvoll, sich die verschiedenen ExpressRoute-Verbindungsmodelle sowie die Auswahl der Partner und Standorte anzusehen und zu lesen, wie Sie ExpressRoute erwerben und in Ihrem Unternehmen bereitstellen. Hier sind einige Ressourcen für die ersten Schritte: 
  
- [Azure ExpressRoute]( https://go.microsoft.com/fwlink/?LinkId=690283)
    
- [ExpressRoute-Preise](https://go.microsoft.com/fwlink/?LinkId=690284)
    
- [ExpressRoute-Dokumentation](https://go.microsoft.com/fwlink/?LinkId=690285)
    
## <a name="part-1-case-study---expressroute-for-dewey-law-llc"></a>Teil 1: Fallstudie - ExpressRoute für Dewey Law, LLC.

In dieser Fallstudie zu Dewey Law, LLC. erfahren Sie, wie Sie ein Netzwerk einrichten, Netzwerkzugriffsdienste bestellen und die Bandbreitenanforderungen zur Unterstützung von ExpressRoute für Skype for Business Online festlegen.
  
 **Hintergrund** Dewy Law LLC. ist eine große US-Anwaltskanzlei mit 790 Anwälten und insgesamt 5.580 Mitarbeitern an 78 Standorten. Das Unternehmen hat seinen Hauptsitz in New York, drei regionale Niederlassungen in Chicago, San Francisco und Dallas sowie 24 große und 50 kleine Zweigstellen, die über das Land verteilt sind. Die Kanzlei bearbeitet große, komplexe Fälle, bei denen die Arbeitsauslastung normalerweise über zwei oder mehr der einzelnen Büros verteilt ist. Dieses Netzwerkdesign führt zu erheblichem Netzwerkdatenverkehr zwischen den Büros.
  
Da Dewy Law LLC. ein relativ junges Unternehmen ist, sind die Anwälte und anderen Mitarbeiter mit Technologie vertraut und verlassen sich in ihrer alltäglichen Arbeit stark darauf. 
  
 **Verteilung von Benutzern nach Standorten und Positionen**
  
||**Hauptsitz (NY)**|**Regionale Büros (3)**|**Große Niederlassungen (24)**|**Kleine Zweigstellen (50)**|
|:-----|:-----|:-----|:-----|:-----|
|Führungskräfte  <br/> |20  <br/> |10  <br/> |1  <br/> |1  <br/> |
|Partner  <br/> |150  <br/> |50  <br/> |10  <br/> |5  <br/> |
|Anwälte  <br/> |300  <br/> |100  <br/> |20  <br/> |10  <br/> |
|Anwaltsgehilfen  <br/> |400  <br/> |125  <br/> |30  <br/> |15  <br/> |
|Führungskräfte in der Verwaltung  <br/> |100  <br/> |35  <br/> |6  <br/> |3  <br/> |
|IT- und allgemeine Verwaltungsmitarbeiter  <br/> |100  <br/> |25  <br/> |3  <br/> |2  <br/> |
|Anzahl pro Standort  <br/> |1.070  <br/> |345  <br/> |70  <br/> |36  <br/> |
|Anzahl pro Standortklasse  <br/> |1.070  <br/> |1.035  <br/> |1.680  <br/> |1.800  <br/> |
   
### <a name="setting-up-the-network"></a>Einrichten des Netzwerks

Für die Bereitstellung von konsistenten und hochwertigen Echtzeitdiensten für Dewey Law LLC. müssen eine Reihe von grundlegenden Anforderungen erfüllt sein:
  
- Da das Unternehmen auch bei Stromausfällen VoIP-Dienste nutzen möchte, müssen die Netzwerkverteilungsswitche und -router Power over Ethernet (PoE) IEEE 802.3af oder 802.3at bereitstellen.
    
- Die Netzwerkswitche und -router müssen außerdem eine unterbrechungsfreie Stromversorgung (USV) nutzen, damit sie ihren Betrieb bei einem Stromausfall fortsetzen können.
    
    Da das Unternehmen über WLAN-Verbindungen zu seinen LAN-Büros verfügt, wird dringend empfohlen, mit einem zertifizierten Skype for Business-WLAN-Infrastrukturpartner aus [Skype for Business-Lösungen](https://go.microsoft.com/fwlink/?LinkId=690281) zusammenzuarbeiten.
    
    > [!TIP]
    >  Drahtlose 802.11n- und 802.11ac-Zugriffspunkte werden empfohlen.
  
- Und der wichtigste Punkt ist, dass alle LAN-Netzwerke in allen Büros für die Bereitstellung von QoS (Quality of Service) eingerichtet werden müssen. Dies schließt PCs, Laptops und sämtliche Netzwerkhardware wie Switche und Router ein.
    
Nachdem die Grundlagen abgedeckt sind, empfehlen wir für die Bereitstellung von VoIP-Diensten der Unternehmensklasse für Dewey Law LLC. die Verwendung des MPLS-IP-Diensts (Multi-Protocol Label Switching) eines Netzwerkpartners für die Herstellung der Verbindung mit dem Azure ExpressRoute-Dienst. MPLS stellt einen IP-Dienst mit Leistungsgarantien in Bezug auf Verzögerung, Jitter und Paketverlust bereit. Falls MPLS nicht verfügbar ist, kann jedoch eine Ethernetverbindung zu einem unserer ExpressRoute-Datenaustauschpartner verwendet werden.
  
MPLS-Anbieter bieten verschiedene Klassen von Serviceleveln, die allerdings von jedem mit unterschiedlichen Begriffen identifiziert werden. Sie müssen eng mit Ihrem Anbieter zusammenarbeiten, um sicherzustellen, dass dieser die von Ihnen in den [Lync 2010- und 2013-Bandbreiten-Rechner](https://go.microsoft.com/fwlink/?LinkID=690282) eingegebenen Daten und die Optionen versteht, die für die verschiedenen Office 365-Echtzeitarbeitsauslastungs-Anwendungen verfügbar sind und empfohlen werden.
  
Es gibt zwei Möglichkeiten, wie Daten von Skype for Business-Anwendungen zu den geeigneten MPLS-Dienstklassen zugeordnet werden können:
  
- Endpunktmarkierung des Datenverkehrs mithilfe von DiffServ Control Point (DSCP)
    
- Basierend auf einer Netzwerk-Zugriffssteuerungsliste (ACL)
    
Zum Implementieren der Endpunktmarkierung müssen Sie alle mit der Domäne verbundenen Windows-Rechner für Dewey Law LLC. so konfigurieren, dass jedes Paket mit der geeigneten DiffServ Control Point (DSCP)-Markierung markiert wird, und dann QoS auf allen Netzwerkswitchen und -routern über alle Bürostandorte hinweg implementieren, um sicherzustellen, dass die QoS-Markierungen beibehalten und nicht entfernt werden. DSCP-Markierungen auf Netzwerkpaketen teilen dem Dienstanbieter mit, welche Priorität für dieses Netzwerkpaket festgelegt ist. **Weitere Informationen zu DSCP finden Sie im Abschnitt zu QoS in Teil 2.**
  
Für eine Netzwerk-ACL-basierte Zuweisung werden die DSCP-Prioritätsmarkierungen auf einem Upstreamrouter implementiert und basieren auf dem UDP-Quellport. Die empfohlenen Portbereiche für die einzelnen Anwendungen sind in Abschnitt 2.6.1.1 von [Network Planning, Monitoring, and Troubleshooting with Lync Server](https://go.microsoft.com/fwlink/?LinkId=690286) (Netzwerkplanung, -überwachung und -problembehandlung mit Lync Server) aufgeführt. Es ist wichtig, dass Sie dies mit der allgemeinen QoS-Implementierung von Dewey Law LLC koordinieren und auf unterschiedliche QoS-Richtlinien und potenzielle Konflikte bei der Paketmarkierung achten.
  
Jeder ExpressRoute-Netzwerkdienstanbieter verfügt über eine Dienstklasse (QoS), die für Echtzeit-VoIP und -video geeignet ist. Diese Dienstklasse heißt „Expedited Forwarding" (EF) für VoIP und „Assured Forwarding" (AF) für Video. Sie müssen die Menge der Bandbreite, die Sie für VoIP-EF-Datenverkehr erwerben, sehr sorgfältig dimensionieren. Denn die VoIP-Dienstklasse ist sehr unnachgiebig, falls Sie mehr VoIP-Datenverkehr senden, als die Dienstklasse bereitstellt.
  
> [!TIP]
>  Sämtlicher Datenverkehr, der gesendet wird und die Verpflichtung des Dienstanbieters überschreitet, wird sofort verworfen, was sich unmittelbar auf die Sprachqualität auswirkt.
  
Bei der Betrachtung des allgemeinen Designs für Dewey Law LLC. ist es äußerst wichtig, dass Sie die Menge der Bandbreite, die zur Unterstützung des VoIP-Datenverkehrs im gesamten Netzwerk erforderlich ist, präzise bestimmen und jedes VoIP-Paket (und nur VoIP-Pakete) mit der DSCP-Einstellung für VoIP markieren (d. h. DSCP EF 46).
  
Zum Implementieren von QoS im gesamten Unternehmensnetzwerk müssen die Endpunkte oder Router jedes Paket mit dem geeigneten Layer-3-Prioritätenindikator markieren (d. h. DSCP). Für jeden Switch und Router am gesamten Netzwerkpfad muss die QoS-Option aktiviert sein. Wenn nur ein Netzwerkswitch oder -router vorhanden ist, für den QoS nicht aktiviert ist, können die QoS-Markierungen für VoIP- oder Videopakete, die über diesen Switch oder Router übertragen werden, entfernt werden. Damit wird QoS im Wesentlichen in allen Downstreamswitchen und Routern deaktiviert, was den Wert von ExpressRoute schmälern würde.
  
All dies erfordert auch, dass die Verknüpfung der Layer-3- und Layer-2-QoS-Prioritäten an jedem Punkt definiert werden muss. Die Mechanismen für die Layer-2-Priorität sind in IEEE 802.1p für verkabelte Netzwerke und in 802.11e/WMM für WLAN-Netzwerke definiert. Noch wichtiger ist, dass der Netzwerkrouter, der auf das MPLS-Netzwerk des Netzwerkdienstanbieters gerichtet ist, die DSCP-Einstellungen für alle ausgehenden Pakete beibehalten muss, damit diese die geeignete MPLS-Dienstklasse beibehalten. 
  
> [!TIP]
>  Spezifische Details zur QoS-Einrichtung finden Sie in Abschnitt 2.6 von [Network Planning, Monitoring, and Troubleshooting with Lync Server]( https://go.microsoft.com/fwlink/?LinkId=760669) (Netzwerkplanung, -überwachung und -problembehandlung mit Lync Server). Weitere Anforderungen an die Netzwerkplanung finden Sie unter[Planen von Netzwerkanforderungen für Skype for Business 2015](https://go.microsoft.com/fwlink/?LinkId=690287).
  
### <a name="ordering-network-access-services"></a>Bestellen von Netzwerkzugriffsdiensten

Nachdem Sie die QoS-Netzwerkvoraussetzungen und -mechanismen zur Unterstützung von ExpressRoute eingerichtet haben, besteht der nächste Schritt darin, eine Bestellung für die ExpressRoute-Netzwerkzugriffsdienste aufzugeben. Beim Bestellen von ExpressRoute-Zugriffsdiensten für Dewey Law LLC vom Microsoft-Netzwerkdienstanbieter-Partner müssen zwei Dinge bereitgestellt werden:
  
- Die Gesamtmenge der Bandbreite, die für die Verbindung jedes Standorts mit ExpressRoute und Office 365 erforderlich ist
    
- Die Gesamtbandbreite, die für jede Dienstklasse erforderlich ist, um Skype for Business-Anwendungen zu unterstützen, die bei Dewey Law LLC verwendet werden. Die Bandbreitenanforderung für die Dienstklasse wird vom erwarteten Datenverkehrsvolumen für jede der verschiedenen Skype for Business-Anwendungen wie VoIP, Video, Chat, Anwesenheit und Bildschirmfreigabe gesteuert.
    
### <a name="determining-bandwidth-requirements-for-skype-for-business-applications"></a>Festlegen von Bandbreitenanforderungen für Skype for Business-Anwendungen

Nach dem Festlegen der insgesamt erforderlichen Bandbreite für Dewey Law LLC. müssen Sie jetzt wissen, wie diese Gesamtbandbreitenmenge unter den verschiedenen Dienstklassen aufgeteilt werden soll. Sie müssen beispielsweise ermitteln, wie viel Bandbreite Sie für jede Skype for Business-Anwendung benötigen.
  
Zum Festlegen dieser Anforderungen an jedem Standort von Dewey Law LLC. verwenden Sie den [Lync 2010- und 2013-Bandbreiten-Rechner](https://go.microsoft.com/fwlink/?LinkID=690282). Dieser Rechner ist ein Excel-basiertes Tool, mit dem Sie die erwartete Verwendung für die verschiedenen Skype for Business-Anwendungen wie VoIP, Video, Konferenzen und Bildschirmfreigabe angeben können. Der Rechner generiert automatisch eine Schätzung der Bandbreiten- und Dienstklassenanforderungen für jeden Standort im Netzwerk. Beim Herunterladen des Lync 2010- und 2013-Bandbreiten-Rechners wird auch ein Benutzerhandbuch heruntergeladen, in dem Sie alle Details zur Verwendung des Tools finden. 
  
Um die Verwendung des Arbeitsblattes zu vereinfachen, sind die verschieden Zellen im Arbeitsblatt farbig codiert:
  
- **Grün** Dies sind Bereiche für die Eingabe allgemeiner Daten.
    
- **Gelb** Dies sind Bereiche für die Eingabe erweiterter Daten. Sie können diese ändern, sollten dabei aber vorsichtig vorgehen.
    
- **Rot** Dies sind schreibgeschützte Bereiche mit gesperrten Eingabewerten, die nicht geändert werden können.
    
- **Grau** Dies sind reine Anzeigebereiche. Dabei handelt es sich um die Ergebnisse oder Daten aus den allgemeinen Eingabebereichen.
    
Der Entwurfsprozess für Dewey Law LLC. beginnt mit der Charakterisierung der Benutzer in verschiedene „Personas". Sie können für jede Persona, die Sie definieren, die erwartete Nutzung der verschiedenen Skype for Business-Anwendungen angeben („Keine", „Wenig", „Mittel", „Hoch" oder eine der drei „benutzerdefinierten" Einstellungen). Sie finden diese Auswahlmöglichkeiten im Arbeitsblatt „Persona". Für jede Auswahl („Wenig", „Mittel" oder „Hoch") ist die bestimmte Nutzung bereitgestellt, aber Sie können die Standardwerte für jede Auswahl ändern. Durch Ermitteln der Anzahl der Benutzer für jede Persona an jedem Standort kann der Rechner die für den jeweiligen Standort erforderliche Gesamtbandbreite berechnen.
  
Sie können außerdem die verwendeten Audio- und Videocodecs, eine eventuelle Verwendung der Fehlerkorrektur bei Weiterleitung und andere Systemparameter angeben, die sich auf die Bandbreitenanforderungen auswirken. Sie können die Standardeinstellungen im Lync 2010- und 2013-Bandbreiten-Rechner verwenden oder andere Codecs und Systemparameter auswählen. Für das Standortdesign bei Dewey Law LLC können die Standardeinstellungen verwendet werden. Wenn Sie eine der Standardeinstellungen ändern möchten, ist jedoch ein Pulldownmenü mit allen verfügbaren Optionen verfügbar. Die für jede Auswahl verwendeten Bandbreiten sind im Arbeitsblatt „Codecs" enthalten. Wenn Sie eine Einstellung ändern, wird die Änderung der Bandbreiten- und Dienstklassenmischung an jedem Standort aktualisiert. Mit dieser Funktion können Sie verschiedene potenzielle Konfigurationen für die Standorte testen und die Auswirkungen sehen, die die Änderungen auf die Bandbreitenanforderungen für den Standort haben.
  
Wir haben für Dewey Law LLC. drei Personas definiert, „Führungskraft/Partner", „Anwalt/Anwaltsgehilfe" und „IT-Admins". In der Tabelle unten ist dargestellt, wie wir die Nutzungsprofile für die verschiedenen Skype for Business-Anwendungen für jede Persona festgelegt haben.
  
 **Personas und Nutzungsprofile (Arbeitsblatt „Persona" - Spalten A bis P)**
  
|**Persona**|**Chat/Anwesenheit**|**P2P-Audio**|**P2P-Video**|**Audiokonferenzen**|**Videokonferenzen**|**Desktopfreigabe**|**Audio bei Einwahlkonferenzen**|**Lync 2010 RTV_Type**|**Remotebenutzer**|**Lync 2013 Stereoaudio**|**Lync 2013 Videoqualität**|**Lync 2013 Benutzerverhalten für P2P-Videofenster**|**Lync 2013 Verwendung der Mehrfachansicht**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Führungskraft/ Partner  <br/> |Hoch  <br/> |Mittel  <br/> |Niedrig  <br/> |Mittel  <br/> |Mittel  <br/> |Keine  <br/> |Mittel  <br/> |CIF  <br/> |0 %  <br/> |0 %  <br/> |Optimal  <br/> |Typisch  <br/> |Typisch  <br/> |
|Anwalt/ Anwaltsgehilfen  <br/> |Hoch  <br/> |Mittel  <br/> |Niedrig  <br/> |Mittel  <br/> |Hoch  <br/> |Hoch  <br/> |Mittel  <br/> |CIF  <br/> |0 %  <br/> |0 %  <br/> |Mittel  <br/> |Typisch  <br/> |Typisch  <br/> |
|IT-Admins  <br/> |Hoch  <br/> |Mittel  <br/> |Keine  <br/> |Niedrig  <br/> |Keine  <br/> |Keine  <br/> |Mittel  <br/> |CIF  <br/> |0 %  <br/> |0 %  <br/> |Mittel  <br/> |Typisch  <br/> |Typisch  <br/> |
   
Sie müssen die Informationen in die Tabelle **Verteilung der Benutzer nach Standort und Positionen** über dem Arbeitsblatt „Standorte" des Lync 2010- und 2013-Bandbreiten-Rechners eingeben. Da die Anzahl der Benutzer in den regionalen Büros identisch ist, werden diese für einen „Standort" definiert und es wird angegeben, dass drei Instanzen davon vorhanden sind. Dasselbe wurde für die großen und kleinen Zweigstellen durchgeführt, in denen 24 bzw. 50 Benutzer in den Standorten vorhanden waren.
  
Nachdem Sie die Einstellungen für jede Persona angegeben haben, müssen Sie die Anzahl der Benutzer in jeder Persona an jedem Standort in das Arbeitsblatt „Standorte" eingeben. Die Gesamtanzahl der Benutzer für alle Standorte wird automatisch aktualisiert. Da keine Benutzer am Office 365-Standort vorhanden sind, sollten diese in den Zeilen für die Zweigstellen des Arbeitsblatts eingegeben werden. Der Lync 2010 und 2013-Bandbreiten-Rechner füllt dann die Spalten „Klasse für beste Leistung", „Klasse für Datenverkehr" und „Klasse für Echtzeitdatenverkehr" in der Tabelle für die WAN-Bandbreite pro QoS-Datenverkehrsklasse aus. Das wird bei den Daten in der Tabelle weiter unten gezeigt.
  
> [!TIP]
>  Das vollständige Arbeitsblatt beinhaltet auch die maximale Anzahl von gleichzeitigen Sitzungen für jede Anwendung, diese Spalten wurden aber aus Platzgründen ausgelassen.
  
 **Personas nach Standort (Arbeitsblatt „Standorte" - Spalten A, D, I und AI bis AX)**
  
|**Standortname**|**Gesamtanzahl der Benutzer am Standort**|**Gesamtanzahl ähnlicher Standorte**|**Benutzerprofil 1**|**Benutzer mit Profil 1**|**Benutzerprofil 2**|**Benutzer mit Profil 2**|**Benutzerprofil 3**|**Benutzer mit Profil 3**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Hauptsitz  <br/> |1070  <br/> |1  <br/> |Führungskraft/Partner  <br/> |170  <br/> |Anwalt/Anwaltsgehilfe  <br/> |700  <br/> |IT-Admins  <br/> |200  <br/> |
|Regionale Büros  <br/> |345  <br/> |3  <br/> |Führungskraft/Partner  <br/> |60  <br/> |Anwalt/Anwaltsgehilfe  <br/> |225  <br/> |IT-Admin  <br/> |60  <br/> |
|Große Zweigstellen  <br/> |70  <br/> |24  <br/> |Führungskraft/Partner  <br/> |11  <br/> |Anwalt/Anwaltsgehilfe  <br/> |50  <br/> |IT-Admin  <br/> |9  <br/> |
|Kleine Zweigstellen  <br/> |36  <br/> |50  <br/> |Führungskraft/Partner  <br/> |6  <br/> |Anwalt/Anwaltsgehilfe  <br/> |25  <br/> |IT-Admin  <br/> |1  <br/> |
   
 **Pro Anwendung erforderliche Bandbreite nach Standort in KBit/s (Arbeitsblatt „Standorte" - Spalten A und BQ bis LF)**
  
|**Standort**|**Spitzen-SIP/Chatbandbreite**|**Spitzenbandbreite für standortübergreifendes Peer-Audio**|**Spitzenbandbreite für standortübergreifendes Peer-Video**|**Spitzenbandbreite für Audiokonferenzen**|**Spitzenbandbreite für Videokonferenzen**|**Spitzenbandbreite für WAN-Freigaben**|**Spitzen-WAN-Bandbreite für PSTN-Anrufe**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Hauptsitz  <br/> |1070  <br/> |525,30  <br/> |560,00  <br/> |739,50  <br/> |2640,00  <br/> |4224,00  <br/> |2688,30  <br/> |
|Regionale Büros  <br/> |345  <br/> |185,40  <br/> |560,00  <br/> |255,00  <br/> |1320,00  <br/> |1536,00  <br/> |896,10  <br/> |
|Große Zweigstellen  <br/> |70  <br/> |92,70  <br/> |560,00  <br/> |102,00  <br/> |600,00  <br/> |384,00  <br/> |216,30  <br/> |
|Kleine Zweigstellen  <br/> |36  <br/> |119,40  <br/> |560,00  <br/> |76,50  <br/> |600,00  <br/> |384,00  <br/> |123,60  <br/> |
   
Die wahrscheinlich wichtigsten Spalten im Arbeitsblatt sind die Spalten, in denen die WAN-Bandbreite nach QoS-Klasse beschrieben wird. Dies wird in der Tabelle unten gezeigt. Diese Daten sind eine Zusammenfassung, die Sie für den Netzwerkdienstanbieter bereitstellen müssen, um die Zugriffsverbindung an jedem Ihrer Standorte bestellen zu können. Denken Sie bei der Berechnung der Gesamtbandbreite daran, die Bandbreite für jeden Zweigstellenstandorttyp mit der Anzahl der Standorte gleichen Typs zu multiplizieren. Weitere Informationen zur Verbindung mit Ihrem ExpressRoute-Netzwerkdienstpartner finden Sie unter [Azure ExpressRoute]( https://go.microsoft.com/fwlink/?LinkId=690283).
  
Es ist sehr wichtig, dass Sie die Bandbreite in der VoIP- oder EF-Dienstklasse (Expedited Forwarding) nicht überschreiten. Da ein zufälliger Paketsatz verworfen werden kann, wird nicht die Qualität eines einzigen Anrufs oder einer einzigen Anrufgruppe reduziert, sondern alle stattfindenden Anrufe können beeinträchtigt werden. Es ist außerdem wichtig, dass nur VoIP mit dem DSCP für EF (d. h. DSCP = 46) markiert wird, da sonst die VoIP-Warteschlange überlaufen kann, wenn Nicht-VoIP-Datenverkehr hinzugefügt wird.
  
> [!TIP]
>  Auch gilt, dass die EF-Dienstklasse zwar die beste Leistungsgarantie bietet, zusätzliche Pakete jedoch bei einer Überschreitung der definierten Bandbreite sofort verworfen werden.
  
 **Aggregierte Bandbreite pro Standort nach QoS-Datenverkehrsklasse (Arbeitsblatt „Standorte" - Spalten A und ML bis MR) **
  
|**Standortname**|**Klasse für beste Leistung (DSCP 0)**|**Datenverkehrsklasse (DSCP benutzerdefiniert)**|**Echtzeit-Datenverkehrsklasse (DSCP 34, AF41)**|**Prioritäts-Datenverkehrsklasse (DSCP 46, EF)**|
|:-----|:-----|:-----|:-----|:-----|
|Hauptsitz  <br/> |0,00  <br/> |5764,80  <br/> |3200,00  <br/> |3953,10  <br/> |
|Regionale Büros  <br/> |0,00  <br/> |2033,60  <br/> |1880,00  <br/> |1336,50  <br/> |
|Große Zweigstellen  <br/> |0,00  <br/> |486,40  <br/> |1160,00  <br/> |411,00  <br/> |
|Kleine Zweigstellen  <br/> |0,00  <br/> |438,40  <br/> |1160,00  <br/> |319,50  <br/> |
   
### <a name="putting-your-plan-into-action"></a>Ihren Plan in die Tat umsetzen

Mit Hilfe der Bandbreitenschätzungen aus der oben stehenden Tabelle **Per application Per site** können wir die Gesamtbandbreite berechnen, die das WAN durchlaufen wird, und die Bandbreite, die ExpressRoute durchlaufen wird Der Anteil des Datenverkehrs, der ExpressRoute durchläuft, schließt die Bandbreite für standortübergreifende Peers aus.

 
|**Standort**|**Spitzen-SIP/Chatbandbreite**|**Spitzenbandbreite für Audiokonferenzen**|**Spitzenbandbreite für Videokonferenzen**|**Spitzenbandbreite für WAN-Freigaben**|**Spitzen-WAN-Bandbreite für PSTN-Anrufe**|**Insgesamt ExpressRoute<br/>Datenverkehr pro Website Klasse<br/>(d. h. insgesamt<br/>Zeit # Websites)**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**Hauptsitz** <br/> |1.070  <br/> |739,50  <br/> |2640,00  <br/> |4224,00  <br/> |2688,30  <br/> |11361,80  <br/> |
|**Regionale Büros** <br/> |345  <br/> |255,00  <br/> |1320,00  <br/> |1536,00  <br/> |896,10  <br/> |8704,20  <br/> |
|**Große Zweigstellen** <br/> |70  <br/> |102,00  <br/> |600,00  <br/> |384,00  <br/> |216,30  <br/> |32935,20  <br/> |
|**Kleine Zweigstellen** <br/> |36  <br/> |76,50  <br/> |600,00  <br/> |384,00  <br/> |123,60  <br/> |61005,00  <br/> |
   
Dies bedeutet, dass der Online-Datenverkehr von Skype for Business die Express-Route mit ca. 114 MBit/s durchlaufen wird. Dewey benötigt also wenigstens das 200 MBit/s-Abonnement für ExpressRoute. Mehrfache ExpressRoute-Netze können bei unterschiedlichen ExpressRoute Peering-Standorten erworben werden. Falls sich die Standorte von Dewey in unterschiedlichen geographischen Regionen befinden oder falls die Verbindung zum ExpressRoute-Netz fehlschlägt, könnte dies als Ausfallsicherheit empfohlen werden. Beim Erwerb von ExpressRoute-Netzen in mehreren Azure-Regionen ist das ExpressRoute-Premium-Add-on erforderlich, um globale Konnektivität über ExpressRoute zu erhalten.
  
Nachdem Sie jetzt die Gesamtmenge der erforderlichen Bandbreite und die Dienstklassen (CoS)-Bandbreitenzahlen haben, können Sie Ihre Bestellungen bei den ausgewählten Netzwerkdienstbetreibern aufgeben. Denken Sie daran, Schätzungen des Datenverkehrs anderer Anwendungen und Dienste anzugeben. Wir bieten Informationen zur Netzwerkplanung für andere Office 365-Dienste, einschließlich Bandbreitenrechner für Exchange und OneDrive. Das Bandbreiten-Abonnement für den Netzwerkdienstanbieter wird höher liegen, da der Datenverkehr zwischen Standorten dazugerechnet werden muss. Der Lync 2010- und 2013-Bandbreiten-Rechner stellt jedoch nur eine Schätzung des erwarteten Datenverkehrs bereit. Für die Bestätigung, dass das Netzwerk in der Lage ist, dieses Datenverkehrsvolumen zu unterstützen, müssen Sie einen Stresstest durchführen. 
  
> [!TIP]
> Ein Stresstest Ihres Netzwerks ist äußerst empfehlenswert, wenn Sie eine Vorabevaluierung eines Netzwerks durchführen. 
  
Ein Stresstest beinhaltet das Aufbauen und Konfigurieren der Infrastruktur und das anschließende Ausführen der Infrastruktur mit dem erwarteten Volumen von simuliertem Datenverkehr bei gleichzeitiger Überwachung der Leistung. Ihre Datenverkehrsschätzungen sind möglicherweise in einigen Bereichen ungenau, aber zumindest können Sie sicher sein, dass das Netzwerk das Datenverkehrsvolumen unterstützen kann, das der Lync 2010- und 2013-Bandbreiten-Rechner prognostiziert hat. Es wird empfohlen, den Stresstest zumindest über einige Tage auszuführen, aber eine längere Ausführung kann Ihnen helfen, die Zahlen genauer abzustimmen. Eine Erweiterung des Stresstestzeitraums muss jedoch gegen die Kosten der Netzwerkdienste abgewogen werden, für die Sie zahlen, ohne dass echter Benutzernetzwerkdatenverkehr übertragen wird. Microsoft hat eine Reihe von Partnern im Rahmen seines IT Pro Tools-Programms zertifiziert, die Netzwerkverwaltungs- und -betriebstools anbieten, darunter auch Stresstools für die Vorabevaluierung. Skype for Business bietet außerdem Systemintegrationstools, die mithilfe der zertifizierten IT Pro-Tools die Netzwerkevaluierung für Sie durchführen können. Weitere Informationen finden Sie unter [Skype for Business Solutions: IT Pro Tools](https://go.microsoft.com/fwlink/?LinkID=690307) (Skype for Business-Lösungen: IT Pro-Tools).
  
Der Stresstest bietet eine gewisse Bestätigung dafür, dass das Netzwerk das erforderliche Datenverkehrsvolumen unterstützen kann, aber in der Realität kann der Lync 2010- und 2013-Bandbreiten-Rechner aus verschiedenen Gründen falsch liegen. Sie sollten außerdem in Betracht ziehen, Ihre Standortnetzwerke weiterhin zu überwachen, indem Sie eine fortlaufende Netzwerkevaluierung nach der Bereitstellung durchführen, um sicherzustellen, dass die Bandbreite ausreicht und die QoS-Mechanismen ordnungsgemäß funktionieren. Es ist wichtig, die Überwachung der Netzwerkleistung fortzusetzen, wenn immer mehr reale Benutzer online gebracht werden.
  
## <a name="part-2-expressroute-skype-for-business-qos"></a>Teil 2: QoS für ExpressRoute für Skype for Business

Der Microsoft ExpressRoute-Dienst stellt eine dedizierte Verbindung mit der Azure-Cloud her, für die Kommunikationsdienste von Office 365-Echtzeitarbeitsauslastungen sind jedoch Netzwerkdienste mit einer ausreichenden Bandbreite erforderlich, die das Datenverkehrsvolumen übertragen und außerdem QoS (Quality of Service) unterstützen können, um eine Benutzererfahrung der Unternehmensklasse zu sichern. Eine QoS-fähige Verbindung muss auf einer End-to-End-Konfiguration basieren (PC, Netzwerkswitche und -router bis zur Cloud), da jeder Teil in dem Pfad, der QoS nicht unterstützen kann, die Qualität des gesamten Anrufs verschlechtern kann.
  
Dieser Abschnitt soll Ihnen dabei helfen, die Herausforderungen zu verstehen, auf die Sie treffen werden, wenn Sie Echtzeitdatenverkehr in einem IP-Netzwerk unterstützen und eine erfolgreiche ExpressRoute-Bereitstellung von Office 365-Echtzeitarbeitsauslastungen mithilfe eines Microsoft ExpressRoute-Austauschanbieter- oder Netzwerkdienstanbieter-Partners konfigurieren und unterstützen möchten.
  
QoS wird von Ihrem Netzwerk exklusiv über ExpressRoute-Netzwerkverbindungen akzeptiert und innerhalb des Microsoft-Netzwerks für Skype for Business-Datenverkehr verwendet. Gegenwärtig weisen Teile einiger ausgehender Verbindungen von Microsoft fehlende DSCP-Werte für Skype for Business auf. So lange ausgehende DSCP-Werte vollständig mit DSCP-Werten gekennzeichnet sind, sollten Sie die Richtlinien zum Hinzufügen von QoS-Kennzeichnungen zum Datenverkehr befolgen, wie im Abschnitt **Implementierung von QoS mithilfe einer Netzwerk-Zugriffssteuerungsliste (ACL)** in diesem Artikel näher erläutert.
  
### <a name="the-real-time-problem"></a>Das Echtzeitproblem

Die Bereitstellung von VoIP- und Videodiensten in Unternehmensqualität stellt spezielle Anforderungen an ein IP-Netzwerk. Echtzeitdatenverkehr verwendet das Real-time Transport Protocol (RTP), das mithilfe von UDP (User Datagram Protocol) übertragen wird. Im Gegensatz zu TCP (Transmission Control Protocol), bei dem jede Nachricht nummeriert und auf Fehler getestet wird, und das andere Mechanismen für die Erkennung und erneute Übertragung verlorener oder fehlerhafter Nachrichten beinhaltet, bietet UDP nicht diese Art der Zuverlässigkeit. Wenn Nachrichten durch Fehler beschädigt sind oder aufgrund von Pufferüberläufen verloren gehen, sind sie einfach verloren. UDP wurde zur Verwendung mit RTP ausgewählt, da die reine Beschaffenheit von Echtzeitdatenverkehr bedingt, dass selbst bei einer erneuten Übermittlung der verlorenen Nachrichten diese viel zu spät kommen würden, um eine positive Auswirkung auf den Fluss von Sprachnachrichten zu haben.
  
Da Entwickler die Auswirkung verlorener VoIP-Pakete kennen, entwickelten Sie zwei Ansätze, um die Leistung von VoIP und Video über IP zu verbessern:
  
- Der erste besteht darin, die VoIP-Codierung/-Decodierung stabiler zu machen, wenn Pakete verloren gehen. Dies kann entweder über die Fehlerkorrektur bei Weiterleitung zur Korrektur eines Prozentsatzes der gefundenen Fehler erfolgen, was eine Funktion in Office 365 Real-Time Transport ist, oder durch Entwerfen von Sprachdecodierungssystemen, die versuchen, die Auswirkung von verlorenen Paketen zu maskieren, was ein Merkmal von Microsoft-Codecs ist. 
    
- Der zweite ist die Verwendung von Transportdiensten, die QoS-Mechanismen verwenden, um die Leistung des Netzwerks in Bezug auf Verzögerung, Paketverlust und Jitter sowie die Abweichung bei der Verzögerung zwischen Paketen zu garantieren.
    
Eine stabile Sprachcodierung geht nur auf das Problem von Paketverlusten ein, deshalb ist es wichtig, dass ein Netzwerk, das für die Übertragung von Echtzeit-VoIP- und Videoinhalten verwendet wird, über Mechanismen verfügt, die Verzögerungen und Jitter minimieren. Selbst mit einer robusten Codierung verfügt die empfangende Station bei einem Verlust zu vieler Pakete nicht über ausreichend Informationen, um eine erkennbare Version des VoIP-Signals zu rekonstruieren. Der Prozentsatz der verlorenen Pakete, der zu einer erkennbaren Verschlechterung der Sprachqualität führen würde, ist je nach verwendeter Sprachcodierungstechnik unterschiedlich. In allen Fällen ist jedoch der Verlust mehrerer nachfolgender Pakete sehr problematisch.
  
Eine Minimierung der Verzögerung ist wichtig, da sich eine übermäßige Verzögerung auf den Unterhaltungsfluss auswirken und für Sprecher sehr störend sein kann. Laut bewährter Methoden sollte die End-to-End-Verzögerung für VoIP (was wir als Mund-zu-Ohr-Verzögerung bezeichnen) unter 150 Millisekunden gehalten werden. Und das bezieht sich auf die unidirektionale, nicht die Roundtripverzögerung. Natürlich verstärkt sich die Verzögerung bei längeren Übertragungsverbindungen wie solchen, die Ozeane überschreiten, allein wegen der Verteilungsverzögerung oder der Zeit, die es braucht, bis das Signal physisch über das Kabel übertragen ist.
  
Wenn die Verzögerung höher als 150 Millisekunden unidirektional ist, hat das eine seltsame Auswirkung auf den Sprecher. Psychologisch schaltet sich im Gehirn des Sprechers ein Warnsignal ein und er glaubt, dass der Empfänger ihn nicht gehört hat, sodass er das Letzte, was er gesagt hat, wiederholt. Das kollidiert mit der verzögerten Antwort vom anderen Ende. Wenn Sie jemals über einen Satellitenkanal telefoniert haben, kennen Sie den Effekt. Über einen Satellitenkanal liegt die unidirektionale Verzögerung bei rund 250 Millisekunden, was weit über der zulässigen Verzögerung liegt.
  
 **Empfohlene Netzwerkparameter für VoIP der Unternehmensklasse**
  
|**Parameter**|**Empfohlener Wert**|
|:-----|:-----|
|Paketjitter zwischen der Ankunftszeit (Durchschnitt)  <br/> |≤ 5 ms  <br/> |
|Paketjitter zwischen der Ankunftszeit (maximal)  <br/> |≤ 40 ms  <br/> |
|Paketverlustrate (Durchschnitt)  <br/> |0 % Annäherung  <br/> |
|Netzwerkwartezeit unidirektional  <br/> |≤ 100 ms (sollte Überprüfungen der Verzögerung im Vergleich zur geografischen Distanz beinhalten)  <br/> |
   
### <a name="expressroute-as-part-of-a-business-grade-voice-network"></a>ExpressRoute als Bestandteil eines VoIP-Netzes der Unternehmensklasse

ExpressRoute bietet eine dedizierte Verbindung über einen Netzwerkdienstanbieter (NSP) oder einen Exchange Provider (EXP) in einer von 3 Verbindungsoptionen an: 
  
- Cloud Exchange Colocation
    
- Point-to-Point Ethernet-Verbindung
    
- Any-to-Any (IPVPN)-Verbindung
    
Dies bietet alle Vorteile der hohen Verfügbarkeit (99,9 % SLA-Verfügbarkeit) sowie verlässliches Routing, das sicher ist (keine Internetübertragung), von Änderungen im Internet-Datenverkehr unberührt bleibt und Quality of Service-Markierungen zum Priorisieren von Datenverkehr respektiert (QoS wird weiter unten erläutert). ExpressRoute kann zusammen mit einem gut geplanten WAN ein VoIP-Netz der Unternehmensklasse zur Verfügung stellen.
  
ExpressRoute kann (bei Hybrid-Topologie) zur Datenübertragung zwischen Büros oder Datenzentren verwendet werden, die mit dem Netz verbunden sind. Daten für standortexterne Nutzer (zum Beispiel vom Home-Office oder von unterwegs aus) werden das ExpressRoute-Netz nicht belasten, es sei denn, sie sind über VPN verbunden, und müssen nicht in der Bandbreitenschätzung zur Dimensionierung des ExpressRoute-Netzes eingeschlossen werden. Multinationale Kunden können ExpressRoute-Netze in allen Regionen erwerben und BGP Community-Tags zum Informieren von Routingregeln verwenden, damit der Datenverkehr in das bevorzugte ExpressRoute-Netz geleitet wird (typischerweise das jedem Standort nächstgelegene), wohingegen die anderen Netze Redundanz bieten, falls eines der Netze von einem Ausfall betroffen ist. 
  
### <a name="if-expressroute-isnt-an-option"></a>Falls ExpressRoute keine Option ist

Unter Umständen ist es nicht praktikabel, alle Standorte mit ExpressRoute zu verbinden, entweder aus Kostengründen, weil die Voraussetzungen für ExpressRoute nicht erfüllt sind oder wegen Einschränkungen Ihrer aktuellen NSP. Falls Sie ExpressRoute nicht verwenden können, empfehlen wir, unten stehende Empfehlungen zur Markierung von QoS in Ihrem Netzwerk zu befolgen und die Verträge mit Ihrem NSP so zu planen, dass genügend Bandbreite und Unterstützung für QoS-basierte Priorisierung des Datenverkehrs gewährleistet ist.
  
Falls Sie außerdem Büros in mehreren Regionen, aber nicht in allen Regionen ExpressRoute-Netze haben, sollten Sie die regionalen BGP Community-Tags bei der Konfiguration der Datenverkehrsführung zu/von Außenstellen verwenden, damit unnötig lange Übertragungswege vermieden werden. Denken Sie zum Beispiel an ein Unternehmen, das eine Skype for Business Online-Organisation in den USA hat, aber Zweigstellen in Europa besitzt und nur ein ExpressRoute-Netz in Silicon Valley unterhält. Der Großteil des Skype for Business Online-Datenverkehrs wird an ein Datenzentrum geleitet, bei dem die Organisation gehostet wird (zum Beispiel Telefonkonferenzen mit anderen Nutzern innerhalb des Unternehmens). Hier kann das ExpressRoute-Netz möglicherweise für den meisten Datenverkehr bevorzugt werden. Falls jedoch ein Nutzer in Europa einer Telefonkonferenz beitreten möchte, die von einem anderen Unternehmen gehostet wird, deren Organisation sich in Europa befindet, wäre das Ziel für Medien in diesem Anruf das Datenzentrum in Europa, wo sich das zweite Unternehmen befindet. Die Führung des Datenverkehrs durch das ExpressRoute-Netz in Silicon Valley wäre weniger direkt, als dies über das Internet möglich wäre. In einem solchen Fall wäre es angebracht, Router innerhalb des Netzwerks zu konfigurieren (zum Beispiel in den europäischen Büros), um die Community-Tags bei der Erstellung der Routing-Regeln zu prüfen und Datenverkehr mit europäischen Regions-Tags eher über das Internet als über das Silicon Valley ExpressRoute-Netz zu routen.
  
### <a name="basic-concepts-of-quality-of-service-qosclass-of-service-cos"></a>Grundlegende Konzepte für Quality of Service (QoS)/Dienstklassen

Im IP-Kontext beschreibt Quality of Service (QoS) jeden Mechanismus, der verwendet wird, um eine auf Priorität basierende Verarbeitung einiger Pakete im Vergleich zu anderen Paketen bereitzustellen. Gemäß der Definition der International Telecommunications Union (ITU) umfasst QoS alle Qualitätsaspekte einer Verbindung wie Verzögerung, Verlust, Signal-Stör-Verhältnis, Nebensprechen, Echo, Unterbrechungen, Frequenzantwort, Lautstärke und so weiter. Was wir in Paketnetzwerken als QoS bezeichnen, sollte richtiger als Dienstklasse benannt werden, die sich auf die Verbesserung der Leistung in Bezug auf Verzögerung, Jitter und Paketverlust bezieht, aber wir werden weiterhin den Begriff QoS verwenden, da er geläufiger ist.
  
Für die Bereitstellung von QoS in einem IP-Netzwerk sind zwei primäre Komponenten erforderlich:
  
- Die Reservierung einer definierten Bandbreitenmenge auf jeder Verbindung für Echtzeitdatenverkehr. Wenn diese Bandbreite nicht immer für Echtzeitdatenverkehr erforderlich ist, kann sie für anderen Datenverkehr verwendet werden. Als allgemeine Richtlinie gilt, nicht mehr als 30 % einer beliebigen Verbindung für VoIP-Datenverkehr zuzuweisen.
    
- Die Markierung der Pakete mit einem Prioritätenindikator im Header, der den Switchen und Routern im Pfad mitteilt, welche Priorität dem Paket zugewiesen werden sollte.
    
Wenn ein Paket von einem Switch oder Router empfangen wird, wird es für den nächsten Schritt oder Hop an eine Ausgabewarteschlange verschoben. Es gibt unterschiedliche Ausgabewarteschlangen für die verschiedenen Prioritätsstufen. Ein Switch oder Router verwendet einen Algorithmus, der die Warteschlange mit hoher Priorität häufiger bedient als die Warteschlangen mit niedrigerer Priorität.
  
Die Herausforderung besteht darin, dass verschiedene QoS-Techniken vorhanden sind, die auf Layer 2 (d. h. der Ethernet- oder WLAN-Schicht) und Layer 3 (d. h. der IP-Schicht) implementiert sind. Diese verschiedenen QoS-Implementierungen müssen möglicherweise in jedem einzelnen Switch und Router im Netzwerk sowie der Schnittstelle zwischen Ihrem Netzwerk und dem Netzwerk des Netzwerkdienstanbieters konfiguriert werden.
  
Es gibt zwei Möglichkeiten, wie Daten von den verschiedenen Skype for Business-Anwendungen den geeigneten Dienstklassen zugeordnet werden können:
  
- Endpunktmarkierung des Datenverkehrs mithilfe von DSCP (Differentiated Services Control Point) 
    
- Basierend auf einer Netzwerk-Zugriffssteuerungsliste (ACL)
    
### <a name="end-point-traffic-marking--differentiated-services-control-point-dscp"></a>Endpunktmarkierung des Datenverkehrs - Differentiated Services Control Point (DSCP)

Differentiated Services (DiffServ) wird als ein „grobkörniger" Mechanismus für die Klassifizierung und Verwaltung des Netzwerkdatenverkehrs und die Bereitstellung von QoS in IP-Netzwerken bezeichnet. Router und andere Geräte, die Layer-3-Funktionen implementieren, verwenden DiffServ Control Point (DSCP), um die Priorität des Pakets zu definieren. QoS wird über das Einfügen eines 6-Bit-DSCP-Werts in das Differentiated Services-Feld (früher das Feld für den Diensttyp) im IP-Header implementiert. 6 Bit ermöglichen 64 verschiedene Prioritätsstufen. Die Prioritätsstufen sind normalerweise wie im Folgenden gezeigt definiert.
  
 **Empfohlene DSCP-Einstellungen**
  
|**Datenverkehrsklasse**|**Bearbeitung (DSCP-Markierung)**|**Skype for Business-Auslastungen**|
|:-----|:-----|:-----|
|**VoIP** <br/> |EF (46)  <br/> |Skype for Business und Lync-Sprachanrufe  <br/> |
|**Interaktiv** <br/> |AF41 (34)  <br/> |Video  <br/> |
||AF21 (18)  <br/> |Anwendungsfreigabe  <br/> |
|**Standard** <br/> |AF11 (10)  <br/> |Dateiübertragung  <br/> |
||CS0 (0)  <br/> |Sonstiges  <br/> |
   
 ** IP-Version-4-Header**
  
![IPv4-Header](../images/c8a6a714-2784-4328-8297-2e62706f302d.png)
  
### <a name="layer-2-qos-ieee-8021pwi-fi-multi-media-ieee-80211e"></a>Layer-2-QoS: IEEE 802.1p/WLAN-Multimedia (IEEE 802.11e)

Zwar ist DSCP der Standardmechanismus für die Implementierung von QoS in Layer 3, aber es gibt andere Layer-2-QoS-Mechanismen für verkabelte Netzwerke (d. h. Ethernet) und drahtlose Netzwerke (d. h. WLAN-Netzwerke). Der QoS-Mechanismus für verkabelte Netzwerke ist im Standard IEEE 802.1p definiert, der WLAN-QoS-Mechanismus in IEEE 802.11e, was die Wi-Fi Alliance als „Wi-Fi Multi-Media Certified (WMM Certified)" bezeichnet.
  
IEEE 802.1p verwendet einen 3-Bit-PCP (Priority Code Point), um die Priorität der Nachricht zu ermitteln. Der PCP ist Teil eines 32-Bit-Felds im Ethernetheader, der auch die VLAN-Kennung enthält. Die Definitionen für die PCP-Werte sind im Folgenden aufgeführt.
  
 ** IEEE 802.1p-PCP-Werte**
  
|**PCP-Wert**|**Priorität**|**Abkürzung**|**Datenverkehrstypen**|
|:-----|:-----|:-----|:-----|
|7  <br/> |7  <br/> |NC  <br/> |Netzwerksteuerung  <br/> |
|6  <br/> |6  <br/> |IC  <br/> |Netzwerkübergreifende Steuerung  <br/> |
|5  <br/> |5  <br/> |VO  <br/> |VoIP  <br/> |
|4  <br/> |4  <br/> |VI  <br/> |Video  <br/> |
|3  <br/> |3  <br/> |CA  <br/> |Kritische Anwendungen  <br/> |
|2  <br/> |2  <br/> |EE  <br/> |Hervorragende Leistung  <br/> |
|0  <br/> |1  <br/> |BE  <br/> |Beste Leistung  <br/> |
|1  <br/> |0  <br/> |BK  <br/> |Hintergrund  <br/> |
   
IEEE 802.1p wird im Wesentlichen auf dieselbe Weise wie DSCP implementiert, da auch hier der Datenverkehr für jede Prioritätsstufe in verschiedene Prioritätswarteschlangen sortiert wird, aber die Shared-Media-Beschaffenheit von WLANs verlangt nach einem anderen Ansatz. Während der Zugriffspunkt und der Client separate Ausgabewarteschlangen für die verschiedenen Prioritätsstufen verwalten, gibt es auch Unterschiede, wie die Frames an den Funkkanal ausgesendet werden.
  
In einem WLAN-Netzwerk teilen alle mit einem Zugriffspunkt verbundenen Clients einen einzigen Halbduplexkanal (d. h. es kann jeweils nur eine Clientstation oder der Zugriffspunkt senden). Zum Minimieren potenzieller Kollisionen im Funkkanal wartet die Station vor dem Senden eines Frames, bis der Kanal für einen definierten Zeitraum, der als „Inter-Frame-Spacing" bezeichnet wird, im Leerlauf war. Falls der Kanal belegt ist, wenn eine Station sendet, zieht er sich für einen zufälligen Zeitraum zurück (was als „Back-off" bezeichnet wird). Wenn der Frame gesendet wurde und der Absender keine Bestätigungsmeldung vom Empfänger erhält, geht er davon aus, dass eine Kollision oder ein anderer Fehler aufgetreten ist, und tritt für ein zufälliges Intervall zurück, bevor er versucht, zum erneuten Senden auf den Funkkanal zuzugreifen. Das Back-off-Intervall ist zufällig, um die Wahrscheinlichkeit zu verringern, dass dieselben zwei Stationen erneut kollidieren.
  
Zur Priorisierung des Zugriffs auf den Funkkanal definiert IEEE 802.11e/WMM verschiedene Warteintervalle vor der Übertragung, die als „Arbitrated Inter-Frame Spacings (AFIS)" bezeichnet werden, sowie verschiedene Back-off-Bereiche für die unterschiedlichen Datenverkehrsklassen. Es werden vier Prioritätsstufen definiert, die als „Zugriffskategorien" bezeichnet werden.
  
Die Priorität wird durch Zuweisen kürzerer AFIS-Werte zu den Frames mit höherer Priorität erreicht. Wenn also eine Station darauf wartet, einen VoIP-Frame zu senden, und eine andere darauf, einen Datenframe zu senden, wird der VoIP-Frame immer zuerst gesendet. Technisch gesehen werden VoIP- und Videoframes dieselben AFIS-Werte zugewiesen, aber der Bereich für Back-off-Intervalle ist für Videoframes höher. So können ein VoIP- und ein Videoframe zwar beim ersten Versuch kollidieren, aber der VoIP-Frame wird immer früher erneut übermittelt. Die Korrelation zwischen IEEE 802.1p und IEEE 802.11e ist unten gezeigt:
  
 ** Zuordnung von IEEE 802.11e/Wi-Fi Multi-Media (WMM) zu 802.1P**
  
|**WMM-Zugriffskategorie**|**WMM Beschreibung**|**802.1P-PCP-Wert**|**802.1P-Bezeichnung**|
|:-----|:-----|:-----|:-----|
|1 (AC_VO)  <br/> |VoIP  <br/> |7 (111)  <br/> |NC  <br/> |
|6 (110)  <br/> |VO  <br/> |
|2 (AC_VI)  <br/> |Video  <br/> |5 (101)  <br/> |VI  <br/> |
|4 (100)  <br/> |CL  <br/> |
|3 (AC_BE)  <br/> |Beste Leistung Daten  <br/> |3 (011)  <br/> |EE  <br/> |
|0 (000)  <br/> |BE  <br/> |
|4 (AC_BK)  <br/> |Hintergrund Daten  <br/> |1 (001)  <br/> |BK  <br/> |
|2 (010)  <br/> |---  <br/> |
   
Die empfohlene Zuweisung von Layer-3- zu Layer-2-Prioritäten ist im Folgenden dargestellt:
  
 **Empfohlene Layer-3- zu Layer-2-Zuweisung von Prioritäten**
  
||**Layer-3-Markierungen**|**Layer 2 (PCP-Wert)**|**WLAN (Zugriffskategorie)**|
|:-----|:-----|:-----|:-----|
|Netzwerksteuerung  <br/> |Per Hop Behavior (PHB) - Class Selector (CS) 6  <br/> |6  <br/> |1 (AC_VO)  <br/> |
|DSCP-Wert - 48  <br/> |
|VoIP  <br/> |Per Hop Behavior (PHB) - Expedited Forwarding (EF)  <br/> |5  <br/> |1 (AC_VO)  <br/> |
|DSCP-Wert - 46  <br/> |
|Videokonferenzen  <br/> |Per Hop Behavior (PHB) - Assured Forwarding (AF) 41  <br/> |4  <br/> |2 (AC_VI)  <br/> |
|DSCP-Wert - 34  <br/> |
|Anrufsignale  <br/> |Per Hop Behavior (PHB) - Class Selector (CS) 3  <br/> |3  <br/> |2 (AC_VI)  <br/> |
|DSCP-Wert - 24  <br/> |
|Daten mit niedriger Wartezeit  <br/> |Per Hop Behavior (PHB) - Assured Forwarding (AF) 21  <br/> |2  <br/> |3 (AC_BE)  <br/> |
|DSCP-Wert - 18  <br/> |
|Daten mit hohem Durchsatz  <br/> |Per Hop Behavior (PHB) - Assured Forwarding (AF) 11  <br/> |1  <br/> |3 (AC_BE)  <br/> |
|DSCP-Wert - 10  <br/> |
|Beste Leistung  <br/> |Per Hop Behavior (PHB) - 0  <br/> |0  <br/> |4 (AC_BK)  <br/> |
|DSCP-Wert - 0  <br/> |
   
Es ist wichtig zu bemerken, dass ein Konflikt in der Codierung der Priorität für IEEE 802.1p und WMM besteht. Der 802.1p-PCP-Wert für VoIP ist 5, in der Standardäquivalenzzuordnung zu WMM wird PCP 5 jedoch in die Zugriffskategorie 2 übersetzt, also die WMM-Zugriffskategorie für Video (AC_VI). Sie sollten diese Zuordnung möglichst außer Kraft setzen, damit PCP 5 in Zugriffskategorie 1 übersetzt wird, oder einfach vermeiden, VoIP und Video im selben WLAN-Netzwerk zu verwenden, bis die Wi-Fi Alliance dieses Problem behoben hat. Weitere Informationen zu WLAN finden Sie unter [WLAN-Katalogelemente]( https://go.microsoft.com/fwlink/?LinkId=690322)
  
### <a name="implementing-qos-using-network-access-control-list-acl"></a>Implementierung von QoS mithilfe einer Netzwerk-Zugriffssteuerungsliste (ACL)

Die alternative Methode für die Implementierung von QoS in einer ExpressRoute-Konfiguration ist die Verwendung einer Netzwerk-Zugriffssteuerungsliste (ACL). Bei diesem Ansatz fügen nicht die Endpunkte die geeignete DSCP-Markierung in den Header jedes Pakets ein, sondern die Markierung kann von einem Upstreamrouter basierend auf dem UDP-Quellport durchgeführt werden. Alle Switche und Router müssen trotzdem für die Unterstützung von QoS konfiguriert werden, um sicherzustellen, dass die DSCP-Einstellungen beibehalten werden. Noch wichtiger ist, dass der Router, der mit dem Netzwerk des Dienstanbieters verbunden ist, die DSCP-Markierung im Header jedes Pakets beibehalten muss, da diese DSCP-Einstellung im Wesentlichen Ihre Anweisung an den Netzwerkdienstanbieter ist, wie dieses Paket behandelt werden soll.
  
Die empfohlenen Portbereiche für jede Skype for Business-Anwendung sind in Abschnitt 2.6.1.1 des Handbuchs [Network Planning, Monitoring, and Troubleshooting with Lync Server](https://go.microsoft.com/fwlink/?LinkId=690286) (Netzwerkplanung, -überwachung und -problembehandlung mit Lync Server) aufgeführt. Es ist wichtig, dies mit dem allgemeinen Ansatz der Organisation hinsichtlich QoS zu koordinieren. Zudem sollten Sie auf unterschiedliche QoS-Richtlinien und potenzielle Konflikte bei der erneuten Markierung von Paketen achten.
  
Zwar ist der Hauptgrund für die Verwendung von QoS und MPLS-Netzwerkdiensten, eine gute Benutzererfahrung für Echtzeit-VoIP und -video sicherzustellen, aber dieselben Funktionen können auch für Datenanwendungen angewendet werden. Statt alle Anwendungen gleich zu behandeln, können Organisationen mit MPLS-Netzwerken einigen Datenanwendungen eine höhere Priorität zuweisen als anderen. Mit MPLS können Echtzeitanwendungen wie Kreditkartentransaktionen oder Bildschirmfreigaben eine höhere Priorität als weniger zeitsensibler Datenverkehr wie E-Mails erhalten.
  
### <a name="understanding-the-types-of-ip-network-services--basic-ip-and-mpls"></a>Grundlegendes zu den Typen von IP-Netzwerkdiensten - einfache IP-Dienste und MPLS

Die ursprüngliche IP-Paketweiterleitung basierte auf dem „Best Effort"-Prinzip. Das hieß, dass die Router, die diese IP-Pakete weiterleiteten, ihr Bestes gaben, um die Pakete an ihr Ziele zu bringen, aber es gab keine Garantie in Bezug darauf, wann und ob sie an ihrem Ziel ankommen würden. So funktionieren heute einfache Internetdienste, einschließlich Ihrer privaten Internetverbindung. Die Idee war, dass die Zuverlässigkeit, die für eine bestimmte Anwendung erforderlich war, in einer höheren Ebene des Protokollstapels bereitgestellt werden würde. Der zuverlässige Übermittlungsmechanismus ist das Transmission Control Protocol (TCP). Das User Datagram Protocol (UDP), das für Echtzeit-VoIP und -video verwendet wird, ist der unzuverlässige Übermittlungsmechanismus (d. h. „Best Effort"). 
  
Multi-Protocol Label Switching (MPLS) wurde als ein Mittel für Netzwerkdienstanbieter entwickelt, damit diese einen IP-Dienst mit Leistungsgarantien in Bezug auf Verzögerung, Jitter und Paketverlust anbieten können. Zur Bereitstellung dieser Leistungsgarantien vermeidet MPLS einen Teil der Unvorhersehbarkeit von herkömmlichen IP-Diensten. Erstens lässt MPLS nicht jedes Paket seinen Weg zum Ziel Router für Router finden (was bedeuten könnte, dass jedes Paket eine andere Route von der Quelle zum Ziel nimmt), sondern leitet alle Pakete in einer „Virtual Circuit"-Verbindung mit einer festen Route namens „Label Switched Path (LSP)" weiter. Wenn in einer der Verbindungen in diesem Pfad ein Fehler auftritt, werden alle LSPs, die diese Verbindung verwenden, schnell umgeleitet.
  
Wenn ein Paket in das MPLS-Netzwerk gesendet wird, hängt der Edgerouter des Netzwerkdienstanbieters einen zusätzlichen Header mit einer Bezeichnung an das Paket an, die verwendet wird, um das Paket über den geeigneten LSP weiterzuleiten. Die Bezeichnung wird vom Edgerouter am anderen Ende des MPLS-Netzwerks entfernt.
  
Neben der Vereinfachung des Weiterleitungsprozesses besteht ein weiterer Vorteil von MPLS darin, dass das Netzwerkverwaltungssystem weiß, welche Verbindungen auf jedem Link im Netzwerk übertragen werden. Durch die Steuerung der Art und Weise, in der Datenverkehr über das Netzwerk weitergeleitet wird, kann der Bediener die QoS garantieren, die jeder Pfad bereitstellt. Im Gegensatz zur Best-Effort-Leistung von herkömmlichen oder einfachen IP-Diensten kann MPLS Bedienern einen IP-Dienst mit einer zuverlässigen Leistung bereitstellen. Außerdem sorgt LSP dafür, dass MPLS an sich sicherer als herkömmliche Internetdienste ist. Bei einfachen IP-Diensten können wir also hoffen, dass das Netzwerk eine ausreichende Leistung bietet, um eine gute Sprachqualität bereitzustellen, und Techniken wie FEC und eine robustere VoIP-Codierung verwenden, um unsere Chancen zu erhöhen, aber mit der Verwendung von MPLS können wir sicher sein, dass das so ist.
  
MPLS-Anbieter bieten verschiedene Klassen von Serviceabstufungen, die allerdings leider von jedem mit unterschiedlichen Begriffen identifiziert werden. Sie müssen eng mit Ihrem Anbieter zusammenarbeiten, um sicherzustellen, dass dieser die Ausgaben des [Lync 2010- und 2013-Bandbreiten-Rechners](https://go.microsoft.com/fwlink/?LinkID=690282) und die empfohlenen Optionen für verschiedene Office 365-Echtzeitarbeitsauslastungs-Anwendungen versteht.
  
## <a name="conclusion"></a>Fazit

Skype for Business verbessert die Art und Weise, in der die Geschäftskommunikation durchgeführt wird. Statt ein mit dem Festnetz verbundenes Telefon, ein eigenständiges Videokonferenzsystem, eine separate Plattform für E-Mails, einen externen Dienst für Audiokonferenzen und ein Mittel für Chat und Anwesenheit zu nutzen, kann Skype for Business all diese Funktionen in einer einzigen Benutzeroberfläche zusammenbringen.
  
Für eine konsistente Bereitstellung von Echtzeit-VoIP- und Videodiensten der Unternehmensklasse ist eine End-to-End-Netzwerkinfrastruktur erforderlich, die QoS bereitstellen kann. Das beinhaltet sowohl LAN- als auch WAN-Dienste. Microsoft bietet Tools wie den [Lync 2010- und 2013-Bandbreiten-Rechner](https://go.microsoft.com/fwlink/?LinkID=690282), um die für die verschiedenen Dienste erforderliche Netzwerkkapazität abzuschätzen. Außerdem gibt es Partner im IT Pro Tools-Programm [Skype for Business Solutions: IT Pro Tools](https://go.microsoft.com/fwlink/?LinkID=690307), die Tools anbieten, die eine Vorabevaluierung der Netzwerkinfrastruktur ermöglichen und Überwachung, Berichterstellung und Problembehandlung unterstützen. Ohne eine korrekt dimensionierte und konfigurierte Netzwerkinfrastruktur besteht das Risiko, dass Ihre ExpressRoute Skype of Business-Bereitstellung nicht die Erwartungen an Qualität und Konsistenz Ihrer Benutzer erfüllt.
  
Effektive Unternehmenstools müssen eine zuverlässige und konsistente Leistung bieten und eine Benutzererfahrung bereitstellen, die dafür sorgt, dass Benutzer das Angebot gern annehmen. Aus Netzwerksicht bedeutet das, dass Sie eine Netzwerkinfrastruktur einrichten, sowohl für LAN als auch WAN, fest und mobil, die dies ermöglichen kann. Das Planen, Entwerfen, Implementieren und Verwalten dieser Infrastruktur ist nicht immer leicht. Die Hardware, Tools und Netzwerkdienste, mit denen Sie eine solche Infrastruktur erreichen können, stehen heute zur Verfügung. Es liegt jedoch in der Verantwortung der IT-Mitarbeiter, diese auf eine Weise zu entwerfen, zu implementieren und zu verwalten, die sicherstellt, dass Benutzer eine Reihe von Diensten für die Kommunikation und Zusammenarbeit erhalten, mit denen sie effizient und effektiv arbeiten können, und dass die Organisation die Vorteile dieser Technologie vollständig ausschöpfen kann. 
  
## <a name="related-topics"></a>See Also

[ExpressRoute-Dokumentation](https://go.microsoft.com/fwlink/?LinkId=690285)

