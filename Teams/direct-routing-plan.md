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
description: Erfahren Sie Microsoft-Telefon Sie mit System Direct Routing eine Verbindung mit einem unterstützten, vom Kunden bereitgestellten Session Border Controller (SBC) mit Microsoft-Telefon System herstellen können.
ms.openlocfilehash: 3e174aa2d78eb6ecee7be545cb904efa2573f3c1
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2021
ms.locfileid: "58235350"
---
# <a name="plan-direct-routing"></a>Planen von direktem Routing

> [!Tip]
> Schauen Sie sich die folgende Sitzung an, um mehr über die Vorteile von Direct-Routing, die Planung und die Bereitstellung zu erfahren: [Direct-Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)

Microsoft-Telefon Mit System Direct Routing können Sie einen unterstützten, vom Kunden bereitgestellten Session Border Controller (SBC) mit Microsoft-Telefon verbinden.  Mit dieser Funktion können Sie z. B. die lokale PSTN-Konnektivität (Public Switched Telephone Network) mit dem Microsoft Teams-Client konfigurieren, wie in der folgenden Abbildung dargestellt: 

![Diagramm, das die Konfiguration der lokalen PSTN-Anbindung zeigt](media/PlanDirectRouting1-PSTNwithTeams.png "Konfiguration der lokalen PSTN-Anbindung mit Microsoft Teams Client")

  > [!NOTE]
  > Skype for Business Online ermöglicht Ihnen auch das Koppeln eines vom Kunden bereitgestellten SBC, dies erfordert jedoch eine lokale Skype for Business Server-Bereitstellung oder eine spezielle Edition von Skype for Business, die als Cloud Connector bezeichnet wird, zwischen dem SBC und der Microsoft Cloud. Dieses Szenario wird als Hybridstimme bezeichnet. Im Gegensatz dazu ermöglicht Direct-Routing eine direkte Verbindung zwischen dem unterstützten SBC und der Microsoft Cloud.

> [!Important]
> Cloud Connector Edition wird am 31. Juli 2021 sowie Skype for Business Online abziehen. Nachdem Ihre Organisation ein Upgrade auf Teams durchgeführt hat, erfahren Sie hier, wie Sie Ihr lokales Telefonienetzwerk mit dem Teams mit [Direct Routing verbinden.](direct-routing-landing-page.md) 

Mit Direct Routing können Sie Ihren SBC mit nahezu jedem Telefonie-Trunk verbinden oder mit Drittanbieter-PSTN-Geräten verbinden. Mit Direct Routing haben Sie die Möglichkeit: 

- Verwenden Sie praktisch jeden PSTN-Trunk mit Microsoft-Telefon System. 
- Konfigurieren der Interoperabilität zwischen Telefoniegeräten im Besitz des Kunden, z. B. einer Drittanbieter-Telefonanlage (Private Branch Exchange, PBX), analogen Geräten und Microsoft-Telefon System.

Microsoft bietet außerdem Voicelösungen für die Cloud an, z. B. Anrufplan. Eine Hybrid-Sprachlösung ist jedoch möglicherweise für Ihre Organisation die beste Lösung, wenn: 

- Der Microsoft-Anrufplan ist in Ihrem Land nicht verfügbar. 
- Ihre Organisation benötigt eine Verbindung mit analogen Geräten von Drittanbietern, Callcentern und so weiter. 
- Ihre Organisation hat einen Vertrag mit einem PSTN-Netzbetreiber.

Direct Routing unterstützt auch Benutzer, die über eine zusätzliche Lizenz für den Microsoft-Anrufplan verfügen. Weitere Informationen hierzu finden Sie in [Telefonsystem und Anrufpläne](calling-plan-landing-page.md). 

Mit Direct Routing wird bei Teilnahme an einer geplanten Konferenz die Einwahlnummer durch den Microsoft-Audiokonferenzdienst bereitgestellt, für den eine ordnungsgemäße Lizenzierung erforderlich ist.  Beim Abwählen verwendet der Microsoft-Audiokonferenzdienst die Onlineanruffunktionen, für die eine ordnungsgemäße Lizenzierung erforderlich ist. (Wenn ein Benutzer nicht über eine Microsoft Audio Conferencing-Lizenz verfügt, wird der Anruf durch Direct Routing routen.) Weitere Informationen finden Sie unter [Onlinebesprechungen mit Teams.](https://products.office.com/microsoft-teams/online-meeting-solutions) 
 
Die Planung der Bereitstellung von Direct-Routing ist der Schlüssel zu einer erfolgreichen Implementierung. In diesem Artikel werden Die Anforderungen an die Infrastruktur und Lizenzierung beschrieben und Informationen zur SBC-Konnektivität enthalten: 

- [Infrastrukturanforderungen](#infrastructure-requirements)
- [Lizenzierungs- und andere Anforderungen](#licensing-and-other-requirements)
- [SBC-Domänennamen](#sbc-domain-names)
- [Öffentliches vertrauenswürdiges Zertifikat für den SBC](#public-trusted-certificate-for-the-sbc)
- [SIP-Signalisierung: FQDNs](#sip-signaling-fqdns)
- [SIP-Signalisierung: Ports](#sip-signaling-ports)
- [Medienverkehr: Portbereiche](#media-traffic-port-ranges)
- [Unterstützte Session Border Controller (SBCs)](#supported-session-border-controllers-sbcs)

Ausführliche Informationen zum Konfigurieren von Direct-Routing finden Sie unter [Konfigurieren von Direct-Routing.](direct-routing-configure.md)

## <a name="infrastructure-requirements"></a>Infrastrukturanforderungen
Die Infrastrukturanforderungen für die unterstützten SBCs, Domänen und anderen Anforderungen an die Netzwerkkonnektivität für die Bereitstellung von Direct Routing sind in der folgenden Tabelle aufgeführt:  

|Infrastrukturanforderung|Sie benötigen Folgendes:|
|:--- |:--- |
|Session Border Controller (SBC)|Ein unterstützter SBC. Weitere Informationen finden Sie unter [Unterstützte SBCs.](#supported-session-border-controllers-sbcs)|
|Mit SBC verbundene Telefonie-Trunks|Mindestens ein Telefonie-Trunk ist mit dem SBC verbunden. An einem Ende stellt der SBC eine Verbindung mit dem Microsoft-Telefon über Direct-Routing ein. Der SBC kann auch Verbindungen mit Telefonieen von Drittanbietern wie PBXs, Analog Telephony Adapters und so weiter herstellen. Alle mit dem SBC verbundenen PSTN-Konnektivitätsoption funktionieren. (Informationen zur Konfiguration der PSTN-Trunks zum SBC finden Sie unter SBC-Anbieter oder Trunkanbieter.)|
|Microsoft 365 oder Office 365 Organisation|Eine Microsoft 365 oder Office 365, die Sie zum Heiming Ihrer Microsoft Teams-Benutzer sowie die Konfiguration und Verbindung mit dem SBC verwenden.|
|Benutzerregistrierungsstelle|Der Benutzer muss in einem Microsoft 365 oder einem Office 365.<br/>Wenn Ihr Unternehmen über eine lokale Skype for Business- oder Lync-Umgebung mit hybrider Konnektivität zu Microsoft 365 oder Office 365 verfügt, können Sie Voice in Teams für einen Benutzer, der lokal heimiert ist, nicht aktivieren.<br/><br/>Um die Registrierungsstelle eines Benutzers zu überprüfen, verwenden Sie das Skype for Business Online-PowerShell-Cmdlet:<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>Die Ausgabe des Cmdlets sollte wie hier gezeigt sein:<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|Domänen|Eine oder mehrere Domänen, die Zu Microsoft 365 oder Office 365 hinzugefügt wurden.<br/><br/>Beachten Sie, dass Sie nicht die Standarddomäne (.onmicrosoft.com) verwenden können, die \* automatisch für Ihren Mandanten erstellt wird.<br/><br/>Zum Anzeigen der Domänen können Sie das folgende PowerShell Skype for Business Online-PowerShell-Cmdlet verwenden:<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>Weitere Informationen zu Domänen und Microsoft 365 oder Office 365 finden Sie unter Häufig [gestellte Fragen](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)zu Domänen.|
|Öffentliche IP-Adresse für den SBC|Eine öffentliche IP-Adresse, die zum Herstellen einer Verbindung mit dem SBC verwendet werden kann. Basierend auf dem Typ von SBC kann SBC NAT verwenden.|
|Fully Qualified Domain Name (FQDN) for the SBC|Ein FQDN für den SBC, wobei der Domänenteil des FQDN eine der registrierten Domänen in Ihrer Microsoft 365- oder Office 365 ist. Weitere Informationen finden Sie unter [SBC-Domänennamen.](#sbc-domain-names)|
|Öffentlicher DNS-Eintrag für SBC |Ein öffentlicher DNS-Eintrag, der den SBC-FQDN der öffentlichen IP-Adresse zuzuordnen. |
|Öffentliches vertrauenswürdiges Zertifikat für den SBC |Ein Zertifikat für den SBC, der für die Kommunikation mit Direct-Routing verwendet werden soll. Weitere Informationen finden Sie unter [Öffentliches vertrauenswürdiges Zertifikat für SBC.](#public-trusted-certificate-for-the-sbc)|
|Verbindungspunkte für direktes Routing |Die Verbindungspunkte für Direct Routing sind die folgenden drei FQDNs:<br/><br/>`sip.pstnhub.microsoft.com` – Globaler FQDN muss zuerst ausprobiert werden.<br/>`sip2.pstnhub.microsoft.com` – Sekundärer FQDN, geografische Zuordnung zur zweiten Region mit Priorität.<br/>`sip3.pstnhub.microsoft.com` – Drittgrößter FQDN, geografisch der Region mit dritter Priorität zu.<br/><br/>Informationen zu Den Konfigurationsanforderungen finden Sie unter [SIP-Signalisierung: FQDNs](#sip-signaling-fqdns).|
|IP-Adressen und Ports der Firewall für Direct Routing-Medien |Der SBC kommuniziert mit den folgenden Diensten in der Cloud:<br/><br/>SIP-Proxy, der die Signalisierung behandelt<br/>Medienprozessor, der Medien behandelt ( außer wenn die Medienumgehung<br/><br/>Diese beiden Dienste verfügen über separate IP-Adressen in der Microsoft Cloud, die weiter unten in diesem Dokument beschrieben werden.<br/><br/>Weitere Informationen finden Sie im Abschnitt [Microsoft Teams unter](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) [URLs und IP-Adressbereiche.](/office365/enterprise/urls-and-ip-address-ranges) |
|Medientransportprofil|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Firewall-IP-Adressen und Ports für Microsoft Teams-Medien |Weitere Informationen finden Sie unter [URLs und IP-Adressbereiche.](/office365/enterprise/urls-and-ip-address-ranges) |
|||

## <a name="licensing-and-other-requirements"></a>Lizenzierungs- und andere Anforderungen 

Den Benutzern von Direct-Routing müssen in einem Microsoft 365 oder einer Office 365: 

- Microsoft-Telefon "System" aus. 
- Microsoft Teams + Skype for Business Plan 2, falls in der Lizenzierung enthalten.
- Microsoft Audio Conferencing (Bitte lesen Sie die Hinweise und den nachfolgenden Absatz, um konkrete Beispiele dazu zu erhalten, wann die Lizenz erforderlich ist).

> [!NOTE]
> Skype for Business Der Plan sollte nicht aus einem Lizenzvertrag entfernt werden, in dem er enthalten ist. 
> 
> [!IMPORTANT]
> GCC Benutzer von "Hoch" und "DoD" sollten die in G5 enthaltene Lizenzierung für Audiokonferenzen deaktivieren und mit der Aktivierung von Audiokonferenzen warten, bis Direct Routing vollständig konfiguriert ist. Vor dem Aktivieren von Lizenzen für Audiokonferenzen sollten Benutzer Einwahltelefonnummern und eine funktionierende Wählta nicht konfiguriert haben. Weitere [Informationen finden Sie unter Audiokonferenzen mit Direct Routing für GCC High und DoD.](./audio-conferencing-with-direct-routing-for-gcch-and-dod.md)


> [!IMPORTANT]
>  Für den Fall, dass Sie externe Teilnehmer zu geplanten Besprechungen hinzufügen möchten , entweder durch Einenwählen oder durch Angabe der Einwahlnummer, ist die Lizenz für Audiokonferenzen erforderlich.
> Weisen GCC "High" und "DoD" G5-Benutzern keine Lizenz für Audiokonferenzen zu.  Weisen Sie G3-Benutzern erst dann eine Lizenz für Audiokonferenzen zu, wenn Direct Routing vollständig konfiguriert ist und der Benutzer über eine funktionierende Wähltatischen verfügt.


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>Ad-hoc-Anrufskalation und Lizenz für Audiokonferenzen

Ein Teams Benutzer kann einen 1:1-Anruf Teams PSTN starten oder Teams, Teams und einen PSTN-Teilnehmer hinzufügen. Dieses Szenario wird als Ad-hoc-Konferenz bezeichnet. Der Weg, den der Anruf einnimmt, hängt davon ab, ob dem Benutzer, der den Anruf eskaliert, eine Microsoft Audio Conferencing-Lizenz zugewiesen wurde:

- Wenn dem Teams, der den Anruf eskaliert, eine Microsoft Audio Conferencing-Lizenz zugewiesen wurde, erfolgt die Eskalation über den Microsoft Audio Conferencing-Dienst. Der Remote-PSTN-Teilnehmer, der zum bestehenden Anruf eingeladen wird, erhält eine Benachrichtigung über den eingehenden Anruf und sieht die Nummer der Microsoft-Brücke, die dem Teams-Benutzer zugewiesen wurde, der die Eskalation ausgelöst hat.
- Wenn dem Teams, der den Anruf eskaliert, keine Microsoft Audio Conferencing-Lizenz zugewiesen wurde, erfolgt die Eskalation über einen Session Border Controller, der mit der Direct Routing-Schnittstelle verbunden ist. Der Remote-PSTN-Teilnehmer, der zu dem Anruf eingeladen wird, erhält eine Benachrichtigung über den eingehenden Anruf und sieht die Nummer des Teams Benutzers, der die Eskalation ausgelöst hat. Der spezifische SBC, der für die Eskalation verwendet wird, wird durch die Routingrichtlinie des Benutzers definiert. 


Darüber hinaus müssen Sie Folgendes sicherstellen:
 
- CsOnlineVoiceRoutingPolicy wird dem Benutzer zugewiesen. 
- Private Anrufe zulassen ist auf Mandantenebene für Microsoft Teams. 

Direct Routing unterstützt auch Benutzer, die für den Microsoft-Anrufplan lizenziert sind. Microsoft-Telefon Das System mit Anrufplan kann einige Anrufe über die Direct Routing-Schnittstelle weiterleiten. Die Telefonnummern der Benutzer müssen jedoch entweder online erworben oder zu Microsoft portiert werden.  

Das Mischen von Anrufplan- und Direct-Routingkonnektivität für denselben Benutzer ist optional, kann aber hilfreich sein (z. B. wenn dem Benutzer ein Microsoft-Anrufplan zugewiesen ist, er aber einige Aufrufe mit SBC weiterleiten möchte). Eines der am häufigsten verwendeten Szenarien sind Anrufe an PbXs von Drittanbietern.  Bei Festnetztelefonanlagen von Drittanbietern werden alle Anrufe, mit Ausnahme von Anrufen an die mit dieser PbX verbundenen Telefone, über den Microsoft-Anrufplan geroutet, aber Anrufe an Telefone, die mit Drittanbieter-PBXs verbunden sind, gehen an den SBC und bleiben daher im Unternehmensnetzwerk und nicht im PSTN. 

Weitere Informationen zur Lizenzierung Telefonsystem Sie unter ["Holen](https://products.office.com/compare-all-microsoft-office-products?tab=2) Sie sich das Beste aus Ihrer Office und [Planen von Optionen .](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options) 

Weitere Informationen zur Lizenzierung Telefonsystem Finden Sie unter [Microsoft Teams-Add-On-Lizenzierung.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) 

## <a name="supported-end-points"></a>Unterstützte Endpunkte 

Sie können als Endpunkt verwenden:

- Ein beliebiger Teams-Client. 
- Telefone in der Nähe. Weitere Informationen finden Sie unter Einrichten [der Telefon für Microsoft Teams.](./set-up-common-area-phones.md) Beachten Sie, dass Sie beim Einrichten eines gemeinsamen Bereichs mit Direct-Routing Telefon Anrufplanlizenz benötigen.
- Skype for Business 3PIP-Telefone. Siehe [Skype for Business(3PIP)-Unterstützung für Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)


## <a name="sbc-domain-names"></a>SBC-Domänennamen

Der SBC-Domänenname muss aus einem der Namen kommen, die in Domains des Mandanten registriert sind. Sie können den \* .onmicrosoft.com-Mandanten nicht für den FQDN-Namen der SBC verwenden.

Die folgende Tabelle enthält Beispiele für DNS-Namen, die für den Mandanten registriert sind, ob der Name als FQDN für den SBC verwendet werden kann, und Beispiele für gültige FQDN-Namen:

|DNS-Name|Kann für SBC-FQDN verwendet werden|Beispiele für FQDN-Namen|
|:--- |:--- |:--- |
contoso.com|Ja|**Gültige Namen:**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|Nein|Die Verwendung von *.onmicrosoft.com-Domänen wird für SBC-Namen nicht unterstützt.

Angenommen, Sie möchten einen neuen Domänennamen verwenden. Ihr Mandant hat z. contoso.com einen Domänennamen, der in Ihrem Mandanten registriert ist, und Sie möchten sbc1.sip.contoso.com. Bevor Sie einen SBC mit dem Sbc1.sip.contoso.com koppeln können, müssen Sie den Domänennamen in sip.contoso.com In Domänen Ihres Mandanten registrieren. Wenn Sie versuchen, einen SBC mit sbc1.sip.contoso.com zu koppeln, bevor Sie den Domänennamen registrieren, wird die folgende Fehlermeldung angezeigt: "Die Domäne "sbc1.sip.contoso.com" kann nicht verwendet werden, da sie für diesen Mandanten nicht konfiguriert wurde."
Nachdem Sie den Domänennamen hinzugefügt haben, müssen Sie auch einen Benutzer mit UPN-User@sip.contoso.com erstellen und eine Lizenz Teams zuweisen. Es kann bis zu 24 Stunden dauern, bis der Domänenname vollständig bereitgestellt wurde, nachdem er zu Domänen Ihres Mandanten hinzugefügt wurde, ein Benutzer mit einem neuen Namen erstellt und dem Benutzer eine Lizenz zugewiesen wurde. 

Es ist möglich, dass ein Unternehmen mehrere SIP-Adressbereiche in einem Mandanten hat. Beispielsweise könnte ein Unternehmen einen contoso.com als SIP-Adressraum und fabrikam.com als zweiten SIP-Adressraum verwenden. Einige Benutzer verfügen über Adressadressen, user@contoso.com einige Benutzer über Adressadressen user@fabrikam.com. 

Der SBC benötigt nur einen FQDN und kann Benutzer von jedem beliebigen Adressbereich im gekoppelten Mandanten aus serviceen. Beispielsweise kann ein SBC mit dem Namen sbc1.contoso.com den PSTN-Datenverkehr für Benutzer mit Adressen user@contoso.com und user@fabrikam.com empfangen und senden, solange diese SIP-Adressräume im selben Mandanten registriert sind.  

## <a name="public-trusted-certificate-for-the-sbc"></a>Öffentliches vertrauenswürdiges Zertifikat für den SBC

Microsoft empfiehlt, dass Sie das Zertifikat für den SBC anfordern, indem Sie eine Zertifizierungssignaturanforderung (Certification Signing Request, CSR) generieren. Spezifische Anweisungen zum Generieren eines CSR für einen SBC finden Sie in den Anleitungen zu Anleitungen zur Anleitung oder Dokumentation ihrer SBC-Hersteller. 

  > [!NOTE]
  > Die meisten Zertifizierungsstelle erfordern eine Größe von mindestens 2048 privatem Schlüssel. Beachten Sie dies beim Generieren des CSR.

Für das Zertifikat muss der SBC-FQDN als gemeinsamer Name (Common Name, CN) oder als Alternativer Subject Name (SAN)-Feld verwendet werden. Das Zertifikat sollte direkt von einer Zertifizierungsstelle ausgestellt werden, nicht von einem Zwischenanbieter.

Alternativ unterstützt Direct-Routing einen Platzhalter im CN und/oder SAN, und der Platzhalter muss RFC [HTTP Over TLS](https://tools.ietf.org/html/rfc2818#section-3.1)-Standard entsprechen. Ein Beispiel wäre die Verwendung von contoso.com, die mit der SBC-FQDN-sbc.contoso.com, aber nicht mit der \* sbc.test.contoso.com.

Das Zertifikat muss von einer der folgenden Stammzertifizierungsstelle generiert werden:

- Trust vertrauenswürdig
- AddTrust External CA Root
- Baltimore CyberTrust Root*
- Kaufpass
- Cybertrust
- Öffentliche primäre Zertifizierungsstelle von Klasse 3
- Comodo Secure Root CA
- Deutsche Telekom 
- DigiCert Global Root CA
- DigiCert High Assurance EV Root CA
- Anvertrauen
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
- Denkvadis
- USERTrust RSA-Zertifizierungsstelle
- Hongkong Post Root CA 1,2,3
- Cacheigo Root CA

Für direct Routing in Office 365 GCCH- und DoD-Umgebungen muss das Zertifikat von einer der folgenden Stammzertifizierungsstelle generiert werden:
- DigiCert Global Root CA
- DigiCert High Assurance EV Root CA

> [!NOTE]
> *Wenn DIE Unterstützung von Mutual TLS (MTLS) für die Teams-Verbindung auf dem SBC aktiviert ist, müssen Sie das Baltimore CyberTrust-Stammzertifikat im SBC Trusted Root Store des TLS-Kontexts von Teams installieren. (Dies liegt daran, dass für die Microsoft-Dienstzertifikate das Baltimore-Stammzertifikat verwendet wird.) Informationen zum Herunterladen des Baltimore-Stammzertifikats finden Sie [unter Office 365 Verschlüsselungsketten.](/microsoft-365/compliance/encryption-office-365-certificate-chains)

Microsoft arbeitet daran, basierend auf Kundenanforderungen zusätzliche Zertifizierungsstellen hinzufügen. 

## <a name="sip-signaling-fqdns"></a>SIP-Signalisierung: FQDNs 

Direct Routing wird in den folgenden Umgebungen angeboten:
- Microsoft 365 oder Office 365
- Office 365 GCC
- Office 365 GCC Hoch
- Office 365 DoD

Erfahren Sie mehr [über Office 365 und US Government-Umgebungen](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) wie GCC, GCC High und DoD.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365, Office 365 und Office 365 GCC Umgebung

Die Verbindungspunkte für Direct-Routing sind die folgenden drei FQDNs:

- **sip.pstnhub.microsoft.com** – Globaler FQDN – muss zuerst ausprobiert werden. Wenn der SBC eine Anforderung zum Auflösen dieses Namens sendet, geben die Microsoft Azure-DNS-Server eine IP-Adresse zurück, die auf das primäre Azure-Rechenzentrum verweisen, das dem SBC zugewiesen ist. Die Zuordnung basiert auf Leistungsmetriken der Rechenzentren und der geografischen Nähe zum SBC. Die zurückgegebene IP-Adresse entspricht dem primären FQDN.
- **sip2.pstnhub.microsoft.com** – Sekundärer FQDN – ist der zweiten Prioritätsregion geografisch zuordnungen.
- **sip3.pstnhub.microsoft.com** – Dritter FQDN – geografische Zuordnung zur dritten Region mit Priorität.

Das Platzieren dieser drei FQDNs in dieser Reihenfolge ist für Folgendes erforderlich:

- Stellen Sie eine optimale Erfahrung (weniger geladen und dem SBC-Rechenzentrum am nächsten, das durch Abfragen des ersten FQDNs zugeordnet ist) zur Verfügung.
- Stellen Sie Failover bereit, wenn die Verbindung von einem SBC zu einem Rechenzentrum hergestellt wird, bei dem ein temporäres Problem auftritt. Weitere Informationen finden Sie unten unter [Failovermechanismus.](#failover-mechanism-for-sip-signaling)  

Die FQDNs – sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com und sip3.pstnhub.microsoft.com – werden in IP-Adressen aus den folgenden Subnetzen aufgelöst:

- 52.112.0.0/14
- 52.120.0.0/14

Sie müssen Ports für alle diese IP-Adressbereiche in Ihrer Firewall öffnen, um eingehenden und ausgehenden Datenverkehr zu und von den Adressen für Signale zu ermöglichen.  Wenn Ihre Firewall DNS-Namen unterstützt, wird der FQDN **sip-all.pstnhub.microsoft.com** in alle diese IP-Subnetze aufgelöst. 

> [!IMPORTANT]
> Im Rahmen Teams Direct Routing-Erweiterung und der Verbesserung der Dienste haben wir im November 2020 neue Instanzen der Direct Routing-Infrastruktur in Australien bereitgestellt. Dies wird in zwei zusätzlichen IP-Adressen (52.114.16.74 und 52.114.20.29) widerspiegelt, denen die folgenden FQDNs für australische Kunden – sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com und sip3.pstnhub.microsoft.com – aufgelöst werden. Sie müssen sicherstellen, dass diese beiden IP-Adressen (52.114.16.74 und 52.114.20.29) in Ihren IP-Zugriffssteuerungslisten (ACLs) zulässig sind, und ports sind für alle diese IP-Adressen in Ihrer Firewall geöffnet, um eingehenden und ausgehenden Datenverkehr an und von den Adressen zur Signalisierung zu ermöglichen.

> [!IMPORTANT]
> Im Rahmen Teams Direct Routing-Erweiterung und der Verbesserung der Dienste haben wir im Mai 2021 neue Instanzen der Direct-Routing-Infrastruktur in Japan bereitgestellt. Dies spiegelt sich in zwei zusätzlichen IP-Adressen (52.114.36.156 und 52.114.32.169) wider, denen die folgenden FQDNs für japanische Kunden – sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com und sip3.pstnhub.microsoft.com – aufgelöst werden. Sie müssen sicherstellen, dass diese beiden IP-Adressen (52.114.36.156 und 52.114.32.169) in Ihren IP-Zugriffssteuerungslisten (ACLs) zulässig sind und dass Ports für alle diese IP-Adressen in Ihrer Firewall geöffnet sind, um eingehenden und ausgehenden Datenverkehr von den Adressen zu und von den Adressen für Signale zu ermöglichen.

### <a name="office-gcc-dod-environment"></a>Office GCC DoD-Umgebung

Der Verbindungspunkt für Direct-Routing ist der folgende FQDN:

**sip.pstnhub.dod.teams.microsoft.us** – Globaler FQDN. Da die Office 365 DoD-Umgebung nur in den US-Rechenzentren vorhanden ist, gibt es keine sekundären und dritten FQDNs.

Die FQDN sip.pstnhub.dod.teams.microsoft.us wird in eine IP-Adresse aus dem folgenden Subnetz aufgelöst:

- 52.127.64.0/21

Sie müssen Ports für alle diese IP-Adressen in Ihrer Firewall öffnen, damit der eingehende und ausgehende Datenverkehr an die und von den Adressen für Die Signalisierung zulässig ist.

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High-Umgebung

Der Verbindungspunkt für Direct-Routing ist der folgende FQDN:

**sip.pstnhub.gov.teams.microsoft.us** – Globaler FQDN. Da die GCC High-Umgebung nur in den US-Rechenzentren vorhanden ist, gibt es keine sekundären und dritten FQDNs.

Die FQDN sip.pstnhub.gov.teams.microsoft.us wird in eine IP-Adresse aus dem folgenden Subnetz aufgelöst:

- 52.127.88.0/21

Sie müssen Ports für alle diese IP-Adressen in Ihrer Firewall öffnen, damit der eingehende und ausgehende Datenverkehr an die und von den Adressen für Die Signalisierung zulässig ist. Wenn Ihre Firewall DNS-Namen unterstützt, wird der FQDN **sip-all.pstnhub.gov.teams.microsoft.us** alle diese IP-Adressen aufgelöst. Dieser FQDN kann auch als Verbund-FQDN für die Klassifizierung eingehender Anrufe verwendet werden.

## <a name="sip-signaling-ports"></a>SIP-Signalisierung: Ports

Sie müssen die folgenden Ports für Microsoft 365 oder Office 365 verwenden, in denen Direct-Routing angeboten wird:
- Microsoft 365 oder Office 365
- Office 365 GCC
- Office 365 GCC Hoch
- Office 365 DoD

|Verkehr|Von|Bis|Quellport|Zielport|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP-Proxy|SBC|1024 – 65535|Definiert im SBC (für Office 365 GCC High/DoD muss nur Port 5061 verwendet werden)|
SIP/TLS|SBC|SIP-Proxy|Definiert im SBC|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>Failovermechanismus für SIP-Signalisierung

Der SBC erstellt eine DNS-Abfrage, um die sip.pstnhub.microsoft.com. Basierend auf dem SBC-Standort und den Leistungsmetriken des Rechenzentrums wird das primäre Rechenzentrum ausgewählt. Wenn beim primären Rechenzentrum ein Problem vorfeilt, versucht der SBC den sip2.pstnhub.microsoft.com, der zum zweiten zugewiesenen Rechenzentrum aufgelöst wird, und im seltenen Fall, dass Rechenzentren in zwei Regionen nicht verfügbar sind, wiederholen die SBC den letzten FQDN (sip3.pstnhub.microsoft.com), der die IP des dritten Rechenzentrums enthält.

In der folgenden Tabelle sind die Beziehungen zwischen primären, sekundären und dritten Rechenzentren zusammengefasst:

|Wenn das primäre Rechenzentrum|EMEA|NOAM|ASIEN|
|:--- |:--- |:--- |:--- |
|Das sekundäre Rechenzentrum (sip2.pstnhub.microsoft.com)|US|EU|US|
|Das Rechenzentrum der dritten Welt (sip3.pstnhub.microsoft.com)|ASIEN|ASIEN|EU|
|||||

## <a name="media-traffic-port-ranges"></a>Medienverkehr: Portbereiche
Beachten Sie, dass die folgenden Anforderungen gelten, wenn Sie Direct-Routing ohne Medienumgehung bereitstellen möchten. Informationen zu den Firewallanforderungen für die Medienumgehung finden Sie unter [Planen der Medienumgehung mit Direct-Routing.](./direct-routing-plan-media-bypass.md)



Der Medienverkehr fließt zu und von einem separaten Dienst in der Microsoft-Cloud. Die IP-Adressbereiche für Medienverkehr lauten wie folgt:

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365, Office 365 und Office 365 GCC Umgebung

- 52.112.0.0/14 (IP-Adressen von 52.112.0.1 bis 52.115.255.254).
- 52.120.0.0/14 (IP-Adressen von 52.120.0.1 bis 52.123.255.254).

### <a name="office-365-dod-environment"></a>Office 365 DoD-Umgebung

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High-Umgebung

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>Portbereich (gilt für alle Umgebungen)
Der Portbereich der Medienprozessoren ist in der folgenden Tabelle aufgeführt: 

|Verkehr|Von|Bis|Quellport|Zielport|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|Medienprozessor|SBC|3478-3481 und 49152 – 53247|Definiert im SBC|
|UDP/SRTP|SBC|Medienprozessor|Definiert im SBC|3478-3481 und 49152 – 53247|

  > [!NOTE]
  > Microsoft empfiehlt mindestens zwei Ports pro gleichzeitigem Aufruf des SBC.


## <a name="media-traffic-media-processors-geography"></a>Medienverkehr: Geographie der Medienprozessoren

Der Mediendatenverkehr fließt über Komponenten, die als Medienprozessoren bezeichnet werden. Medienprozessoren werden in den gleichen Rechenzentren wie SIP-Proxys platziert. Darüber hinaus gibt es weitere Medienprozessoren zur Optimierung des Medienflusses. Beispielsweise gibt es zurzeit keine SIP-Proxykomponente in Australien (SIP-Datenfluss über Singapur oder Hongkong), aber der Medienprozessor ist lokal in Australien verfügbar. Die lokale Notwendigkeit der Medienprozessoren wird durch die Latenz bestimmt, die durch das Senden von Datenverkehr über lange Entfernungen auftreten, z. B. von Australien nach Singapur oder Hongkong. Die Latenz im Beispiel für den Datenverkehr, der von Australien nach Hongkong oder Singapur fließt, ist zwar akzeptabel, um eine gute Anrufqualität für DEN SIP-Datenverkehr zu erhalten, bei Echtzeitmedienverkehr aber nicht.

Speicherort der Medienprozessoren:

Standorte, an denen sowohl SIP-Proxy- als auch Medienprozessorkomponenten bereitgestellt wurden:
- US (zwei in den Rechenzentren USA West und US East)
- Europa (Amsterdam und Dublin-Rechenzentren)
- Asien (Rechenzentrum Singapur)
- Japan (Rechenzentrums JP East und West)
- Australien (AU-Rechenzentrum im Osten und Südosten)

## <a name="media-traffic-codecs"></a>Mediendatenverkehr: Codecs

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>Leg between SBC and Cloud Media Processor or Microsoft Teams client.
Gilt sowohl für Fälle der Medienumgehung als auch für Nichtumgehungsfälle.

Die Direct Routing-Schnittstelle auf dem Weg zwischen Dem Session Border Controller und Cloud Media Processor (ohne Medienumgehung) oder zwischen dem Teams-Client und dem SBC (wenn die Medienumgehung aktiviert ist) kann die folgenden Codecs verwenden:

- Nicht-Medienumgehung (SBC zu Cloud Media Processor): SILK, G.711, G.722, G.729
- Medienumgehung (SBC Teams Client): SILK, G.711, G.722, G.729

Sie können die Verwendung des spezifischen Codecs auf dem Session Border Controller erzwingen, indem Sie unerwünschte Codecs aus dem Angebot ausschließen.

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>Leg between Microsoft Teams Client and Cloud Media Processor
Gilt nur für den Fall der Nicht-Medienumgehung. Bei der Medienumgehung fließen die Medien direkt zwischen dem Teams und dem SBC.

Auf dem Bein zwischen Cloud Media Processor und Microsoft Teams wird entweder SILK oder G.722 verwendet. Die Codec-Auswahl in diesem Abschnitt basiert auf Microsoft-Algorithmen, für die mehrere Parameter berücksichtigt werden. 


## <a name="supported-session-border-controllers-sbcs"></a>Unterstützte Session Border Controller (SBCs)

Microsoft unterstützt nur zertifizierte SBCs für die Kopplung mit Direct Routing. Da Enterprise-VoIP Unternehmen von entscheidender Bedeutung ist, führt Microsoft intensive Tests mit den ausgewählten SBCs durch und arbeitet mit den SBC-Anbietern zusammen, um sicherzustellen, dass die beiden Systeme kompatibel sind. 

Geräte, die überprüft wurden, werden als Zertifiziert für Teams Direct-Routing aufgeführt. Die zertifizierten Geräte funktionieren garantiert in allen Szenarien. 

Weitere Informationen zu unterstützten SBCs finden Sie unter [Liste der Session Border Controller, die für Direct Routing zertifiziert sind.](direct-routing-border-controllers.md)

 
## <a name="see-also"></a>Mehr dazu

[Konfigurieren von direktem Routing](direct-routing-configure.md)
