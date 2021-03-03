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
description: Erfahren Sie, wie Sie mit Microsoft Phone System Direct Routing einen unterstützten, vom Kunden bereitgestellten Session Border Controller (SBC) mit dem Microsoft Phone System verbinden können.
ms.openlocfilehash: 77757cf76215dbed0b3ec572b5f1f57120551d86
ms.sourcegitcommit: b12ec4703b164c545d17b02815edd6ee28d40bed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49923827"
---
# <a name="plan-direct-routing"></a>Planen von direktem Routing

> [!Tip]
> Schauen Sie sich die folgende Sitzung an, um mehr über die Vorteile von Direct Routing zu erfahren, die Planung dafür und die Bereitstellung zu erfahren: [Direktes Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)

Mit microsoft Phone System Direct Routing können Sie einen unterstützten, vom Kunden bereitgestellten Session Border Controller (SBC) mit dem Microsoft Phone System verbinden.  Mit dieser Funktion können Sie z. B. die lokale Konnektivität des öffentlichen Telefonnetzwerks (PSTN) mit dem Microsoft Teams-Client konfigurieren, wie in der folgenden Abbildung dargestellt: 

![Diagramm, das die Konfiguration der lokalen PSTN-Konnektivität zeigt](media/PlanDirectRouting1-PSTNwithTeams.png "Konfiguration der lokalen PSTN-Konnektivität mit dem Microsoft Teams-Client")

  > [!NOTE]
  > Mit Skype for Business Online können Sie auch einen vom Kunden bereitgestellten SBC koppeln. Dafür ist jedoch eine lokale Skype for Business Server-Bereitstellung oder eine spezielle Edition von Skype for Business, der so genannte Cloud Connector, zwischen dem SBC und der Microsoft Cloud erforderlich. Dieses Szenario wird als Hybridstimme bezeichnet. Im Gegensatz dazu ermöglicht das direkte Routing eine direkte Verbindung zwischen dem unterstützten SBC und der Microsoft Cloud.

> [!Important]
> Cloud Connector Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online abgeschaltet. Nachdem Ihr Unternehmen ein Upgrade auf Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mithilfe von Direct Routing mit Teams [verbinden.](direct-routing-landing-page.md) 

Mit Direct Routing können Sie Ihren SBC mit nahezu jedem Telefoniestamm oder mit Drittanbieter-PSTN-Ausrüstung verbinden. Mit Direct Routing können Sie: 

- Verwenden Sie praktisch jeden PSTN-Trunk mit Microsoft Phone System. 
- Konfigurieren Sie die Interoperabilität zwischen Telefoniegeräten im Besitz des Kunden, z. B. pbX (Private Branch Exchange) eines Drittanbieters, analogen Geräten und Microsoft Phone System.

Microsoft bietet auch Sprachlösungen für all-in-die-Cloud-Sprachlösungen an, z. B. Anrufplan. Eine Hybridlösung für Sprachanrufe ist jedoch möglicherweise für Ihre Organisation die beste Lösung, wenn: 

- Der Anrufplan von Microsoft ist in Ihrem Land nicht verfügbar. 
- Ihre Organisation benötigt eine Verbindung mit analogen Geräten, Callcentern und anderen Geräten von Drittanbietern. 
- Ihre Organisation hat einen bestehenden Vertrag mit einem PSTN-Netzbetreiber.

Direct Routing unterstützt auch Benutzer, die über eine zusätzliche Lizenz für den Microsoft-Anrufplan verfügen. Weitere Informationen finden Sie unter [Telefonsystem und Anrufpläne.](calling-plan-landing-page.md) 

Bei Verwendung von Direct Routing wird bei Teilnahme an einer geplanten Konferenz die Einwahlnummer vom Microsoft Audiokonferenzdienst bereitgestellt, für den eine ordnungsgemäße Lizenzierung erforderlich ist.  Beim Anrufen verwendet der Microsoft-Audiokonferenz-Dienst Onlineanruffunktionen, für die eine ordnungsgemäße Lizenzierung erforderlich ist. (Hinweis: Wenn ein Benutzer nicht über eine Lizenz für Microsoft-Audiokonferenzen verfügt, wird der Anruf über Direct Routing weiterleiten.) Weitere Informationen finden Sie unter [Onlinebesprechungen mit Teams.](https://products.office.com/microsoft-teams/online-meeting-solutions) 
 
Die Planung der Bereitstellung von Direct Routing ist der Schlüssel zu einer erfolgreichen Implementierung. In diesem Artikel werden die Infrastruktur- und Lizenzierungsanforderungen beschrieben, und es werden Informationen zur SBC-Konnektivität beschrieben: 

- [Infrastrukturanforderungen](#infrastructure-requirements)
- [Lizenzierung und andere Anforderungen](#licensing-and-other-requirements)
- [Namen von SBC-Domänen](#sbc-domain-names)
- [Öffentliches vertrauenswürdiges Zertifikat für den SBC](#public-trusted-certificate-for-the-sbc)
- [SIP-Signalisierung: FQDNs](#sip-signaling-fqdns)
- [SIP-Signalisierung: Ports](#sip-signaling-ports)
- [Mediendatenverkehr: Portbereiche](#media-traffic-port-ranges)
- [Unterstützte Session Border Controllers (SBCs)](#supported-session-border-controllers-sbcs)

Ausführliche Informationen zum Konfigurieren des direkten Routings finden Sie unter ["Konfigurieren des direkten Routings".](direct-routing-configure.md)

## <a name="infrastructure-requirements"></a>Infrastrukturanforderungen
Die Infrastrukturanforderungen für die unterstützten SBCs, Domänen und anderen Netzwerkverbindungsanforderungen für die Bereitstellung von Direct Routing sind in der folgenden Tabelle aufgeführt:  

|Infrastrukturanforderung|Sie benötigen Folgendes:|
|:--- |:--- |
|Session Border Controller (SBC)|Ein unterstützter SBC. Weitere Informationen finden Sie unter ["Unterstützte SBCs".](#supported-session-border-controllers-sbcs)|
|Telefonie-Trunks, die mit dem SBC verbunden sind|Mindestens ein Telefoniestamm, der mit dem SBC verbunden ist. An einem Ende stellt der SBC über Direct Routing eine Verbindung mit dem Microsoft Phone System auf. Der SBC kann auch Verbindungen mit Telefonieentitäten von Drittanbietern wie PBXs, Analog Telephony Adapters und so weiter herstellen. Jede pstN-Konnektivitätsoption, die mit dem SBC verbunden ist, funktioniert. (Informationen zur Konfiguration der PSTN-Trunks zum SBC finden Sie unter den SBC-Anbietern oder Trunkanbietern.)|
|Microsoft 365- oder Office 365-Organisation|Eine Microsoft 365- oder Office 365-Organisation, über die Sie Ihre Microsoft Teams-Benutzer sowie die Konfiguration und Verbindung mit dem SBC nutzen können.|
|Benutzerregistrierungsstelle|Der Benutzer muss in Microsoft 365 oder Office 365 homed sein.<br/>Wenn Ihr Unternehmen über eine lokale Skype for Business- oder Lync-Umgebung mit Hybridkonnektivität mit Microsoft 365 oder Office 365 verfügt, können Sie voice in Teams nicht für einen Benutzer aktivieren, der lokal verwendet wird.<br/><br/>Verwenden Sie das folgende Skype for Business Online-PowerShell-Cmdlet, um die Registrierungsstelle eines Benutzers zu überprüfen:<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>In der Ausgabe des Cmdlets sollte dies angezeigt werden:<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|Domänen|Eine oder mehrere Domänen, die Ihren Microsoft 365- oder Office 365-Organisationen hinzugefügt wurden.<br/><br/>Beachten Sie, dass Sie die Standarddomäne (.onmicrosoft.com) nicht verwenden können, die \* automatisch für Ihren Mandanten erstellt wird.<br/><br/>Zum Anzeigen der Domänen können Sie das folgende Skype for Business Online-PowerShell-Cmdlet verwenden:<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>Weitere Informationen zu Domänen und Microsoft 365- oder Office 365-Organisationen finden Sie unter "Häufig gestellte [Fragen zu Domänen".](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)|
|Öffentliche IP-Adresse für den SBC|Eine öffentliche IP-Adresse, die zum Herstellen einer Verbindung mit dem SBC verwendet werden kann. Basierend auf dem Typ von SBC kann SBC NAT verwenden.|
|Fully Qualified Domain Name (FQDN) für den SBC|Ein FQDN für den SBC, bei dem der Domänenteil des FQDN eine der registrierten Domänen in Ihrer Microsoft 365- oder Office 365-Organisation ist. Weitere Informationen finden Sie unter ["SBC-Domänennamen".](#sbc-domain-names)|
|Öffentlicher DNS-Eintrag für SBC |Ein öffentlicher DNS-Eintrag, der den SBC-FQDN der öffentlichen IP-Adresse zuzuordnen. |
|Öffentliches vertrauenswürdiges Zertifikat für den SBC |Ein Zertifikat für den SBC, das für die Kommunikation mit Direct Routing verwendet wird. Weitere Informationen finden Sie unter ["Öffentliches vertrauenswürdiges Zertifikat für den SBC".](#public-trusted-certificate-for-the-sbc)|
|Verbindungspunkte für das direkte Routing |Die Verbindungspunkte für direct Routing sind die folgenden drei FQDNs:<br/><br/>`sip.pstnhub.microsoft.com` – Der globale FQDN muss zuerst ausprobiert werden.<br/>`sip2.pstnhub.microsoft.com` – Sekundärer FQDN, geografisch zur Region mit zweiter Priorität.<br/>`sip3.pstnhub.microsoft.com` – Dritter FQDN, geografisch der dritten Region mit Priorität zu.<br/><br/>Informationen zu Konfigurationsanforderungen finden Sie unter [SIP Signaling: FQDNs.](#sip-signaling-fqdns)|
|Firewall-IP-Adressen und Ports für Direct-Routing-Medien |Der SBC kommuniziert mit den folgenden Diensten in der Cloud:<br/><br/>SIP-Proxy, der die Signalisierung behandelt<br/>Medienprozessor, der Medien behandelt – außer wenn die Medienumgehung<br/><br/>Diese beiden Dienste verfügen über separate IP-Adressen in der Microsoft Cloud, die weiter unten in diesem Dokument beschrieben werden.<br/><br/>Weitere Informationen finden Sie im Abschnitt ["Microsoft Teams"](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) in [URLs und IP-Adressbereichen.](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) |
|Medientransportprofil|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Firewall-IP-Adressen und Ports für Microsoft Teams-Medien |Weitere Informationen finden Sie unter [URLs und IP-Adressbereiche.](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) |
|||

## <a name="licensing-and-other-requirements"></a>Lizenzierung und andere Anforderungen 

Benutzern von Direct Routing müssen die folgenden Lizenzen in Microsoft 365 oder Office 365 zugewiesen sein: 

- "Microsoft Phone System" aus. 
- Microsoft Teams + Skype for Business Plan 2, falls in der Lizenzierung enthalten.
- Microsoft Audio Conferencing (bitte lesen Sie die Hinweise und den nachfolgenden Absatz, um spezifische Beispiele dafür zu erhalten, wann die Lizenz erforderlich ist).

> [!NOTE]
> Skype for Business Plan sollte nicht aus einem Lizenzvertrag entfernt werden, in dem er enthalten ist. 


> [!IMPORTANT]
>  Für den Fall, dass Sie externe Teilnehmer zu geplanten Besprechungen hinzufügen möchten, entweder durch Einenwählen oder durch Angabe der Einwahlnummer, ist die Lizenz für Audiokonferenzen erforderlich.


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>Ad-hoc-Anrufskalation und Lizenz für Audiokonferenzen

Ein Teams-Benutzer kann einen Eins-zu-Eins-Anruf von Teams über das PSTN oder einen Anruf von Teams zu Teams starten und einen Teilnehmer im öffentlichen Telefonnetz hinzufügen. Dieses Szenario wird als Ad-hoc-Konferenz bezeichnet. Der Weg, den der Anruf einnimmt, hängt davon ab, ob dem Benutzer, der den Anruf eskaliert, eine Microsoft-Audiokonferenz-Lizenz zugewiesen wurde:

- Wenn dem Teams-Benutzer, der den Anruf eskaliert, eine Lizenz für Microsoft Audiokonferenzen zugewiesen wurde, erfolgt die Konflikt durch den Microsoft Audio conferencing-Dienst. Der Remote-PSTN-Teilnehmer, der zum bestehenden Anruf eingeladen wird, erhält eine Benachrichtigung über den eingehenden Anruf und sieht die Nummer der Microsoft Bridge, die dem Teams-Benutzer, der die Konflikt ausgelöst hat, zugewiesen wurde.
- Wenn dem Teams-Benutzer, der den Anruf eskaliert, keine Microsoft-Audiokonferenz-Lizenz zugewiesen ist, erfolgt die Konflikt durch einen Session Border Controller, der mit der Direct-Routing-Schnittstelle verbunden ist. Der Remote-PSTN-Teilnehmer, der zu dem Anruf eingeladen wird, erhält eine Benachrichtigung über den eingehenden Anruf und sieht die Nummer des Teams-Benutzers, der die Konflikt ausgelöst hat. Der spezifische SBC, der für die Eskalierung verwendet wird, wird durch die Routingrichtlinie des Benutzers definiert. 


Darüber hinaus müssen Sie Folgendes sicherstellen:
 
- CsOnlineVoiceRoutingPolicy wird dem Benutzer zugewiesen. 
- "Private Anrufe zulassen" ist auf Mandantenebene für Microsoft Teams aktiviert. 

Direct Routing unterstützt auch Benutzer, die für den Anrufplan von Microsoft lizenziert sind. Microsoft Phone System with Calling Plan can route some calls using the Direct Routing interface. Die Telefonnummern der Benutzer müssen jedoch entweder online erworben oder zu Microsoft portiert werden.  

Das Mischen von Anrufplan- und Direct-Routing-Konnektivität für denselben Benutzer ist optional, kann aber hilfreich sein (z. B. wenn dem Benutzer ein Microsoft-Anrufplan zugewiesen ist, er aber einige Anrufe mit dem SBC weiterleiten möchte). Eines der am häufigsten verwendeten Szenarien sind Anrufe an PbXs von Drittanbietern.  Bei Festnetztelefonen von Drittanbietern werden alle Anrufe, mit Ausnahme von Anrufen an die mit dieser Telefonanlage verbundenen Telefone, über den Anrufplan von Microsoft geroutet, aber Anrufe an Telefone, die mit PbXs von Drittanbietern verbunden sind, gehen an den SBC und bleiben daher im Unternehmensnetzwerk und nicht im PSTN. 

Weitere Informationen zur Telefonsystemlizenzierung finden Sie unter ["Office-](https://products.office.com/compare-all-microsoft-office-products?tab=2) und [Planoptionen am besten verwenden".](https://technet.microsoft.com/library/office-365-plan-options.aspx) 

Weitere Informationen zur Telefonsystemlizenzierung finden Sie unter [Microsoft Teams-Add-On-Lizenzierung.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) 

## <a name="supported-end-points"></a>Unterstützte Endpunkte 

Sie können dies als Endpunkt verwenden:

- Ein beliebiger Teams-Client. 
- Telefone in der Nähe. Weitere Informationen finden Sie unter Einrichten [der Common Area Phone-Lizenz für Microsoft Teams.](https://docs.microsoft.com/microsoftteams/set-up-common-area-phones) Beachten Sie, dass Sie keine Anrufplanlizenz benötigen, wenn Sie ein Telefon im allgemeinen Bereich mit Direktrouting einrichten.
- Skype for Business 3PIP-Telefone. Support [für Skype for Business-Telefone (3PIP) mit Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)


## <a name="sbc-domain-names"></a>Namen von SBC-Domänen

Der Name der SBC-Domäne muss aus einem der Namen kommen, die in "Domänen" des Mandanten registriert sind. Sie können den \* Mandanten ".onmicrosoft.com" nicht für den FQDN-Namen des SBC verwenden.

Die folgende Tabelle enthält Beispiele für DNS-Namen, die für den Mandanten registriert sind, ob der Name als FQDN für den SBC verwendet werden kann, und Beispiele für gültige FQDN-Namen:

|DNS name|Kann für SBC-FQDN verwendet werden|Beispiele für FQDN-Namen|
|:--- |:--- |:--- |
contoso.com|Ja|**Gültige Namen:**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|Nein|Die Verwendung von *.onmicrosoft.com-Domänen wird für #A0 nicht unterstützt.

Angenommen, Sie möchten einen neuen Domänennamen verwenden. Ihr Mandant hat beispielsweise contoso.com in Ihrem Mandanten registrierten Domänennamen, und Sie möchten sbc1.sip.contoso.com. Bevor Sie einen SBC mit dem Namen sbc1.sip.contoso.com koppeln können, müssen Sie den Domänennamen in sip.contoso.com In Domains in Ihrem Mandanten registrieren. Wenn Sie versuchen, einen SBC mit sbc1.sip.contoso.com zu koppeln, bevor Sie den Domänennamen registrieren, wird die folgende Fehlermeldung angezeigt: "Die Domäne "sbc1.sip.contoso.com" kann nicht verwendet werden, da sie für diesen Mandanten nicht konfiguriert wurde."
Nachdem Sie den Domänennamen hinzugefügt haben, müssen Sie auch einen Benutzer mit UPN-user@sip.contoso.com und eine Teamlizenz zuweisen. Es kann bis zu 24 Stunden dauern, bis der Domänenname vollständig bereitgestellt wurde, nachdem er den Domänen Ihres Mandanten hinzugefügt wurde, ein Benutzer mit einem neuen Namen erstellt und dem Benutzer eine Lizenz zugewiesen wurde. 

Es ist möglich, dass ein Unternehmen mehrere SIP-Adressräume in einem Mandanten hat. Beispielsweise könnte ein Unternehmen über contoso.com A0 verfügen und fabrikam.com als zweiten SIP-Adressbereich. Einige Benutzer verfügen über Adressadressen user@contoso.com und einige Benutzer haben Adressadressen user@fabrikam.com. 

Der SBC benötigt nur einen FQDN und kann die Benutzer über einen beliebigen Adressbereich im gekoppelten Mandanten serviceen. So kann beispielsweise ein SBC mit dem Namen sbc1.contoso.com den Datenverkehr über das Festnetz für Benutzer mit den Adressen user@contoso.com und user@fabrikam.com empfangen und senden, solange diese SIP-Adressräume im selben Mandanten registriert sind.  

## <a name="public-trusted-certificate-for-the-sbc"></a>Öffentliches vertrauenswürdiges Zertifikat für den SBC

Microsoft empfiehlt, dass Sie das Zertifikat für den SBC anfordern, indem Sie eine Zertifizierungssignaturanforderung (Certification Signing Request, CSR) generieren. Spezifische Anweisungen zum Generieren eines CSR für einen SBC finden Sie in den Anleitungen oder Dokumentationen Ihrer SBC-Anbieter. 

  > [!NOTE]
  > Die meisten Zertifizierungsstelle (Certificate Authorities, CAs) benötigen die Größe des privaten Schlüssels mindestens 2048. Beachten Sie dies beim Generieren des CSR.

Für das Zertifikat muss der SBC-FQDN als gemeinsamer Name (Common Name, CN) oder das Feld mit dem alternativen Betreffnamen (Subject Alternative Name, SAN) verwendet werden. Das Zertifikat sollte direkt von einer Zertifizierungsstelle ausgestellt werden, nicht von einem Zwischenanbieter.

Alternativ unterstützt Direct Routing einen Platzhalter im CN und/oder SAN, und der Platzhalter muss rfc [HTTP Over TLS (STANDARD RFC HTTP Over TLS) entsprechen.](https://tools.ietf.org/html/rfc2818#section-3.1) Ein Beispiel wäre die Verwendung von contoso.com, die dem \* SBC-FQDN-sbc.contoso.com entsprechen würde, aber nicht mit sbc.test.contoso.com.

Das Zertifikat muss von einer der folgenden Stammzertifizierungsstelle generiert werden:

- Trust
- Stamm der externen AddTrust-Zertifizierungsstelle
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
- StatusVadis

Für das direkte Routing in Office 365-GCCH- und -DoD-Umgebungen muss das Zertifikat von einer der folgenden Stammzertifizierungsstelle generiert werden:
- DigiCert Global Root CA
- DigiCert High Assurance EV Root CA

> [!NOTE]
> *Wenn die Unterstützung von Mutual TLS (MTLS) für die #A0 auf dem SBC aktiviert ist, müssen Sie das Baltimore CyberTrust Root Certificate im vertrauenswürdigen SBC-Stammspeicher des Teams-TLS-Kontexts installieren. (Dies liegt daran, dass für die Microsoft-Dienstzertifikate das Rootzertifikat von Baltimore verwendet wird.) Informationen zum Herunterladen des Rootzertifikats für Baltimore finden Sie unter [Office 365-Verschlüsselungsketten.](https://docs.microsoft.com/microsoft-365/compliance/encryption-office-365-certificate-chains)

Microsoft arbeitet daran, basierend auf Kundenanforderungen zusätzliche Zertifizierungsstellen hinzufügen. 

## <a name="sip-signaling-fqdns"></a>SIP-Signalisierung: FQDNs 

Direct Routing wird in den folgenden Umgebungen angeboten:
- Microsoft 365 oder Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

Erfahren Sie mehr über [Office 365- und US-Government-Umgebungen](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) wie GCC, GCC High und DoD.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365-, Office 365- und Office 365 -GCC-Umgebungen

Die Verbindungspunkte für Direct Routing sind die folgenden drei FQDNs:

- **sip.pstnhub.microsoft.com** – Globaler FQDN – muss zuerst ausprobiert werden. Wenn der SBC eine Anforderung zum Auflösen dieses Namens sendet, geben die Microsoft Azure-DNS-Server eine IP-Adresse zurück, die auf das primäre Azure-Rechenzentrum, das dem SBC zugewiesen ist, verweisen. Die Zuweisung basiert auf Leistungsmetriken der Rechenzentren und der geografischen Nähe zum SBC. Die zurückgegebene IP-Adresse entspricht dem primären FQDN.
- **sip2.pstnhub.microsoft.com** – Sekundärer FQDN – ist der Region mit zweiter Priorität geografisch zu ordnet.
- **sip3.pstnhub.microsoft.com** – Dritter FQDN – geografische Zuordnung zur dritten Region mit Priorität.

Das Platzieren dieser drei FQDNs in dieser Reihenfolge ist für Folgendes erforderlich:

- Stellen Sie eine optimale Benutzererfahrung (weniger geladen und dem SBC-Rechenzentrum am nächsten, das durch Abfragen des ersten FQDNs zugeordnet ist) zur Verfügung.
- Stellen Sie Failover bereit, wenn die Verbindung von einem SBC zu einem Rechenzentrum hergestellt wird, bei dem ein temporäres Problem auftritt. Weitere Informationen finden Sie weiter unten unter ["Failovermechanismus".](#failover-mechanism-for-sip-signaling)  

Die FQDNs – sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com und sip3.pstnhub.microsoft.com – werden in eine der folgenden IP-Adressen aufgelöst:

- 52.114.148.0
- 52.114.132.46 
- 52.114.75.24 
- 52.114.76.76 
- 52.114.7.24 
- 52.114.14.70
- 52.114.16.74
- 52.114.20.29

Sie müssen Ports für alle diese IP-Adressen in Ihrer Firewall öffnen, damit eingehender und ausgehender Datenverkehr an und von den Adressen für Signalisierungen zulässig ist.  Wenn Ihre Firewall DIE NAMEN von  DNS unterstützt, sip-all.pstnhub.microsoft.com der FQDN für alle diese IP-Adressen aufgelöst. 

> [!IMPORTANT]
>  Im Rahmen der Erweiterung und Dienstverbesserung von Teams Direct Routing haben wir neue Instanzen der Direct -Routing-Infrastruktur in Australien bereitgestellt. Dies spiegelt sich in zwei zusätzlichen IP-Adressen (52.114.16.74 und 52.114.20.29) wider, denen die folgenden FQDNs für australische Kunden aufgelöst werden – sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com und sip3.pstnhub.microsoft.com. Sie müssen diese beiden IP-Adressen (52.114.16.74 und 52.114.20.29) zu Ihren IP Access Control Lists (ACLs) hinzufügen und Ports für alle diese IP-Adressen in Ihrer Firewall öffnen, um eingehenden und ausgehenden Datenverkehr an und von den Adressen zur Signalisierung zu ermöglichen.

### <a name="office-365-gcch-and-dod-environment"></a>Office 365-GGCH- und -DoD-Umgebung

Der Verbindungspunkt für das direkte Routing ist der folgende FQDN:

**sip.pstnhub.dod.teams.microsoft.us** – Globaler FQDN. Da die Office 365 -DoD-Umgebung nur in den USA vorhanden ist, gibt es keine sekundären und dritten FQDNs.

Der FQDN sip.pstnhub.dod.teams.microsoft.us wird in eine der folgenden IP-Adressen aufgelöst:

- 52.127.64.33
- 52.127.68.34

Sie müssen Ports für alle diese IP-Adressen in Ihrer Firewall öffnen, damit eingehender und ausgehender Datenverkehr an und von den Adressen für Signalisierungen zulässig ist.

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High environment

Der Verbindungspunkt für das direkte Routing ist der folgende FQDN:

**sip.pstnhub.gov.teams.microsoft.us** – Globaler FQDN. Da die Umgebung "GCC High" nur in den US-Rechenzentren vorhanden ist, gibt es keine sekundären und dritten FQDNs.

Der FQDN sip.pstnhub.gov.teams.microsoft.us wird in eine der folgenden IP-Adressen aufgelöst:

- 52.127.88.59
- 52.127.92.64

Sie müssen Ports für alle diese IP-Adressen in Ihrer Firewall öffnen, um eingehenden und ausgehenden Datenverkehr zu und von den Adressen für Signalisierungen zu ermöglichen. Wenn Ihre Firewall dns-Namen unterstützt,  wird der FQDN-sip-all.pstnhub.gov.teams.microsoft.us für alle diese IP-Adressen aufgelöst. Dieser FQDN kann auch als Verbund-FQDN für die Klassifizierung eingehender Anrufe verwendet werden.

## <a name="sip-signaling-ports"></a>SIP-Signalisierung: Ports

Sie müssen die folgenden Ports für Microsoft 365- oder Office 365-Umgebungen verwenden, in denen Direct Routing angeboten wird:
- Microsoft 365 oder Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

|Verkehr|Von|Bis|Quellport|Zielport|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP-Proxy|SBC|1024 – 65535|Definiert auf dem SBC (für Office 365 GCC High/DoD muss nur Port 5061 verwendet werden)|
SIP/TLS|SBC|SIP-Proxy|Definiert für den SBC|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>Failovermechanismus für die SIP-Signalisierung

Der SBC erstellt eine DNS-Abfrage, um die Probleme sip.pstnhub.microsoft.com. Basierend auf dem Standort des SBC und den Leistungsmetriken des Rechenzentrums wird das primäre Rechenzentrum ausgewählt. Wenn beim primären Rechenzentrum ein Problem vor sich geht, versucht der SBC den sip2.pstnhub.microsoft.com, der zum zweiten zugewiesenen Rechenzentrum aufgelöst wird, und in dem seltenen Fall, dass Rechenzentren in zwei Regionen nicht verfügbar sind, wiederholen die SBC den letzten FQDN (sip3.pstnhub.microsoft.com), der die IP des dritten Rechenzentrums liefert.

In der folgenden Tabelle sind die Beziehungen zwischen primären, sekundären und dritten Rechenzentren zusammengefasst:

|Wenn das primäre Rechenzentrum|EMEA|NOAM|ASIEN|
|:--- |:--- |:--- |:--- |
|Das sekundäre Rechenzentrum (sip2.pstnhub.microsoft.com)|US|EU|US|
|Das rechenzentrum der dritten Stadt (sip3.pstnhub.microsoft.com)|ASIEN|ASIEN|EU|
|||||

## <a name="media-traffic-port-ranges"></a>Mediendatenverkehr: Portbereiche
Beachten Sie, dass die folgenden Anforderungen gelten, wenn Sie das direkte Routing ohne Medienumgehung bereitstellen möchten. Informationen zu den Firewallanforderungen für die Medienumgehung finden Sie unter "Planen der [Medienumgehung mit Direct Routing".](https://docs.microsoft.com/microsoftteams/direct-routing-plan-media-bypass)



Der Mediendatenverkehr fließt zu und von einem separaten Dienst in der Microsoft Cloud. Die FOLGENDEN IP-Adressbereiche für den Medienverkehr:

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365-, Office 365- und Office 365 -GCC-Umgebungen

- 52.112.0.0/14 (IP-Adressen von 52.112.0.1 bis 52.115.255.254).
- 52.120.0.0/14 (IP-Adressen von 52.120.0.1 bis 52.123.255.254).

### <a name="office-365-dod-environment"></a>Office 365 DoD-Umgebung

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High environment

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>Portbereich (gilt für alle Umgebungen)
Der Portbereich der Medienprozessoren ist in der folgenden Tabelle dargestellt: 

|Verkehr|Von|Bis|Quellport|Zielport|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|Medienprozessor|SBC|3478-3481 und 49152 – 53247|Definiert für den SBC|
|UDP/SRTP|SBC|Medienprozessor|Definiert für den SBC|3478-3481 und 49152 – 53247|

  > [!NOTE]
  > Microsoft empfiehlt mindestens zwei Ports pro gleichzeitigem Aufruf des SBC.


## <a name="media-traffic-media-processors-geography"></a>Mediendatenverkehr: Geographie der Medienprozessoren

Der Mediendatenverkehr fließt über Komponenten, die als Medienprozessoren bezeichnet werden. Medienprozessoren werden in den gleichen Rechenzentren wie die SIP-Proxys platziert. Darüber hinaus gibt es weitere Medienprozessoren, um den Medienfluss zu optimieren. Beispielsweise gibt es derzeit keine SIP-Proxykomponente in Australien (SIP fließt über Singapur oder Hongkong), aber wir haben den Medienprozessor lokal in Australien. Die lokale Notwendigkeit für die Medienprozessoren wird durch die Latenz bestimmt, die durch das Senden von Datenverkehr über eine lange Distanz, z. B. von Australien nach Singapur oder Hongkong, auftreten kann. Im Beispiel für den Datenverkehr, der von Australien nach Hongkong oder Singapur fließt, ist die Latenz zwar akzeptabel, um eine gute Anrufqualität für den SIP-Datenverkehr zu gewährleisten, für Echtzeitmedienverkehr ist dies jedoch nicht zulässig.

Speicherort der Medienprozessoren:

Standorte, an denen sowohl die Komponenten für den SIP-Proxy als auch die Medienprozessorkomponenten bereitgestellt wurden:
- USA (zwei Rechenzentren im Westen und im Osten der USA)
- Europa (Rechenzentrume in Amsterdam und Dublin)
- Asien (Rechenzentren in Singapur und Hongkong)

Speicherorte, an denen nur Medienprozessoren bereitgestellt sind (SIP fließt über das oben aufgeführte nächstgelegene Rechenzentrum):
- Japan (Rechenzentrum JP East and West)
- Australien (Au-Ost- und Südostdatencenter)




## <a name="media-traffic-codecs"></a>Mediendatenverkehr: Codecs

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>Leg between SBC and Cloud Media Processor or Microsoft Teams client.
Gilt sowohl für Medienumgehungsfälle als auch für Fälle, in denen die Umgehung nicht möglich ist.

Die Direct Routing-Schnittstelle auf dem Weg zwischen dem Session Border Controller und dem Cloud Media Processor (ohne Medienumgehung) oder zwischen dem Client von Teams und dem SBC (sofern die Medienumgehung aktiviert ist) kann die folgenden Codecs verwenden:

- Nicht-Medienumgehung (SBC to Cloud Media Processor): SILK, G.711, G.722, G.729
- Medienumgehung (SBC zu Teams-Client): SILK, G.711, G.722, G.729

Sie können die Verwendung des spezifischen Codecs auf dem Session Border Controller erzwingen, indem Sie unerwünschte Codecs aus dem Angebot ausschließen.

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>Leg between Microsoft Teams Client and Cloud Media Processor
Gilt nur für nicht medianumgehungsfreie Fälle. Bei der Medienumgehung fließen die Medien direkt zwischen dem Teams-Client und dem SBC.

Auf dem Abschnitt zwischen dem Cloud Media Processor und dem Microsoft Teams-Client wird entweder SILK oder G.722 verwendet. Die Codecauswahl in diesem Abschnitt basiert auf Microsoft-Algorithmen, die mehrere Parameter berücksichtigen. 


## <a name="supported-session-border-controllers-sbcs"></a>Unterstützte Session Border Controllers (SBCs)

Microsoft unterstützt nur zertifizierte SBCs zur Kopplung mit Direct Routing. Da Enterprise-VoIP für Unternehmen von entscheidender Bedeutung ist, führt Microsoft intensive Tests mit den ausgewählten SBCs durch und arbeitet mit den SBC-Anbietern zusammen, um sicherzustellen, dass die beiden Systeme kompatibel sind. 

Überprüfte Geräte werden als "Für Teams Direct Routing zertifiziert" aufgeführt. Die zertifizierten Geräte funktionieren garantiert in allen Szenarien. 

Weitere Informationen zu unterstützten SBCs finden Sie in der [Liste der Session Border Controller, die für direct Routing zertifiziert sind.](direct-routing-border-controllers.md)

 
## <a name="see-also"></a>Siehe auch

[Konfigurieren von direktem Routing](direct-routing-configure.md)
