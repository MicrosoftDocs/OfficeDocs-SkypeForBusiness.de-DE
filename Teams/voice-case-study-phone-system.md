---
title: Teams Fallstudie zu Contoso Voice
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams Voice Case Study for multi-national corporation
appliesto:
- Microsoft Teams
ms.openlocfilehash: 995b4ddf9c07dea57c8d4de9940776d5137c2d02
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101031"
---
# <a name="contoso-case-study-phone-system"></a>Contoso-Fallstudie: Telefonsystem

Je nach geografischem Standort und anderen Faktoren hatte Contoso Niederlassungen, die die folgenden Telefonielösungen verwendeten:

- Websitetyp A: Skype for Business Enterprise-VoIP

- Websitetyp B: Traditionelle Telefoniesysteme

- Websitetyp C: Eine Kombination aus Skype for Business Enterprise-VoIP herkömmlichen Telefoniesystemen


Zum Implementieren einer Microsoft-Telefon-Systemlösung für die gesamte Organisation musste Contoso für jeden Websitetyp bestimmen, welche der folgenden Optionen mit Telefonsystem verwendet werden würde, um eine Verbindung mit dem Public &mdash; &mdash; Switched Telephone Network (PSTN) herzustellen:

- Telefonsystem mit Anrufplan 

- Telefonsystem mit einem eigenen PSTN-Netzbetreiber über Direct-Routing 

- Kombination aus Telefonsystem Anrufplan und Telefonsystem einem eigenen PSTN-Netzbetreiber über Direct-Routing
 
Um die richtige Lösung für ihre Organisation zu finden, verwendete Contoso [Telefonielösungen](/SkypeForBusiness/hybrid/msft-telephony-solutions) von Microsoft und die Ignite 2019-Sitzung Anrufe [in Microsoft Teams.](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions)  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a>Websitetyp A: Skype for Business Enterprise-VoIP 

Contoso Skype for Business Enterprise-VoIP wurde als Hub eingerichtet und sprach. Es gab einen zentralen Speicherort, an dem das PSTN-Gateway in der Region verwaltet wurde, von der die Verbindung mit dem PSTN für die Skype for Business Enterprise-VoIP im Land bereitgestellt wurde. Oft hatten diese Satellitenniederlassungen keinen eigenen Internet-Egress. Die Nummern für diese Benutzer befinden sich auf dem SIP-Trunk, der mit einem vorhandenen SBC verbunden ist. 

Um festzustellen, ob der SBC bereits für Direct-Routing und Medienumgehung zertifiziert ist, überprüfte Contoso die Liste der [Session Border Controller,](direct-routing-border-controllers.md)die für Direct Routing zertifiziert sind.  

Die Wählgewohnheiten des Benutzers waren, einen Benutzer mit einem älteren Telefoniesystem mit einer Erweiterung zu wählen, auch wenn der Benutzer über einen Skype for Business-Client für Peer-to-Peer-Audio verfügt. 

Contoso basierte auf der Entscheidung auf den folgenden Fragen:

- F. Müssen die von der lokalen Bereitstellung bereitgestellten Funktionen erhalten bleiben?<br>
  A. Nein 

- F. Müssen wir mit PbX-Systemen von Drittanbietern und anderen Telefoniegeräten zusammenarbeiten?<br>
  A. Nein 

- F. Müssen wir unseren aktuellen Drittanbieter beibehalten?<br> A. Ja (regulierte Länder) und Nein 

- F. Müssen wir den ROI für SBCs bereitstellen lassen?<br> A. Ja und Nein  

- F. Sind Microsoft PSTN-Anrufpläne in dieser Region verfügbar?<br> A. Ja und Nein 

Basierend auf den Antworten auf die Fragen hat sich Contoso für die folgenden Lösungen entschieden:

- Verschieben Sie die Benutzer, die sich in einer Region befinden, in der PSTN-Anrufpläne verfügbar sind, Telefonsystem Anrufpläne zu verwenden. 

- Verschieben Sie die Benutzer, die sich nicht in einer Region befinden, in der PSTN-Anrufpläne verfügbar sind, Benutzer an einem Standort, auf dem die ROI für die SBCs noch nicht erfüllt werden muss, und Benutzer, die sich in einem Land befinden, das über Telefoniebestimmungen verfügt, mit Direct Routing auf Telefonsystem. 

Das folgende Diagramm zeigt die anfängliche Bereitstellung Skype for Business Enterprise-VoIP und zeigt, wie diese Bereitstellung sowohl zu Microsoft-Anrufplänen als auch zu Direct-Routing migriert wurde:

![Diagramm, das die Vorher/Nach-Zustände zeigt](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a>Websitetyp B: Traditionelle Telefoniesysteme

Contoso hatte viele Niederlassungen, die alte Telefoniesysteme nutzten. Es gab eine Teilmenge von Benutzern, die eine E1.64-Telefonnummer hatten, während andere nur über eine Durchwahl hatten. Diese Nummern befinden sich auf dem TDM-Trunk zum PSTN-Gateway. Die Wählscheibe für Internetwebsites wurde konfiguriert, indem ein Websitecode vor der Durchwahl verwendet wurde, um zu bestimmen, wohin der Anruf geroutet werden soll. Die Wählgewohnheiten der Benutzer wählten durch eine Durchwahl.   

Contoso basierte auf der Entscheidung auf den folgenden Fragen:

- F. Müssen die von der lokalen Bereitstellung bereitgestellten Funktionen erhalten bleiben?<br>
  A. Nein 

- F. Müssen wir mit PbX-Systemen von Drittanbietern und anderen Telefoniegeräten zusammenarbeiten?<br> A. Ja

- F. Müssen wir unseren aktuellen Drittanbieter beibehalten?<br> A. Nein 

- F. Ist der Anrufplan von Microsoft PSTN in unserer Region verfügbar?<br> A. Ja und Nein 

Basierend auf den Antworten auf die Fragen hat sich Contoso für die folgenden Lösungen entschieden: 

- Verschieben Sie die Benutzer, die sich in einer Region befinden, in der PSTN-Anrufpläne verfügbar sind, Telefonsystem Anrufpläne zu verwenden. 

- Verschieben Sie die Benutzer, die sich nicht in einer Region befinden, in der PSTN-Anrufpläne verfügbar sind, Telefonsystem Direktes Routing zu verwenden. 

- Wiederherstellen einer PSTN-Verbindung mit kritischen analogen Geschäftsgeräten.

Die folgenden Diagramme zeigen die ursprüngliche Legacy-Systembereitstellung mit Remotestandorten und die Migration zu einer Direct-Routingbereitstellung mit lokaler Medienoptimierung:

**Ursprüngliche Legacybereitstellung**  
 ![ Diagramm, das die Vorher/Nach-Zustände zeigt](media/voice-case-study-2.png)


**Bereitstellung mit Direct Routing**

![Diagramm, das die Vorher/Nach-Zustände zeigt](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a>Websitetyp C: Kombination aus Skype for Business Enterprise-VoIP herkömmlichen Telefoniesystemen

Contoso Skype for Business Enterprise-VoIP die Nummern der Benutzer befinden sich auf dem SIP-Trunk zum SBC vom Netzbetreiber. Die Nummern für die herkömmlichen Telefoniesysteme befinden sich auf dem TDM-Trunk zum PSTN-Gateway.   

Contoso basierte auf der Entscheidung auf den folgenden Fragen:

- F. Müssen die von der lokalen Bereitstellung bereitgestellten Funktionen erhalten bleiben?<br>
  A. Nein 

- F. Müssen wir mit PbX-Systemen von Drittanbietern und anderen Telefoniegeräten zusammenarbeiten?<br> A. Nein 

- F. Müssen wir unseren aktuellen Drittanbieter beibehalten?<br> A. Nein 

- F. Müssen wir den ROI für SBCs bereitstellen lassen?<br> A. Ja und Nein  

- F. Ist der PstN-Anrufplan von Microsoft in dieser Region verfügbar?<br> A. Nein 

Auf der Grundlage der Antworten auf die Fragen hat Contoso folgende Punkte entschieden: 

- Für die älteren Telefoniebenutzer, die für Direct Routing aktiviert werden, hat Contoso die Nummern vom TDM-Trunk zum SIP Trunk für SBC portiert, da der SBC für Direct Routing zertifiziert ist. 

- Um eine Teilmenge der Benutzer zu Telefonsystem zu unterstützen und das Routing über das alte System fortgesetzt zu lassen, wurde das alte Telefoniesystem als nächster Wechsel zum SBC eingerichtet.   

- Zur Förderung der Änderung des Benutzerverhaltens und zum Entfernen der Abhängigkeit von der Wählhilfe zwischen und innerhalb des Standorts bietet Contoso eine Anleitung zur Verwendung von Teams für alle internen Anrufe.  

Die folgenden Diagramme zeigen die ursprüngliche Bereitstellung Skype for Business Enterprise-VoIP alten Telefoniesystems und die Migration zu einer gemischten Bereitstellung mithilfe von Direct Routing:

**Ursprüngliche gemischte Bereitstellung** 
 ![ Diagramm, das vor dem Zustand angezeigt wird](media/voice-case-study-4.png)

**Gemischte Bereitstellung mit Direct-Routing** 
 ![ Diagramm, das vor dem Zustand angezeigt wird](media/voice-case-study-4a.png)


## <a name="calling-plans"></a>Anrufpläne

Um die Konfigurationsanforderungen für Anrufpläne zu ermitteln, überprüfte Contoso die grundlegenden [Bereitstellungsentscheidungen für einen Anrufplan.](calling-plan-landing-page.md#core-deployment-decisions) Die daraus resultierenden Entscheidungen wurden getroffen: 

- F. Benötigen meine Benutzer Auslandsrufe?<br> A. Ja 

- F. Verfügen meine Benutzer jeweils über eine direkte nach innen gerichtete Telefonnummer?<br> A. Nicht heute. Alle aktivierten Benutzer erhalten eine Did-Funktion. 

- F. Möchte ich die Anrufer-ID maskieren oder deaktivieren?<br> A. Die Anrufer-ID für einen Benutzer wird für die lokale Nummer von Contoso maskiert. 


## <a name="direct-routing"></a>Direktes Routing

Contoso hat an der Ignite teilgenommen, um auf dem laufenden zu Office 365, einschließlich der features, die über Telefon-System und Direct-Routing verfügbar sind. Technische Führungskräfte und Architekten verwendeten die während der Ignite 2019 bereitgestellte Anleitung, um ihre Richtung zu bestimmen.  Verwendete Schlüsselsitzungen: 

- [Planen des Erfolgs mit Microsoft Teams Direct Routing](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [Updates für Direct-Routing](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a>Konfiguration

### <a name="calling-plans-sites"></a>Anrufpläne-Websites

Um Lizenzen zu erhalten und Benutzern Telefonnummern zuzuordnen, hat Contoso die Schritte unter Einrichten [von Anrufplänen befolgt.](set-up-calling-plans.md) 

Aufgrund der Anzahl der Benutzer, denen Telefonnummern zugewiesen werden mussten, hat Contoso sich entschieden, PowerShell zum Zuweisen der Telefonnummern zu verwenden. Um zu erfahren, wie Zahlen mithilfe von PowerShell zusätzlich zu anderen Einstellungen zugewiesen werden, verwendet Contoso die Teams &mdash; &mdash; [PowerShell Overview](teams-powershell-overview.md).  

### <a name="direct-routing-sites"></a>Direct Routing-Websites

Um die lokale Telefonieinfrastruktur von Contoso mit Microsoft Teams zu verbinden, hat der Administrator von Contoso die Schritte unter Konfigurieren von [Direct](direct-routing-configure.md) Routing befolgt und das Video [Direct Routing in Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) überprüft.  Contoso hat sich außerdem vom zertifizierten SBC-Anbieter auf die Dokumentation zur Direct-Routingbereitstellung verwiesen. 

Nachdem Direct Routing zwischen SBC und Microsoft-Telefon System konfiguriert wurde, musste Contoso die Konfiguration testen. Dazu haben die Contoso-Administratoren den SIP-Testerclient verwendet, der in der Sitzung Updates für [Direct-Routing bei Ignite 2019 besprochen wurde.](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions) Das Clientskript und die Dokumentation für SIP-Tester wurden aus dem PowerShell-Skript heruntergeladen, um die Verbindungen des Direct Routing Session Border Controller zu testen.   


### <a name="local-media-optimization"></a>Optimierung lokaler Medien

Contoso hatte Gelegenheit, die Optimierung lokaler Medien in den verschiedenen Regionen auf der ganzen Welt zu nutzen. Die unterstützten Szenarien für Contoso werden unter [Optimierung lokaler Medien für Direct-Routing beschrieben.](direct-routing-media-optimization.md) Die Konfiguration der lokalen Medienoptimierung wurde durch die Anleitung des SBC-Anbieters und von Microsoft abgeschlossen. Die Konfigurationsschritte für die Optimierung lokaler Medien umfassen Folgendes: 

- Konfigurieren der Benutzer- und SBC-Websites 

- Konfigurieren Sie den SBC gemäß der SBC-Anbieterspezifikation, 

- Hinzufügen von externen vertrauenswürdigen IP-Adressen zu jeder Website, die für die Optimierung lokaler Medien verwendet wird    

- Definieren der Netzwerktopologie 

- Definieren der virtuellen Netzwerktopologie 

- Bestimmen des Modus: Immer umgehen oder Nur für lokale Benutzer 

## <a name="networking-considerations"></a>Überlegungen zum Netzwerk

Contoso hatte eine Reihe von Benutzern, die für eine längere Zeit remote arbeiten mussten, nachdem sie für die Telefonsystem. Die Benutzer haben VPN für den Zugriff auf bestimmte Line of Business-Anwendungen verwendet. Bei der Verwendung von VPN Telefonsystem Benutzer eine Verschlechterung der Anrufqualität. 

Um das Qualitätsproblem zu beheben, hat Contoso VPN split tunneling implementiert, wodurch der Office 365-Datenverkehr das Internet durchlaufen konnte, während die Verbindung mit den internen Apps auf dem VPN übrig blieb. Um VPN Split Tunneling zu implementieren, folgen Sie den Anweisungen unter Implementieren von [geteilten VPN-Tunnels für Office 365.](/office365/enterprise/office-365-vpn-implement-split-tunnel)  

