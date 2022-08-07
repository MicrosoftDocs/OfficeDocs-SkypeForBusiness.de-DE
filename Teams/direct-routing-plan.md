---
title: Planen von direktem Routing
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: filippse
ms.topic: conceptual
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Erfahren Sie, wie Sie mit Microsoft Direct Routing einen vom Kunden bereitgestellten Session Border Controller (SBC) mit dem Telefonsystem verbinden können.
ms.openlocfilehash: f3fe1e9f6f2244c7d33528488f07e66797509d2a
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267780"
---
# <a name="plan-direct-routing"></a>Planen von direktem Routing

> [!Tip]
> Schauen Sie sich die folgende Sitzung an, um mehr über die Vorteile von Direct Routing zu erfahren, wie Sie es planen und wie Sie es bereitstellen: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)

Mit Direct Routing können Sie einen unterstützten, vom Kunden bereitgestellten Session Border Controller (SBC) mit dem Telefonsystem verbinden. Mit dieser Funktion können Sie die lokale PSTN-Konnektivität (Public Switched Telephone Network) mit dem Microsoft Teams-Client konfigurieren, wie im folgenden Diagramm dargestellt: 

![Diagramm, das die Konfiguration der lokalen PSTN-Konnektivität zeigt.](media/PlanDirectRouting1-PSTNwithTeams.png "Konfiguration der lokalen PSTN-Konnektivität mit dem Microsoft Teams-Client")

  > [!NOTE]
  > mit Skype for Business Online können Sie auch einen vom Kunden bereitgestellten SBC koppeln, dies erfordert jedoch eine lokale Skype for Business Server Bereitstellung oder eine Sonderedition von Skype for Business namens Cloud Connector zwischen dem SBC und der Microsoft Cloud. Dieses Szenario wird als Hybrid-VoIP bezeichnet. Im Gegensatz dazu ermöglicht Direct Routing eine direkte Verbindung zwischen dem unterstützten SBC und der Microsoft Cloud.

> [!Important]
> Cloud Connector Edition wird zusammen mit Skype for Business Online am 31. Juli 2021 eingestellt. Nachdem Ihre Organisation auf Teams aktualisiert wurde, erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mitHilfe von [Direct Routing](direct-routing-landing-page.md) mit Teams verbinden. 

Mit Direct Routing können Sie Ihren SBC mit fast jedem Telefonietrunk verbinden oder mit PSTN-Geräten von Drittanbietern verbinden. Direct Routing ermöglicht Folgendes: 

- Verwenden Sie praktisch jeden PSTN-Trunk mit Telefonsystem. 

- Konfigurieren Sie die Interoperabilität zwischen kundeneigenen Telefoniegeräten, z. B. einer Nebenstellenanlage (Private Branch Exchange, PBX) eines Drittanbieters, analogen Geräten und Teams.

Microsoft bietet auch All-in-the-Cloud-VoIP-Lösungen an, z. B. Anrufplan. Eine Hybrid-VoIP-Lösung eignet sich jedoch möglicherweise am besten für Ihre Organisation, wenn: 

- Der Microsoft-Anrufplan ist in Ihrem Land nicht verfügbar. 

- Ihre Organisation erfordert eine Verbindung mit analogen Geräten, Callcentern usw. von Drittanbietern. 

- Ihre Organisation verfügt über einen bestehenden Vertrag mit einem PSTN-Netzbetreiber.

Direct Routing unterstützt auch Benutzer, die über die zusätzliche Lizenz für den Microsoft-Anrufplan verfügen. Weitere Informationen hierzu finden Sie in [Telefonsystem und Anrufpläne](calling-plan-landing-page.md). 

Wenn Benutzer an einer geplanten Konferenz teilnehmen, wird bei Direct Routing die Einwahlnummer vom Microsoft-Audiokonferenzdienst bereitgestellt, was eine ordnungsgemäße Lizenzierung erfordert.  Beim Ausgehenden platziert der Microsoft Audiokonferenzdienst den Anruf mithilfe von Onlineanruffunktionen, was eine ordnungsgemäße Lizenzierung erfordert. (Wenn ein Benutzer nicht über eine Lizenz für Microsoft-Audiokonferenzen verfügt, leitet der Anruf über Direct Routing weiter.) Weitere Informationen finden Sie unter [Onlinebesprechungen mit Teams](https://www.microsoft.com/en-us/microsoft-teams/online-meetings). 
 
Die Planung der Bereitstellung von Direct Routing ist der Schlüssel zu einer erfolgreichen Implementierung. In diesem Artikel werden Infrastruktur- und Lizenzierungsanforderungen beschrieben und Informationen zur SBC-Konnektivität bereitgestellt: 

- [Infrastrukturanforderungen](#infrastructure-requirements)
- [Lizenzierung und andere Anforderungen](#licensing-and-other-requirements)
- [SBC-Domänennamen](#sbc-domain-names)
- [Öffentliches vertrauenswürdiges Zertifikat für den SBC](#public-trusted-certificate-for-the-sbc)
- [SIP-Signalisierung: FQDNs](#sip-signaling-fqdns)
- [SIP-Signalisierung: Ports](#sip-signaling-ports)
- [Mediendatenverkehr: Portbereiche](#media-traffic-port-ranges)
- [Unterstützte Session Border Controller (SBCs)](#supported-session-border-controllers-sbcs)

Ausführliche Informationen zum Konfigurieren von Direct Routing finden [Sie unter Konfigurieren von Direct Routing](direct-routing-configure.md).

## <a name="infrastructure-requirements"></a>Infrastrukturanforderungen
Die Infrastrukturanforderungen für die unterstützten SBCs, Domänen und anderen Netzwerkkonnektivitätsanforderungen für die Bereitstellung von Direct Routing sind in der folgenden Tabelle aufgeführt:  

|Infrastrukturanforderung|Sie benötigen Folgendes:|
|:--- |:--- |
|Session Border Controller (SBC)|Ein unterstützter SBC. Weitere Informationen finden Sie unter [Unterstützte SBCs](#supported-session-border-controllers-sbcs).|
|Telefonietrunks, die mit dem SBC verbunden sind|Ein oder mehrere Telefonietrunks, die mit dem SBC verbunden sind. Auf einer Seite stellt der SBC über Direct Routing eine Verbindung mit dem Telefonsystem her. Der SBC kann auch eine Verbindung mit Telefonieentitäten von Drittanbietern herstellen, z. B. Nebenstellenanlagen, Analogtelefonieadapter usw. Jede PSTN-Konnektivitätsoption, die mit dem SBC verbunden ist, funktioniert. (Informationen zur Konfiguration der PSTN-Trunks für den SBC finden Sie unter den SBC-Anbietern oder Trunkanbietern.)|
|Microsoft 365-Organisation|Eine Microsoft 365-Organisation, mit der Sie Ihre Microsoft Teams-Benutzer und die Konfiguration und Verbindung mit dem SBC verwalten.|
|Benutzerregistrierungsstelle|Der Benutzer muss in Microsoft 365 verwaltet werden.<br/>Wenn Ihr Unternehmen über eine lokale Skype for Business- oder Lync-Umgebung mit Hybridverbindung zu Microsoft 365 verfügt, können Sie voIP in Teams für einen lokalen Benutzer nicht aktivieren.<br/><br/>Verwenden Sie zum Überprüfen der Registrierungsstelle eines Benutzers das folgende Skype for Business Online-PowerShell-Cmdlet:<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>Die Ausgabe des Cmdlets sollte Folgendes anzeigen:<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|Domänen|Eine oder mehrere Domänen, die Ihrer Microsoft 365- oder Office 365-Organisation hinzugefügt wurden.<br/><br/>Beachten Sie, dass Sie nicht die Standarddomäne . \*onmicrosoft.com verwenden können, die automatisch für Ihren Mandanten erstellt wird.<br/><br/>Zum Anzeigen der Domänen können Sie das folgende Skype for Business Online PowerShell-Cmdlet verwenden:<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>Weitere Informationen zu Domänen und Microsoft 365 oder Office 365 Organisationen finden Sie unter [Häufig gestellte Fragen (FAQ) zu Domänen](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).|
|Öffentliche IP-Adresse für den SBC|Eine öffentliche IP-Adresse, die zum Herstellen einer Verbindung mit dem SBC verwendet werden kann. Basierend auf dem SBC-Typ kann der SBC NAT verwenden.|
|Vollqualifizierter Domänenname (Fully Qualified Domain Name, FQDN) für den SBC|Ein FQDN für den SBC, wobei der Domänenteil des FQDN eine der registrierten Domänen in Ihrer Microsoft 365- oder Office 365 Organisation ist. Weitere Informationen finden Sie unter [SBC-Domänennamen](#sbc-domain-names).|
|Öffentlicher DNS-Eintrag für den SBC |Ein öffentlicher DNS-Eintrag, der den SBC-FQDN der öffentlichen IP-Adresse zuordnung. |
|Öffentliches vertrauenswürdiges Zertifikat für den SBC |Ein Zertifikat für den SBC, das für die gesamte Kommunikation mit Direct Routing verwendet werden soll. Weitere Informationen finden Sie unter [Öffentliches vertrauenswürdiges Zertifikat für den SBC](#public-trusted-certificate-for-the-sbc).|
|Verbindungspunkte für Direct Routing |Die Verbindungspunkte für Direct Routing sind die folgenden drei FQDNs:<br/><br/>`sip.pstnhub.microsoft.com` – Globaler FQDN, muss zuerst ausprobiert werden.<br/>`sip2.pstnhub.microsoft.com` – Sekundärer FQDN, geografisch der zweiten Prioritätsregion zugeordnet.<br/>`sip3.pstnhub.microsoft.com` – Tertiärer FQDN, geografisch der dritten Prioritätsregion zugeordnet.<br/><br/>Informationen zu den Konfigurationsanforderungen finden Sie unter [SIP-Signalisierung: FQDNs](#sip-signaling-fqdns).|
|Firewall-IP-Adressen und Ports für Direct Routing-Medien |Der SBC kommuniziert mit den folgenden Diensten in der Cloud:<br/><br/>SIP-Proxy, der die Signalisierung behandelt<br/>Medienprozessor, der Medien verarbeitet– außer wenn die Medienumgehung aktiviert ist<br/><br/>Diese beiden Dienste verfügen über separate IP-Adressen in Microsoft Cloud, die weiter unten in diesem Dokument beschrieben werden.<br/><br/>Weitere Informationen finden Sie im [Microsoft Teams-Abschnitt](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) in [URLs und IP-Adressbereichen](/office365/enterprise/urls-and-ip-address-ranges). |
|Medientransportprofil|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Firewall-IP-Adressen und Ports für Microsoft Teams-Medien |Weitere Informationen finden Sie unter [URLs und IP-Adressbereiche](/office365/enterprise/urls-and-ip-address-ranges). |
|||

## <a name="licensing-and-other-requirements"></a>Lizenzierung und andere Anforderungen 

Benutzern von Direct Routing müssen die folgenden Lizenzen in Microsoft 365 zugewiesen sein: 

- Microsoft-Telefonsystem
- Microsoft Teams + Skype for Business Plan 2, wenn in der Lizenzierung enthalten
- Microsoft Audio conferencing (Lesen Sie die Notizen und den folgenden Absatz, um spezifische Beispiele zu finden, wann diese Lizenz erforderlich ist.)

> [!NOTE]
> Skype for Business Plan sollte nicht aus einem Lizenzvertrag entfernt werden, in dem er enthalten ist. 
> 
> [!IMPORTANT]
> GCC High- und DoD-Benutzer sollten die in G5 enthaltene Audiokonferenzlizenzierung deaktivieren und warten, bis das Direct Routing vollständig konfiguriert wurde. Benutzer sollten Einwahltelefonnummern und eine funktionierende Wähltastatur konfiguriert haben, bevor Sie Audiokonferenzlizenzen aktivieren. Weitere Informationen finden Sie unter [Audiokonferenzen mit Direct Routing für GCC High und DoD](./audio-conferencing-with-direct-routing-for-gcch-and-dod.md) .


> [!IMPORTANT]
>  Wenn Sie externe Teilnehmer zu geplanten Besprechungen hinzufügen möchten, indem Sie sie entweder anrufen oder die Einwahlnummer angeben, ist die Audiokonferenzlizenz erforderlich.
> Weisen Sie für GCC High und DoD keine Audiokonferenzlizenz für G5-Benutzer zu. Weisen Sie G3-Benutzern erst dann eine Audiokonferenzlizenz zu, wenn Direct Routing vollständig konfiguriert ist und der Benutzer über eine funktionierende Wähltastatur verfügt.


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>Lizenz für Ad-hoc-Anrufeskalation und Audiokonferenz

Ein Teams-Benutzer kann einen 1:1-Anruf von Teams zu PSTN oder von Teams zu Teams starten und einen PSTN-Teilnehmer hinzufügen. Dieses Szenario wird als Ad-hoc-Konferenz bezeichnet. Der Anrufpfad hängt davon ab, ob dem Benutzer, der den Anruf eskaliert, eine Lizenz für Microsoft-Audiokonferenzen zugewiesen ist oder nicht:

- **Wenn dem Teams-Benutzer, der den Anruf eskaliert, eine Lizenz für Microsoft-Audiokonferenzen zugewiesen ist**, erfolgt die Eskalation über den Microsoft-Audiokonferenzdienst. Der Remote-PSTN-Teilnehmer, der zum vorhandenen Anruf eingeladen wird, erhält eine Benachrichtigung über den eingehenden Anruf und sieht die Nummer der Microsoft-Brücke, die dem Teams-Benutzer zugewiesen ist, der die Eskalation initiiert hat.

- **Wenn dem Teams-Benutzer, der den Anruf eskaliert, keine Lizenz für Microsoft-Audiokonferenzen zugewiesen** ist, erfolgt die Eskalation über einen Session Border Controller, der mit der Direct Routing-Schnittstelle verbunden ist. Der zum Anruf eingeladene Remote-PSTN-Teilnehmer erhält eine Benachrichtigung über den eingehenden Anruf und sieht die Nummer des Teams-Benutzers, der die Eskalation initiiert hat. Der für die Eskalation verwendete SBC wird durch die Routingrichtlinie des Benutzers definiert. 

Sie müssen Folgendes sicherstellen:
 
- CsOnlineVoiceRoutingPolicy wird dem Benutzer zugewiesen. 

- Private Anrufe zulassen ist auf Mandantenebene für Microsoft Teams aktiviert. 

Direct Routing unterstützt auch Benutzer, die für Microsoft Calling Plan lizenziert sind. Das Telefonsystem mit Anrufplan kann einige Anrufe über die Direct Routing-Schnittstelle weiterleiten. Die Telefonnummern der Benutzer müssen jedoch entweder online erworben oder zu Microsoft portiert werden.  

Das Mischen von Anrufplan- und Direct Routing-Konnektivität für denselben Benutzer ist optional, kann aber hilfreich sein. Wenn dem Benutzer beispielsweise ein Microsoft-Anrufplan zugewiesen ist, aber einige Anrufe mithilfe des SBC weitergeleitet werden sollen. Eines der häufigsten Szenarien sind Anrufe an Nebenstellenanlagen von Drittanbietern.  Bei Nebenstellenanlagen von Drittanbietern werden alle Anrufe, mit Ausnahme der Anrufe an die telefone, die mit dieser Nebenstellenanlage verbunden sind, mithilfe des Microsoft-Anrufplans weitergeleitet, aber Anrufe an telefone, die mit Nebenstellenanlagen von Drittanbietern verbunden sind, gehen an den SBC und bleiben daher im Unternehmensnetzwerk und nicht im PSTN. 

Weitere Informationen zur Telefonsystemlizenzierung finden [Sie unter "Optimale Nutzung von Office](https://products.office.com/compare-all-microsoft-office-products?tab=2) - und [Planoptionen](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options) und [Microsoft Teams-Add-On-Lizenzierung](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)". 

## <a name="supported-end-points"></a>Unterstützte Endpunkte 

Sie können folgendes als Endpunkt verwenden:

- Ein beliebiger Teams-Client. 

- Telefone für gemeinsame Bereiche. Weitere Informationen finden [Sie unter Einrichten von Telefonen für gemeinsame Bereiche für Microsoft Teams](./set-up-common-area-phones.md). Sie benötigen keine Anrufplanlizenz, wenn Sie ein Telefon für gemeinsame Bereiche mit Direct Routing einrichten.

- Skype for Business 3PIP-Telefone. Informationen [zur Unterstützung von Skype for Business Smartphones (3PIP) mit Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)


## <a name="sbc-domain-names"></a>SBC-Domänennamen

Der SBC-Domänenname muss aus einem der Namen stammen, die in Domänen des Mandanten registriert sind. Sie können den \*Mandanten onmicrosoft.com nicht für den FQDN-Namen des SBC verwenden.

Die folgende Tabelle enthält Beispiele für für den Mandanten registrierte DNS-Namen, ob der Name als FQDN für den SBC verwendet werden kann, und Beispiele für gültige FQDN-Namen:

|DNS-Name|Kann für SBC-FQDN verwendet werden|Beispiele für FQDN-Namen|
|:--- |:--- |:--- |
contoso.com|Ja|**Gültige Namen:**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|Nein|Die Verwendung von *.onmicrosoft.com-Domänen wird für SBC-Namen nicht unterstützt.

Angenommen, Sie möchten einen neuen Domänennamen verwenden. Ihr Mandant hat beispielsweise contoso.com als Domänennamen in Ihrem Mandanten registriert, und Sie möchten sbc1.sip.contoso.com verwenden. Bevor Sie einen SBC mit dem Namen sbc1.sip.contoso.com koppeln können, müssen Sie den Domänennamen sip.contoso.com in Domänen in Ihrem Mandanten registrieren. Wenn Sie versuchen, einen SBC mit sbc1.sip.contoso.com zu koppeln, bevor Sie den Domänennamen registrieren, wird die folgende Fehlermeldung angezeigt: "Die Domäne "sbc1.sip.contoso.com" kann nicht verwendet werden, da sie nicht für diesen Mandanten konfiguriert wurde."
Nachdem Sie den Domänennamen hinzugefügt haben, müssen Sie auch einen Benutzer mit UPN-user@sip.contoso.com erstellen und eine Teams-Lizenz zuweisen. Es kann bis zu 24 Stunden dauern, bis der Domänenname vollständig bereitgestellt wird, nachdem er domänen Ihres Mandanten hinzugefügt wurde, ein Benutzer mit einem neuen Namen erstellt und dem Benutzer eine Lizenz zugewiesen wurde. 

Es ist möglich, dass ein Unternehmen mehrere SIP-Adressräume in einem Mandanten hat. Beispielsweise kann ein Unternehmen contoso.com als SIP-Adressraum und fabrikam.com als zweiten SIP-Adressraum haben. Einige Benutzer verfügen über Adress-user@contoso.com und einige Benutzer über Adress-user@fabrikam.com. 

Der SBC benötigt nur einen FQDN und kann Benutzer von jedem Adressraum im gekoppelten Mandanten aus unterstützen. Beispielsweise kann ein SBC mit dem Namen sbc1.contoso.com den PSTN-Datenverkehr für Benutzer mit adressen user@contoso.com und user@fabrikam.com empfangen und senden, solange diese SIP-Adressräume im selben Mandanten registriert sind.  

 > [!NOTE]
 > SBC FQDN in Azure Communication Services Direct Routing muss sich von SBC FQDN in Teams Direct Routing unterscheiden.
  
## <a name="public-trusted-certificate-for-the-sbc"></a>Öffentliches vertrauenswürdiges Zertifikat für den SBC

Microsoft empfiehlt, das Zertifikat für den SBC durch Generieren einer Zertifizierungssignaturanforderung (CSR) anzufordern. Spezifische Anweisungen zum Generieren eines CSR für einen SBC finden Sie in den Verbindungsanweisungen oder dokumentationen, die von Ihren SBC-Anbietern bereitgestellt werden. 

> [!NOTE]
> Für die meisten Zertifizierungsstellen (CAs) muss die Größe des privaten Schlüssels mindestens 2048 sein. Beachten Sie dies beim Generieren der CSR.

Das Zertifikat muss den SBC-FQDN als allgemeinen Namen (CN) oder das Feld mit alternativen Antragstellernamen (SAN) aufweisen.

Alternativ unterstützt Direct Routing einen Platzhalter im CN und/oder SAN, und der Platzhalter muss dem standardmäßigen [RFC HTTP Over TLS](https://tools.ietf.org/html/rfc2818#section-3.1) entsprechen. Ein Beispiel wäre die Verwendung von \*.contoso.com, die dem SBC-FQDN-sbc.contoso.com entspricht, aber nicht mit sbc.test.contoso.com übereinstimmt.

Die SIP-Schnittstelle für direktes Routing vertraut nur Zertifikaten, die von Zertifizierungsstellen (CAs) signiert sind, die Teil des vertrauenswürdigen Microsoft-Stammzertifikatprogramms sind. Stellen Sie sicher, dass Ihr SBC-Zertifikat von einer Zertifizierungsstelle signiert ist, die Teil des Programms ist, und dass die Erweiterung für die erweiterte Schlüsselnutzung (Extended Key Usage, EKU) Ihres Zertifikats die Serverauthentifizierung umfasst.
Weitere Informationen: [Programmanforderungen – Microsoft Trusted Root Program](/security/trusted-root/program-requirements)
  
[Liste der enthaltenen Zertifizierungsstellenzertifikate](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)
  
 Für direct Routing in Office 365 GCCH- und DoD-Umgebungen muss das Zertifikat von einer der folgenden Stammzertifizierungsstellen generiert werden:

- DigiCert Global Root CA
- DigiCert High Assurance EV Root CA

> [!NOTE]
> Wenn die Mtls-Unterstützung (Mutual TLS) für die Teams-Verbindung auf dem SBC aktiviert ist, müssen Sie das Baltimore CyberTrust Root- und das DigiCert Global Root G2-Zertifikat im vertrauenswürdigen SBC-Stammspeicher des Teams TLS-Kontexts installieren. (Dies liegt daran, dass die Microsoft-Dienstzertifikate eines dieser beiden Stammzertifikate verwenden.) Informationen zum Herunterladen dieser Stammzertifikate finden Sie [unter Office 365 Verschlüsselungsketten](/microsoft-365/compliance/encryption-office-365-certificate-chains). Weitere Informationen finden Sie unter [Office TLS-Zertifikatänderungen](/microsoft-365/compliance/encryption-office-365-tls-certificates-changes).

## <a name="sip-signaling-fqdns"></a>SIP-Signalisierung: FQDNs 

Direct Routing wird in den folgenden Umgebungen angeboten:

- Microsoft 365 oder Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

Erfahren Sie mehr über [Office 365 und US Government-Umgebungen](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) wie GCC, GCC High und DoD.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365-, Office 365- und Office 365 GCC-Umgebungen

Die Verbindungspunkte für Direct Routing sind die folgenden drei FQDNs:

- **sip.pstnhub.microsoft.com** – globaler FQDN – muss zuerst ausprobiert werden. Wenn der SBC eine Anforderung zum Auflösen dieses Namens sendet, geben die Microsoft Azure-DNS-Server eine IP-Adresse zurück, die auf das primäre Azure-Rechenzentrum verweist, das dem SBC zugewiesen ist. Die Zuordnung basiert auf Leistungsmetriken der Rechenzentren und der geografischen Nähe zum SBC. Die zurückgegebene IP-Adresse entspricht dem primären FQDN.

- **sip2.pstnhub.microsoft.com** – Sekundärer FQDN – ist geografisch der zweiten Prioritätsregion zugeordnet.

- **sip3.pstnhub.microsoft.com** – Tertiärer FQDN – ist geografisch der dritten Prioritätsregion zugeordnet.

Diese drei FQDNs müssen in der folgenden Reihenfolge platziert werden:

- Optimale Benutzerfreundlichkeit (weniger geladen und am nächsten am SBC-Rechenzentrum, das durch Abfragen des ersten FQDN zugewiesen wurde).

- Bereitstellen eines Failovers, wenn eine Verbindung von einem SBC mit einem Rechenzentrum hergestellt wird, bei dem ein temporäres Problem auftritt. Weitere Informationen finden Sie unten unter [Failovermechanismus](#failover-mechanism-for-sip-signaling) .  

Die FQDNs – sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com und sip3.pstnhub.microsoft.com – werden in IP-Adressen aus den folgenden Subnetzen aufgelöst:

- 52.112.0.0/14
- 52.120.0.0/14

Sie müssen Ports für alle diese IP-Adressbereiche in Ihrer Firewall öffnen, um eingehenden und ausgehenden Datenverkehr zu und von den Adressen für die Signalisierung zuzulassen.

### <a name="office-gcc-dod-environment"></a>Office GCC-DoD-Umgebung

Der Verbindungspunkt für Direct Routing ist der folgende FQDN:

**sip.pstnhub.dod.teams.microsoft.us** – Globaler FQDN. Da die Office 365 DoD-Umgebung nur in den US-Rechenzentren vorhanden ist, gibt es keine sekundären und tertiären FQDNs.

Der FQDN-sip.pstnhub.dod.teams.microsoft.us wird in eine IP-Adresse aus dem folgenden Subnetz aufgelöst:

- 52.127.64.0/21

Sie müssen Ports für alle diese IP-Adressen in Ihrer Firewall öffnen, um eingehenden und ausgehenden Datenverkehr zu und von den Adressen für die Signalisierung zuzulassen.

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High-Umgebung

Der Verbindungspunkt für Direct Routing ist der folgende FQDN:

**sip.pstnhub.gov.teams.microsoft.us** – Globaler FQDN. Da die GCC High-Umgebung nur in den US-Rechenzentren vorhanden ist, gibt es keine sekundären und tertiären FQDNs.

Der FQDN-sip.pstnhub.gov.teams.microsoft.us wird in eine IP-Adresse aus dem folgenden Subnetz aufgelöst:

- 52.127.88.0/21

Sie müssen Ports für alle diese IP-Adressen in Ihrer Firewall öffnen, um eingehenden und ausgehenden Datenverkehr zu und von den Adressen für die Signalisierung zuzulassen.

## <a name="sip-signaling-ports"></a>SIP-Signalisierung: Ports

Sie müssen die folgenden Ports für Microsoft 365- oder Office 365-Umgebungen verwenden, in denen Direct Routing angeboten wird:

- Microsoft 365 oder Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

|Verkehr|Von|Bis|Quellport|Zielport|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP-Proxy|Sbc|1024 – 65535|Definiert auf dem SBC (für Office 365 GCC High/DoD muss nur Port 5061 verwendet werden)|
SIP/TLS|Sbc|SIP-Proxy|Definiert auf dem SBC|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>Failovermechanismus für die SIP-Signalisierung

Der SBC führt eine DNS-Abfrage aus, um sip.pstnhub.microsoft.com aufzulösen. Basierend auf dem SBC-Standort und den Leistungsmetriken des Rechenzentrums wird das primäre Rechenzentrum ausgewählt. Wenn im primären Rechenzentrum ein Problem auftritt, versucht der SBC die sip2.pstnhub.microsoft.com, die zum zweiten zugewiesenen Rechenzentrum aufgelöst wird, und in dem seltenen Fall, dass Rechenzentren in zwei Regionen nicht verfügbar sind, versucht der SBC den letzten FQDN (sip3.pstnhub.microsoft.com) erneut, der die tertiäre Rechenzentrums-IP bereitstellt.

In der folgenden Tabelle sind die Beziehungen zwischen primären, sekundären und tertiären Rechenzentren zusammengefasst:

|Wenn das primäre Rechenzentrum|EMEA|NOAM|ASIEN|
|:--- |:--- |:--- |:--- |
|Das sekundäre Rechenzentrum (sip2.pstnhub.microsoft.com)|US|Eu|US|
|Das tertiäre Rechenzentrum (sip3.pstnhub.microsoft.com)|ASIEN|ASIEN|Eu|
|||||

## <a name="media-traffic-port-ranges"></a>Mediendatenverkehr: Portbereiche
Beachten Sie, dass die folgenden Anforderungen gelten, wenn Sie Direct Routing ohne Medienumgehung bereitstellen möchten. Firewallanforderungen für die Medienumgehung finden Sie unter [Planen der Medienumgehung mit Direct Routing](./direct-routing-plan-media-bypass.md).

Der Mediendatenverkehr fließt zu und von einem separaten Dienst in der Microsoft-Cloud. Die IP-Adressbereiche für Mediendatenverkehr lauten wie folgt.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365-, Office 365- und Office 365 GCC-Umgebungen

- 52.112.0.0/14 (IP-Adressen von 52.112.0.1 bis 52.115.255.254).
- 52.120.0.0/14 (IP-Adressen von 52.120.0.1 bis 52.123.255.254).

### <a name="office-365-dod-environment"></a>Office 365 DoD-Umgebung

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High-Umgebung

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>Portbereich (gilt für alle Umgebungen)
Der Portbereich der Medienprozessoren wird in der folgenden Tabelle angezeigt: 

|Verkehr|Von|Bis|Quellport|Zielport|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|Medienprozessor|Sbc|3478-3481 und 49152 – 53247|Definiert auf dem SBC|
|UDP/SRTP|Sbc|Medienprozessor|Definiert auf dem SBC|3478-3481 und 49152 – 53247|

  > [!NOTE]
  > Microsoft empfiehlt mindestens zwei Ports pro gleichzeitigen Anruf auf dem SBC.


## <a name="media-traffic-media-processors-geography"></a>Mediendatenverkehr: Geografie der Medienprozessoren

Der Mediendatenverkehr fließt über Komponenten, die als Medienprozessoren bezeichnet werden. Medienprozessoren befinden sich in denselben Rechenzentren wie SIP-Proxys:

- NOAM (US South Central, two in US West and US East datacenters)
- Europa (Rechenzentren in Großbritannien Süd, Frankreich Zentral, Amsterdam und Dublin)
- Asien (Rechenzentrum in Singapur)
- Japan (JP Ost- und West-Rechenzentren)
- Australien (AU Ost- und Südost-Rechenzentren)
- LATAM (Brasilien Süd)
- Afrika (Südafrika Nord)

## <a name="media-traffic-codecs"></a>Mediendatenverkehr: Codecs

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>Leg zwischen SBC und Cloud Media Processor oder Microsoft Teams-Client

Gilt sowohl für Medienumgehungsfälle als auch für Nichtumgehungsfälle.

Die Direct Routing-Schnittstelle auf dem Bein zwischen dem Session Border Controller und dem Cloud-Medienprozessor (ohne Medienumgehung) oder zwischen dem Teams-Client und dem SBC (wenn Medienumgehung aktiviert ist) kann die folgenden Codecs verwenden:

- Non-Media-Umgehung (SBC zu Cloud Media Processor): SILK, G.711, G.722, G.729
- Medienumgehung (SBC zu Teams-Client): SILK, G.711, G.722, G.729

Sie können die Verwendung des bestimmten Codecs auf dem Session Border Controller erzwingen, indem Sie unerwünschte Codecs aus dem Angebot ausschließen.

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>Leg zwischen Microsoft Teams-Client und Cloud-Medienprozessor

Gilt nur für Umgehungsfälle ohne Medien. Mit der Medienumgehung fließen die Medien direkt zwischen dem Teams-Client und dem SBC.

Auf der Strecke zwischen cloudbasiertem Medienprozessor und Microsoft Teams-Client wird entweder SILK oder G.722 verwendet. Die Codec-Auswahl auf diesem Bein basiert auf Microsoft-Algorithmen, die mehrere Parameter berücksichtigen. 

  > [!NOTE]
  > Erneute Medienadressierung wird nicht unterstützt. Wenn der SBC während eines Direct Routing-Anrufs eine neue Medien-IP an Teams Direct Routing sendet, obwohl diese in der SIP-Signalisierung ausgehandelt wird, werden die Medien nie von Teams Direct Routing an die neue IP-Adresse gesendet.

## <a name="supported-session-border-controllers-sbcs"></a>Unterstützte Session Border Controller (SBCs)

Microsoft unterstützt nur zertifizierte SBCs für die Kopplung mit Direct Routing. Da Enterprise-VoIP für Unternehmen wichtig ist, führt Microsoft intensive Tests mit den ausgewählten SBCs durch und arbeitet mit den SBC-Anbietern zusammen, um sicherzustellen, dass die beiden Systeme kompatibel sind. 

Geräte, die überprüft wurden, werden als "Zertifiziert für Teams Direct Routing" aufgeführt. Die zertifizierten Geräte funktionieren garantiert in allen Szenarien. 

Weitere Informationen zu unterstützten SBCs finden Sie unter [Session Border Controller, die für Direct Routing zertifiziert sind](direct-routing-border-controllers.md).

## <a name="support-boundaries"></a>Supportgrenzen
Microsoft unterstützt das Telefonsystem mit Direct Routing nur, wenn es mit zertifizierten Geräten verwendet wird. Bei Problemen müssen Sie sich zuerst an den Kundensupport Ihres SBC-Lieferanten wenden. Bei Bedarf wird der SBC-Lieferant das Problem über interne Kanäle an Microsoft eskalieren. Microsoft behält sich das Recht vor, Supportfälle abzulehnen, in denen ein nicht zertifiziertes Gerät über Direct Routing mit dem Telefonsystem verbunden ist. Wenn Microsoft feststellt, dass das Direct Routing-Problem eines Kunden mit dem SBC-Gerät eines Lieferanten zusammenhängt, muss der Kunde den SBC-Anbieter erneut engagieren, um Support zu erhalten.
 
## <a name="see-also"></a>Siehe auch

[Konfigurieren von direktem Routing](direct-routing-configure.md)
