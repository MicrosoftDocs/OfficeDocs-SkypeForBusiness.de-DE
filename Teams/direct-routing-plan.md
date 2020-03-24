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
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Lesen Sie dieses Thema, um zu erfahren, wie Sie mit dem Microsoft Phone System Direct Routing einen unterstützten, vom Kunden bereitgestellten Session Border Controller (SBC) an Microsoft Phone System anschließen können.
ms.openlocfilehash: 5efed6ed21e6eb4bfa4e2ae89e625595b0307ada
ms.sourcegitcommit: 545e466f1fa9163bb00cc96c8db70a70b02af697
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "42928438"
---
# <a name="plan-direct-routing"></a>Planen von direktem Routing

> [!Tip]
> Schauen Sie sich die folgende Sitzung an, um mehr über die Vorteile des direkten Routings, die Vorgehensweise für die Planung und die Bereitstellung zu erfahren: [Direktes Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)

Mit dem direkt Routing von Microsoft Phone System können Sie einen unterstützten, vom Kunden bereitgestellten Session Border Controller (SBC) an Microsoft Phone System anschließen.  Mit dieser Funktion können Sie beispielsweise die lokale PSTN-Konnektivität (Public Switched Telephone Network) mit Microsoft Teams-Client konfigurieren, wie im folgenden Diagramm gezeigt: 

![Diagramm mit Konfiguration der lokalen PSTN-Konnektivität](media/PlanDirectRouting1-PSTNwithTeams.png "Konfiguration der lokalen PSTN-Konnektivität mit Microsoft Teams-Client")

  > [!NOTE]
  > Mit Skype for Business Online können Sie auch einen vom Kunden bereitgestellten SBC koppeln, dies erfordert aber eine lokale Skype for Business Server-Bereitstellung oder eine spezielle Edition von Skype for Business, genannt Cloud Connector, zwischen dem SBC und der Microsoft-Cloud. Dieses Szenario wird als Hybridsprache bezeichnet. Im Gegensatz dazu ermöglicht die direkte Weiterleitung eine direkte Verbindung zwischen dem unterstützten SBC und der Microsoft-Cloud. 

Mit der direkten Weiterleitung können Sie Ihren SBC mit fast jedem Telefon Stamm oder mit einem PSTN-Gerät von Drittanbietern verbinden. Direktes Routing ermöglicht Ihnen Folgendes: 

- Verwenden Sie praktisch jeden PSTN-trunk mit Microsoft Phone System. 
- Konfigurieren Sie die Interoperabilität zwischen kundeneigenen Telefonanlagen, wie etwa einer PBX-Anlage (Private Branch Exchange), analogen Geräten und einem Microsoft Phone-System.

Microsoft bietet auch Sprachlösungen für alle in der Cloud, wie Anrufplan. Eine Hybrid-VoIP-Lösung kann jedoch für Ihre Organisation am besten geeignet sein, wenn: 

- Microsoft-Anrufplan steht in Ihrem Land nicht zur Verfügung. 
- Für Ihre Organisation ist eine Verbindung mit analogen Geräten von Drittanbietern, Anruf Zentren usw. erforderlich. 
- Ihre Organisation verfügt über einen bestehenden Vertrag mit einem PSTN-Netzbetreiber.

Das direkte Routing unterstützt auch Benutzer, die über die zusätzliche Lizenz für den Microsoft-Anrufplan verfügen. Weitere Informationen finden Sie unter [Telefon System und Anrufpläne](calling-plan-landing-page.md). 

Bei der direkten Weiterleitung, wenn Benutzer an einer geplanten Konferenz teilnehmen, wird die Einwahlnummer vom Microsoft-Audiokonferenzdienst bereitgestellt, für den eine ordnungsgemäße Lizenzierung erforderlich ist.  Wenn Sie sich auswählen, platziert der Microsoft-Audiokonferenzdienst den Anruf über Online-Anruffunktionen, was eine ordnungsgemäße Lizenzierung erfordert. (Beachten Sie, dass das auswählen nicht durch direkte Weiterleitung weitergeleitet wird.) Weitere Informationen finden Sie unter [Online Besprechungen mit Teams](https://products.office.com/microsoft-teams/online-meeting-solutions). 
 
Die Planung der Bereitstellung des direkten Routings ist der Schlüssel zu einer erfolgreichen Implementierung. In diesem Artikel werden Infrastruktur-und Lizenzierungsanforderungen beschrieben und Informationen zur SBC-Konnektivität bereitgestellt: 

- [Infrastrukturanforderungen](#infrastructure-requirements)
- [Lizenzierung und andere Anforderungen](#licensing-and-other-requirements)
- [SBC-Domänennamen](#sbc-domain-names)
- [Öffentliches vertrauenswürdiges Zertifikat für den SBC](#public-trusted-certificate-for-the-sbc)
- [SIP-Signalisierung: FQDNs](#sip-signaling-fqdns)
- [SIP-Signalisierung: Anschlüsse](#sip-signaling-ports)
- [Medien Verkehr: Port Bereiche](#media-traffic-port-ranges)
- [Unterstützte Session Border Controllers (SBCS)](#supported-session-border-controllers-sbcs)

Detaillierte Informationen zum Konfigurieren des direkten Routings finden Sie unter [Konfigurieren des direkten Routings](direct-routing-configure.md).

## <a name="infrastructure-requirements"></a>Infrastrukturanforderungen
In der folgenden Tabelle sind die Infrastrukturanforderungen für die unterstützten SBCS, Domänen und anderen Netzwerkverbindungsanforderungen zum Bereitstellen des direkten Routings aufgeführt:  

|**Infrastruktur Anforderung**|**Sie benötigen Folgendes**|
|:--- |:--- |
|Session Border Controller (SBC)|Ein unterstützter SBC. Weitere Informationen finden Sie unter [unterstützte SBCS](#supported-session-border-controllers-sbcs).|
|Telefonie-Trunks, die mit dem SBC verbunden sind|Eine oder mehrere Telefon Stämme, die mit dem SBC verbunden sind. An einem Ende stellt der SBC eine Verbindung mit dem Microsoft Phone-System über direkte Weiterleitung her. Der SBC kann auch eine Verbindung mit externen Telefonie-Entitäten wie PBX-Anlagen, analogen Telefon Adaptern usw. herstellen. Alle mit dem SBC verbundenen Optionen für PSTN-Konnektivität funktionieren. (Für die Konfiguration der PSTN-Stämme zum SBC wenden Sie sich bitte an die SBC-Anbieter oder trunk-Anbieter.)|
|Office 365-Mandant|Ein Office 365-Mandant, mit dem Sie Ihre Microsoft Teams-Benutzer sowie die Konfiguration und die Verbindung mit dem SBC zu Hause verwenden können.|
|Benutzer Registrierungsstelle|Der Benutzer muss in Office 365 verwaltet werden.<br/>Wenn Ihr Unternehmen über eine lokale Skype for Business-oder lync-Umgebung mit Hybrid-Konnektivität mit Office 365 verfügt, können Sie die Sprachausgabe in Microsoft Teams für einen lokal gehosteten Benutzer nicht aktivieren.<br/><br/>Verwenden Sie das folgende Skype for Business Online PowerShell-Cmdlet, um die Registrierungsstelle eines Benutzers zu überprüfen:<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>Die Ausgabe des Cmdlets sollte Folgendes anzeigen:<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|Domänen|Eine oder mehrere Domänen, die Ihren Office 365-Mandanten hinzugefügt wurden.<br/><br/>Beachten Sie, dass Sie die Standarddomäne, \*onmicrosoft.com, nicht verwenden können, die automatisch für Ihren Mandanten erstellt wird.<br/><br/>Zum Anzeigen der Domänen können Sie das folgende Skype for Business Online PowerShell-Cmdlet verwenden:<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>Weitere Informationen zu Domänen und Office 365-Mandanten finden Sie unter [häufig gestellte Fragen zu Domains](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).|
|Öffentliche IP-Adresse für den SBC|Eine öffentliche IP-Adresse, die zum Herstellen einer Verbindung mit dem SBC verwendet werden kann. Basierend auf dem SBC-Typ kann der SBC NAT verwenden.|
|Vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den SBC|Ein FQDN für den SBC, wobei der Domänenanteil des FQDN eine der registrierten Domänen in Ihrem Office 365-Mandanten ist. Weitere Informationen finden Sie unter [SBC-Domänennamen](#sbc-domain-names).|
|Öffentlicher DNS-Eintrag für den SBC |Ein öffentlicher DNS-Eintrag, der den SBC-FQDN an die öffentliche IP-Adresse anordnet. |
|Öffentliches vertrauenswürdiges Zertifikat für den SBC |Ein Zertifikat für den SBC, der für die gesamte Kommunikation mit direktem Routing verwendet werden soll. Weitere Informationen finden Sie unter [öffentliches vertrauenswürdiges Zertifikat für den SBC](#public-trusted-certificate-for-the-sbc).|
|Verbindungspunkte für die direkte Weiterleitung |Die Verbindungspunkte für die direkte Weiterleitung sind die folgenden drei FQDNs:<br/><br/>`sip.pstnhub.microsoft.com`– Globaler FQDN, muss zuerst ausprobiert werden.<br/>`sip2.pstnhub.microsoft.com`– Sekundärer FQDN, der geografisch dem zweiten Prioritätsbereich zugeordnet ist.<br/>`sip3.pstnhub.microsoft.com`– Tertiärer FQDN, der geografisch dem dritten Prioritätsbereich zugeordnet ist.<br/><br/>Informationen zu den Konfigurationsanforderungen finden Sie unter [SIP-Signalisierungen: FQDNs](#sip-signaling-fqdns).|
|Firewall-IP-Adressen und Ports für Direct-Routing Medien |Der SBC kommuniziert mit den folgenden Diensten in der Cloud:<br/><br/>SIP-Proxy, der die Signalübertragung übernimmt<br/>Medienprozessor, der Medien verarbeitet, es sei denn, die medienumgehung ist aktiviert.<br/><br/>Diese beiden Dienste verfügen über separate IP-Adressen in der Microsoft-Cloud, die weiter unten in diesem Dokument beschrieben werden.<br/><br/>Weitere Informationen finden Sie im [Abschnitt Microsoft Teams](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) in [Office 365-URLs und IP-Adressbereiche](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). |
|Medien Transport Profil|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Firewall-IP-Adressen und Ports für Microsoft Teams-Medien |Weitere Informationen finden Sie unter [Office 365-URLs und IP-Adressbereiche](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). |
|||

## <a name="licensing-and-other-requirements"></a>Lizenzierung und andere Anforderungen 

Benutzern des direkten Routings muss in Office 365 die folgenden Lizenzen zugewiesen sein: 

- Microsoft Phone-System. 
- Microsoft Teams + Skype for Business Plan 2, wenn Sie in der Lizenzierung enthalten sind.
- Microsoft-Audiokonferenzen (Bitte lesen Sie die Hinweise und den Abschnitt unten, um konkrete Beispiele für die erforderliche Lizenz zu finden.)

> [!NOTE]
> Skype for Business-Plan sollte nicht von einem Lizenzvertrag entfernt werden, in dem er enthalten ist. 


> [!IMPORTANT]
>  Für den Fall, dass Sie externe Teilnehmer zu geplanten Besprechungen hinzufügen möchten, indem Sie sich entweder durch wählen oder die Einwahlnummer angeben, ist die Audiokonferenz-Lizenz erforderlich.


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>Ad-hoc-Anruf Eskalation und Audiokonferenz-Lizenz

Ein Teams-Benutzer kann eine Einzel Mannschaft mit dem PSTN-oder Teams-Team-Anruf beginnen und ihm einen PSTN-Teilnehmer hinzufügen. Dieses Szenario wird als Ad-hoc-Konferenz bezeichnet. Der Pfad, den der Anruf ausführt, hängt davon ab, ob der Benutzer, der den Anruf eskaliert, eine Microsoft-Audiokonferenz-Lizenz zugewiesen hat oder nicht:

- Wenn der Benutzer des Teams, der den Anruf eskaliert, eine Microsoft Audio Conferencing-Lizenz zugewiesen hat, erfolgt die Eskalation über den Microsoft-Audiokonferenzdienst. Der Remote-PSTN-Teilnehmer, der zum vorhandenen Anruf eingeladen wird, erhält eine Benachrichtigung über den eingehenden Anruf und sieht die Nummer der Microsoft Bridge, die dem Team Benutzer zugewiesen ist, der die Eskalation initiiert hat.
- Wenn der Benutzer des Teams, der den Anruf eskaliert, die Microsoft Audio Conferencing-Lizenz nicht zugewiesen hat, erfolgt die Eskalation über einen an die direkte Routing Schnittstelle angeschlossenen Sitzungs Grenz Controller. Der Remote-PSTN-Teilnehmer, der zum Anruf eingeladen wird, erhält eine Benachrichtigung über den eingehenden Anruf und sieht die Nummer des Teams-Benutzers, der die Eskalation initiiert hat. Der spezifische SBC, der für die Eskalation verwendet wird, wird durch die Routing Richtlinie des Benutzers definiert. 


Darüber hinaus müssen Sie Folgendes sicherstellen:
 
- CsOnlineVoiceRoutingPolicy wird dem Benutzer zugewiesen. 
- Private Anrufe zulassen ist auf Mandantenebene für Microsoft Teams aktiviert. 

Das direkte Routing unterstützt auch Benutzer, die für Microsoft-Anrufplan lizenziert sind. Microsoft Phone System with Calling Plan kann einige Anrufe über die direkte Routing Schnittstelle weiterleiten. Die Telefonnummern der Benutzer müssen jedoch entweder online erworben oder an Microsoft portiert werden.  

Das Mischen des Anruf Plans und der direkten Routing Konnektivität für denselben Benutzer ist optional, kann aber hilfreich sein (beispielsweise, wenn dem Benutzer ein Microsoft-Anrufplan zugewiesen wird, aber einige Anrufe über den SBC weitergeleitet werden sollen). Eines der häufigsten Szenarien sind Anrufe an PBX-Anlagen von Drittanbietern.  Bei PBX-Anlagen von Drittanbietern werden alle Anrufe, mit Ausnahme von Anrufen an die Telefone, die mit diesen PBX-Anlagen verbunden sind, mithilfe von Microsoft-Anrufplan weitergeleitet, aber Anrufe an Telefone, die mit Drittanbieter-PBX-Anlagen verbunden sind, gehen an den SBC und bleiben daher im Unternehmensnetzwerk und nicht im PSTN. 

Weitere Informationen zur Lizenzierung von Telefonsystemen finden Sie unter [Nutzen von Office mit Office 365](https://products.office.com/compare-all-microsoft-office-products?tab=2) und [Office 365-Plan Optionen](https://technet.microsoft.com/library/office-365-plan-options.aspx). 

Weitere Informationen zur Lizenzierung von Telefonsystemen finden Sie unter [Microsoft Teams-Add-on-Lizenzierung](teams-add-on-licensing/microsoft-teams-add-on-licensing.md). 

## <a name="supported-end-points"></a>Unterstützte Endpunkte 

Sie können als Endpunkt verwenden:

- Jeder Team-Client. 
- Telefone im öffentlichen Bereich. Weitere Informationen finden Sie unter [Einrichten der Telefon Lizenz für den öffentlichen Bereich für Microsoft Teams](https://docs.microsoft.com/microsoftteams/set-up-common-area-phones). Hinweis beim Einrichten eines öffentlichen Bereichs Telefons mit direktem Routing ist keine Anruf Plan Lizenz erforderlich.
- Skype for Business-3PIP-Telefone. Unter [Stützung für Skype for Business-Telefone (3PIP) mit Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)


## <a name="sbc-domain-names"></a>SBC-Domänennamen

Der SBC-Domänenname muss aus einem der Namen stammen, die in Domänen des Mandanten registriert sind. Sie können den \*onmicrosoft.com-Mandanten nicht für den FQDN-Namen des SBC verwenden.

Die folgende Tabelle enthält Beispiele für DNS-Namen, die für den Mandanten registriert sind, ob der Name als FQDN für den SBC verwendet werden kann, und Beispiele für gültige FQDN-Namen:

|**DNS-Name**|**Kann für SBC-FQDN verwendet werden**|**Beispiele für FQDN-Namen**|
|:--- |:--- |:--- |
contoso.com|Ja|**Gültige Namen:**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|Nein|Die Verwendung von *. onmicrosoft.com-Domänen wird für SBC-Namen nicht unterstützt.

Angenommen, Sie möchten einen neuen Domänennamen verwenden. Beispielsweise hat ihr Mandant contoso.com als Domänennamen, der in Ihrem Mandanten registriert ist, und Sie möchten sbc1.SIP.contoso.com verwenden. Bevor Sie einen SBC mit dem Namen sbc1.SIP.contoso.com koppeln können, müssen Sie den Domänennamen SIP.contoso.com in Domänen in Ihrem Mandanten registrieren. Wenn Sie versuchen, einen SBC mit sbc1.SIP.contoso.com zu koppeln, bevor Sie den Domänennamen registrieren, erhalten Sie die folgende Fehlermeldung: "die Domäne" sbc1.SIP.contoso.com "kann nicht verwendet werden, da Sie für diesen Mandanten nicht konfiguriert wurde."
Nachdem Sie den Domänennamen hinzugefügt haben, müssen Sie auch einen Benutzer mit UPN-User@SIP.contoso.com erstellen und eine Teams-Lizenz zuweisen. Es kann bis zu 24 Stunden dauern, bis der Domänenname vollständig bereitgestellt wird, nachdem er Domänen Ihres Mandanten hinzugefügt wurde, ein Benutzer mit einem neuen Namen erstellt und dem Benutzer eine Lizenz zugewiesen wurde. 

Es ist möglich, dass ein Unternehmen mehrere SIP-Adressräume in einem Mandanten hat. Beispielsweise kann ein Unternehmen Contoso.com als SIP-Adressraum und fabrikam.com als zweiten SIP-Adressraum haben. Einige Benutzer haben Adress user@contoso.com und einige Benutzer haben Adress User@Fabrikam.com. 

Der SBC benötigt nur einen FQDN und kann Benutzer aus jedem Adressraum des gekoppelten Mandanten bedienen. Beispielsweise kann ein SBC mit dem Namen sbc1.contoso.com den PSTN-Datenverkehr für Benutzer mit den Adressen user@contoso.com und User@Fabrikam.com empfangen und senden, solange diese SIP-Adressräume im gleichen Mandanten registriert sind.  

## <a name="public-trusted-certificate-for-the-sbc"></a>Öffentliches vertrauenswürdiges Zertifikat für den SBC

Microsoft empfiehlt, dass Sie das Zertifikat für den SBC anfordern, indem Sie eine Zertifizierungssignatur Anforderung (CSR) erstellen. Spezifische Anweisungen zum Generieren einer CSR für einen SBC finden Sie in den Verbindungsanweisungen oder der Dokumentation, die von ihren SBC-Anbietern bereitgestellt wird. 

  > [!NOTE]
  > Bei den meisten Zertifizierungsstellen muss die Größe des privaten Schlüssels mindestens 2048 sein. Beachten Sie dies beim Generieren der CSR.

Das Zertifikat muss den SBC-FQDN in den Feldern subject, Common Name oder Subject Alternative Name aufweisen.

Alternativ unterstützt Direct Routing einen Platzhalter in San, und der Platzhalter muss dem Standard [RFC http über TLS](https://tools.ietf.org/html/rfc2818#section-3.1)entsprechen. Ein Beispiel wäre die Verwendung \*von contoso.com im San, das mit dem SBC-FQDN-SBC.contoso.com übereinstimmen würde, aber nicht mit SBC.Test.contoso.com übereinstimmen würde.

Das Zertifikat muss von einer der folgenden Stammzertifizierungsstellen generiert werden:

- AffirmTrust
- Externes Zertifizierungsstellen-Stammverzeichnis
- Baltimore CyberTrust Root
- Buypass
- Cybertrust
- Öffentliche primäre Zertifizierungsstelle der Klasse 3
- Comodo Secure Root CA
- Deutsche Telekom 
- Globale Digicert-Stammzertifizierungsstelle
- Digicert-Stammzertifizierungsstelle für höchste Sicherheit
- Anvertrauen
- GlobalSign
- Go Daddy
- GeoTrust
- VeriSign, Inc. 
- Starfield 
- Symantec Enterprise Mobile-root für Microsoft 
- SwissSign
- Thawte-Timestamping-Zertifizierungsstelle
- Trustwave
- TeliaSonera 
- T-Systems International GmbH (Deutsche Telekom)
- QuoVadis

Microsoft arbeitet daran, zusätzliche Zertifizierungsstellen basierend auf Kundenanforderungen hinzuzufügen. 

## <a name="sip-signaling-fqdns"></a>SIP-Signalisierung: FQDNs 

Das direkte Routing wird in den folgenden Office 365-Umgebungen angeboten:
- Office 365
- Office 365 gcc
- Office 365 gcc-höchst
- Office 365 DoD

Erfahren Sie mehr über [Office 365 und US Government-Umgebungen](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) wie gcc, gcc-höchst-und DoD.

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365 und Office 365 gcc-Umgebungen

Der Verbindungspunkt für das direkte Routing sind die folgenden drei FQDNs:

- **SIP.pstnhub.Microsoft.com** – globaler FQDN – muss zuerst ausprobiert werden. Wenn der SBC eine Anforderung zum Beheben dieses Namens sendet, geben die Microsoft Azure-DNS-Server eine IP-Adresse zurück, die auf das primäre Azure Datacenter verweist, das dem SBC zugewiesen ist. Die Aufgabe basiert auf den Leistungs Metriken der Rechenzentren und der geographischen Nähe zum SBC. Die zurückgegebene IP-Adresse entspricht dem primären FQDN.
- **sip2.pstnhub.Microsoft.com** – sekundärer FQDN – wird geografisch dem zweiten Prioritätsbereich zugeordnet.
- **sip3.pstnhub.Microsoft.com** – tertiärer FQDN – ordnet geographisch dem dritten Prioritätsbereich zu.

Das Platzieren dieser drei FQDNs in der Reihenfolge ist für Folgendes erforderlich:

- Optimale Benutzerfreundlichkeit (geringere Belastung und Nähe zum SBC-Rechenzentrum, das durch Abfragen des ersten FQDN zugeordnet ist).
- Stellen Sie ein Failover bereit, wenn eine Verbindung von einem SBC zu einem Datacenter hergestellt wird, bei dem ein temporäres Problem auftritt. Weitere Informationen finden Sie unten unter [Failover-Mechanismus](#failover-mechanism-for-sip-signaling) .  

Die FQDNs – SIP.pstnhub.Microsoft.com, sip2.pstnhub.Microsoft.com und sip3.pstnhub.Microsoft.com – werden in eine der folgenden IP-Adressen aufgelöst:

- 52.114.148.0
- 52.114.132.46 
- 52.114.75.24 
- 52.114.76.76 
- 52.114.7.24 
- 52.114.14.70

Sie müssen Ports für alle diese IP-Adressen in Ihrer Firewall öffnen, um eingehenden und ausgehenden Datenverkehr zu und von den Adressen für das signalisieren zu ermöglichen.  Wenn Ihre Firewall DNS-Namen unterstützt, wird der FQDN-SIP-all.pstnhub.Microsoft.com in alle diese IP-Adressen aufgelöst. 


### <a name="office-365-gcc-dod-environment"></a>Office 365 gcc DoD-Umgebung

Der Verbindungspunkt für das direkte Routing ist der folgende FQDN:

**SIP.pstnhub.DoD.Teams.Microsoft.US** – globaler FQDN. Da die Office 365 DoD-Umgebung nur in den US-Rechenzentren vorhanden ist, gibt es keine sekundären und tertiären FQDNs.

Der FQDN-SIP.pstnhub.DoD.Teams.Microsoft.US wird in eine der folgenden IP-Adressen aufgelöst:

- 52.127.64.33
- 52.127.68.34

Sie müssen Ports für alle diese IP-Adressen in Ihrer Firewall öffnen, um eingehenden und ausgehenden Datenverkehr zu und von den Adressen für das signalisieren zu ermöglichen.  Wenn Ihre Firewall DNS-Namen unterstützt, wird der FQDN-SIP.pstnhub.DoD.Teams.Microsoft.US in alle diese IP-Adressen aufgelöst. 

### <a name="office-365-gcc-high-environment"></a>Office 365 gcc-höchst Umgebung

Der Verbindungspunkt für das direkte Routing ist der folgende FQDN:

**SIP.pstnhub.gov.Teams.Microsoft.US** – globaler FQDN. Da die gcc-höchst Umgebung nur in den US-Rechenzentren vorhanden ist, gibt es keine sekundären und tertiären FQDNs.

Der FQDN-SIP.pstnhub.gov.Teams.Microsoft.US wird in eine der folgenden IP-Adressen aufgelöst:

- 52.127.88.59
- 52.127.92.64

Sie müssen Ports für alle diese IP-Adressen in Ihrer Firewall öffnen, um eingehenden und ausgehenden Datenverkehr zu und von den Adressen für das signalisieren zu ermöglichen.  Wenn Ihre Firewall DNS-Namen unterstützt, wird der FQDN-SIP.pstnhub.gov.Teams.Microsoft.US in alle diese IP-Adressen aufgelöst. 

## <a name="sip-signaling-ports"></a>SIP-Signalisierung: Anschlüsse

Sie müssen die folgenden Ports für Office 365-Umgebungen verwenden, in denen ein direktes Routing angeboten wird:
- Office 365
- Office 365 gcc
- Office 365 gcc-höchst
- Office 365 DoD

|**Datenverkehr**|**Von**|**Bis**|**Quell-Port**|**Ziel-Port**|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP-Proxy|Sbchttps|1024 – 65535|Definiert auf dem SBC (für Office 365 gcc-höchst/DoD-Port 5061 muss verwendet werden)|
SIP/TLS|Sbchttps|SIP-Proxy|Im SBC definiert|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>Failover-Mechanismus für SIP-Signalisierungen

Der SBC führt eine DNS-Abfrage aus, um SIP.pstnhub.Microsoft.com zu lösen. Basierend auf dem SBC-Speicherort und den Datencenter-Leistungs Metriken wird das primäre Rechenzentrum ausgewählt. Wenn das primäre Rechenzentrum ein Problem auftritt, versucht der SBC die sip2.pstnhub.Microsoft.com, die in das zweite zugewiesene Rechenzentrum aufgelöst wird, und in dem seltenen Fall, dass Rechenzentren in zwei Regionen nicht verfügbar sind, versucht der SBC den letzten FQDN erneut ( sip3.pstnhub.Microsoft.com), das die IP des tertiären Rechenzentrums bereitstellt.

In der folgenden Tabelle sind die Beziehungen zwischen primären, sekundären und tertiären Rechenzentren zusammengefasst:

|**Wenn das primäre Rechenzentrum**|**EMEA**|**Noam**|**Asien**|
|:--- |:--- |:--- |:--- |
|Das sekundäre Rechenzentrum (sip2.pstnhub.Microsoft.com)|US|EU|US|
|Das tertiäre Rechenzentrum (sip3.pstnhub.Microsoft.com)|Asien|Asien|EU|
|||||

## <a name="media-traffic-port-ranges"></a>Medien Verkehr: Port Bereiche
Beachten Sie, dass die folgenden Anforderungen gelten, wenn Sie Direktes Routing ohne medienumgehung bereitstellen möchten. Informationen zu den Firewall-Anforderungen für die medienumgehung finden Sie unter [Planen der medienumgehung mit direktem Routing](https://docs.microsoft.com/microsoftteams/direct-routing-plan-media-bypass).



Der Mediendatenverkehr fließt in die und aus einem separaten Dienst in der Microsoft-Cloud. Der IP-Bereich für den Medien Verkehr lautet wie folgt:

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365 und Office 365 gcc-Umgebungen

- 52.112.0.0/14 (IP-Adressen von 52.112.0.1 nach 52.115.255.254).

### <a name="office-365-gcc-dod-environment"></a>Office 365 gcc DoD-Umgebung

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 gcc-höchst Umgebung

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>Port Bereich (gilt für alle Umgebungen)
Der Portbereich der Medien Prozessoren ist in der folgenden Tabelle dargestellt: 

|**Datenverkehr**|**Von**|**Bis**|**Quell-Port**|**Ziel-Port**|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|Medienprozessor|Sbchttps|49152 – 53247|Im SBC definiert|
|UDP/SRTP|Sbchttps|Medienprozessor|Im SBC definiert|49152 – 53247|

  > [!NOTE]
  > Microsoft empfiehlt mindestens zwei Ports pro gleichzeitigen Anruf im SBC.


## <a name="media-traffic-media-processors-geography"></a>Mediendatenverkehr: Geographie der Medien Prozessoren

Der Mediendatenverkehr fließt über Komponenten mit dem Namen Media processors. Medien Prozessoren werden in dieselben Rechenzentren wie SIP-Proxys gespeichert. Darüber hinaus gibt es zusätzliche Medien Prozessoren zur Optimierung des Medienflusses. So verfügen wir beispielsweise nicht über eine SIP-Proxykomponente in Australien (SIP-Flows über Singapur oder Hongkong), aber wir haben den medienprozessor lokal in Australien. Der Bedarf an lokalen Medien Prozessoren hängt von der Latenz ab, die wir durch das Senden von Fernverkehr, beispielsweise von Australien nach Singapur oder Hongkong, erfahren. Während Latenz im Beispiel des Datenverkehrs, der von Australien nach Hongkong oder Singapur fließt, akzeptabel ist, um eine gute Anrufqualität für den SIP-Datenverkehr zu gewährleisten, ist dies für echt Zeit Medien Verkehr nicht möglich.

Speicherort der Medien Prozessoren:

Speicherorte, an denen SIP-Proxy-und medienprozessor Komponenten bereitgestellt werden:
- USA (zwei in den US-amerikanischen West-und US East-Rechenzentren)
- Europa (Amsterdam-und Dublin-Rechenzentren)
- Asien (Rechenzentren in Singapur und Hongkong)

Speicherorte, an denen nur Medien Prozessoren bereitgestellt werden (SIP fließt über das nächstgelegene Rechenzentrum):
- Japan (JP Ost-und West-Rechenzentren)
- Australien (au-Ost-und West-Rechenzentren)




## <a name="media-traffic-codecs"></a>Mediendatenverkehr: Codecs

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>Bein zwischen SBC und Cloud Media Processor oder Microsoft Teams-Client.
Gilt für Case-und Non-Bypass-Fälle in der medienumgehung.

Die direkte Routing Schnittstelle auf dem Bein zwischen dem Session Border Controller und dem Cloud Media Processor (ohne medienumgehung) oder zwischen dem Teams-Client und dem SBC (sofern die medienumgehung aktiviert ist) kann die folgenden Codecs verwenden:

- Nicht medienumgehung (SBC to Cloud Media Processor): Seide, g. 711, g. 722, g. 729
- Medienumgehung (SBC to Teams Client): Seide, g. 711, g. 722, g. 729

Sie können die Verwendung des jeweiligen Codecs auf dem Session Border Controller erzwingen, indem Sie unerwünschte Codecs aus dem Angebot ausschließen.

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>Bein zwischen Microsoft Teams-Client und Cloud Media Processor
Gilt nur für nicht-Medien-Bypass-Fälle. Bei der medienumgehung fließt das Medium direkt zwischen dem Teams-Client und dem SBC.

Auf dem Bein zwischen dem Cloud Media Processor und dem Microsoft Teams-Client wird entweder Silk oder G. 722 verwendet. Die Codec-Auswahl für dieses Bein basiert auf Microsoft-Algorithmen, die mehrere Parameter berücksichtigen. 


## <a name="supported-session-border-controllers-sbcs"></a>Unterstützte Session Border Controllers (SBCS)

Microsoft unterstützt nur zertifizierte SBCS, um mit Direct Routing zu koppeln. Da Enterprise-VoIP für Unternehmen von entscheidender Bedeutung ist, führt Microsoft Intensivtests mit dem ausgewählten SBCS durch und arbeitet mit den SBC-Anbietern zusammen, um sicherzustellen, dass die beiden Systeme kompatibel sind. 

Geräte, die überprüft wurden, werden als Certified für Teams Direct Routing aufgeführt. Die zertifizierten Geräte funktionieren in allen Szenarien garantiert. 

Weitere Informationen zu unterstützten SBCS finden Sie unter [Liste der für die direkte Weiterleitung zertifizierten Session Border Controller](direct-routing-border-controllers.md).

 
## <a name="see-also"></a>Siehe auch

[Konfigurieren von direktem Routing](direct-routing-configure.md)
