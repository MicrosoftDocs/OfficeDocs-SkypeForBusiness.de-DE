---
title: Planen von Hybrid-Anbindung zwischen Skype for Business Server und Skype for Business Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
description: 'Zusammenfassung: Lesen Sie dieses Thema, um Informationen zum Planen von hybridkonnektivität zwischen Skype für Business Server und Skype für Business Online. Die Einrichtung von hybrider Konnektivität ist der erste Schritt bei der Implementierung zahlreicher hybrider Skype for Business-Lösungen.'
ms.openlocfilehash: 31c10423c6ba838e595de75e39d6f166de30c756
ms.sourcegitcommit: 7bb52d5d998415555a535a32419e99b68e3be6a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2018
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-skype-for-business-online"></a>Planen von Hybrid-Anbindung zwischen Skype for Business Server und Skype for Business Online
 
**Zusammenfassung:** Lesen Sie dieses Thema und erfahren Sie, wie Hybrid-Anbindung zwischen Skype for Business Server und Skype for Business Online geplant wird.  Die Einrichtung von hybrider Konnektivität ist der erste Schritt bei der Implementierung zahlreicher hybrider Skype for Business-Lösungen.
  
Dieses Thema bietet eine Übersicht und beschreibt die Infrastruktur und Systemanforderungen müssen Sie das Konfigurieren von hybridkonnektivität zwischen den vorhandenen lokalen Skype für Business Server-Bereitstellung – mit Benutzern, die in Ihrer lokalen erstellt wurden Active Directory – und Skype für Unternehmen Online. 
  
Dieses Thema enthält die folgenden Abschnitte:
  
- [Übersicht über die](plan-hybrid-connectivity.md#BKMK_Overview)
    
- [Anforderungen an die Netzwerkinfrastruktur](plan-hybrid-connectivity.md#BKMK_Infrastructure)
    
- [Unterstützung mit mehreren Gesamtstrukturen](plan-hybrid-connectivity.md#BKMK_MultiForest)
    
- [Koexistenz von Exchange](plan-hybrid-connectivity.md#BKMK_Exchange)
    
- [Administratoranmeldeinformationen](plan-hybrid-connectivity.md#BKMK_Credentials)
    
- [Skype für Business Online-PowerShell](plan-hybrid-connectivity.md#BKMK_PowerShell)
    
- [Skype für Business-Client-Unterstützung](plan-hybrid-connectivity.md#BKMK_ClientSupport)
    
- [Topologieanforderungen](plan-hybrid-connectivity.md#BKMK_Topology)
    
- [Anforderungen an den Identitätsverbund zulässige/blockiert werden aufgelistet.](plan-hybrid-connectivity.md#BKMK_Federation)
    
- [DNS-Einstellungen](plan-hybrid-connectivity.md#BKMK_DNS)
    
- [Überlegungen zur Firewall](plan-hybrid-connectivity.md#BKMK_Firewall)
    
- [Anforderungen an Ports und Protokolle](plan-hybrid-connectivity.md#BKMK_Ports)
    
- [Benutzerkonten und Daten](plan-hybrid-connectivity.md#BKMK_UserAccounts)
    
- [Richtlinien für Benutzer und features](plan-hybrid-connectivity.md#BKMK_UserPolicies)
    
Nachdem Sie in diesem Thema gelesen haben und bereit zum Bereitstellen von finden Sie unter [Deploy hybridkonnektivität zwischen Skype für Business Server und Skype für Business Online](deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)sind. Die Bereitstellungsthemen enthalten schrittweise Anleitungen zum Einrichten von hybrider Konnektivität zwischen Ihrer lokalen Bereitstellung und Skype for Business Online.
  
(Informationen zum Konfigurieren des Lync Server 2013 oder der Lync Server 2010-Bereitstellung für hybride finden Sie unter [Lync Server 2013 Hybrid](https://go.microsoft.com/fwlink/p/?LinkId=617360).)
  
## <a name="overview"></a>Übersicht
<a name="BKMK_Overview"> </a>

Mithilfe von hybriden Lösungen können Sie Ihre Benutzer auf der Grundlage Ihres Zeitplans und Ihrer geschäftlichen Anforderungen in die Cloud verschieben. Im Mittelpunkt dieses Themas steht die hybride Konnektivität zwischen einer lokalen Skype for Business Server-Bereitstellung und Skype for Business Online. Diese Konnektivität ermöglicht es Ihnen, einen Teil der Benutzer lokal und einen anderen Teil online zu verwalten.
  
Diese Art der Bereitstellung wird manchmal als "geteilte Domäne" bezeichnet – Bedeutung Benutzer einer Domäne, z. B. "contoso.com", aufgeteilt mit Skype für Business Server lokal und Skype für Business Online wie folgt:
  
- Lokal verwaltete Benutzer interagieren mit lokalen Skype for Business-Servern.
    
- Online verwaltete Benutzer interagieren mit Skype for Business-Onlinediensten.
    
- Benutzer aus beiden Umgebungen können zusammenarbeiten, indem sie Chat verwenden und an Telefonkonferenzen, VoIP-Anrufen usw. teilnehmen.
    
- Ihr lokales Verzeichnis wird über Azure Active Directory Connect mit Office 365 synchronisiert.
    
Die lokale Active Directory-Instanz ist autoritativ. Daher müssen Sie mit den folgenden Schritten sicherstellen, dass lokale Benutzer und Onlinebenutzer sich gegenseitig ermitteln können:
  
- Alle Benutzer sollten zunächst in die lokale Active Directory erstellt, und klicken Sie dann mit Azure Active Directory synchronisiert werden. 
    
- Wenn Ihre Benutzer für Skype for Business lokal verwaltet werden, müssen Sie sie lokal für Skype for Business aktivieren.
    
- Wenn die Benutzer lokal verwaltet werden, aber einige der Onlinefunktionen wie zum Beispiel Skype-Livekonferenz nutzen möchten, müssen Sie ihnen eine Lizenz für Skype for Business Online (Plan 2) zuweisen.
    
- Wenn die Benutzer in Skype for Business Online verwaltet werden, müssen Sie ihnen eine Lizenz für Skype for Business Online (Plan 2) zuweisen, sobald ihr Konto mit Azure AD synchronisiert wird. 
    
- Wenn Sie den Skype for Business Online-Benutzern eine Lizenz zugewiesen haben, müssen Sie sie lokal für Skype for Business oder für Enterprise-VoIP aktivieren. Weitere Informationen finden Sie unter [Aktivieren der Benutzer für Enterprise-VoIP lokal](plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises.md). Weitere Informationen zu Anforderungen für Hybrid-VoIP finden Sie unter [Planen von Telefonsystem in Office 365 mit lokalen PSTN-Konnektivität in Skype für Business Server](plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md).
    
In den folgenden Abschnitten erfahren Sie mehr über die Konfiguration von Active Directory. Zuerst möchten wir Ihnen jedoch einen Überblick über die Begriffe und Akronyme geben, die in den folgenden Diagrammen und in vielen der Themen zur hybriden Konnektivität verwendet werden:
  
- PSTN – Public Switched Telephone Network (Telefonfestnetz)
    
- PBX – Private Branch Exchange (Nebenstellenanlage)
    
- Telefonsystem – das von Microsoft angebotene Cloud-PBX-Telefonsystem
    
- Trunk - Telefonie-Zeile, die an das Telefonfestnetz Nebenstellenanlagen verbindet – möglicherweise ein Trunk Session Initiation Protocol (SIP) verwenden – A Voice over Internet Protocol (VoIP) – oder die ältere Time Division Multiplexing (TDM)-Technologie 
    
- SBC – Session Border Controller – ein Gerät, das als Firewall und Router in Telefonienetzwerken dient. Ein SBC bietet zum Beispiel Sicherheit, Konnektivität, Interoperabilität und Dienstqualität (Quality of Service, QoS). 
    
- PSTN-Gateway – ein Gerät, das in Telefonienetzwerken als Router dient und größtenteils die gleichen Funktionen wie ein SBC bietet (mit Ausnahme von Sicherheit und NAT-Traversal)
    
Das folgende Diagramm zeigt einen Skype Business "Split-Domäne" hybridkonfiguration. Die Benutzer A und B werden online verwaltet, können aber von lokalen Benutzern ermittelt werden. Die Benutzer C und D werden lokal verwaltet, können aber von Onlinebenutzern ermittelt werden.
  
![Skype for Business mit hybrider Konnektivität – geteilte Domäne](../media/c4fc9311-1930-4a58-877f-3c1524dfab5c.png)
  
Möglicherweise kennen Sie auch den Begriff „Hybridtelefonie“. Damit sind lokale VoIP-Trunks gemeint, die Funktionen für in der Cloud verwaltete Benutzer bereitstellen. Hybridtelefonie ermöglicht die Migration zur Cloud, während die lokale VoIP-Konfiguration erhalten bleibt. Wenn Sie bereits über eine Skype for Business Server-Bereitstellung verfügen und Hybridtelefonie aktivieren möchten, müssen Sie zunächst eine Umgebung mit geteilter Domäne konfigurieren. 
  
Angenommen, Ihr Unternehmen verfügt über eine große Felds Mobil Organisation unterstützt werden, die erfordert minimale Nebenstellenanlage VoIP, aber umfassende Smartphone verwenden. Sie können diese Benutzer in die Cloud verschieben, um von den Vorteilen des von Microsoft angebotenen Telefonsystems in Office 365 (Cloud-PBX) zu profitieren. Wenn Ihr Unternehmen auch eine große lokale Callcenter, die als Teil Ihrer lokalen PBX erweitert, komplexer Kontakt Center Software erforderlich sind verfügt, können Sie diese Benutzer lokal zu lassen. Sowohl die online verwalteten als auch die lokal verwalteten Benutzer verfügen durch die lokale Bereitstellung über PSTN-Anbindung.
  
Das folgende Diagramm zeigt eine Skype for Business-Bereitstellung mit Hybridtelefonie:
  
![Skype for Business mit geteilter Domäne und Cloud-PBX](../media/5e755772-269e-45ce-8b48-2e06ababfe6c.png)
  
Weitere Informationen zum Einrichten einer Hybrid-VoIP-Lösung mit Ihrer Skype für Business Server-Bereitstellung finden Sie unter [Planen von Telefonsystem in Office 365 mit lokalen PSTN-Konnektivität in Skype für Business Server](plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md). 
  
Sie können auch konfigurieren, hybridbereitstellungen für die Integration in lokale Exchange und SharePoint oder mit Microsoft Office 365-Anwendungen, einschließlich Exchange Online und SharePoint Online. Außerdem können Sie eine Hybridtelefonielösung konfigurieren, für die keine vollständige Skype for Business Server-Bereitstellung mit Cloud Connector Edition erforderlich ist. Weitere Informationen zu allen Skype für hybridlösungen für geschäftliche und zum Planen Ihrer in der Cloud verschieben finden Sie unter [Skype für Business hybridlösungen](skype-for-business-hybrid-solutions.md).
  
## <a name="infrastructure-requirements"></a>Infrastrukturanforderungen
<a name="BKMK_Infrastructure"> </a>

Um hybride Konnektivität zwischen Skype for Business Server und Skype for Business Online zu implementieren und bereitzustellen, müssen Sie in Ihrer Umgebung Folgendes konfigurieren:
  
- Ein einzelnes lokale Bereitstellung von Skype für Business Server oder Lync Server, die in einer unterstützten Topologie bereitgestellt wird. Finden Sie in diesem Thema in der [topologieanforderungen](plan-hybrid-connectivity.md#BKMK_Topology) .
    
- Microsoft Office 365-Mandanten mit der Skype für Business Online aktiviert werden soll. 
    
    > [!NOTE]
    > Sie können nur einen einzelnen Mandanten für eine Hybridkonfiguration mit Ihrer lokalen Bereitstellung verwenden. 
  
- Skype für Business Server 2015 Verwaltungstools. (Wenn Sie Lync Server 2013 oder Lync Server 2010 verwenden, können Sie die Verwaltungstools von Lync Server 2013 verwenden. Weitere Informationen finden Sie unter [Lync Server 2013 Hybrid](https://go.microsoft.com/fwlink/p/?LinkId=617360).)
    
- Azure Active Directory Connect zum Synchronisieren Ihres lokalen Verzeichnisses mit Office 365. Weitere Informationen finden Sie unter [Active Directory mit Azure Active Directory verbinden](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions).
    
    Wenn Sie einmaliges Anmelden mit Office 365 unterstützen möchten, damit Benutzer die gleichen Anmeldeinformationen wie für die lokale Bereitstellung verwenden können, können Sie die Kennwortsynchronisierungsfunktionen von Azure Active Directory (AAD) Connect nutzen. Sie können auch die Active Directory Federation Services (AD FS) für das einmalige Anmelden mit Office 365 verwenden. 
    
- Einen aktivierten Partnerverbund zwischen Ihrer lokalen Skype for Business-Bereitstellung und Ihrem Office 365-Mandanten. Verbund ermöglicht Benutzern in Ihrer lokalen Bereitstellung mit Office 365-Benutzern in Ihrer Organisation kommunizieren. Weitere Informationen finden Sie unter [Configure Verbund mit Skype für Business Online](deploy-hybrid-connectivity/configure-federation-with-skype-for-business-online.md).
    
- Einen aktivierten freigegebenen SIP-Adressraum (Session Initiation-Protokoll). Eine SIP-Adresse ist ein eindeutiger Bezeichner für jeden Benutzer in einem Netzwerk, ähnlich wie eine Telefonnummer oder eine E-Mail-Adresse. Bevor Sie versuchen, den Benutzer aus der lokalen in Skype für Business Online zu verschieben, müssen Sie Ihre Office 365-Mandanten zum Freigeben von des Adressraums Shared Session Initiation Protocol (SIP) mit der lokalen Bereitstellung konfigurieren. Weitere Informationen finden Sie unter [Configure Verbund mit Skype für Business Online](deploy-hybrid-connectivity/configure-federation-with-skype-for-business-online.md).
    
## <a name="multi-forest-support"></a>Unterstützung für mehrere Gesamtstrukturen
<a name="BKMK_MultiForest"> </a>

Wenn die folgenden Anforderungen erfüllt sind, können Benutzer auf Skype for Business-Funktionen in einer anderen Gesamtstruktur zugreifen:
  
- Die Benutzer werden ordnungsgemäß mit der Gesamtstruktur synchronisiert, in der Skype for Business gehostet wird: In Hybridkonfigurationen bedeutet dies, dass die Benutzer als deaktivierte Benutzerobjekte synchronisiert werden müssen.
    
- Die Gesamtstruktur, in der Skype for Business gehostet wird, muss der Gesamtstruktur, in der sich die Benutzer befinden, vertrauen.
    
Ausführliche Informationen zum hybridszenarien mit mehreren Gesamtstrukturen finden Sie unter [Konfigurieren einer Umgebung mit mehreren Gesamtstrukturen für hybride Skype für Unternehmen](deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md).
  
## <a name="exchange-co-existence"></a>Koexistenz mit Exchange
<a name="BKMK_Exchange"> </a>

Berücksichtigen Sie im Hinblick auf die Unterstützung von Koexistenz mit Exchange die folgenden Punkte:
  
- Bewährt hat sich das Postfach des Benutzers zu Exchange Online verschieben, vor dem Verschieben des Benutzers Skype für Unternehmen privat.
    
- Benutzer mit lokalen Exchange-Postfächern werden mit den folgenden Einschränkungen unterstützt:
    
  - Clientanmeldung: Die Benutzer müssen sich möglicherweise zweimal beim Skype for Business-Client anmelden.
    
  - Server Seite Unterhaltungen, Archivierung, Unified Contact Store, HighRes Foto erfordert Exchange 2013 oder höher, und Sie müssen die OAuth-Server zu-Server-Kommunikation aktivieren. Weitere Informationen finden Sie unter [Manage Server-zu-Server-Authentifizierung (OAuth) und partneranwendungen in Skype für Business Server 2015](https://technet.microsoft.com/en-us/library/jj204817.aspx).
    
Ausführliche Informationen zum Koexistenz mit Exchange Server finden Sie unter einschließlich Unterstützung Kriterien und Einschränkungen in verschiedenen Kombinationen von lokalen und online, [Feature unterstützen](../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) in [Planen der Integration von Skype für Unternehmen und Exchange](../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
  
## <a name="administrator-credentials"></a>Administratoranmeldeinformationen
<a name="BKMK_Credentials"> </a>

Wenn Sie gefragt werden, um Ihren Administratoranmeldeinformationen bereitzustellen, verwenden Sie den Benutzernamen und das Kennwort für das Administratorkonto für Ihre Office 365-Mandanten. Verwenden Sie diese Anmeldeinformationen auch, wenn Sie Azure Active Directory für den Verbund, verzeichnissynchronisierung, einmaliges Anmelden und Benutzer zu Skype für Business Online konfigurieren.
  
## <a name="skype-for-business-online-powershell"></a>Skype for Business Online-PowerShell
<a name="BKMK_PowerShell"> </a>

Administratoren haben jetzt die Möglichkeit, mithilfe von Windows PowerShell zum Verwalten von Skype für Business Online und ihre Skype für Business Online Benutzerkonten. Zu diesem Zweck müssen Sie zuerst herunterladen und installieren Sie die Skype für Business Online Connectormodul aus dem Microsoft Download Center. Weitere Informationen zum Herunterladen finden Sie unter Installieren und Verwenden der Skype für Business Online Connectormodul, und Informationen zur Verwendung von Windows PowerShell zum Verwalten von Skype für Online Business [Using Windows PowerShell zum Verwalten von Skype für Unternehmen Online](https://technet.microsoft.com/library/dn362831.aspx). 
  
## <a name="skype-for-business-client-support"></a>Unterstützung für Skype for Business-Clients
<a name="BKMK_ClientSupport"> </a>

Es gibt einige Unterschiede in Bezug auf die Features, die von Clients unterstützt werden, und die Features, die in lokalen und Onlineumgebungen verfügbar sind. Die folgenden Clients werden in einer hybridbereitstellung mit Skype für Business Online unterstützt:
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Windows Store-App für Lync
    
- Lync Web App
    
- Lync Mobile
    
- Lync für Mac 2011
    
- Lync-Chatroom-System und Skype für Raum Geschäftssystem
    
- Lync Basic 2013
    
- Microsoft Surface Hub
    
Bevor Sie sich entschließen, in dem Sie Privatbenutzer in Ihrer Organisation möchten, sollten Sie den [Desktopclient Featurevergleich für Skype für Unternehmen](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) zum Bestimmen der Client-Unterstützung für die verschiedenen Konfigurationen der Skype für Business Server überprüfen. Siehe auch:
  
- [Planen von Clients und Geräten](../plan-your-deployment/clients-and-devices/clients-and-devices.md)
    
- [Mobiler Client Featurevergleich für Skype für Unternehmen](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)
    
## <a name="topology-requirements"></a>Topologieanforderungen
<a name="BKMK_Topology"> </a>

Um die für hybride Bereitstellung mit Skype für Business Online zu konfigurieren, müssen Sie einen der folgenden unterstützten Topologien aufweisen:
  
- Eine Skype für die Bereitstellung mit allen Servern mit Skype für Business Server 2015 Business Server 2015.
    
- Ein Lync Server 2013-Bereitstellung mit allen Servern mit Lync Server 2013.
    
    Für Hybridtelefoniekonnektivität muss auf dem Edgeserver, der als Partnerverbund-Edge festgelegt ist, Skype for Business 2015 ausgeführt werden. Außerdem wird für den Edge ein Skype for Business Server-Back-End benötigt. Sie können einen Pool verwenden, der keine Benutzer enthält. 
    
- Ein Lync Server 2010-Bereitstellung mit allen Servern mit Lync Server 2010 mit den neuesten kumulativen Updates.
    
  - Der Verbund Edge-Server und Hopserver für den nächsten aus den Edge-Server-Verbund müssen Lync Server 2010 mit den neuesten kumulativen Updates ausgeführt werden.
    
  - Die Skype für Business Server 2015 oder Administrative Tools für Lync Server 2013 muss auf mindestens einem Server oder Verwaltungscomputer installiert werden.
    
- Eine gemischte Lync Server 2013 und Skype für die Business Server 2015 Bereitstellung mit der folgenden Serverrollen in mindestens einem Standort Skype für Business Server 2015 ausgeführt:
    
  - Mindestens ein Enterprise-Pool- oder Standard Edition-Server  
    
  - Der dem SIP-Partnerverbund zugeordnete Director-Pool, falls vorhanden
    
  - Der dem SIP-Partnerverbund zugeordnete Edgepool
    
- Eine gemischte Lync Server 2010 und Skype für die Business Server 2015 Bereitstellung mit der folgenden Serverrollen in mindestens einem Standort Skype für Business Server 2015 ausgeführt:
    
  - Mindestens ein Enterprise-Pool- oder Standard Edition-Server  
    
  - Der dem SIP-Partnerverbund zugeordnete Director-Pool, falls vorhanden
    
  - Der dem SIP-Partnerverbund zugeordnete Edgepool für den Standort
    
- Eine gemischte Lync Server 2010 und Lync Server 2013-Bereitstellung mit der folgenden Serverrollen in mindestens einem Standort mit Lync Server 2013:
    
  - Mindestens ein Enterprise-Pool- oder Standard Edition-Server am Standort
    
  - Der dem SIP-Partnerverbund zugeordnete Director-Pool, falls am Standort vorhanden
    
  - Der dem SIP-Partnerverbund zugeordnete Edgepool für den Standort
    
## <a name="federation-allowedblocked-lists-requirements"></a>Anforderungen in Bezug auf die Listen der zugelassenen und blockierten Domänen für den Partnerverbund
<a name="BKMK_Federation"> </a>

Die Liste der zulässigen Domänen umfasst, Domänen, die einen Partner Edge vollqualifizierten Domänennamen (FQDN) konfiguriert haben. Diese werden manchmal als zugelassenen Partner Servern Ordirect Verbundpartner bezeichnet. Sie sollten mit den Unterschied zwischen offenen Verbund und geschlossen Verbund genannt Partner Andallowed Partner Domäne Suchliste, jeweils in lokalen Bereitstellungen vertraut sein.
  
Die folgenden Anforderungen müssen erfüllt sein, um eine Hybridbereitstellung erfolgreich zu konfigurieren:
  
- Der Domänenabgleich muss für die lokale Bereitstellung und den Office 365-Mandanten identisch konfiguriert sein. Wenn die Partnerermittlung für die lokale Bereitstellung aktiviert ist, muss der öffentliche Partnerverbund für den Onlinemandaten konfiguriert sein. Wenn die Partnerermittlung nicht aktiviert ist, muss für den Onlinemandanten der geschlossene Partnerverbund konfiguriert sein.
    
- Die Liste der blockierten Domänen in der lokalen Bereitstellung muss genau mit der Liste der blockierten Domänen für den Onlinemandanten übereinstimmen.
    
- Die Liste der zugelassenen Domänen in der lokalen Bereitstellung muss genau mit der Liste der zugelassenen Domänen für den Onlinemandanten übereinstimmen.
    
- Für die externen Kommunikation für den Mandanten online, die mithilfe der Skype für Business Online-Systemsteuerung konfiguriert ist, muss den Verbund aktiviert sein.
    
## <a name="dns-settings"></a>DNS-Einstellungen
<a name="BKMK_DNS"> </a>

Beim Erstellen von DNS-Einträgen für hybridbereitstellungen sollten alle Skype für Business externe DNS-Einträge für die lokale Infrastruktur verweisen. Informationen zu den erforderlichen DNS-Einträgen finden Sie unter [DNS-Anforderungen für Skype für Business Server 2015](../plan-your-deployment/network-requirements/dns.md).
  
Darüber hinaus müssen Sie sicherstellen, dass die in der folgenden Tabelle erläuterte DNS-Auflösung in Ihrer lokalen Bereitstellung funktioniert:
  
|DNS-Eintrag  <br/> |Aufzulösen durch  <br/> |DNS-Anforderung  <br/> |
|:-----|:-----|:-----|
|DNS-SRV-Eintrag für _sipfederationtls. \<sipdomain.com\> für alle unterstützten SIP-Domänen, die zum Auflösen von in externen IP(s) Zugriffs-Edgeservers  <br/> |Edgeserver  <br/> |Aktivieren Sie Partnerverbundkommunikation in einer Hybridkonfiguration. Der Edgeserver muss wissen, wohin der Datenverkehr im Partnerverbund für die zwischen lokal und online aufgeteilte SIP-Domäne geleitet werden soll.  <br/> Es muss strenge DNS-Namensübereinstimmung zwischen der Domäne im Benutzernamen und dem SRV-Eintrag verwendet werden.  <br/> |
|DNS-A-Eintrag/Einträge für den Edge-Webkonferenzdienst-FQDN, zum Beispiel „webcon.contoso.com“, aufgelöst zu der externen IP/den IPs des Webkonferenzdienst-Edgeservers  <br/> |Interne Firmennetzwerk den Computern der Benutzer verbunden  <br/> |Versetzen Sie Onlinebenutzer in die Lage, in lokal gehosteten Besprechungen Inhalte zu präsentieren oder zu betrachten. Entsprechende Inhalte sind unter anderem PowerPoint-Dateien, Whiteboards, Umfragen und freigegebene Notizen.   <br/> |
   
Je nachdem, wie DNS in Ihrer Organisation konfiguriert ist, müssen Sie möglicherweise der intern gehosteten DNS-Zone für die entsprechenden SIP-Domäne(n) diese Einträge hinzufügen, um die interne DNS-Auflösung dieser Datensätze zu gewährleisten.
  
## <a name="firewall-considerations"></a>Überlegungen zu Firewalls
<a name="BKMK_Firewall"> </a>

Die Computer in Ihrem Netzwerk müssen Standard-Internet-DNS-Lookups ausführen können. Wenn diese Computer Standard-Internetwebsites erreichen können, erfüllt Ihr Netzwerk diese Anforderung.
  
Je nach den Speicherort des Microsoft Online Services-Rechenzentrum, müssen Sie auch Ihre Netzwerkgeräte Firewall, um Verbindungen basierend auf Platzhalter-Domänennamen akzeptieren konfigurieren (beispielsweise alle Datenverkehr von \*. outlook.com). Wenn der Firewalls der Organisation keine Platzhalter Namen Konfigurationen unterstützen, müssen Sie manuell ermitteln der IP-Adressbereiche, die Sie zulassen möchten und die angegebenen Ports.
  
Weitere Informationen finden Sie unter [Office 365-URLs und IP-Adressbereiche](https://go.microsoft.com/fwlink/p/?LinkId=252942).
  
## <a name="port-and-protocol-requirements"></a>Port- und Protokollanforderungen
<a name="BKMK_Ports"> </a>

Sie müssen nicht nur die Portanforderungen für die interne Kommunikation berücksichtigen, sondern auch die folgenden Ports konfigurieren, um die Hybrid-Anbindung zu aktivieren:
  

|**Protokoll**|**TCP oder UDP**|**Quell-IP**|**Ziel-IP-**|**Quellport**|**Zielport**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|SIP (MTLS)  <br/> |TCP  <br/> |Zugriffs-Edge  <br/> |Office 365  <br/> |Beliebig  <br/> |5061  <br/> |Signalisierung  <br/> |
|SIP (MTLS)  <br/> |TCP  <br/> |Office 365  <br/> |Zugriffs-Edge  <br/> |Beliebig  <br/> |5061  <br/> |Signalisierung  <br/> |
|STUN  <br/> |TCP  <br/> |A/V-Edge  <br/> |Office 365  <br/> |50000–59999  <br/> |443  <br/> |Geöffnet für Audio-, Video- und Anwendungsfreigabesitzungen  <br/> |
|STUN  <br/> |TCP  <br/> |Office 365  <br/> |A/V-Edge  <br/> |50000–59999  <br/> |443  <br/> |Geöffnet für Audio-, Video- und Anwendungsfreigabesitzungen  <br/> |
|STUN  <br/> |UDP  <br/> |A/V-Edge  <br/> |Office 365  <br/> |3478  <br/> |3478  <br/> |Geöffnet für Audio- und Videositzungen  <br/> |
|STUN  <br/> |UDP  <br/> |Office 365  <br/> |A/V-Edge  <br/> |443  <br/> |3478  <br/> |Geöffnet für Audio- und Videositzungen  <br/> |
   
Weitere Informationen zu Ports und Planen von Edge-Server-Firewall finden Sie unter [umgebungsanforderungen in Skype für Business Server 2015 Edge-Server](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md). Siehe auch [Ports und Protokolle-Anforderungen für Server](../plan-your-deployment/network-requirements/ports-and-protocols.md) und das [Protokoll Arbeitslasten Diagramm](http://go.microsoft.com/fwlink/p/?LinkId=550989).
  
## <a name="user-accounts-and-data"></a>Benutzerkonten und -daten
<a name="BKMK_UserAccounts"> </a>

In einer hybridbereitstellung muss alle Benutzer, die Sie online home möchten zunächst in die lokale Bereitstellung erstellt werden, so, dass das Benutzerkonto in Active Directory-Domänendienste erstellt wird. Sie können den Benutzer zu Skype für Online Business verschieben, die Kontaktliste des Benutzers verschoben werden.
  
Beim Synchronisieren von Benutzerkonten zwischen Ihrer Bereitstellung in lokalen und online-Mandanten mit AAD verbinden, müssen Sie, auch wenn der Benutzer nicht online in verschoben werden die Active Directory-Konten für alle Skype für Business oder Lync-Benutzer in Ihrer Organisation zu synchronisieren. Wenn Sie nicht alle Benutzer synchronisieren, funktioniert die Kommunikation zwischen lokalen und Onlinebenutzern in Ihrem Unternehmen möglicherweise nicht erwartungsgemäß.
  
> [!IMPORTANT]
> Benutzerverwaltung für alle, einschließlich der Benutzer wechselt zwischen lokalen und Skype für Online Business vorgenommen werden mit der neuesten installierten Version der Verwaltungstools. Auf einem separaten Server, die Zugriff mit der vorhandenen lokalen Bereitstellung und mit dem Internet verbunden wurde, müssen die Verwaltungstools installiert werden. Das Cmdlet, um Benutzer aus der lokalen Bereitstellung nach Skype für Online Business [Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser?view=skype-ps), verschieben, muss über die Verwaltung für Ihre lokale Bereitstellung verbunden ausgeführt werden. Weitere Informationen zum Verschieben von Benutzern finden Sie unter [Verschieben von Benutzern aus lokal zu Skype für Business Online](deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online.md). 
  
> [!IMPORTANT]
> Wenn der Benutzer mit dem Onlineportal für Office 365 erstellt wurde, wird das Benutzerkonto nicht mit der lokalen Active Directory-Bereitstellung synchronisiert und der Benutzer ist dort nicht vorhanden. Wenn Sie bereits Benutzer in Ihrem Onlinemandanten erstellt haben und eine Hybridkonfiguration mit einer lokalen Bereitstellung erstellen möchten, finden Sie entsprechende Informationen unter „Konfiguration von Hybridbereitstellungen von online zu lokal in Skype for Business Server 2015“. 
  
> [!NOTE]
> Wenn Sie zurzeit einen Skype für Business Online-Kunden, die für Business Online Skype-fähigen Benutzer umfasst, die nicht in einer lokalen Bereitstellung aktiviert wurden sind, finden Sie unter [Verschieben von Benutzern von Skype für Business Online auf lokal](deploy-hybrid-connectivity/move-users-from-skype-for-business-online-to-on-premises.md). 
  
Sie sollten bei der Planung einer Hybridbereitstellung auch die folgenden benutzerbezogenen Aspekte berücksichtigen.
  
- **Benutzerkontakte** Der Grenzwert für Kontakte für Lync Online-Benutzer ist 250. Kontakte über diese Nummer werden aus der Kontaktliste des Benutzers entfernt werden, wenn das Konto zu Lync Online verschoben wird.
    
- **Instant Messaging und Anwesenheit** Kontaktlisten der Benutzer, Gruppen und Zugriffssteuerungslisten (ACLs) werden mit dem Benutzerkonto migriert.
    
- **Konferenzdaten, Besprechungsinhalte, und geplante Besprechungen** Dieser Inhalt wird nicht mit dem Benutzerkonto migriert. Benutzer müssen Besprechungen neu planen, nachdem ihre Konten zu Lync Online migriert wurden.
    
## <a name="user-policies-and-features"></a>Benutzerrichtlinien und Funktionen
<a name="BKMK_UserPolicies"> </a>

- In einer Hybridumgebung können Benutzer entweder lokal oder online für Chats und Konferenzen (Besprechungen) aktiviert werden. Beides gleichzeitig ist nicht möglich.
    
- **Clientunterstützung** Einige Benutzer eine neue Clientversion erfordern möglicherweise, wenn sie in Skype für Business Online verschoben werden. Für Office Communications Server 2007 R2 müssen Benutzer in einen Skype für Business Server oder für Lync Server 2013-Pool vor der Migration zu Skype für Business Online verschoben werden.
    
- **Lokale Richtlinien und Konfiguration (nicht-Benutzer)** Online und lokalen Richtlinien erfordern getrennte Konfiguration. Sie können keine globalen Richtlinien festlegen, die für beide Umgebungen gelten.
    

