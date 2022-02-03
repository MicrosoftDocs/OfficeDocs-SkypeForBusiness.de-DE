---
title: 'Contoso-Fallstudie: Telefonsystem für ein multinationales Unternehmen'
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
description: 'Teams Sprachfallstudie für multinationale Unternehmen: Telefonsystem'
appliesto:
- Microsoft Teams
ms.openlocfilehash: c83cd07cb8943c19b783658a15db99351d11f995
ms.sourcegitcommit: 8ddafd0901b6b4f4109f3b6e687ae7fae667d61c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2022
ms.locfileid: "62353370"
---
# <a name="contoso-case-study-phone-system-for-a-multi-national-corporation"></a>Contoso-Fallstudie: Telefonsystem für ein multinationales Unternehmen

Je nach geografischem Standort und anderen Faktoren verwendet Contoso Niederlassungen mit den folgenden Telefonielösungen:

- Websitetyp A: Skype for Business Enterprise-VoIP

- Websitetyp B: Traditionelle Telefoniesysteme

- Websitetyp C: Eine Kombination aus Skype for Business Enterprise-VoIP herkömmlichen Telefoniesystemen


Zum Implementieren einer Microsoft-Telefon-Systemlösung für die gesamte Organisation musste Contoso&mdash;&mdash; für jeden Websitetyp bestimmen, welche der folgenden Optionen mit Telefonsystem verwendet werden würde, um eine Verbindung mit dem Public Switched Telephone Network (PSTN) herzustellen:

- Telefonsystem mit Anrufplan 

- Telefonsystem mit einem eigenen PSTN-Netzbetreiber über Direct-Routing 

- Kombination aus Telefonsystem Anrufplan und Telefonsystem einem eigenen PSTN-Netzbetreiber über Direct-Routing
 
Um die richtige Lösung für ihre Organisation zu finden, hat [](/SkypeForBusiness/cloud-voice-landing-page) Contoso Ihre Teams-Sprachlösung und die Ignite 2019-Sitzung Anrufe [in Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a>Websitetyp A: Skype for Business Enterprise-VoIP 

Contoso Skype for Business Enterprise-VoIP wurde als Hub eingerichtet und sprach. Es gab einen zentralen Speicherort, an dem das PSTN-Gateway in der Region verwaltet wurde, von der die Verbindung mit dem PSTN für die Skype for Business Enterprise-VoIP im Land bereitgestellt wurde. Oft hatten diese Satellitenniederlassungen keinen eigenen Internet-Egress. Die Nummern für diese Benutzer befinden sich auf dem SIP-Trunk, der mit einem vorhandenen SBC verbunden ist. 

Um festzustellen, ob der bereits bereitgestellte SBC für Direct-Routing und Medienumgehung zertifiziert ist, überprüfte Contoso die Liste der Für Direct Routing zertifizierten Session [Border Controller](direct-routing-border-controllers.md).  

Die Wählgewohnheiten der Benutzer waren, einen Benutzer mit einem älteren Telefoniesystem mit einer Erweiterung zu wählen, auch wenn der Benutzer über einen Skype for Business-Client für Peer-zu-Peer-Audio verfügt. 

Contoso basierte auf der Entscheidung auf den folgenden Fragen:

- Q. Müssen die von der lokalen Bereitstellung bereitgestellten Funktionen erhalten bleiben?<br>
  A. Nein 

- Q. Müssen wir mit PbX-Systemen von Drittanbietern und anderen Telefoniegeräten zusammenarbeiten?<br>
  A. Nein 

- Q. Müssen wir unseren aktuellen Drittanbieter beibehalten?<br> A. Ja (regulierte Länder) und Nein 

- Q. Müssen wir den ROI für SBCs bereitstellen lassen?<br> A. Ja und Nein  

- Q. Sind Microsoft PSTN-Anrufpläne in dieser Region verfügbar?<br> A. Ja und Nein 

Basierend auf den Antworten auf die Fragen hat sich Contoso für die folgenden Lösungen entschieden:

- Verschieben Sie die Benutzer, die sich in einer Region befinden, in der PSTN-Anrufpläne verfügbar sind, Telefonsystem Anrufpläne zu verwenden. 

- Verschieben Sie die Benutzer, die sich nicht in einer Region befinden, in der PSTN-Anrufpläne verfügbar sind, Benutzer an einem Standort, auf dem die ROI für die SBCs noch nicht erfüllt werden muss, und Benutzer, die sich in einem Land befinden, in dem Telefoniebestimmungen gelten, mit Direct-Routing auf Telefonsystem. 

Das folgende Diagramm zeigt die anfängliche Bereitstellung Skype for Business Enterprise-VoIP und zeigt, wie diese Bereitstellung sowohl zu Microsoft-Anrufplänen als auch zu Direct-Routing migriert wurde:

![Diagramm zeigt die Vorher-/Nach-Zustände an.](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a>Websitetyp B: Traditionelle Telefoniesysteme

Contoso hatte viele Niederlassungen, die alte Telefoniesysteme nutzten. Es gab eine Teilmenge von Benutzern, die eine E1.64-Telefonnummer hatten, während andere nur eine Durchwahl hatten. Diese Nummern befinden sich auf dem TDM-Trunk zum PSTN-Gateway. Die Wählscheibe für  Internetwebsites wurde konfiguriert, indem ein Websitecode vor der Durchwahl verwendet wurde, um zu bestimmen, wohin der Anruf geroutet werden soll. Die Wählgewohnheiten der Benutzer wählten durch eine Durchwahl.   

Contoso basierte auf der Entscheidung auf den folgenden Fragen:

- Q. Müssen die von der lokalen Bereitstellung bereitgestellten Funktionen erhalten bleiben?<br>
  A. Nein 

- Q. Müssen wir mit PbX-Systemen von Drittanbietern und anderen Telefoniegeräten zusammenarbeiten?<br> A. Ja

- Q. Müssen wir unseren aktuellen Drittanbieter beibehalten?<br> A. Nein 

- Q. Ist der Anrufplan von Microsoft PSTN in unserer Region verfügbar?<br> A. Ja und Nein 

Basierend auf den Antworten auf die Fragen hat sich Contoso für die folgenden Lösungen entschieden: 

- Verschieben Sie die Benutzer, die sich in einer Region befinden, in der PSTN-Anrufpläne verfügbar sind, Telefonsystem Anrufpläne zu verwenden. 

- Verschieben Sie die Benutzer, die sich nicht in einer Region befinden, in der PSTN-Anrufpläne verfügbar sind, Telefonsystem direktes Routing zu verwenden. 

- Wiederherstellen einer PSTN-Verbindung mit kritischen analogen Geschäftsgeräten.

Die folgenden Diagramme zeigen die ursprüngliche Legacy-Systembereitstellung mit Remotestandorten und die Migration zu einer Direct-Routingbereitstellung mit lokaler Medienoptimierung:

**Ursprüngliche Legacybereitstellung** 
![ Ein Diagramm zeigt die Vorher-/Nach-Zustände an.](media/voice-case-study-2.png)


**Bereitstellung mit Direct Routing**

![Ein Diagramm mit den Vorher-/Nach-Zuständen.](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a>Site Type C: Combination of Skype for Business Enterprise-VoIP and traditional legacy telephony systems

Contoso Skype for Business Enterprise-VoIP benutzernummern befinden sich auf dem SIP-Trunk zum SBC vom Netzbetreiber. Die Nummern für die herkömmlichen Telefoniesysteme befinden sich auf dem TDM-Trunk zum PSTN-Gateway.   

Contoso basierte auf der Entscheidung auf den folgenden Fragen:

- Q. Müssen die von der lokalen Bereitstellung bereitgestellten Funktionen erhalten bleiben?<br>
  A. Nein 

- Q. Müssen wir mit PbX-Systemen von Drittanbietern und anderen Telefoniegeräten zusammenarbeiten?<br> A. Nein 

- Q. Müssen wir unseren aktuellen Drittanbieter beibehalten?<br> A. Nein 

- Q. Müssen wir den ROI für SBCs bereitstellen lassen?<br> A. Ja und Nein  

- Q. Ist der PstN-Anrufplan von Microsoft in dieser Region verfügbar?<br> A. Nein 

Auf der Grundlage der Antworten auf die Fragen hat Contoso folgende Punkte entschieden: 

- Für die älteren Telefoniebenutzer, die für Direct Routing aktiviert werden, hat Contoso die Nummern vom TDM-Trunk zum SIP Trunk für SBC portiert, da der SBC für Direct Routing zertifiziert ist. 

- Um eine Teilmenge der Benutzer zu Telefonsystem zu unterstützen und das fortgesetzte Routing über das alte System zu ermöglichen, wurde das alte Telefoniesystem als nächster Wechsel zum SBC eingerichtet.   

- Um Benutzerverhaltensänderung zu fördern und die Abhängigkeit von der Wählung zwischen und innerhalb der Standorterweiterung zu entfernen, bietet Contoso eine Anleitung zur Verwendung von Teams für alle internen Anrufe.  

Die folgenden Diagramme zeigen die ursprüngliche Bereitstellung Skype for Business Enterprise-VoIP alten Telefoniesystems und die Migration zu einer gemischten Bereitstellung mithilfe von Direct-Routing:

**Ursprüngliche gemischte Bereitstellung**
![ Diagramm 1 mit dem Zustand "Vorher".](media/voice-case-study-4.png)

**Gemischte Bereitstellung mit Direct-Routing**
![ Diagramm 2 mit dem Zustand "Vorher".](media/voice-case-study-4a.png)


## <a name="calling-plans"></a>Anrufpläne

Um die Konfigurationsanforderungen für Anrufpläne zu ermitteln, überprüfte Contoso die grundlegenden [Bereitstellungsentscheidungen für einen Anrufplan](calling-plan-landing-page.md#core-deployment-decisions). Die daraus resultierenden Entscheidungen wurden getroffen: 

- Q. Benötigen meine Benutzer Auslandsrufe?<br> A. Ja 

- Q. Verfügen meine Benutzer jeweils über eine direkte nach innen gerichtete Telefonnummer?<br> A. Nicht heute. Alle aktivierten Benutzer erhalten eine Did-Funktion. 

- Q. Möchte ich die Anrufer-ID maskieren oder deaktivieren?<br> A. Die Anrufer-ID für einen Benutzer wird für die lokale Nummer von Contoso maskiert. 


## <a name="direct-routing"></a>Direct Routing

Contoso hat an der Ignite teilgenommen, um auf dem laufenden zu Office 365, einschließlich der mit ihrem Telefon und Direct-Routing verfügbaren Features. Technische Führungskräfte und Architekten verwendeten die während der Ignite 2019 bereitgestellte Anleitung, um ihre Richtung zu bestimmen.  Verwendete Schlüsselsitzungen: 

- [Planen des Erfolgs mit Microsoft Teams Direct Routing](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [Updates für Direct-Routing](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a>Konfiguration

### <a name="calling-plans-sites"></a>Anrufpläne-Websites

Um Lizenzen zu erhalten und Benutzern Telefonnummern zuzuordnen, hat Contoso die Schritte unter Einrichten [von Anrufplänen befolgt](set-up-calling-plans.md). 

Aufgrund der Anzahl der Benutzer, denen Telefonnummern zugewiesen werden mussten, hat Contoso sich entschieden, PowerShell zum Zuweisen der Telefonnummern zu verwenden. Erfahren Sie, wie Sie Zahlen mithilfe von PowerShellin&mdash;&mdash; zusätzlich zu anderen Einstellungen zuweisenContoso das Teams [PowerShell Overview verwendet.](teams-powershell-overview.md)  

### <a name="direct-routing-sites"></a>Direct Routing-Websites

Um die lokale Telefonieinfrastruktur von Contoso mit Microsoft Teams zu verbinden, hat der Administrator von Contoso die Schritte unter Konfigurieren von [Direct](direct-routing-configure.md) Routing befolgt und das Video [Direct Routing in Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) überprüft.  Contoso hat sich außerdem vom zertifizierten SBC-Anbieter auf die Dokumentation zur Direct-Routingbereitstellung verwiesen. 

Nachdem Direct Routing zwischen SBC und Microsoft-Telefon System konfiguriert wurde, musste Contoso die Konfiguration testen. Dazu verwendeten die Contoso-Administratoren den SIP-Testerclient, der in der [Sitzung Updates für Direct-Routing bei Ignite 2019 besprochen wurde](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions). Das Clientskript und die Dokumentation für SIP Tester wurden aus dem PowerShell-Skript heruntergeladen, um die Direct Routing Session Border Controller-Verbindungen zu testen.   


### <a name="local-media-optimization"></a>Optimierung lokaler Medien

Contoso hatte Gelegenheit, die Optimierung lokaler Medien in den verschiedenen Regionen auf der ganzen Welt zu nutzen. Die unterstützten Szenarien für Contoso werden unter [Optimierung lokaler Medien für direktes Routing beschrieben](direct-routing-media-optimization.md). Die Konfiguration der lokalen Medienoptimierung wurde durch die Anleitung des SBC-Anbieters und von Microsoft abgeschlossen. Die Konfigurationsschritte für die Optimierung lokaler Medien umfassen Folgendes: 

- Konfigurieren der Benutzer- und SBC-Websites 

- Konfigurieren Sie den SBC gemäß der SBC-Anbieterspezifikation, 

- Hinzufügen von externen vertrauenswürdigen IP-Adressen zu jeder Website, die für die Optimierung lokaler Medien verwendet wird    

- Definieren der Netzwerktopologie 

- Definieren der virtuellen Netzwerktopologie 

- Bestimmen des Modus: Immer umgehen oder Nur für lokale Benutzer 

## <a name="networking-considerations"></a>Überlegungen zum Netzwerk

Contoso hatte eine Reihe von Benutzern, die über einen längeren Zeitraum remote arbeiten mussten, nachdem sie für die Telefonsystem. Die Benutzer haben VPN für den Zugriff auf bestimmte Line of Business-Anwendungen verwendet. Während Sie sich bei VPN Telefonsystem die Benutzer eine Verschlechterung der Anrufqualität. 

Um das Qualitätsproblem zu beheben, hat Contoso VPN split tunneling implementiert, wodurch der Office 365-Datenverkehr das Internet durchlaufen konnte, während die Verbindung mit den internen Apps auf dem VPN übrig blieb. Zum Implementieren eines VPN-geteilten Tunnels befolgte Contoso die Anleitung unter [Implementieren des geteilten VPN-Tunnels für Office 365](/office365/enterprise/office-365-vpn-implement-split-tunnel).  

