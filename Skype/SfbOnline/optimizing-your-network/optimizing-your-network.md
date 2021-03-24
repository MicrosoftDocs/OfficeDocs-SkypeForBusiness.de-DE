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
f1.keywords:
- NOCSH
ms.custom:
- Optimization
description: Die folgenden Anforderungen sind wichtig, um langfristig die Integrität und die erfolgreiche Nutzung aller Skype for Business Online-Funktionen sicherzustellen, die Sie für Ihre Organisation einrichten. Wir wissen, dass einige von Ihnen technisch sehr versiert sind. An Sie richtet sich dieses Dokument. Andere jedoch sind auf diesem Gebiet weniger erfahren. Wenn Sie Hilfe beim Einrichten von Skype for Business Online benötigen, lesen Sie dieses Dokument, um sich mit den Dingen vertraut zu machen, die Sie berücksichtigen müssen. Außerdem erhalten Sie Anhaltspunkte für Gespräche mit dem Microsoft FastTrack Center, Ihren Microsoft Services-Teams und Account-Teams oder mit Microsoft-Partnern, um herauszufinden, wie Sie diese Anforderungen erfüllen können.
ms.openlocfilehash: ece99899400d8fca063f9b28c868ba94d4f72b99
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100681"
---
# <a name="optimizing-your-network-for-skype-for-business-online"></a>Optimieren Ihres Netzwerks für Skype for Business Online

Die folgenden Anforderungen sind wichtig, um langfristig die Integrität und die erfolgreiche Nutzung aller Skype for Business Online-Funktionen sicherzustellen, die Sie für Ihre Organisation einrichten. Wir wissen, dass einige von Ihnen technisch sehr versiert sind. An Sie richtet sich dieses Dokument. Andere jedoch sind auf diesem Gebiet weniger erfahren. Wenn Sie Hilfe beim Einrichten von Skype for Business Online benötigen, lesen Sie dieses Dokument, um sich mit den Dingen vertraut zu machen, die Sie berücksichtigen müssen. Außerdem erhalten Sie Anhaltspunkte für Gespräche mit dem [Microsoft FastTrack Center](https://fasttrack.microsoft.com/office), Ihren Microsoft Services-Teams und Account-Teams oder mit [Microsoft-Partnern](https://partnercenter.microsoft.com/pcv/search), um herauszufinden, wie Sie diese Anforderungen erfüllen können.

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

In Zusammenarbeit [](https://partnercenter.microsoft.com/pcv/search)mit einem Microsoft-Partner können Sie eine Vielzahl von Microsoft 365- oder Office 365-Anwendungen, einschließlich Skype for Business Online in der Cloud, mit Ihrem Netzwerk verbinden, und Die Sprach- und Videokommunikationsfunktionen in Echtzeit für Skype for Business erfordern, dass Netzwerkdienste speziell für die Unterstützung dieser Microsoft 365- und Office 365-Echtzeitarbeitsauslastungen konfiguriert werden müssen. Dazu gehören ein Netzwerk mit ausreichend Bandbreite für die Übertragung des erforderlichen Datenverkehrsvolumens und Unterstützung für eine Dienstqualität (Quality of Service, QoS), die Ihren Benutzern eine Erfahrung der Unternehmensklasse bietet.

Neben den hier genannten Informationen gibt es weitere Ressourcen, mit deren Hilfe Sie Skype for Business Online-Dienste und -Funktionen erfolgreich planen und bereitstellen können. Außerdem können Sie sicherstellen, dass Ihre Netzwerkdienste diese Anforderungen erfüllen:

- [Anruffluss mit ExpressRoute](call-flow-using-expressroute.md)

- [ExpressRoute und QoS in Skype for Business Online](expressroute-and-qos-in-skype-for-business-online.md)

- [Medienqualität und Leistung der Netzwerkkonnektivität in Skype for Business Online](media-quality-and-network-connectivity-performance.md)

## <a name="implement-quality-of-service-qos-for-skype-for-business"></a>Implementieren von Quality of Service (QoS) für Skype for Business

Vor dem Wechsel zu Skype for Business Online sollten Sie sich die Kapazität Ihres Netzwerks zur Verarbeitung von Audio-, Video- und Freigabesitzungsverkehr ansehen. Wie bei anderen Microsoft 365- und Office 365-Diensten steht Microsoft zum Herunterladen des Skype for Business-Bandbreitenrechners zur Verfügung, mit dem der erforderliche Netzwerkdatenverkehr für jede Ihrer Unternehmenswebsites ermittelt wird. [](https://www.microsoft.com/download/details.aspx?id=19011) Sie sollten Nutzungsmodellierung durchführen, einschließlich der Modellierung von Medienflüssen im Echtzeitkommunikationsverkehr und der Menge des Skype for Business-Datenverkehrs pro Unternehmensstandort, der Berechnung des Datenverkehrsvolumens und der Analyse, wie sich dieser Datenverkehr auf Ihr gesamtes Netzwerk aus wirkt. Nachdem Sie dies getan haben, sollte die Analyse dieser Daten Empfehlungen enthalten, wo Ihr Netzwerk verbessert werden muss, und Warteschlangengrößen empfehlen, um eine hervorragende Endbenutzererfahrung zu bieten.

Der Echtzeit-Datenverkehr von Skype for Business reagiert empfindlich auf Paketverluste, Verzögerungen und Jitter, die in überlasteten Netzwerken häufig auftreten. Quality of Service (QoS) - manchmal auch Class of Service genannt - muss in verwalteten externen WANs, verwalteten internen LANs und unternehmensbasierten WLANs ebenfalls bereitgestellt werden. Auf diese Weise können Sie den Echtzeit-Datenverkehr von Skype for Business wie beispielsweise Audio und Video gegenüber anderem Nicht-Echtzeit-Datenverkehr in lokalen Netzwerken und über WAN priorisieren und damit die Benutzerfreundlichkeit für die Endbenutzer erhöhen.

Skype for Business-Audio muss in der EF-Warteschlange (Expedited Forwarding - DSCP 46) und Skype for Business-Video in der AF41-Warteschlange (Assured Forwarding - DSCP 34) bereitgestellt werden. Dies gilt auch für Peer-to-Peer- und Konferenzdatenverkehr, unabhängig davon, ob Telefonsystem in Microsoft 365 oder Office 365 oder andere Telefoniefeatures bereitgestellt werden.

Während möglicherweise im LAN und WAN bereits vorhandene QoS-Richtlinien für andere IP-Telefonieprodukte gelten, können Benutzer mit Skype for Business mobil bleiben und bei der Verwendung des Produkts den Standort wechseln. Daher müssen QoS-Richtlinien im LAN, im WAN und in Funknetzwerken gekennzeichnet sein, um sicherzustellen, dass der gesamte Skype for Business-Datenverkehr über verwaltete Netzwerke priorisiert wird.

Laden Sie als Unterstützung bei der Dimensionierung des Netzwerks den [Skype for Business-Bandbreitenrechner](https://www.microsoft.com/download/details.aspx?id=19011) herunter.

Weitere Informationen zur Medienqualität und zu QoS finden Sie unter [Medienqualität und Leistung der Netzwerkkonnektivität in Skype for Business Online](media-quality-and-network-connectivity-performance.md).

Weitere Informationen zum Einrichten und Verwalten von QoS finden Sie unter [Verwalten von Quality of Service](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md).

## <a name="bypass-proxies-and-wan-optimization-devices"></a>Umgehen von Proxys und WAN-Optimierungsgeräten

Alle Microsoft 365- oder Office 365-Geräte, einschließlich Skype for Business Online, sind verschlüsselt und können normalerweise nicht von Proxygeräten überprüft werden. Aus diesen Gründen wird empfohlen, Proxygeräte für den ganzen Microsoft 365- und Office 365-Netzwerkdatenverkehr zu umgehen, die als Verbindungen definiert sind, die Ihre Benutzer mit [Office 365-URLs](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)und IP-Adressbereichen herstellen. Da Proxygeräte wahrscheinlich Verzögerungen bei Skype for Business Online-Medienstreams in Echtzeit mit sich bringen, empfehlen wir dringend, Proxygeräte für diesen Datenverkehr mindestens zu umgehen.

Microsoft empfiehlt, URLs von Microsoft 365 und Office 365 mit PAC-Dateien zu ausschließen, um Microsoft 365- und Office 365-Datenverkehr an eine Firewall zu senden.

Die folgenden verfügbaren Ressourcen können ebenfalls hilfreich sein:

- [Microsoft 365- oder Office 365-Leistungsoptimierung mithilfe von Basiswerten und Leistungsverlauf](https://support.office.com/article/1492cb94-bd62-43e6-b8d0-2a61ed88ebae)

- [Netzwerk- und Migrationsplanung für Microsoft 365 oder Office 365](https://support.office.com/article/f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132)

- [Proxy-PAC-Generator für Office 365](https://gallery.technet.microsoft.com/Office-365-Proxy-Pac-60fb28f7)

- [Verwenden von WAN-Optimierungscontrollern oder Datenverkehrs-/Inspektionsgeräten mit Microsoft 365 oder Office 365](/office365/troubleshoot/miscellaneous/office-365-third-party-network-devices)

- [Routing mit ExpressRoute für Microsoft 365 oder Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)

## <a name="bypass-double-encryption"></a>Umgehen der doppelten Verschlüsselung

Um Benutzern die bestmögliche Audio- und Videoerfahrung zu bieten, müssen Sie eine Lösung implementieren, die verhindert, dass Skype for Business-Medien (Audio und Video) einen VPN(Virtual Private Network)-Tunnel durchlaufen. Der ganze Skype for Business-Datenverkehr wird mit Transport Layer Security (TLS) verschlüsselt, und die Medienarbeitslasten werden mit Secure Real Time Protocol (SRTP) verschlüsselt. Die Signalisierung wird mit TLS verschlüsselt, und die Medienarbeitslasten werden mit SRTP verschlüsselt. Durch das Senden dieses Datenverkehrs über den VPN-Tunnel wird eine zusätzliche Verschlüsselungsebene und zusätzliche Netzwerkhops zwischen dem Client und Microsoft 365 oder Office 365 hinzugefügt, die beide zu einer beeinträchtigten Sitzung führen können, da dadurch Jitter, Paketverlust und Latenz erhöht werden.

Getrenntes Tunneln ist eine Möglichkeit, mit der Sie verhindern können, dass der Skype for Business-Datenverkehr den VPN-Tunnel durchläuft. Kunden, die getrenntes Tunneln implementieren möchten, sollten sich bei ihrem VPN-Anbieter erkundigen, wie sie dazu in ihrer Software vorgehen müssen.

> [!NOTE]
> Dies ist nur für die Medienarbeitslasten von Skype for Business erforderlich und gilt nicht für andere Microsoft 365- oder Office 365-Dienste.

Zusätzliche Ressourcen:

- [Ermöglichen, dass Lync-Medien einen VPN-Tunnel umgehen](https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/)

- [Weitere Informationen zu DirectAccess, getrenntem Tunneln und Tunnelerzwingung](/archive/blogs/tomshinder/more-on-directaccess-split-tunneling-and-force-tunneling)

- [Aktivieren von DirectAccess](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj574163(v=ws.11))

## <a name="ensure-the-right-ports-and-protocols-are-open"></a>Sicherstellen, dass die richtigen Ports und Protokolle geöffnet sind

Kunden müssen die Erreichbarkeit der URLs und IP-Adressen sicherstellen, die für den Microsoft 365- oder Office 365-Dienst erforderlich sind. Eine vollständige Liste aller IP-Adressen und URLs für Skype for Business Online finden Sie unter [URLs und IP-Adressbereiche von Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).

Skype for Business-Clients verwenden eine Vielzahl von Ports und Protokollen. Richtung und Fluss des Netzwerkdatenverkehrs für eine Skype for Business-Sitzung hängen von der Art der Interaktionen (Peer-zu-Peer oder mehrere Teilnehmer) sowie von der Verwendung von Inhaltsfreigabe und VoIP/Video ab. Sie müssen die Liste der Ports und Protokolle überprüfen und öffnen. Achten Sie dabei besonders auf die Quell- und Zielports. So verwendet zum Beispiel Audiodatenverkehr nur 20 Ports (50000-50019 TCP/UDP) auf der Clientseite, während der Zielport auf der Dienstseite in einem 10.000 umfassenden Portbereich (50000-59999 TCP/UDP) liegen kann. Dabei müssen Sie auch TCP 443 und UDP 3478 in der Firewall öffnen.

Für die Unterstützung von Skype for Business Online müssen Sie möglicherweise zusätzliche Konfigurationen im Netzwerk vornehmen.


## <a name="use-phones-and-devices-optimized-for-skype-for-business"></a>Verwenden von Telefonen und Geräten, die für Skype for Business optimiert sind

In einer Echtzeitmedien-Sitzung haben die von allen Teilnehmern verwendeten Mediengeräte, zum Beispiel Headsets und Webcams, großen Einfluss auf die allgemeine Audio- und Videoqualität. Geräte mit geringerer Qualität oder Geräte mit falschen Gerätetreibern führen zu einer geringeren Gesamtsoundqualität für Audio und zu einer geringeren Bildqualität für Video. Zertifizierte Geräte oder Geräte von hoher Qualität dagegen verbessern Echounterdrückung, Rauschunterdrückung und Videoauflösung und verringern die Latenz.

Telefone und Geräte haben großen Einfluss auf die Audio- und Videoqualität für Endbenutzer. Das Skype for Business-Zertifizierungsprogramm ist eine Weiterentwicklung des „Lync Compatible"-Programms und bestätigt, dass das jeweilige Gerät den Microsoft-Standards für Audio und Video entspricht. Es gibt zahlreiche IP-Telefone, USB-Audio- und -Videogeräte, PCs und Geräte für Besprechungsräume, die von Microsoft getestet und für geeignet befunden wurden. Sehen Sie sich die Liste der für Skype for Business optimierten Geräte an, und stellen Sie verschiedene Geräte bereit, um den vielfältigen Anforderungen und persönlichen Vorlieben der Endbenutzer in der Organisation gerecht zu werden.

In den folgenden Artikeln finden Sie weitere Informationen zu unterstützten und zertifizierten Geräten:  

- [Kauf von Telefonen für Skype for Business Online](../what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)

- [Telefone und Geräte für Skype for Business](../../SfbPartnerCertification/certification/devices-ip-phones.md)

- [Lösungskatalog für persönliche Peripheriegeräte](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

- [Für Microsoft Lync geeignete Telefone und Geräte](../../SfbPartnerCertification/lync-cert/ip-phones.md)

Die Umgebung und das Umfeld, in dem sich Nutzer treffen und Audio- und Videogeräte verwenden, stellen ebenfalls einen wichtigen Faktor für die Audio- und Videoqualität dar. Nutzer, die aus einer lauten Umgebung anrufen, hören gedämpften und undeutlichen Ton mit Echos. Nutzer in einer dunklen oder lichtarmen Umgebung können keine hellen und scharfen Videos erzeugen. In einem Konferenzraum wirkt sich die Position des Mikrofons und des Videogeräts direkt auf die Ton- und Bildqualität für die Teilnehmer aus.

Um ein übersichtlicheres Bild der Audio- und Videoerfahrung eines Benutzers zu erhalten, verwenden Sie die Skype for **Business-App-Tools** Optionen  >    >  **Audiogerät** oder **Videogerät,** um Änderungen am verwendeten Gerät vorzunehmen und seine Einstellungen anzupassen. Sie können auch die Audioqualität eines Anrufs überprüfen, indem Sie **auf Anrufqualität überprüfen klicken.** Wenn sie auf **Anrufqualität überprüfen** klicken, können sie die Qualität und probleme melden, die beim Testanruf gefunden wurden.

![Testing audio in the Skype for Business client.](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)

## <a name="related-topics"></a>Verwandte Themen

[ExpressRoute und QoS in Skype for Business Online](expressroute-and-qos-in-skype-for-business-online.md)