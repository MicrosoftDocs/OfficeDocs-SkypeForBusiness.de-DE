---
title: Planen der direkten Routing
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: ''
description: Lesen Sie die Informationen in diesem Thema erfahren, wie Microsoft Phone System direkten Routing Microsoft Telefonsystem einer unterstützten, Kunden bereitgestellten Session Border Controller (SBC) herstellen können.
ms.openlocfilehash: 91d188f63a0645d0df81817dd98dbd3ef54418a9
ms.sourcegitcommit: c864a4b5337960deed01ff8c481326dbbd23c960
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2018
ms.locfileid: "24975202"
---
# <a name="plan-direct-routing"></a>Planen der direkten Routing

Microsoft Phone System direkten Routing können Sie einer unterstützten, Kunden bereitgestellten Session Border Controller (SBC) auf Microsoft Telefonsystem herstellen.  Mit dieser Funktion können beispielsweise Sie lokale PSTN-Konnektivität mit Microsoft-Teams-Client konfigurieren wie in der folgenden Abbildung dargestellt: 

![Zeigt die Konfiguration der PSTN-Anbindung: lokal mit Microsoft-Teams, client](media/PlanDirectRouting1-PSTNwithTeams.png)

  > [!NOTE]
  > Skype für Business Online können Sie Paar auch einen Kunden bereitgestellter SBC, aber dies erfordert eine lokale Skype für Business Server-Bereitstellung oder eine spezielle Version von Skype für Unternehmen, Cloud-Connector zwischen dem SBC und die Microsoft-Cloud aufgerufen. In diesem Szenario wird als Hybrid-VoIP bezeichnet. Im Gegensatz dazu können die direkten Routing eine direkte Verbindung zwischen den unterstützten SBC und die Microsoft-Cloud. 

Sie können mit direktem Routing Herstellen einer Verbindung nahezu alle Telefonie-Trunk mit Ihrer SBC oder interconnect mit Geräten von Drittanbietern (Public Switched Telephone Network, PSTN). Direktes Routing können Sie: 

- Verwenden Sie nahezu alle PSTN-Trunk mit Microsoft Telefonsystem. 
- Konfigurieren der Interoperabilität zwischen im Besitz des Kunden telephonieausrüstung, wie ein Drittanbieter-private Branch Exchange, (PBX), analoge Geräte und Microsoft Telefonsystem.

Microsoft bietet auch all-in-Cloud-VoIP-Lösungen, wie etwa aufrufen planen.  Jedoch möglicherweise eine Hybrid-VoIP-Lösung am besten für Ihre Organisation wenn: 

- Planen der Aufruf von Microsoft ist in Ihrem Land nicht verfügbar. 
- Ihre Organisation erfordert Verbindung zu analogen Geräten von Drittanbietern Callcentern und So weiter. 
- Ihre Organisation hat einen vorhandenen Vertrag mit einem PSTN-Betreibers.

Direktes Routing unterstützt auch Benutzer, die zusätzliche Lizenz für die Microsoft aufrufen planen müssen. Weitere Informationen finden Sie unter [Aufrufen in Office 365-Pläne](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365) und [Lizenzierung sowie zu weiteren Anforderungen](#licensing-and-other-requirements). 

Mit direktem Routing Wenn Benutzer an einer geplanten Konferenz teilnehmen wird die Einwahlnummer vom Microsoft-Audiokonferenzen-Dienst bereitgestellt die entsprechenden Lizenzen erforderlich sind.  Beim wählen, platziert der Dienst Microsoft Audiokonferenzen den Anruf mithilfe der aufrufende Onlinefunktionen, der entsprechenden Lizenzen erforderlich sind. (Beachten Sie, dass die Telefonverbindung über direkte Weiterleitung nicht weitergeleitet wird.) Weitere Informationen finden Sie unter [Besprechungen mit Teams](https://products.office.com/microsoft-teams/online-meeting-solutions). 
 
Planung der Bereitstellung von direkten Routing ist Schlüssel für eine erfolgreiche Implementierung. In diesem Artikel wird beschrieben, Infrastruktur und lizenzanforderungen und Informationen zu SBC-Konnektivität: 

- [Infrastrukturanforderungen](#infrastructure-requirements)
- [Lizenzierung und sonstige Anforderungen](#licensing-and-other-requirements)
- [SBC-Domänennamen](#sbc-domain-names)
- [Öffentliche vertrauenswürdiges Zertifikat für den SBC](#public-trusted-certificate-for-the-sbc)
- [SIP-Signalisierung: FQDNs und Firewallports](#sip-signaling-fqdns-and-firewall-ports)
- [Mediendatenverkehr: port Bereiche](#media-traffic-port-ranges)
- [Unterstützte SBCs](#supported-session-border-controllers-sbcs)

Ausführliche Informationen zum Konfigurieren von direkten Routing finden Sie unter [Konfigurieren von direkten Routing](direct-routing-configure.md).

## <a name="infrastructure-requirements"></a>Infrastrukturanforderungen
Anforderungen an die Infrastruktur für die unterstützten SBCs, Domänen und andere netzwerkanforderungen Konnektivität zum Bereitstellen von direkten Routing werden in der folgenden Tabelle aufgeführt:  

|**Infrastruktur-Anforderung**|**Sie benötigen Folgendes**|
|:--- |:--- |
|Session Border Controller (SBC)|Eine unterstützte SBC. Weitere Informationen finden Sie unter [SBCs unterstützt](#supported-session-border-controllers-sbcs).|
|Verbunden mit dem SBC Telefonie-trunks|Einen oder mehrere Telefonie-Trunks mit den SBC verbunden ist. An einem Ende verbindet der SBC mit der Microsoft-Telefonsystem über direkte Routing. Der SBC kann auch Verbinden mit Drittanbieter-Telefonie-Entitäten wie Nebenstellenanlagen, Analog Telefonie Adapter, und so weiter. Jeder PSTN-Konnektivitätsoption verbunden mit dem SBC funktioniert. (Hinweis: die PSTN-Trunks mit SBC konfiguriert ist, finden Sie in den SBC Lieferanten oder Trunk-Anbieter.)|
|Office 365-Mandanten|Ein Office 365-Mandanten, mit denen Sie Ihre Benutzer Microsoft-Teams, und die Konfiguration und Verbindung mit den SBC (privat).|
|Benutzer-Registrierung|Benutzer muss in Office 365, verwaltet werden.<br/>Sie können VoIP in Teams für einen Benutzer nicht aktivieren, wenn Ihr Unternehmen über eine lokale Skype für Business oder Lync-Umgebung mit hybridkonnektivität zu Office 365 verfügt, lokalen verwaltet.<br/><br/>Um die Registrierung eines Benutzers zu überprüfen, verwenden Sie die folgenden Skype für Business Online-PowerShell-Cmdlet aus:<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>Die Ausgabe des Cmdlets sollte angezeigt werden:<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|Domänen|Eine oder mehrere Domänen in Ihrer Office 365-Mandanten.<br/><br/>**Hinweis:** Die Standarddomäne kann nicht verwendet werden *. "onmicrosoft.com" dargestellt, die für Ihre Mandanten automatisch erstellt wird.<br/><br/>Um die Domänen anzuzeigen, können Sie die folgenden Skype für Business Online-PowerShell-Cmdlets verwenden:<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>Weitere Informationen zu Domänen und Office 365-Mandanten finden Sie unter [Häufig gestellte Fragen zu Domänen](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).|
|Öffentliche IP-Adresse für den SBC|Eine öffentliche IP-Adresse, die Verbindung mit dem SBC verwendet werden können. Basierend auf den Typ des SBC, kann der SBC NAT verwenden.|
|Vollqualifizierter Domänenname (FQDN) für den SBC|Der FQDN für den SBC, wobei der Domänenteil der den FQDN eines registrierten Domänen in Office 365-Mandanten ist. Weitere Informationen finden Sie unter [SBC-Domänennamen](#sbc-domain-names).|
|Öffentlichen DNS-Eintrag für den SBC |Einen öffentlichen DNS-Eintrag der öffentlichen IP-Adresse den FQDN SBC zuordnen. |
|Öffentliche vertrauenswürdiges Zertifikat für den SBC |Ein Zertifikat für die SBC für die gesamte Kommunikation mit direktem Routing verwendet werden soll. Weitere Informationen finden Sie unter [Öffentliche vertrauenswürdiges Zertifikat für den SBC](#public-trusted-certificate-for-the-sbc).|
|Verbindungspunkte zum direkten weiterleiten |Die Verbindungspunkte für direkte Routing sind die folgenden drei FQDNs:<br/><br/>`sip.pstnhub.microsoft.com`– Globale FQDN muss zuerst getestet werden.<br/>`sip2.pstnhub.microsoft.com`– Sekundären FQDN, ordnet geografisch die zweite Region Priorität.<br/>`sip3.pstnhub.microsoft.com`– Tertiäre FQDN, ordnet geografisch die dritte Priorität Region.<br/><br/>Informationen zu konfigurationsanforderungen, finden Sie unter [SIP-Signale: FQDNs und Firewallports](#sip-signaling-fqdns-and-firewall-ports).|
|Firewall-IP-Adressen und Ports für die direkte Routing |Der SBC kommuniziert, um die folgenden Dienste in der Cloud:<br/><br/>SIP-Proxy, der die Signale behandelt<br/>Media-Prozessor, der Medien verarbeitet-es sei denn, die Medienumgehung auf<br/><br/>Diese beiden Dienste über separate IP-Adressen in Microsoft Cloud, weiter unten in diesem Dokument beschriebenen verfügen.<br/><br/>Weitere Informationen finden Sie im [Abschnitt Microsoft-Teams](https://docs.microsoft.com/en-us/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) in [Office 365-URLs und IP-Adressbereiche](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). |
|Media Transport-Profil|TCP/RTP/SAVP <br/>RTP/UDP/SAVP|
Firewall-IP-Adressen und Ports für die Microsoft-Teams |Weitere Informationen finden Sie unter [Office 365-URLs und IP-Adressbereiche](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). |
|||

## <a name="licensing-and-other-requirements"></a>Lizenzierung und sonstige Anforderungen 

Benutzer von direkten Routing müssen die folgenden Lizenzen im Office 365 zugewiesen: 

- Microsoft Telefonsystem 
- Microsoft Teams 
- Microsoft-Audiokonferenzen 

Die Lizenz Audiokonferenzen ist erforderlich für das Hinzufügen von externer Teilnehmern auf geplante Besprechungen von Ihnen Telefonverbindung oder durch die Einwahlnummer bereitstellen. 
 
  > [!NOTE]
  > Die E5 Lizenz enthält Telefonsystem und Audiokonferenzen.   

Darüber hinaus müssen Sie Folgendes sicherstellen:
 
- CsOnlineVoiceRoutingPolicy wird dem Benutzer zugewiesen. 
- Zulassen Sie, dass Private Aufrufen für Microsoft-Teams, auf der Ebene der Mandanten aktiviert ist. 

Direktes Routing unterstützt auch Benutzer, die für Microsoft aufrufen planen lizenziert sind. Microsoft Telefonsystem mit Aufrufen planen können einige Anrufe über die Benutzeroberfläche direkten Routing weiterleiten. Jedoch müssen Rufnummern der Benutzer entweder online oder werden an Microsoft übertragen.  

Mischen von Aufrufen planen und direkte Routing-Konnektivität für den gleichen Benutzer kann ist optional, jedoch sinnvoll sein, beispielsweise, wenn der Benutzer Microsoft aufrufen planen zugeordnet ist, jedoch einige Anrufe über den SBC weiterleiten möchte. Eines der gängigsten Szenarien sind Aufrufe von Drittanbieter-PBX-Anlagen.  Mit Drittanbietern Nebenstellenanlagen werden alle Anrufe, mit Ausnahme von Anrufen an die Telefone mit diesem Nebenstellenanlagen verbunden über Microsoft aufrufen planen weitergeleitet; jedoch Anrufe an die Telefone mit Drittanbieter-PBX-Anlagen verbunden an den SBC daher bleiben innerhalb des Unternehmensnetzwerks und nicht an das Telefonfestnetz. 

Weitere Informationen zur Lizenzierung Telefonsystem finden Sie unter [Optimieren Sie die Nutzung von Office mit Office 365](https://products.office.com/compare-all-microsoft-office-products?tab=2) und [Planen von Office 365-Produkten](https://technet.microsoft.com/library/office-365-plan-options.aspx). 

Weitere Informationen zur Lizenzierung Telefonsystem finden Sie unter [Skype für Geschäfts- und Microsoft-Teams, Add-On-Lizenzierung](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing). 

## <a name="sbc-domain-names"></a>SBC-Domänennamen

Der Domänenname SBC muss von einem der in "Domänen" des Mandanten registrierten Namen. Sie können keine der *. onmicrosoft.com Mandanten für den Vollqualifizierten Domänennamen der SBC.

Die folgende Tabelle enthält Beispiele für DNS-Namen für den Mandanten registriert sind, ob der Name als FQDN für den SBC verwendet werden kann, und Beispiele gültiger FQDN-Namen:

|**DNS-name**|**Kann für SBC-FQDN verwendet werden**|**Beispiele für die FQDN-Namen**|
|:--- |:--- |:--- |
"contoso.com"|Ja|**Gültige Namen:**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>"Europe.contoso.com"|
|Contoso.onmicrosoft.com|Nein|<br/>Mit *. onmicrosoft.com Domänen wird nicht unterstützt, für die Namen von SBC

Wird davon ausgegangen Sie, dass Sie einen neuen Domänennamen verwenden möchten. Ihres Mandanten hat beispielsweise "contoso.com" als ein Domänennamen in Ihrem Mandanten registriert, und Sie sbc1.sip.contoso.com verwenden möchten. Bevor Sie einen SBC mit dem Namen sbc1.sip.contoso.com Kopplung können, müssen Sie die Domäne Name sip.contoso.com in "Domänen" in Ihrem Mandanten registrieren. Wenn Sie versuchen, eine Kopplung einen SBC mit sbc1.sip.contoso.com vor den Domänennamen registrieren, erhalten Sie die folgende Fehlermeldung: "Können die Domäne"sbc1.sip.contoso.com"wie verwenden sie nicht für diesen Mandanten konfiguriert wurde."
Nachdem Sie den Domänennamen hinzugefügt haben, müssen Sie auch zum Erstellen eines Benutzers mit UPN user@sip.contoso.com und weisen Sie eine Lizenz "Teams". Es kann bis zu 24 Stunden dauern, vollständig bereitstellen, die der Domänennamen nach dem "Domänen" Ihres Mandanten ein Benutzer mit einem neuen Namen erstellt, und der Benutzer eine Lizenz zugewiesen wurde hinzugefügt wird. 

Es ist möglich, dass ein Unternehmen möglicherweise mehrere SIP-Adresse Leerzeichen in einem Mandanten muss. Beispielsweise ein Unternehmen als einen SIP-Adressraum contoso.com und fabrikam.com als zweite SIP-Adressraum möglicherweise. Einige Benutzer haben Adresse user@contoso.com und einige Benutzer haben die Adresse user@fabrikam.com. 

Der SBC nur benötigt einen FQDN und kann Benutzer alle Adressraum im gekoppelten Mandanten service. Beispielsweise kann den PSTN-Datenverkehr für Benutzer mit Adressen user@contoso.com und user@fabrikam.com, solange diese SIP-Adresse Leerzeichen in derselben mandantenorganisation registriert sind ein SBC mit dem Namen sbc1.contoso.com empfangen und senden.  

## <a name="public-trusted-certificate-for-the-sbc"></a>Öffentliche vertrauenswürdiges Zertifikat für den SBC

Microsoft empfiehlt, dass Sie das Zertifikat für die SBC anzufordern, generiert eine Zertifizierung signieranforderung (CSR). Ausführliche Informationen zum Generieren einer Zertifikatsignieranforderung für einen SBC finden Sie in der Gasverbund Anweisungen oder Dokumentation, die von den Herstellern Ihrer SBC bereitgestellt. 

  > [!NOTE]
  > Die meisten Zertifizierungsstellen (CAs) erfordern die Größe des private Schlüssels mindestens 2048 sein. Beachten Sie dies, wenn die CSR generiert.

Das Zertifikat muss die SBC-FQDN im Betreff, allgemeiner Name oder Subject alternative Name-Felder aufweisen.

Alternativ direkten Routing unterstützt einen Platzhalter in der allgemeine Name oder SAN und der Platzhalter standard [RFC HTTP über TLS](https://tools.ietf.org/html/rfc2818#section-3.1)entsprechen muss. Ein Beispiel wäre die Verwendung *. contoso.com im SAN, die die SBC FQDN sbc.contoso.com würde sich eine Übereinstimmung, jedoch nicht mit sbc.test.contoso.com überein.

Das Zertifikat muss von einem der folgenden Stammzertifizierungsstellen generiert werden:

- AffirmTrust
- AddTrust externe Zertifizierungsstelle Stamm
- Baltimore CyberTrust Root
- Buypass
- Cybertrust
- Öffentliche primären Zertifizierungsstelle Klasse 3
- Comodo Secure Stammzertifizierungsstelle
- Deutsche Telekom 
- Globale Stammzertifizierungsstelle DigiCert 
- Entrust
- Informationen
- Wechseln Sie Daddy
- GeoTrust
- VeriSign, Inc. 
- Starfield 
- Symantec Enterprise Mobile Stamm für Microsoft 
- SwissSign
- Thawte Zeitstempel Zertifizierungsstelle
- Trustwave
- TeliaSonera 
- T-Systems International GmbH (Deutsche Telekom)
- QuoVadis

Microsoft ist funktionsfähig, zum Hinzufügen von zusätzlichen Zertifizierungsstellen basierend auf Kundenanfragen. 

## <a name="sip-signaling-fqdns-and-firewall-ports"></a>SIP-Signalisierung: FQDNs und Firewallports 

Der Verbindungspunkt für das direkte Routing sind die folgenden drei FQDNs:

- **sip.pstnhub.microsoft.com** – globale FQDN – müssen zuerst versucht werden. Wenn der SBC eine Anforderung an diesen Namen auflösen sendet, zurückgeben die Microsoft Azure DNS-Server eine IP-Adresse, die im primären Datencenter Azure zeigen die SBC zugewiesen. Die Zuordnung basiert auf Leistungsmetriken der Rechenzentren und geografische in der Nähe der SBC. Die zurückgegebene IP-Adresse entspricht des primären FQDN.
- **sip2.pstnhub.microsoft.com** – sekundären FQDN – ordnet geografisch zweiten Bereich Priorität.
- **sip3.pstnhub.microsoft.com** – tertiäre FQDN – ordnet geografisch die dritte Priorität Region.

Ordnen diese drei FQDNs in der Reihenfolge ist erforderlich:

- Geben Sie optimale Erfahrungen (weniger geladen und dem SBC-Rechenzentrum durch Abfragen den ersten FQDN zugewiesen am nächsten).
- Bereitzustellen Sie Failover, wenn Verbindung über einen SBC in einem Rechenzentrum hergestellt wird, die ein vorübergehendes Problem aufgetreten ist. Weitere Informationen finden Sie unter [Failover-Mechanismus](#failover-mechanism-for-sip-signaling) unten.  

Die FQDNs – sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com und sip3.pstnhub.microsoft.com – werden auf eine der folgenden IP-Adressen aufgelöst werden:

- 52.114.148.0
- 52.114.132.46 
- 52.114.75.24 
- 52.114.76.76 
- 52.114.7.24 
- 52.114.14.70

Sie müssen zum Öffnen von Ports für diese IP-Adressen in Ihrer Firewall für eingehenden und ausgehenden Datenverkehr zu und von der Adressen für Signale zu ermöglichen.  Wenn die Firewall DNS-Namen unterstützt, die Sip-all.pstnhub.microsoft.com-FQDN in die IP-Adressen über aufgelöst wird.  Sie müssen die folgenden Ports verwenden:

|**Datenverkehr**|**Von**|**Bis**|**Quellport**|**Zielport**|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP-Proxy|SBC|1024 – 65535|Klicken Sie auf die SBC definiert|
SIP/TLS|SBC|SIP-Proxy|Klicken Sie auf die SBC definiert|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>Failover-Mechanismus für SIP-Signale

Der SBC ist eine DNS-Abfrage zum Auflösen der sip.pstnhub.microsoft.com. Basierend auf den Speicherort SBC und den Datacenter festgestellten Leistungsmetriken, wird im primäre Datencenter ausgewählt. Wenn das primäre Datencenter ein Problem auftritt, der SBC der sip2.pstnhub.microsoft.com, die in der zweiten Datencenter zugewiesenen aufgelöst wird versucht, und in seltenen Fällen dieser Rechenzentren in zwei Bereiche sind nicht verfügbar, der SBC ein Wiederholungsversuch der letzten FQDN ( sip3.pstnhub.Microsoft.com), den dritten Datacenter IP bereitstellt.

In der folgenden Tabelle sind die Beziehungen zwischen primären, sekundären und tertiären Rechenzentren zusammengefasst:

|**Wenn das primäre Datencenter ist**|**EMEA**|**NOAM**|**ASIEN**|
|:--- |:--- |:--- |:--- |
|Die sekundären Rechenzentrum (sip2.pstnhub.microsoft.com)|USA|EU|USA|
|Im dritten Datencenter (sip3.pstnhub.microsoft.com)|ASIEN|ASIEN|EU|
|||||

## <a name="media-traffic-port-ranges"></a>Mediendatenverkehr: Port Bereiche

Media-Datenverkehr fließt zu und von einem separaten Dienst in der Microsoft-Cloud. Die IP-Adressbereich für Mediendatenverkehr:
- 52.112.0.0 /14 (IP-Adressen von 52.112.0.1 bis 52.115.255.254).

Der Portbereich von des Prozessors Medien wird in der folgenden Tabelle gezeigt: 

|**Datenverkehr**|**Von**|**Bis**|**Quellport**|**Zielport**|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|Media-Prozessor|SBC|49 152 – 53 247|Klicken Sie auf die SBC definiert|
|UDP/SRTP|SBC|Media-Prozessor|Klicken Sie auf die SBC definiert|49 152 – 53 247|
|

  > [!NOTE]
  > Microsoft empfiehlt mindestens zwei Ports pro gleichzeitigem Anruf auf die SBC.

## <a name="supported-session-border-controllers-sbcs"></a>Unterstützte Session Border Controller (SBCs)

Microsoft unterstützt nur den zertifizierten SBC mit direktem Routing ein. Da Enterprise-VoIP für Unternehmen wichtig ist, Microsoft führt intensiven Tests mit den ausgewählten SBCs und kann mit den Herstellern SBC sicherstellen, dass die zwei Systeme kompatibel sind. 

Geräte, die überprüft wurden, werden als zertifiziert für Teams direkten Routing aufgelistet. Die zertifizierte Geräte werden garantiert in allen Szenarien arbeiten. Es gibt auch eine gemeinsame supportprozesse zwischen Microsoft und die SBC-Anbietern hergestellt.  

Zu den Herstellern zurzeit zertifiziert wird:
- [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)
- Menüband-Kommunikation (früher von Sonus):
   - [SBC-Edge-Serie](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+SBC+Edge+1000+-+2000+for+Microsoft+Teams+Direct+Routing)
   - [SBC-Core-Serie](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe)
- ThinkTel: ThinkTel ist die SBCs für das Unternehmen nicht verkaufen, aber ihre SBC zertifiziert ist.  
 
## <a name="see-also"></a>Siehe auch

[Konfigurieren der Weiterleitung von direkten](direct-routing-configure.md)



