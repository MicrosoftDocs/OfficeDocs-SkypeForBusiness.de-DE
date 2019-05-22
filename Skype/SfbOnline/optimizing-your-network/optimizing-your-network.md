---
title: Optimieren Ihres Netzwerks
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.topic: article
ms.assetid: b363bdca-b00d-4150-96c3-ec7eab5a8a43
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: Die folgenden Anforderungen sind wichtig, um langfristig die Integrität und die erfolgreiche Nutzung aller Skype for Business Online-Funktionen sicherzustellen, die Sie für Ihre Organisation einrichten. Wir wissen, dass einige von Ihnen technisch sehr versiert sind. An Sie richtet sich dieses Dokument. Andere jedoch sind auf diesem Gebiet weniger erfahren. Wenn Sie Hilfe beim Einrichten von Skype for Business Online benötigen, lesen Sie dieses Dokument, um sich mit den Dingen vertraut zu machen, die Sie berücksichtigen müssen. Außerdem erhalten Sie Anhaltspunkte für Gespräche mit dem Microsoft FastTrack Center, Ihren Microsoft Services-Teams und Account-Teams oder mit Microsoft-Partnern, um herauszufinden, wie Sie diese Anforderungen erfüllen können.
ms.openlocfilehash: f81b2bebded33bf65ff391909dea4e6f638390fb
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2019
ms.locfileid: "34344550"
---
# <a name="optimizing-your-network-for-skype-for-business-online"></a>Optimieren Ihres Netzwerks für Skype for Business Online

Die folgenden Anforderungen sind wichtig, um langfristig die Integrität und die erfolgreiche Nutzung aller Skype for Business Online-Funktionen sicherzustellen, die Sie für Ihre Organisation einrichten. Wir wissen, dass einige von Ihnen technisch sehr versiert sind. An Sie richtet sich dieses Dokument. Andere jedoch sind auf diesem Gebiet weniger erfahren. Wenn Sie Hilfe beim Einrichten von Skype for Business Online benötigen, lesen Sie dieses Dokument, um sich mit den Dingen vertraut zu machen, die Sie berücksichtigen müssen. Außerdem erhalten Sie Anhaltspunkte für Gespräche mit dem [Microsoft FastTrack Center](https://fasttrack.microsoft.com/office), Ihren Microsoft Services-Teams und Account-Teams oder mit [Microsoft-Partnern](https://partnercenter.microsoft.com/en-us/pcv/search), um herauszufinden, wie Sie diese Anforderungen erfüllen können.
  
## <a name="a-quick-overview"></a>Kurze Übersicht

Skype for Business bringt Sie mit Kollegen oder Geschäftspartnern im eigenen Unternehmen oder in aller Welt in Verbindung.
  
Mit Skype for Business haben Sie folgende Möglichkeiten:
  
- Unterhaltungen mit Chat, Sprach- oder Videoanrufen beginnen
    
- Sehen, wenn Ihre Kontakte online verfügbar sind, in einer Besprechung sind oder eine Präsentation halten
    
- Hohe Sicherheit für Besprechungen festlegen
    
- Onlineübertragungen für ein großes Publikum
    
- In Besprechungen Ihren Bildschirm präsentieren oder anderen die Steuerung übergeben
    
- Skype for Business in anderen Office-Programmen verwenden, um mit nur einem Klick zu chatten, einen Anruf zu tätigen oder an einer Besprechung teilzunehmen
    
## <a name="why-is-this-all-so-important"></a>Warum sind alle diese Punkte so wichtig?

Die Qualität der End-to-End-Netzwerkkonnektivität hat großen Einfluss auf die Qualität von Echtzeitmedien (Audio, Video und Anwendungsfreigabe) über IP. Für optimale Medienqualität in Skype for Business Online benötigen Sie eine Verbindung von hoher Qualität zwischen Ihrem Unternehmensnetzwerk und Skype for Business Online. Am besten orientieren Sie sich beim Einrichten der Konnektivität zwischen dem internen Netzwerk und der Cloud an der Kapazität des Netzwerks, damit auch Spitzendatenaufkommen für Skype for Business Online über alle Verbindungen kein Problem darstellen.
  
Wenn Sie mit einem [Microsoft-Partner](https://partnercenter.microsoft.com/en-us/pcv/search)zusammenarbeiten, können Sie eine Vielzahl von Office 365-Anwendungen, einschließlich Skype for Business Online in der Cloud, an Ihr Netzwerk anschließen, und in Echtzeit sprach-und Video Kommunikationsfunktionen für Skype for Business require-Netzwerk Dienste müssen speziell für die Unterstützung dieser Office 365-Echt Zeit Arbeitslasten konfiguriert sein. Dazu gehören ein Netzwerk mit ausreichend Bandbreite für die Übertragung des erforderlichen Datenverkehrsvolumens und Unterstützung für eine Dienstqualität (Quality of Service, QoS), die Ihren Benutzern eine Erfahrung der Unternehmensklasse bietet.
  
Neben den hier genannten Informationen gibt es weitere Ressourcen, mit deren Hilfe Sie Skype for Business Online-Dienste und -Funktionen erfolgreich planen und bereitstellen können. Außerdem können Sie sicherstellen, dass Ihre Netzwerkdienste diese Anforderungen erfüllen:
  
- [Anruffluss mit ExpressRoute](call-flow-using-expressroute.md)
    
- [ExpressRoute und QoS in Skype for Business Online](expressroute-and-qos-in-skype-for-business-online.md)
    
- [Medienqualität und Leistung der Netzwerkkonnektivität in Skype for Business Online](media-quality-and-network-connectivity-performance.md)
    
## <a name="implement-quality-of-service-qos-for-skype-for-business"></a>Implementieren von Quality of Service (QoS) für Skype for Business

Betrachten Sie vor dem Wechsel zu Skype for Business Online die Verarbeitungskapazität Ihres Netzwerks für den Datenverkehr von Audio-, Video- und Freigabesitzungen. Wie für andere Office 365-Dienste hat Microsoft den [Skype for Business-Bandbreitenrechner](https://www.microsoft.com/en-us/download/details.aspx?id=19011) als Download zur Verfügung gestellt. Mit seiner Hilfe können Sie den erforderlichen Netzwerkdatenverkehr für jeden Ihrer Unternehmensstandorte ermitteln. Erstellen Sie Nutzungsmodelle, einschließlich Modellen der Medienflüsse des Datenverkehrs bei der Echtzeitkommunikation und der Menge des Skype for Business-Datenverkehrs pro Firmenstandort. Berechnen Sie das Datenaufkommen, und analysieren Sie, wie sich dieser Datenverkehr auf das Gesamtnetzwerk auswirkt. Anschließend können Sie der Analyse dieser Daten Empfehlungen für Verbesserungsmöglichkeiten im Netzwerk und für die Warteschlangengröße entnehmen. Diese ermöglichen es Ihnen, den Endbenutzern hohe Benutzerfreundlichkeit zu bieten.
  
Der Echtzeit-Datenverkehr von Skype for Business reagiert empfindlich auf Paketverluste, Verzögerungen und Jitter, die in überlasteten Netzwerken häufig auftreten. Quality of Service (QoS) - manchmal auch Class of Service genannt - muss in verwalteten externen WANs, verwalteten internen LANs und unternehmensbasierten WLANs ebenfalls bereitgestellt werden. Auf diese Weise können Sie den Echtzeit-Datenverkehr von Skype for Business wie beispielsweise Audio und Video gegenüber anderem Nicht-Echtzeit-Datenverkehr in lokalen Netzwerken und über WAN priorisieren und damit die Benutzerfreundlichkeit für die Endbenutzer erhöhen.
  
Skype for Business-Audio muss in der EF-Warteschlange (Expedited Forwarding - DSCP 46) und Skype for Business-Video in der AF41-Warteschlange (Assured Forwarding - DSCP 34) bereitgestellt werden. Dies gilt auch für Peer-zu-Peer- und Konferenzdatenverkehr, unabhängig davon, ob Telefonsysteme in Office 365 oder andere Telefoniefunktionen bereitgestellt werden.
  
Während möglicherweise im LAN und WAN bereits vorhandene QoS-Richtlinien für andere IP-Telefonieprodukte gelten, können Benutzer mit Skype for Business mobil bleiben und bei der Verwendung des Produkts den Standort wechseln. Daher müssen QoS-Richtlinien im LAN, im WAN und in Funknetzwerken gekennzeichnet sein, um sicherzustellen, dass der gesamte Skype for Business-Datenverkehr über verwaltete Netzwerke priorisiert wird.
  
Laden Sie als Unterstützung bei der Dimensionierung des Netzwerks den [Skype for Business-Bandbreitenrechner](https://www.microsoft.com/en-us/download/details.aspx?id=19011) herunter.
  
Weitere Informationen zur Medienqualität und zu QoS finden Sie unter [Medienqualität und Leistung der Netzwerkkonnektivität in Skype for Business Online](media-quality-and-network-connectivity-performance.md).
  
Weitere Informationen zum Einrichten und Verwalten von QoS finden Sie unter [Verwalten von Quality of Service](https://technet.microsoft.com/en-us/library/gg425841.aspx).
  
## <a name="bypass-proxies-and-wan-optimization-devices"></a>Umgehen von Proxys und WAN-Optimierungsgeräten

Alle Komponenten von Office 365 einschließlich Skype for Business Online sind verschlüsselt und können in der Regel von Proxygeräten nicht untersucht werden. Aus diesem Grund empfehlen wir die Umgehung von Proxygeräten für den gesamten Office 365-Netzwerkverkehr. Dieser ist definiert als Verbindungen, die Ihre Benutzer mit [URLs und IP-Adressbereiche von Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) herstellen. Da Proxygeräte wahrscheinlich zu Verzögerungen bei Echtzeit-Medienströmen von Skype for Business Online führen, empfehlen wir dringend, zumindest für diesen Datenverkehr Proxygeräte zu umgehen.
  
Microsoft empfiehlt, Office 365-URLs mithilfe von PAC-Dateien auszuschließen, um Office 365-Datenverkehr an eine Firewall zu senden.
  
Die folgenden verfügbaren Ressourcen können ebenfalls hilfreich sein:
  
- [Office 365-Leistung optimieren mit Basisplänen und Leistungsverlauf ](https://support.office.com/article/1492cb94-bd62-43e6-b8d0-2a61ed88ebae)
    
- [Netzwerk- und Migrationsplanung für Office 365](https://support.office.com/article/f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132)
    
- [Proxy-PAC-Generator für Office 365](https://gallery.technet.microsoft.com/Office-365-Proxy-Pac-60fb28f7)
    
- [Verwenden von WAN-Optimierungscontroller- oder Datenverkehrsuntersuchungsgeräten mit Office 365](https://aka.ms/kb2690045)
    
- [Routing mit ExpressRoute für Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)
    
## <a name="bypass-double-encryption"></a>Umgehen der doppelten Verschlüsselung

Um Benutzern bestmögliche Audio- und Videofunktionen bereitzustellen, müssen Sie eine Lösung implementieren, die verhindert, dass Skype for Business-Medien (Audio und Video) einen VPN-Tunnel (virtuelles privates Netzwerk) durchlaufen. Der gesamte Skype for Business-Datenverkehr wird mit TLS (Transport Layer Security) verschlüsselt, und die Medienarbeitsauslastungen werden mit SRTP (Secure Real Time Protocol) verschlüsselt. Die Signale werden mit TLS verschlüsselt und die Medienarbeitsauslastungen mit SRTP. Durch das Senden dieses Datenverkehrs durch den VPN-Tunnel entstehen eine zusätzliche Verschlüsselungsschicht sowie zusätzliche Netzwerk-Hops zwischen dem Client und Office 365. Beides kann zu einer Beeinträchtigung der Sitzung führen, da Jitter, Paketverluste und Latenz erhöht werden.
  
Getrenntes Tunneln ist eine Möglichkeit, mit der Sie verhindern können, dass der Skype for Business-Datenverkehr den VPN-Tunnel durchläuft. Kunden, die getrenntes Tunneln implementieren möchten, sollten sich bei ihrem VPN-Anbieter erkundigen, wie sie dazu in ihrer Software vorgehen müssen.
  
> [!NOTE]
> Dies ist nur für die Skype for Business-Medienarbeitsauslastungen erforderlich und gilt nicht für andere Office 365-Dienste. 
  
Zusätzliche Ressourcen:
  
- [Ermöglichen, dass Lync-Medien einen VPN-Tunnel umgehen](https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/)
    
- [Weitere Informationen zu DirectAccess, getrenntem Tunneln und Tunnelerzwingung](https://blogs.technet.com/b/tomshinder/archive/2010/03/30/more-on-directaccess-split-tunneling-and-force-tunneling.aspx)
    
- [Aktivieren von DirectAccess](https://technet.microsoft.com/en-us/library/jj574163.aspx)
    
## <a name="ensure-the-right-ports-and-protocols-are-open"></a>Sicherstellen, dass die richtigen Ports und Protokolle geöffnet sind

Kunden müssen die Erreichbarkeit der für den O365-Dienst erforderlichen URLs und IP-Adressen sicherstellen. Eine vollständige Liste aller IP-Adressen und URLs für Skype for Business Online finden Sie unter [URLs und IP-Adressbereiche von Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).
  
Skype for Business-Clients verwenden eine Vielzahl von Ports und Protokollen. Richtung und Fluss des Netzwerkdatenverkehrs für eine Skype for Business-Sitzung hängen von der Art der Interaktionen (Peer-zu-Peer oder mehrere Teilnehmer) sowie von der Verwendung von Inhaltsfreigabe und VoIP/Video ab. Sie müssen die Liste der Ports und Protokolle überprüfen und öffnen. Achten Sie dabei besonders auf die Quell- und Zielports. So verwendet zum Beispiel Audiodatenverkehr nur 20 Ports (50000-50019 TCP/UDP) auf der Clientseite, während der Zielport auf der Dienstseite in einem 10.000 umfassenden Portbereich (50000-59999 TCP/UDP) liegen kann. Dabei müssen Sie auch TCP 443 und UDP 3478 in der Firewall öffnen.
  
Für die Unterstützung von Skype for Business Online müssen Sie möglicherweise zusätzliche Konfigurationen im Netzwerk vornehmen.
  
  
## <a name="use-phones-and-devices-optimized-for-skype-for-business"></a>Verwenden von Telefonen und Geräten, die für Skype for Business optimiert sind

In einer Echtzeitmedien-Sitzung haben die von allen Teilnehmern verwendeten Mediengeräte, zum Beispiel Headsets und Webcams, großen Einfluss auf die allgemeine Audio- und Videoqualität. Geräte mit niedrigerer Qualität oder Geräte mit falschen Gerätetreibern führen zu einer niedrigeren Gesamtklang Qualität für Audio und zu einer niedrigeren Bildqualität für Video. Zertifizierte Geräte oder Geräte von hoher Qualität dagegen verbessern Echounterdrückung, Rauschunterdrückung und Videoauflösung und verringern die Latenz.
  
Telefone und Geräte haben großen Einfluss auf die Audio- und Videoqualität für Endbenutzer. Das Skype for Business-Zertifizierungsprogramm ist eine Weiterentwicklung des „Lync Compatible"-Programms und bestätigt, dass das jeweilige Gerät den Microsoft-Standards für Audio und Video entspricht. Es gibt zahlreiche IP-Telefone, USB-Audio- und -Videogeräte, PCs und Geräte für Besprechungsräume, die von Microsoft getestet und für geeignet befunden wurden. Sehen Sie sich die Liste der für Skype for Business optimierten Geräte an, und stellen Sie verschiedene Geräte bereit, um den vielfältigen Anforderungen und persönlichen Vorlieben der Endbenutzer in der Organisation gerecht zu werden.
  
In den folgenden Artikeln finden Sie weitere Informationen zu unterstützten und zertifizierten Geräten:  
  
- [Kauf von Telefonen für Skype for Business Online](../what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)
    
- [Telefone und Geräte für Skype for Business](https://technet.microsoft.com/en-us/office/dn947482.aspx)
    
- [Lösungskatalog für persönliche Peripheriegeräte](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)
    
- [Für Microsoft Lync geeignete Telefone und Geräte](https://technet.microsoft.com/en-us/office/dn788944.aspx)
    
Die Umgebung und das Umfeld, in dem sich Nutzer treffen und Audio- und Videogeräte verwenden, stellen ebenfalls einen wichtigen Faktor für die Audio- und Videoqualität dar. Nutzer, die aus einer lauten Umgebung anrufen, hören gedämpften und undeutlichen Ton mit Echos. Nutzer in einer dunklen oder lichtarmen Umgebung können keine hellen und scharfen Videos erzeugen. In einem Konferenzraum wirkt sich die Position des Mikrofons und des Videogeräts direkt auf die Ton- und Bildqualität für die Teilnehmer aus.
  
Wenn Sie ein klareres Bild von der Audio-und Videoqualität eines Benutzers erhalten möchten, verwenden Sie **** > das Skype for Business-APP-**options** > **-Audiogerät oder-** **Videogerät** , um Änderungen am verwendeten Gerät vorzunehmen und die Einstellungen anzupassen. Sie können die Audioqualität eines Anrufs auch überprüfen, indem Sie auf **Anrufqualität überprüfen**klicken. If they click **Check Call Quality**, they can then report the quality and issues found with the test call.
  
![Testing audio in the Skype for Business client.](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)
  
## <a name="related-topics"></a>Verwandte Themen 

[ExpressRoute und QoS in Skype for Business Online](expressroute-and-qos-in-skype-for-business-online.md)
  
  
 
