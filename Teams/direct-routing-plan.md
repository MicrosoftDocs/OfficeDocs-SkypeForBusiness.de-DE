---
title: Planen von direktem Routing
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Erfahren Sie, wie Sie mit Microsoft Phone System Direct Routing einen unterstützten vom Kunden bereitgestellten Session Border Controller (SBC) mit Microsoft Phone System verbinden können.
ms.openlocfilehash: 5df93bb5248f6077bf0378c5ab461c6cf8856fbf
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121393"
---
# <a name="plan-direct-routing"></a>Planen von direktem Routing

> [!Tip]
> Schauen Sie sich die folgende Sitzung an, um mehr über die Vorteile von Direct Routing zu erfahren, wie Sie das Routing planen und wie Sie es bereitstellen: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)

Mit microsoft Phone System Direct Routing können Sie einen unterstützten, vom Kunden bereitgestellten Session Border Controller (SBC) mit Microsoft Phone System verbinden.  Mit dieser Funktion können Sie z. B. die lokale PstN-Konnektivität (Public Switched Telephone Network) mit dem Microsoft Teams-Client konfigurieren, wie in der folgenden Abbildung dargestellt: 

![Diagramm mit der Konfiguration der lokalen PSTN-Konnektivität](media/PlanDirectRouting1-PSTNwithTeams.png "Konfiguration der lokalen PSTN-Konnektivität mit dem Microsoft Teams-Client")

  > [!NOTE]
  > Mit Skype for Business Online können Sie auch einen vom Kunden bereitgestellten SBC koppeln. Dies erfordert jedoch eine lokale Skype for Business Server-Bereitstellung oder eine Spezielle Edition von Skype for Business, der so genannten Cloud Connector, zwischen SBC und Microsoft Cloud. Dieses Szenario wird als Hybridstimme bezeichnet. Im Gegensatz dazu ermöglicht Direct Routing eine direkte Verbindung zwischen dem unterstützten SBC und der Microsoft Cloud.

> [!Important]
> Cloud Connector Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online in den Ruhestand treten. Nachdem Ihr Unternehmen ein Upgrade auf Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mithilfe von Direct Routing mit Teams [verbinden.](direct-routing-landing-page.md) 

Mit Direct Routing können Sie Ihren SBC mit fast jedem Telefoniestamm verbinden oder mit pstN-Geräten von Drittanbietern verbinden. Mit Direct Routing können Sie: 

- Verwenden Sie praktisch jeden PSTN-Trunk mit Microsoft Phone System. 
- Konfigurieren Sie die Interoperabilität zwischen Telefoniegeräten in Kundenbesitz, z. B. pbX (Private Branch Exchange) eines Drittanbieters, analogen Geräten und Microsoft Phone System.

Microsoft bietet auch Sprachlösungen für alle In-der-Cloud-Sprachlösungen, z. B. Anrufplan. Eine Hybrid-Sprachlösung kann jedoch für Ihre Organisation am besten sein, wenn: 

- Der Microsoft-Anrufplan ist in Ihrem Land nicht verfügbar. 
- Ihre Organisation erfordert eine Verbindung mit analogen Geräten, Callcentern und anderen Geräten von Drittanbietern. 
- Ihre Organisation hat einen bestehenden Vertrag mit einem PSTN-Netzbetreiber.

Direct Routing unterstützt auch Benutzer, die über die zusätzliche Lizenz für den Microsoft-Anrufplan verfügen. Weitere Informationen hierzu finden Sie in [Telefonsystem und Anrufpläne](calling-plan-landing-page.md). 

Bei Direct Routing wird die Einwahlnummer bei der Teilnahme an einer geplanten Konferenz vom Microsoft Audio Conferencing-Dienst bereitgestellt, der eine ordnungsgemäße Lizenzierung erfordert.  Beim Auswählen platziert der Microsoft Audio Conferencing-Dienst den Anruf mithilfe von Onlineanruffunktionen, für die eine ordnungsgemäße Lizenzierung erforderlich ist. (Hinweis: Wenn ein Benutzer nicht über eine Microsoft Audio Conferencing-Lizenz verfügt, leitet der Anruf über Direct Routing.) Weitere Informationen finden Sie unter [Onlinebesprechungen mit Teams.](https://products.office.com/microsoft-teams/online-meeting-solutions) 
 
Die Planung ihrer Bereitstellung von Direct Routing ist der Schlüssel zu einer erfolgreichen Implementierung. In diesem Artikel werden die Infrastruktur- und Lizenzierungsanforderungen beschrieben und Informationen zur SBC-Konnektivität enthalten: 

- [Infrastrukturanforderungen](#infrastructure-requirements)
- [Lizenzierung und andere Anforderungen](#licensing-and-other-requirements)
- [SBC-Domänennamen](#sbc-domain-names)
- [Öffentliches vertrauenswürdiges Zertifikat für den SBC](#public-trusted-certificate-for-the-sbc)
- [SIP-Signalisierung: FQDNs](#sip-signaling-fqdns)
- [SIP-Signalisierung: Ports](#sip-signaling-ports)
- [Mediendatenverkehr: Portbereiche](#media-traffic-port-ranges)
- [Unterstützte Session Border Controller (SBCs)](#supported-session-border-controllers-sbcs)

Ausführliche Informationen zum Konfigurieren von Direct Routing finden Sie unter [Konfigurieren von Direct Routing](direct-routing-configure.md).

## <a name="infrastructure-requirements"></a>Infrastrukturanforderungen
Die Infrastrukturanforderungen für die unterstützten SBCs, Domänen und andere Netzwerkkonnektivitätsanforderungen zum Bereitstellen von Direct Routing sind in der folgenden Tabelle aufgeführt:  

|Infrastrukturanforderung|Sie benötigen Folgendes:|
|:--- |:--- |
|Session Border Controller (SBC)|Ein unterstützter SBC. Weitere Informationen finden Sie unter [Unterstützte SBCs](#supported-session-border-controllers-sbcs).|
|Mit dem SBC verbundene Telefonie trunks|Ein oder mehrere Telefonie trunks, die mit dem SBC verbunden sind. An einem Ende stellt der SBC eine Verbindung mit dem Microsoft Phone System über Direct Routing ein. Der SBC kann auch Verbindungen mit Telefonieentitäten von Drittanbietern herstellen, z. B. PBXs, Analoge Telefonieadapter und vieles mehr. Jede pstN-Konnektivitätsoption, die mit dem SBC verbunden ist, funktioniert. (Informationen zur Konfiguration der PSTN-Trunks zum SBC finden Sie unter den SBC-Anbietern oder -Trunkanbietern.)|
|Microsoft 365- oder Office 365-Organisation|Eine Microsoft 365- oder Office 365-Organisation, mit der Sie Ihre Microsoft Teams-Benutzer sowie die Konfiguration und Verbindung mit dem SBC erstellen.|
|Benutzerregistrierungsstelle|Der Benutzer muss in Microsoft 365 oder Office 365 zu Hause sein.<br/>Wenn Ihr Unternehmen über eine lokale Skype for Business- oder Lync-Umgebung mit Hybridkonnektivität zu Microsoft 365 oder Office 365 verfügt, können Sie voice in Teams nicht für einen Benutzer aktivieren, der lokal zu Hause ist.<br/><br/>Verwenden Sie zum Überprüfen der Registrierungsstelle eines Benutzers das folgende Skype for Business Online PowerShell-Cmdlet:<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>Die Ausgabe des Cmdlets sollte wie hier angezeigt werden:<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|Domänen|Eine oder mehrere Domänen, die Ihren Microsoft 365- oder Office 365-Organisationen hinzugefügt wurden.<br/><br/>Beachten Sie, dass Sie die Standarddomäne ,.onmicrosoft.com, die automatisch \* für Ihren Mandanten erstellt wird, nicht verwenden können.<br/><br/>Zum Anzeigen der Domänen können Sie das folgende Skype for Business Online PowerShell-Cmdlet verwenden:<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>Weitere Informationen zu Domänen und Microsoft 365- oder Office 365-Organisationen finden Sie unter [Häufig gestellte Fragen zu Domänen](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).|
|Öffentliche IP-Adresse für den SBC|Eine öffentliche IP-Adresse, die zum Herstellen einer Verbindung mit dem SBC verwendet werden kann. Basierend auf dem Typ von SBC kann der SBC NAT verwenden.|
|Vollqualifizierter Domänenname (Fully Qualified Domain Name, FQDN) für den SBC|Ein FQDN für den SBC, bei dem der Domänenbereich des FQDN eine der registrierten Domänen in Ihrer Microsoft 365- oder Office 365-Organisation ist. Weitere Informationen finden Sie unter [SBC-Domänennamen](#sbc-domain-names).|
|Öffentlicher DNS-Eintrag für den SBC |Ein öffentlicher DNS-Eintrag, der den SBC-FQDN der öffentlichen IP-Adresse zuzuordnen. |
|Öffentliches vertrauenswürdiges Zertifikat für den SBC |Ein Zertifikat für den SBC, das für die kommunikation mit Direct Routing verwendet werden soll. Weitere Informationen finden Sie unter [Öffentliches vertrauenswürdiges Zertifikat für den SBC](#public-trusted-certificate-for-the-sbc).|
|Verbindungspunkte für Direct Routing |Die Verbindungspunkte für Direct Routing sind die folgenden drei FQDNs:<br/><br/>`sip.pstnhub.microsoft.com` – Globaler FQDN muss zuerst ausprobiert werden.<br/>`sip2.pstnhub.microsoft.com` – Sekundäres FQDN, geografisch der zweiten Prioritätsregion.<br/>`sip3.pstnhub.microsoft.com` – Tertiäres FQDN, geografisch der region mit der dritten Priorität.<br/><br/>Informationen zu den Konfigurationsanforderungen finden Sie unter [SIP-Signalisierung: FQDNs](#sip-signaling-fqdns).|
|Firewall-IP-Adressen und Ports für Direct Routing-Medien |Der SBC kommuniziert mit den folgenden Diensten in der Cloud:<br/><br/>SIP-Proxy, der die Signalisierung behandelt<br/>Medienprozessor, der Medien behandelt – außer wenn die Medienumgehung<br/><br/>Diese beiden Dienste verfügen über separate IP-Adressen in der Microsoft Cloud, die weiter unten in diesem Dokument beschrieben werden.<br/><br/>Weitere Informationen finden Sie im [Abschnitt Microsoft Teams](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) unter [URLs und IP-Adressbereiche.](/office365/enterprise/urls-and-ip-address-ranges) |
|Medientransportprofil|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Firewall-IP-Adressen und -Ports für Microsoft Teams-Medien |Weitere Informationen finden Sie unter [URLs und IP-Adressbereiche](/office365/enterprise/urls-and-ip-address-ranges). |
|||

## <a name="licensing-and-other-requirements"></a>Lizenzierung und andere Anforderungen 

Benutzern von Direct Routing müssen die folgenden Lizenzen in Microsoft 365 oder Office 365 zugewiesen sein: 

- Microsoft Phone System. 
- Microsoft Teams + Skype for Business Plan 2, sofern in der Lizenzierung enthalten.
- Microsoft Audio Conferencing (bitte lesen Sie die Notizen und den absatz weiter unten, um spezifische Beispiele dafür zu erhalten, wann die Lizenz erforderlich ist).

> [!NOTE]
> Skype for Business Plan sollte nicht aus einem Lizenzvertrag entfernt werden, in dem er enthalten ist. 
> 
> [!IMPORTANT]
> GCC High- und DoD-Benutzer sollten alle in G5 enthaltenen Lizenzen für Audiokonferenzen deaktivieren und warten, bis das Direkte Routing vollständig konfiguriert ist. Benutzer sollten Einwahltelefonnummern und eine funktionierende Wähltapad konfiguriert haben, bevor Sie Lizenzen für Audiokonferenzen aktivieren. Weitere Informationen finden Sie unter [Audiokonferenzen mit Direct Routing für GCC High und DoD.](./audio-conferencing-with-direct-routing-for-gcch-and-dod.md)


> [!IMPORTANT]
>  Für den Fall, dass Sie zu geplanten Besprechungen externe Teilnehmer hinzufügen möchten, indem Sie sich entweder zu ihnen oder durch Angabe der Einwahlnummer auswählen, ist die Lizenz für Audiokonferenzen erforderlich.


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>Ad-hoc-Anrufeskalation und Lizenz für Audiokonferenzen

Ein Teams-Benutzer kann einen 1:1-Anruf von Teams zu PSTN oder Teams zu Teams starten und einen PSTN-Teilnehmer hinzufügen. Dieses Szenario wird als Ad-hoc-Konferenz bezeichnet. Der Pfad, den der Anruf einnimmt, hängt davon ab, ob dem Benutzer, der den Anruf eskaliert, eine Microsoft Audio Conferencing-Lizenz zugewiesen ist oder nicht:

- Wenn dem Teams-Benutzer, der den Anruf eskaliert, eine Microsoft Audio Conferencing-Lizenz zugewiesen ist, erfolgt die Eskalation über den Microsoft Audio Conferencing-Dienst. Der Remote-PSTN-Teilnehmer, der zu dem vorhandenen Anruf eingeladen wird, erhält eine Benachrichtigung über den eingehenden Anruf und sieht die Nummer der Microsoft-Brücke, die dem Teams-Benutzer zugewiesen wurde, der die Eskalation initiiert hat.
- Wenn dem Teams-Benutzer, der den Anruf eskaliert, nicht die Microsoft Audio Conferencing-Lizenz zugewiesen ist, erfolgt die Eskalation über einen Session Border Controller, der mit der Direct Routing-Schnittstelle verbunden ist. Der Remote-PSTN-Teilnehmer, der zum Anruf eingeladen wird, erhält eine Benachrichtigung über den eingehenden Anruf und sieht die Nummer des Teams-Benutzers, der die Eskalation initiiert hat. Der spezifische SBC, der für die Eskalation verwendet wird, wird durch die Routingrichtlinie des Benutzers definiert. 


Darüber hinaus müssen Sie Folgendes sicherstellen:
 
- CsOnlineVoiceRoutingPolicy wird dem Benutzer zugewiesen. 
- Private Anrufe zulassen ist auf Mandantenebene für Microsoft Teams aktiviert. 

Direct Routing unterstützt auch Benutzer, die für den Microsoft Calling Plan lizenziert sind. Microsoft Phone System with Calling Plan kann einige Anrufe über die Direct Routing-Schnittstelle weiterleiten. Die Telefonnummern der Benutzer müssen jedoch entweder online erworben oder zu Microsoft portiert werden.  

Das Mischen von Anrufplan und Direct Routing-Konnektivität für denselben Benutzer ist optional, kann aber nützlich sein (z. B. wenn dem Benutzer ein Microsoft-Anrufplan zugewiesen ist, aber einige Anrufe mithilfe des SBC weiterleiten möchten). Eines der am häufigsten verwendeten Szenarien sind Aufrufe von PbXs von Drittanbietern.  Bei PbX-Telefonen von Drittanbietern werden alle Anrufe, mit Ausnahme von Anrufen an die mit dieser PBX verbundenen Telefone, über den Microsoft-Anrufplan geroutet, aber Anrufe an die Telefone, die mit PbXs von Drittanbietern verbunden sind, gehen an den SBC und bleiben daher im Unternehmensnetzwerk und nicht im PSTN. 

Weitere Informationen zur Lizenzierung von Telefonsystem finden Sie unter [Bestes](https://products.office.com/compare-all-microsoft-office-products?tab=2) aus Office und [Planoptionen .](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options) 

Weitere Informationen zur Lizenzierung von Telefonsystem finden Sie unter [Microsoft Teams-Add-On-Lizenzierung.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) 

## <a name="supported-end-points"></a>Unterstützte Endpunkte 

Sie können als Endpunkt verwenden:

- Beliebiger Teams-Client. 
- Telefone im allgemeinen Bereich. Weitere Informationen finden Sie unter Einrichten [der Common Area Phone-Lizenz für Microsoft Teams.](./set-up-common-area-phones.md) Beachten Sie, dass Sie beim Einrichten eines Telefons im allgemeinen Bereich mit Direct Routing keine Anrufplanlizenz benötigen.
- Skype for Business 3PIP-Telefone. Siehe [Support für Skype for Business-Telefone (3PIP) mit Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)


## <a name="sbc-domain-names"></a>SBC-Domänennamen

Der Name der SBC-Domäne muss aus einem der Namen kommen, die in Domänen des Mandanten registriert sind. Sie können den \* .onmicrosoft.com-Mandanten nicht für den FQDN-Namen des SBC verwenden.

Die folgende Tabelle enthält Beispiele für für den Mandanten registrierte DNS-Namen, ob der Name als FQDN für den SBC verwendet werden kann, und Beispiele für gültige FQDN-Namen:

|DNS-Name|Kann für SBC FQDN verwendet werden|Beispiele für FQDN-Namen|
|:--- |:--- |:--- |
contoso.com|Ja|**Gültige Namen:**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|Nein|Die Verwendung von *.onmicrosoft.com-Domänen wird für #A0 nicht unterstützt

Angenommen, Sie möchten einen neuen Domänennamen verwenden. Ihr Mandant hat z. B. contoso.com einen Domänennamen, der in Ihrem Mandanten registriert ist, und Sie möchten sbc1.sip.contoso.com. Bevor Sie einen SBC mit dem Namen sbc1.sip.contoso.com können, müssen Sie den Domänennamen in sip.contoso.com Domänen in Ihrem Mandanten registrieren. Wenn Sie versuchen, einen SBC mit sbc1.sip.contoso.com zu koppeln, bevor Sie den Domänennamen registrieren, wird die folgende Fehlermeldung angezeigt: "Die Domäne "sbc1.sip.contoso.com" kann nicht verwendet werden, da sie nicht für diesen Mandanten konfiguriert wurde."
Nachdem Sie den Domänennamen hinzugefügt haben, müssen Sie auch einen Benutzer mit UPN-User@sip.contoso.com erstellen und eine Teams-Lizenz zuweisen. Es kann bis zu 24 Stunden dauern, bis der Domänenname vollständig bereitgestellt wird, nachdem er zu Domänen Ihres Mandanten hinzugefügt wurde, ein Benutzer mit einem neuen Namen erstellt und dem Benutzer eine Lizenz zugewiesen wurde. 

Es ist möglich, dass ein Unternehmen mehrere SIP-Adressbereiche in einem Mandanten hat. Ein Unternehmen kann z. B. contoso.com als SIP-Adressbereich und fabrikam.com als zweiten SIP-Adressbereich verwenden. Einige Benutzer haben Adressadressen user@contoso.com und einige Benutzer haben Adressadressen user@fabrikam.com. 

Der SBC benötigt nur einen FQDN und kann Benutzer von jedem beliebigen Adressbereich im gekoppelten Mandanten aus serviceen. Beispielsweise kann ein SBC mit dem Namen sbc1.contoso.com den PSTN-Datenverkehr für Benutzer mit den Adressen user@contoso.com und user@fabrikam.com empfangen und senden, solange diese SIP-Adressbereiche im gleichen Mandanten registriert sind.  

## <a name="public-trusted-certificate-for-the-sbc"></a>Öffentliches vertrauenswürdiges Zertifikat für den SBC

Microsoft empfiehlt, dass Sie das Zertifikat für den SBC anfordern, indem Sie eine Zertifizierungssignierungsanforderung (Certification Signing Request, CSR) generieren. Spezifische Anweisungen zum Generieren eines CSR für einen SBC finden Sie in den Verbindungsanweisungen oder der Dokumentation, die von Ihren SBC-Anbietern bereitgestellt werden. 

  > [!NOTE]
  > Für die meisten Zertifizierungsstelle (CAs) muss die Größe des privaten Schlüssels mindestens 2048 sein. Beachten Sie dies beim Generieren des CSR.

Für das Zertifikat muss der SBC-FQDN als gemeinsamer Name (Common Name, CN) oder das Feld für den alternativen Betreffnamen (SUBJECT Alternative Name, SAN) verwendet werden. Das Zertifikat sollte direkt von einer Zertifizierungsstelle und nicht von einem Zwischenanbieter ausgestellt werden.

Alternativ unterstützt Direct Routing ein Platzhalterzeichen im CN und/oder SAN, und das Platzhalterzeichen muss dem Standard [RFC HTTP Over TLS entsprechen.](https://tools.ietf.org/html/rfc2818#section-3.1) Ein Beispiel wäre die Verwendung von .contoso.com, die dem \* SBC-FQDN-sbc.contoso.com entsprechen würde, aber nicht mit sbc.test.contoso.com.

Das Zertifikat muss von einer der folgenden Stammzertifikatbehörden generiert werden:

- BestätigenTrust
- AddTrust External CA Root
- Baltimore CyberTrust Root*
- Buypass
- Cybertrust
- Zertifizierungsstelle für öffentliche primäre Klasse 3
- Comodo Secure Root CA
- Deutsche Telekom 
- Globale Stammzertifizierungsstelle von DigiCert
- DigiCert High Assurance EV Root CA
- Entrust
- GlobalSign
- Go Daddy
- GeoTrust
- Verisign, Inc. 
- SSL.com
- Starfield
- Symantec Enterprise Mobile Root für Microsoft 
- SwissSign
- Thawte Timestamping CA
- Trustwave
- TeliaSonera 
- T-Systems International GmbH (Deutsche Telekom)
- QuoVadis
- USERTrust RSA Certification Authority
- Hongkong Post Root CA 1,2,3
- Stammzertifizierungsstelle für "Sektigo"

Bei Direct Routing in Office 365 GCCH- und DoD-Umgebungen muss das Zertifikat von einer der folgenden Stammzertifikatbehörden generiert werden:
- Globale Stammzertifizierungsstelle von DigiCert
- DigiCert High Assurance EV Root CA

> [!NOTE]
> *Wenn die Unterstützung von Mutual TLS (MTLS) für die #A0 auf dem SBC aktiviert ist, müssen Sie das Baltimore CyberTrust-Stammzertifikat im SBC Trusted Root Store des Teams TLS-Kontexts installieren. (Dies liegt daran, dass die Microsoft-Dienstzertifikate das Stammzertifikat von Baltimore verwenden.) Informationen zum Herunterladen des Stammzertifikats von Baltimore finden Sie unter [Office 365-Verschlüsselungsketten](/microsoft-365/compliance/encryption-office-365-certificate-chains).

Microsoft arbeitet an der Aufnahme zusätzlicher Zertifizierungsstellen basierend auf Kundenanforderungen. 

## <a name="sip-signaling-fqdns"></a>SIP-Signalisierung: FQDNs 

Direct Routing wird in den folgenden Umgebungen angeboten:
- Microsoft 365 oder Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

Erfahren Sie mehr über [Office 365- und US-Regierungsumgebungen](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) wie GCC, GCC High und DoD.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365-, Office 365- und Office 365-GCC-Umgebungen

Die Verbindungspunkte für Direct Routing sind die folgenden drei FQDNs:

- **sip.pstnhub.microsoft.com** – Globaler FQDN – muss zuerst ausprobiert werden. Wenn der SBC eine Anforderung zum Auflösen dieses Namens sendet, geben die Microsoft Azure-DNS-Server eine IP-Adresse zurück, die auf das primäre Azure-Rechenzentrum verweisen soll, das dem SBC zugewiesen ist. Die Zuordnung basiert auf Leistungsmetriken der Rechenzentren und der geografischen Nähe zum SBC. Die zurückgegebene IP-Adresse entspricht dem primären FQDN.
- **sip2.pstnhub.microsoft.com** – Sekundäres FQDN – geografisch der zweiten Prioritätsregion zu.
- **sip3.pstnhub.microsoft.com** – Tertiärer FQDN – geografische Zuordnung zur dritten Prioritätsregion.

Die folgenden drei FQDNs müssen in der folgenden Reihenfolge platziert werden:

- Sorgen Sie für optimale Benutzererfahrung (weniger geladen und dem SBC-Rechenzentrum am nächsten, das durch Abfragen des ersten FQDNs zugewiesen wurde).
- Stellen Sie einen Failover bereit, wenn eine Verbindung von einem SBC zu einem Rechenzentrum hergestellt wird, bei dem ein temporäres Problem auftritt. Weitere Informationen finden Sie weiter unten unter [Failovermechanismus.](#failover-mechanism-for-sip-signaling)  

Die FQDNs – sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com und sip3.pstnhub.microsoft.com – werden in eine der folgenden IP-Adressen aufgelöst:

- 52.114.148.0
- 52.114.132.46 
- 52.114.75.24 
- 52.114.76.76 
- 52.114.7.24 
- 52.114.14.70
- 52.114.16.74
- 52.114.20.29

Sie müssen Ports für alle diese IP-Adressen in Ihrer Firewall öffnen, um eingehenden und ausgehenden Datenverkehr an und von den Adressen für die Signalisierung zu ermöglichen.  Wenn Ihre Firewall DNS-Namen unterstützt,  wird der FQDN sip-all.pstnhub.microsoft.com auf alle diese IP-Adressen aufgelöst. 

> [!IMPORTANT]
>  Im Rahmen der Erweiterung und Dienstverbesserung von Teams Direct Routing haben wir neue Instanzen der Direct Routing-Infrastruktur in Australien bereitgestellt. Dies spiegelt sich in zwei zusätzlichen IP-Adressen wider (52.114.16.74 und 52.114.20.29), an die folgende FQDNs für australische Kunden aufgelöst werden – sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com und sip3.pstnhub.microsoft.com. Sie müssen diese beiden IP-Adressen (52.114.16.74 und 52.114.20.29) zu Ihren IP Access Control Lists (ACLs) hinzufügen und Ports für alle diese IP-Adressen in Ihrer Firewall öffnen, um eingehenden und ausgehenden Datenverkehr zu und von den Adressen zur Signalisierung zu ermöglichen.

### <a name="office-365-gcch-and-dod-environment"></a>Office 365 GCCH- und DoD-Umgebung

Der Verbindungspunkt für Direct Routing ist der folgende FQDN:

**sip.pstnhub.dod.teams.microsoft.us** – Globaler FQDN. Da die Office 365 DoD-Umgebung nur in den US-Rechenzentren vorhanden ist, gibt es keine sekundären und tertiären FQDNs.

Die FQDN-sip.pstnhub.dod.teams.microsoft.us wird in eine der folgenden IP-Adressen aufgelöst:

- 52.127.64.33
- 52.127.68.34

Sie müssen Ports für alle diese IP-Adressen in Ihrer Firewall öffnen, um eingehenden und ausgehenden Datenverkehr an und von den Adressen für die Signalisierung zu ermöglichen.

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High Environment

Der Verbindungspunkt für Direct Routing ist der folgende FQDN:

**sip.pstnhub.gov.teams.microsoft.us** – Globaler FQDN. Da die GCC High-Umgebung nur in den US-Rechenzentren vorhanden ist, gibt es keine sekundären und tertiären FQDNs.

Die FQDN-sip.pstnhub.gov.teams.microsoft.us wird in eine der folgenden IP-Adressen aufgelöst:

- 52.127.88.59
- 52.127.92.64

Sie müssen Ports für alle diese IP-Adressen in Ihrer Firewall öffnen, um eingehenden und ausgehenden Datenverkehr an und von den Adressen für die Signalisierung zu ermöglichen. Wenn Ihre Firewall DNS-Namen unterstützt,  wird der FQDN-sip-all.pstnhub.gov.teams.microsoft.us auf alle diese IP-Adressen aufgelöst. Dieser FQDN kann auch als Verbund-FQDN für die Klassifizierung eingehender Anrufe verwendet werden.

## <a name="sip-signaling-ports"></a>SIP-Signalisierung: Ports

Sie müssen die folgenden Ports für Microsoft 365- oder Office 365-Umgebungen verwenden, in denen Direct Routing angeboten wird:
- Microsoft 365 oder Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

|Datenverkehr|Von|Bis|Quellport|Zielport|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP-Proxy|SBC|1024 – 65535|Definiert auf dem SBC (Für Office 365 GCC High/DoD muss nur Port 5061 verwendet werden)|
SIP/TLS|SBC|SIP-Proxy|Definiert im SBC|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>Failovermechanismus für SIP-Signalisierung

Der SBC erstellt eine DNS-Abfrage zum Auflösen sip.pstnhub.microsoft.com. Basierend auf dem SBC-Speicherort und den Leistungsmetriken des Rechenzentrums wird das primäre Rechenzentrum ausgewählt. Wenn im primären Rechenzentrum ein Problem vor sich geht, versucht der SBC das sip2.pstnhub.microsoft.com, das zum zweiten zugewiesenen Rechenzentrum aufgelöst wird, und in dem seltenen Fall, dass Rechenzentren in zwei Regionen nicht verfügbar sind, versucht der SBC den letzten FQDN (sip3.pstnhub.microsoft.com), der die ip des tertiären Rechenzentrums liefert.

In der nachstehenden Tabelle sind die Beziehungen zwischen primären, sekundären und tertiären Rechenzentren zusammengefasst:

|Wenn das primäre Rechenzentrum|EMEA|NOAM|ASIEN|
|:--- |:--- |:--- |:--- |
|Das sekundäre Rechenzentrum (sip2.pstnhub.microsoft.com)|US|EU|US|
|Das tertiäre Rechenzentrum (sip3.pstnhub.microsoft.com)|ASIEN|ASIEN|EU|
|||||

## <a name="media-traffic-port-ranges"></a>Mediendatenverkehr: Portbereiche
Beachten Sie, dass die folgenden Anforderungen gelten, wenn Sie Direktes Routing ohne Medienumgehung bereitstellen möchten. Firewallanforderungen für die Medienumgehung finden Sie unter [Planen der Medienumgehung mit Direct Routing](./direct-routing-plan-media-bypass.md).



Der Mediendatenverkehr fließt zu und von einem separaten Dienst in der Microsoft Cloud. Die IP-Adressbereiche für Mediendatenverkehr lauten wie folgt:

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365-, Office 365- und Office 365-GCC-Umgebungen

- 52.112.0.0/14 (IP-Adressen von 52.112.0.1 bis 52.115.255.254).
- 52.120.0.0/14 (IP-Adressen von 52.120.0.1 bis 52.123.255.254).

### <a name="office-365-dod-environment"></a>Office 365 DoD-Umgebung

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High Environment

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>Portbereich (gilt für alle Umgebungen)
Der Portbereich der Medienprozessoren wird in der folgenden Tabelle angezeigt: 

|Datenverkehr|Von|Bis|Quellport|Zielport|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|Medienprozessor|SBC|3478-3481 und 49152 – 53247|Definiert im SBC|
|UDP/SRTP|SBC|Medienprozessor|Definiert im SBC|3478-3481 und 49152 – 53247|

  > [!NOTE]
  > Microsoft empfiehlt mindestens zwei Ports pro gleichzeitigem Aufruf des SBC.


## <a name="media-traffic-media-processors-geography"></a>Mediendatenverkehr: Geographie der Medienprozessoren

Der Mediendatenverkehr fließt über Komponenten, die als Medienprozessoren bezeichnet werden. Medienprozessoren werden in denselben Rechenzentren wie SIP-Proxys platziert. Darüber hinaus gibt es zusätzliche Medienprozessoren, um den Medienfluss zu optimieren. Beispielsweise verfügen wir jetzt nicht über eine SIP-Proxykomponente in Australien (SIP-Flüsse über Singapur oder Hongkong), aber wir haben den Medienprozessor lokal in Australien. Die Lokale Notwendigkeit der Medienprozessoren wird durch die Latenz bestimmt, die beim Senden von Datenverkehr über lange Entfernungen auftreten kann, z. B. von Australien nach Singapur oder Hongkong. Die Latenz im Beispiel für Datenverkehr, der von Australien nach Hongkong oder Singapur fließt, ist zwar akzeptabel, um eine gute Anrufqualität für den SIP-Datenverkehr zu erhalten, für den Mediendatenverkehr in Echtzeit ist dies jedoch nicht der Richtige.

Speicherort der Medienprozessoren:

Speicherorte, an denen sowohl SIP-Proxy- als auch Medienprozessorkomponenten bereitgestellt wurden:
- USA (zwei in US West- und US East-Rechenzentren)
- Europa (Amsterdam- und Dublin-Rechenzentren)
- Asien (Singapur- und Hongkong-Rechenzentren)

Speicherorte, an denen nur Medienprozessoren bereitgestellt werden (SIP fließt über das oben aufgeführte nächstgelegene Rechenzentrum):
- Japan (JP East and West datacenters)
- Australien (AU East and Southeast datacenters)




## <a name="media-traffic-codecs"></a>Mediendatenverkehr: Codecs

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>Bein zwischen SBC und Cloud Media Processor oder Microsoft Teams-Client.
Gilt sowohl für Medienumgehungsfälle als auch für Fälle ohne Umgehung.

Die Direct Routing-Schnittstelle auf dem Bein zwischen dem Session Border Controller und Cloud Media Processor (ohne Medienumgehung) oder zwischen dem Teams-Client und dem SBC (wenn die Medienumgehung aktiviert ist) kann die folgenden Codecs verwenden:

- Umgehung ohne Medien (SBC zu Cloud Media Processor): SILK, G.711, G.722, G.729
- Medienumgehung (SBC zu Teams-Client): SILK, G.711, G.722, G.729

Sie können die Verwendung des bestimmten Codecs auf dem Session Border Controller erzwingen, indem Sie unerwünschte Codecs aus dem Angebot ausschließen.

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>Leg between Microsoft Teams Client and Cloud Media Processor
Gilt nur für nicht mediale Umgehungsfalle. Bei der Medienumgehung fließen die Medien direkt zwischen dem Teams-Client und dem SBC.

Auf dem Bein zwischen Cloud Media Processor und Microsoft Teams-Client wird entweder SILK oder G.722 verwendet. Die Codecauswahl in diesem Abschnitt basiert auf Microsoft-Algorithmen, die mehrere Parameter berücksichtigen. 


## <a name="supported-session-border-controllers-sbcs"></a>Unterstützte Session Border Controller (SBCs)

Microsoft unterstützt nur zertifizierte SBCs zum Koppeln mit Direct Routing. Da Enterprise-VoIP für Unternehmen wichtig ist, führt Microsoft intensive Tests mit den ausgewählten SBCs durch und arbeitet mit den SBC-Anbietern zusammen, um sicherzustellen, dass die beiden Systeme kompatibel sind. 

Überprüfte Geräte werden als Zertifiziert für Teams Direct Routing aufgeführt. Die zertifizierten Geräte funktionieren garantiert in allen Szenarien. 

Weitere Informationen zu unterstützten SBCs finden Sie unter Liste der für Direct [Routing zertifizierten Sitzungsgrenzcontroller.](direct-routing-border-controllers.md)

 
## <a name="see-also"></a>Mehr dazu

[Konfigurieren von direktem Routing](direct-routing-configure.md)