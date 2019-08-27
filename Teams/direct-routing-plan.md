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
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Lesen Sie diesen Artikel, um zu erfahren, wie Sie mit dem Direct Routing des Microsoft-Telefonsystems einen unterstützten, vom Kunden bereitgestellten Session Border Controller (SBC) mit dem Microsoft-Telefonsystem verbinden können.
ms.openlocfilehash: 8dc06650a50af5b66931f196c0a1c3d7c5090bc5
ms.sourcegitcommit: b914c044c43ff8147f35eea684fec1de01a7bcd2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464579"
---
# <a name="plan-direct-routing"></a>Planen von direktem Routing

> [!Tip]
> Schauen Sie sich die folgende Sitzung mit Informationen zu den Vorteilen von Direct Routing sowie dessen Planung und Bereitstellung an: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)

Mit dem Direct Routing des Microsoft-Telefonsystems können Sie einen unterstützten, vom Kunden bereitgestellten Session Border Controller (SBC) mit dem Microsoft-Telefonsystem verbinden.  Mit dieser Funktion können Sie z.B. die lokale PSTN-Konnektivität mit Microsoft Teams-Client konfigurieren, wie im folgenden Diagramm dargestellt: 

![Diagramm mit der Konfiguration der lokalen PSTN-Konnektivität](media/PlanDirectRouting1-PSTNwithTeams.png "Konfiguration der lokalen PSTN-Konnektivität mit Microsoft Teams-Client")

  > [!NOTE]
  > In Skype for Business Online können Sie auch einen vom Kunden bereitgestellten SBC koppeln. Dies setzt aber voraus, dass eine lokale Skype for Business Server-Bereitstellung oder eine spezielle Version von Skype for Business namens Cloud Connector zwischen dem SBC und der Microsoft Cloud installiert wird. Dieses Szenario ist als Hybridtelefonie bekannt. Im Gegensatz dazu ermöglicht Direct Routing eine direkte Verbindung zwischen dem unterstützten SBC und der Microsoft Cloud. 

Mit Direct Routing können Sie Ihren SBC mit fast jedem Telefonie-Trunk oder Telefonfestnetz-Gerät (Public Switched Telephone Network, PSTN) von Drittanbietern verbinden. Mit Direct Routing können Sie folgende Aktionen ausführen: 

- Praktisch jeden PSTN-Trunk mit dem Microsoft-Telefonsystem verwenden. 
- Die Interoperabilität zwischen kundeneigenen Telefonanlagen, z.B. einer Festnetztelefonanlage (Third Party Private Branch Exchange, PBX), analogen Geräten und Microsoft-Telefonsystem konfigurieren.

Microsoft bietet auch alle Voice-Lösungen in der Cloud, z.B. Anrufplan.  Möglicherweise ist jedoch eine hybride Telefonlösung für Ihre Organisation am besten, wenn: 

- Microsoft-Anrufplan in Ihrem Land nicht verfügbar ist. 
- Für Ihre Organisation eine Verbindung mit analogen Geräten von Drittanbietern, Call-Centern und so weiter erforderlich ist. 
- Ihre Organisation einen bestehenden Vertrag mit einem PSTN-Betreiber hat. 

Direct Routing auch Benutzer unterstützt, die über die zusätzliche Lizenz für den Microsoft-Anrufplan verfügen. Weitere Informationen hierzu finden Sie unter [Telefonsystem und Anrufpläne](calling-plan-landing-page.md). 

Wenn Benutzer an einer geplanten Konferenz teilnehmen und Direct Routing verwenden, wird die Einwahlnummer vom Microsoft-Audiokonferenzdienst bereitgestellt, für den eine ordnungsgemäße Lizenzierung erforderlich ist.  Bei externen Anrufen führt der Microsoft-Audiokonferenzdienst den Anruf über Online-Anruffunktionen durch, die eine ordnungsgemäße Lizenzierung voraussetzen. (Beachten Sie, dass das Hinauswählen nicht durch Direct Routing geleitet wird.) Weitere Informationen finden Sie unter [Online-Besprechungen mit Teams](https://products.office.com/microsoft-teams/online-meeting-solutions). 
 
Die Bereitstellungsplanung von Direct Routing ist der Schlüssel für eine erfolgreiche Implementierung. In diesem Artikel werden die Infrastruktur- und Lizenzierungsanforderungen sowie Informationen zur SBC-Konnektivität beschrieben: 

- [Infrastrukturanforderungen](#infrastructure-requirements)
- [Lizenzierung und andere Anforderungen](#licensing-and-other-requirements)
- [SBC-Domänennamen](#sbc-domain-names)
- [Öffentliches vertrauenswürdiges Zertifikat für den SBC](#public-trusted-certificate-for-the-sbc)
- [SIP-Signalisierung: FQDNs](#sip-signaling-fqdns)
- [SIP-Signalisierung: Ports](#sip-signaling-ports)
- [Mediendatenverkehr: Portbereiche](#media-traffic-port-ranges)
- [Unterstützte Session Border Controller (SBCs)](#supported-session-border-controllers-sbcs)

Ausführliche Informationen zum Konfigurieren von Direct Routing finden Sie unter [Direct Routing konfigurieren](direct-routing-configure.md).

## <a name="infrastructure-requirements"></a>Infrastrukturanforderungen
In der folgenden Tabelle sind die Infrastrukturanforderungen für die unterstützten SBCs, Domänen und weitere Anforderungen an die Netzwerkkonnektivität zur Bereitstellung von Direct Routing aufgelistet:  

|**Infrastrukturanforderung**|**Sie benötigen Folgendes**|
|:--- |:--- |
|Session Border Controller (SBC)|Einen unterstützten SBC. Weitere Informationen finden Sie unter [Unterstützte SBCs](#supported-session-border-controllers-sbcs).|
|Mit dem SBC verbundene Telefonie-Trunks|Ein oder mehrere mit dem SBC verbundene(r) Telefonie-Trunk(s). An einem Ende stellt der SBC über das Direct Routing eine Verbindung mit dem Microsoft-Telefonsystem her. Der SBC kann auch eine Verbindung mit Telefonie-Entitäten von Drittanbietern herstellen wie PBXs, analogen Telefonadaptern usw. Jede PSTN-Verbindungsoption, die mit dem SBC verbunden ist, funktioniert. (Hinweis: Wenn Sie die PSTN-Trunks für SBC konfigurieren möchten, wenden Sie sich an die SBC- oder Trunk-Anbieter.)|
|Office 365-Mandant|Einen Office 365-Mandanten, den Sie für die private Nutzung Ihrer Microsoft Teams-Benutzer sowie die Konfiguration für und Verbindung mit dem SBC verwenden.|
|Benutzer-Registrierungsstelle|Die Benutzer müssen in Office 365 verwaltet werden.<br/>Wenn Ihr Unternehmen über eine lokale Skype for Business- oder Lync-Umgebung mit Hybridkonnektivität zu Office 365 verfügt, können Sie VoIP in Teams für einen lokal gehosteten Benutzer nicht aktivieren.<br/><br/>Wenn Sie die Registrierungsstelle eines Benutzers überprüfen möchten, verwenden Sie das folgende Skype for Business Online PowerShell-Cmdlet:<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>Die Ausgabe des Cmdlets sollte Folgendes anzeigen:<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|Domänen|Eine oder mehrere Domäne(n) wurde(n) Ihrem Office 365-Mandanten hinzugefügt.<br/><br/>**Hinweis:** Sie können die Standarddomäne *.onmicrosoft.com, die für Ihren Mandanten automatisch erstellt wird, nicht verwenden.<br/><br/>Um die Domänen anzuzeigen, verwenden Sie das folgende Skype for Business Online PowerShell-Cmdlet:<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>Weitere Informationen zu Domänen und Office 365-Mandanten finden Sie unter [Häufig gestellte Fragen zu Domänen](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).|
|Öffentliche IP-Adresse für den SBC|Eine öffentliche IP-Adresse, die zum Herstellen einer Verbindung mit dem SBC verwendet werden kann. Basierend auf dem Typ des SBC kann der SBC NAT verwenden.|
|Vollqualifizierter Domänenname (Fully Qualified Domain Name, FQDN) für den SBC:|Ein FQDN für den SBC, bei dem der Domänenanteil des FQDN eine der registrierten Domänen in Ihrem Office 365-Mandanten ist. Weitere Informationen finden Sie unter [SBC-Domänennamen](#sbc-domain-names).|
|Öffentlicher DNS-Eintrag für den SBC |Ein öffentlicher DNS-Eintrag, der den SBC-FQDN der öffentlichen IP-Adresse zuordnet. |
|Öffentliches vertrauenswürdiges Zertifikat für den SBC |Ein Zertifikat für den SBC, der für die gesamte Kommunikation mit Direct Routing verwendet werden soll. Weitere Informationen finden Sie unter [Öffentliches vertrauenswürdiges Zertifikat für den SBC](#public-trusted-certificate-for-the-sbc).|
|Verbindungspunkte für Direct Routing |Die Verbindungspunkte für Direct Routing sind die folgenden drei FQDNs:<br/><br/>`sip.pstnhub.microsoft.com` – Globaler FQDN, muss zuerst ausprobiert werden.<br/>`sip2.pstnhub.microsoft.com` – Sekundärer FQDN, der geographisch dem zweiten Prioritätsbereich zugeordnet ist.<br/>`sip3.pstnhub.microsoft.com` – Tertiärer FQDN, der geographisch dem dritten Prioritätsbereich zugeordnet ist.<br/><br/>Informationen zu den Konfigurationsanforderungen finden Sie unter [SIP-Signalisierung: FQDNs](#sip-signaling-fqdns).|
|Firewall-IP-Adressen und Ports für Direct Routing-Medien |Der SBC kommuniziert mit den folgenden Diensten in der Cloud:<br/><br/>SIP-Proxy, der die Signalverarbeitung übernimmt<br/>Medienprozessor, der Medien verarbeitet – außer, wenn die Medienumgehung aktiviert ist<br/><br/>Diese beiden Dienste weisen unterschiedliche IP-Adressen in der Microsoft Cloud auf, die weiter unten in diesem Dokument beschrieben werden.<br/><br/>Weitere Informationen finden Sie in dem [Microsoft Teams-Abschnitt](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) in [Office 365-URLs und -IP-Adressbereiche](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). |
|Medientransportprofil|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Firewall-IP-Adressen und Ports für Microsoft Teams-Medien |Weitere Informationen finden Sie unter [Office 365-URLs und -IP-Adressbereiche](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). |
|||

## <a name="licensing-and-other-requirements"></a>Lizenzierung und weitere Anforderungen 

Benutzer des Direct Routings müssen in Office 365 die folgenden Lizenzen zugewiesen haben: 

- Microsoft-Telefonsystem 
- Microsoft Teams + Skype for Business Plan 2, wenn in der Lizenzierungs-SKU enthalten
- Microsoft-Audiokonferenz 

> [!NOTE]
> Der Skype for Business-Plan sollte nicht aus einer Lizenzierungs-SKU entfernt werden, in der er enthalten ist. 


> [!IMPORTANT]
>  Wenn Sie externe Teilnehmer zu geplanten Besprechungen hinzufügen möchten, indem Sie diese entweder anwählen oder die Einwahlnummer zur Verfügung stellen, ist die Audiokonferenz-Lizenz *erforderlich*.

> [!NOTE]
> Die Audiokonferenz-Lizenz ist für folgende Aktionen *erforderlich*:
> - Einen 1:1-Anruf auf einen Gruppenanruf eskalieren.
> - Externe Teilnehmer zu geplanten Besprechungen hinzufügen, indem Sie diese entweder anwählen oder die Einwahlnummer angeben. 


Darüber hinaus müssen Sie Folgendes sicherstellen:
 
- CsOnlineVoiceRoutingPolicy ist dem Benutzer zugewiesen. 
- „Private Anrufe zulassen“ ist auf der Mandantenebene für Microsoft Teams aktiviert. 

Direct Routing unterstützt auch Benutzer, die über die Lizenz für den Microsoft-Anrufplan verfügen. Microsoft-Telefonsystem mit Anrufplan kann einige Anrufe mithilfe der Direct Routing-Benutzeroberfläche weiterleiten. Die Telefonnummern der Benutzer müssen jedoch entweder online erworben oder an Microsoft portiert werden.  

Das Kombinieren von Anrufplan und Direct Routing-Konnektivität für den gleichen Benutzer ist optional, kann aber nützlich sein, wenn dem Benutzer beispielsweise ein Microsoft-Anrufplan zugewiesen ist, er aber einige Anrufe über SBC weiterleiten möchte. Zu den am häufigsten vorkommenden Szenarien zählen Anrufe an PBX-Anlagen von Drittanbietern.  Bei PBX-Anlagen von Drittanbietern werden alle Anrufe, mit Ausnahme von Anrufen an die mit diesen PBX-Anlagen verbundenen Telefone, über Microsoft-Anrufplan weitergeleitet. Aber Anrufe an die mit PBX-Anlagen von Drittanbietern verbundene Telefone werden an den SBC weitergeleitet und verbleiben deshalb im Unternehmensnetzwerk und gehen nicht am das PSTN. 

Weitere Informationen zur Telefonsystem-Lizenzierung finden Sie unter [Optimale Nutzung von Office mit Office 365](https://products.office.com/compare-all-microsoft-office-products?tab=2) und [Office 365-Planoptionen](https://technet.microsoft.com/library/office-365-plan-options.aspx). 

Weitere Informationen zur Telefonsystem-Lizenzierung finden Sie unter [Microsoft Teams-Add-On-Lizensierung](teams-add-on-licensing/microsoft-teams-add-on-licensing.md). 

## <a name="sbc-domain-names"></a>SBC-Domänennamen

Der SBC-Domänenname muss aus einem der Namen stammen, die in „Domänen“ des Mandanten registriert sind. Sie können den *.onmicrosoft.com-Mandanten nicht für den FQDN-Namen des SBC verwenden.

Die folgende Tabelle zeigt Beispiele für DNS-Namen, die für den Mandanten registriert sind, ob der Name als FQDN für den SBC verwendet werden kann sowie Beispiele für gültige FQDN-Namen:

|**DNS-Name**|**Kann für SBC-FQDN verwendet werden**|**Beispiele für FQDN-Namen**|
|:--- |:--- |:--- |
contoso.com|Ja|**Gültige Namen:**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|Nein|<br/>Die Verwendung von *.onmicrosoft.com-Domänen wird für SBC-Namen nicht unterstützt

Angenommen, Sie möchten einen neuen Domänennamen verwenden. So hat beispielsweise Ihr Mandant contoso.com als Domänenname in Ihrem Mandanten registriert, und Sie möchten sbc1.SIP.contoso.com verwenden. Bevor Sie einen SBC mit dem Namen sbc1.SIP.contoso.com koppeln können, müssen Sie den Domänennamen sip.contoso.com in „Domänen“ Ihres Mandanten registrieren. Wenn Sie versuchen, einen SBC mit sbc1.SIP.contoso.com zu koppeln, bevor Sie den Domänennamen registrieren, erhalten Sie folgende Fehlermeldung: „Die Domäne ‚sbc1.sip.contoso.com‘ kann nicht verwendet werden, da Sie für diesen Mandanten nicht konfiguriert wurde.“
Nachdem Sie den Domänennamen hinzugefügt haben, müssen Sie auch einen Benutzer mit UPN-Benutzer@sip.contoso.com erstellen und eine „Teams“-Lizenz zuweisen. Nachdem der Domänenname in „Domänen“ des Mandanten registriert wurde, kann es bis zu 24 Stunden dauern, bis der Domänenname vollständig bereitgestellt, ein Benutzer mit einem neuen Namen erstellt und dem Benutzer eine Lizenz zugewiesen wurde. 

Es kann vorkommen, dass ein Unternehmen mehrere SIP-Adressräume in einem Mandanten hat. So kann beispielsweise ein Unternehmen über contoso.com als SIP-Adressraum und über fabrikam.com als zweiten SIP-Adressraum verfügen. Einige Benutzer haben die Adresse Benutzer@contoso.com und einige Benutzer haben die Adresse Benutzer@fabrikam.com. 

Der SBC benötigt nur einen FQDN und kann Benutzer über alle Adressräume im gekoppelten Mandanten bedienen. So kann beispielsweise ein SBC mit dem Namen sbc1.contoso.com den PSTN-Datenverkehr für Benutzer mit den Adressen Benutzer@contoso.com und Benutzer@fabrikam.com empfangen und senden, sofern diese SIP-Adressräume im selben Mandanten registriert sind.  

## <a name="public-trusted-certificate-for-the-sbc"></a>Öffentliches vertrauenswürdiges Zertifikat für den SBC

Microsoft empfiehlt dringend, das Zertifikat für den SBC anzufordern, indem eine Zertifikatsignaturanforderung (Certification Signing Request, CSR) generiert wird. Spezifische Anweisungen zum Generieren einer CSR für einen SBC finden Sie unter den Anweisungen für die Zusammenschaltung oder in der Dokumentation, die von den SBC-Anbietern bereitgestellt wird. 

  > [!NOTE]
  > Die meisten Zertifizierungsstellen (Certificate Authorities, CAs) setzen voraus, dass die Größe des privaten Schlüssel mindestens 2048 beträgt. Bedenken Sie dies, wenn Sie die CSR generieren.

Das Zertifikat muss über den SBC-FQDN in den Feldern „Antragsteller“, „allgemeiner Name“ oder „alternativer Antragstellername“ verfügen.

Alternativ unterstützt Direct Routing auch einen Platzhalter in SAN, welcher dem standardmäßigen [RFC HTTP gegenüber TLS](https://tools.ietf.org/html/rfc2818#section-3.1) entsprechen muss.  Ein Beispiel dafür wäre die Verwendung von *.contoso.com im SAN, was dem SBC-FQDN sbc.contoso.com entsprechen, aber nicht mit sbc.test.contoso.com übereinstimmen würde.

Das Zertifikat muss von einer der folgenden Stammzertifizierungsstellen generiert werden:

- AffirmTrust
- AddTrust External CA Root
- Baltimore CyberTrust Root
- Buypass
- CyberTrust
- Class 3 Public Primary Certification Authority
- Comodo Secure Root CA
- Deutsche Telekom 
- Digicert Global Root CA
- Digicert High Assurance EV Root CA
- Entrust
- GlobalSign
- Go Daddy
- GeoTrust
- Verisign, Inc. 
- Starfield 
- Symantec Enterprise Mobile Root for Microsoft 
- SwissSign
- Thawte Timestamping CA
- Trustwave
- TeliaSonera 
- T-Systems International GmbH (Deutsche Telekom)
- QuoVadis

Microsoft arbeitet basierend auf Kundenanforderungen daran, zusätzliche Zertifizierungsstellen hinzuzufügen. 

## <a name="sip-signaling-fqdns"></a>SIP-Signalisierung: FQDNs 

Direct Routing wird in den folgenden Office 365-Umgebungen angeboten:
- Office 365
- Office 365 GCC 
- Office 365 GCC High
- Office 365 DoD

Erfahren Sie mehr über [Office 365 und US-Regierungsumfelder](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) wie GCC, GCC High und DoD.

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365- und Office 365-GCC-Umgebungen

Der Verbindungspunkt für Direct Routing sind die folgenden drei FQDNs:

- **sip.pstnhub.microsoft.com** – Globaler FQDN – muss zuerst ausprobiert werden. Wenn der SBC eine Anforderung sendet, diesen Namen aufzulösen, geben die Microsoft Azure DNS-Server eine IP-Adresse zurück, die auf das primäre Azure-Rechenzentrum verweist, das dem SBC zugewiesen ist. Die Zuordnung basiert auf den Leistungsmetriken des Rechenzentrums und der geographischen Nähe zum SBC. Die zurückgegebene IP-Adresse entspricht dem primären FQDN.
- **sip2.pstnhub.microsoft.com** – Sekundärer FQDN – geographisch dem zweiten Prioritätsbereich zugeordnet.
- **sip3.pstnhub.microsoft.com** – Tertiärer FQDN – geographisch dem dritten Prioritätsbereich zugeordnet.

Die Reihenfolge dieser drei FQDNs ist erforderlich für:

- Bereitstellen einer optimalen Benutzeroberfläche (weniger geladen und dem SBC-Rechenzentrum am nächsten, das durch Abfragen des ersten FQDN zugeordnet wurde).
- Bereitstellen eines Failovers, wenn die Verbindung von einem SBC zu einem Rechenzentrum eingerichtet wird, bei dem ein temporäres Problem auftritt. Weitere Informationen finden Sie unten unter [Failover-Mechanismen](#failover-mechanism-for-sip-signaling).  

Die FQDNs – sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com und sip3.pstnhub.microsoft.com – werden in eine der folgenden IP-Adressen aufgelöst:

- 52.114.148.0
- 52.114.132.46 
- 52.114.75.24 
- 52.114.76.76 
- 52.114.7.24 
- 52.114.14.70

Sie müssen Ports für alle diese IP-Adressen in Ihrer Firewall öffnen, um einen eingehenden und ausgehenden Datenverkehr an und von den Adressen für die Signalverarbeitung zuzulassen.  Wenn Ihre Firewall DNS-Namen unterstützt, löst der FQDN sip-all.pstnhub.microsoft.com alle diese IP-Adressen auf. 


### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD-Umgebung

Der Verbindungspunkt für Direct Routing ist folgender FQDN:

**sip.pstnhub.dod.teams.microsoft.us** – Globaler FQDN. Da die Office 365 DoD-Umgebung nur in den US-Rechenzentren vorhanden ist, gibt es keine sekundären und tertiären FQDNs.

Die FQDNs – sip.pstnhub.dod.teams.microsoft.us werden in eine der folgenden IP-Adressen aufgelöst:

- 52.127.64.33
- 52.127.68.34

Sie müssen Ports für alle diese IP-Adressen in Ihrer Firewall öffnen, um einen eingehenden und ausgehenden Datenverkehr an und von den Adressen für die Signalverarbeitung zuzulassen.  Wenn Ihre Firewall DNS-Namen unterstützt, wird der FQDN sip.pstnhub.dod.teams.microsoft.us in alle diese IP-Adressen aufgelöst. 

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High-Umgebung

Der Verbindungspunkt für Direct Routing ist folgender FQDN:

**sip.pstnhub.gov.teams.microsoft.us** – Globaler FQDN. Da die GCC High-Umgebung nur in den US-Rechenzentren vorhanden ist, gibt es keine sekundären und tertiären FQDNs.

Die FQDNs – sip.pstnhub.gov.teams.microsoft.us werden in eine der folgenden IP-Adressen aufgelöst:

- 52.127.88.59
- 52.127.92.64

Sie müssen Ports für alle diese IP-Adressen in Ihrer Firewall öffnen, um einen eingehenden und ausgehenden Datenverkehr an und von den Adressen für die Signalverarbeitung zuzulassen.  Wenn Ihre Firewall DNS-Namen unterstützt, wird der FQDN sip.pstnhub.gov.teams.microsoft.us in alle diese IP-Adressen aufgelöst. 

## <a name="sip-signaling-ports"></a>SIP-Signalisierung: Ports

Die Port-Anforderungen sind in allen Office 365-Umgebungen identisch, in denen Direct Routing angeboten wird:
- Office 365
- Office 365 GCC 
- Office 365 GCC High
- Office 365 DoD

Sie müssen die folgenden Ports verwenden:

|**Verkehr**|**Von**|**An**|**Quellport**|**Zielport**|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP-Proxy|SBC|1024 – 65535|Definiert im SBC|
SIP/TLS|SBC|SIP-Proxy|Definiert im SBC|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>Failover-Mechanismus für SIP-Signalisierung

Der SBC führt eine DNS-Abfrage aus, um sip.pstnhub.microsoft.com zu aufzulösen. Das primäre Rechenzentrum wird ausgehend von der SBC-Position und der Leistungsmetrik des Rechenzentrums ausgewählt. Wenn das primäre Rechenzentrum ein Problem aufweist, versucht der SBC, das sip2.pstnhub.microsoft.com zu öffnen, das zum zweiten zugewiesenen Rechenzentrum aufgelöst wird, und, im seltenen Fall, dass Rechenzentren in zwei Regionen nicht verfügbar sind, versucht der SBC den letzten FQDN (sip3.pstnhub.microsoft.com), der die IP des tertiären Rechenzentrums bereitstellt.

Die folgende Tabelle enthält eine Zusammenfassung der Beziehungen zwischen primären, sekundären und tertiären Rechenzentren:

|**Ist das primäre Rechenzentrum**|**EMEA**|**NOAM**|**ASIEN**|
|:--- |:--- |:--- |:--- |
|Das sekundäre Rechenzentrum (sip2.pstnhub.microsoft.com)|US|EU|US|
|Das tertiäre Rechenzentrum (sip3.pstnhub.microsoft.com)|ASIEN|ASIEN|EU|
|||||

## <a name="media-traffic-port-ranges"></a>Mediendatenverkehr: Portbereiche
Beachten Sie, dass die folgenden Anforderungen gelten, wenn Sie Direct Routing ohne Medienumgehung bereitstellen möchten. Informationen zu den Firewall-Voraussetzungen für die Medienumgehung finden Sie unter [Planen der Medienumgehung mit Direct Routing](https://docs.microsoft.com/de-DE/microsoftteams/direct-routing-plan-media-bypass).



Der Mediendatenverkehr fließt zu und von einem separaten Dienst in der Microsoft Cloud. Der IP-Bereich für den Mediendatenverkehr:

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365- und Office 365-GCC-Umgebungen

- 52.112.0.0 /14 (IP-Adressen von 52.112.0.1 bis 52.115.255.254).

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD-Umgebung

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High-Umgebung

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>Portbereich (gilt für alle Umgebungen)
Der Portbereich der Medienprozessoren wird in der folgenden Tabelle gezeigt: 

|**Verkehr**|**Von**|**An**|**Quellport**|**Zielport**|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|Medienprozessor|SBC|49 152 – 53 247|Definiert im SBC|
|UDP/SRTP|SBC|Medienprozessor|Definiert im SBC|49 152 – 53 247|
|

  > [!NOTE]
  > Microsoft empfiehlt mindestens zwei Ports pro gleichzeitigem Anruf im SBC.

## <a name="media-traffic-codecs"></a>Mediendatenverkehr: Codecs

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>Abschnitt zwischen SBC und Cloud-Medienprozessor oder Microsoft Teams-Client.
Gilt sowohl bei Medienumgehung als auch Nicht-Medienumgehung

Die Direct Routing-Schnittstelle auf dem Abschnitt zwischen dem Session Border Controller und dem Cloud-Medienprozessor (ohne Medienumgehung) oder zwischen dem Teams-Client und dem SBC (sofern die Medienumgehung aktiviert ist) kann die folgenden Codecs verwenden:
- Nicht-Medienumgehung (SBC an Cloud-Medienprozessor): SILK, G.711, G.722, G.729
- Medienumgehung (SBC an Teams-Client):  SILK, G.711, G.722, G.729, OPUS

Sie können die Verwendung des spezifischen Codecs auf dem Session Border Controller erzwingen, indem Sie unerwünschte Codecs aus dem Angebot ausschließen.

### <a name="leg-between-microsoft-teams-client--and-cloud-media-processor"></a>Abschnitt zwischen Microsoft Teams-Client und Cloud-Medienprozessor
Gilt nur im Fall von Nicht-Medienumgehung. Bei Medienumgehung fließen Medien direkt zwischen Teams-Client und SBC

Auf dem Abschnitt zwischen dem Cloud-Medienprozessor und dem Microsoft Teams-Clients wurden entweder SILK oder G.722 verwendet. Die Wahl des Codecs für diesen Abschnitt auf Basis von Microsoft-Algorithmen, bei denen mehrere Parameter berücksichtigt werden. 


## <a name="supported-session-border-controllers-sbcs"></a>Unterstützte Session Border Controller (SBCs)

Microsoft unterstützt nur zertifizierte SBCs zur Kopplung mit Direct Routing. Da Enterprise-VoIP für Unternehmen sehr wichtig ist, führt Microsoft intensive Tests mit den ausgewählten SBCs durch und arbeitet mit den SBC-Anbietern zusammen, um sicherzustellen, dass beide Systeme kompatibel sind. 

Geräte, die validiert wurden, werden als „Zertifiziert für Teams Direct Routing“ aufgelistet. Die zertifizierten Geräte funktionieren garantiert in allen Szenarien. 

Weitere Informationen zu unterstützten SBCs finden Sie in der [Liste von Session Border Controller zertifiziert für Direct Routing](direct-routing-border-controllers.md).

 
## <a name="see-also"></a>Siehe auch

[Direct Routing konfigurieren](direct-routing-configure.md)



