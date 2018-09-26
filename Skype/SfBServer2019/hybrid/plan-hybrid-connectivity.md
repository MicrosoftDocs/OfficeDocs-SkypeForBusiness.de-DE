---
title: Planen von hybridkonnektivität
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Planungsüberlegungen für die Implementierung von hybridkonnektivität zwischen Skype für Business Server und Skype für Business Online oder Teams.
ms.openlocfilehash: 90ea0b5ee73cba718c81e5614b02b5332e223acf
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2018
ms.locfileid: "25030679"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>Plan hybridkonnektivität zwischen Skype für Business Server und Office 365
[!INCLUDE [disclaimer](../disclaimer.md)]


## <a name="overview"></a>Übersicht

Lesen Sie in diesem Thema erfahren, wie Business Online oder Teams hybridkonnektivität zwischen Skype für Business Server und Skype planen. Die Einrichtung von hybrider Konnektivität ist der erste Schritt bei der Implementierung zahlreicher hybrider Skype for Business-Lösungen.

Hybridlösungen können Sie einige lokale-Steuerelement zu behalten, während Sie auch online zur Verfügung gestellt, in der Microsoft-Cloud-Dienste nutzen. Mit hybridkonnektivität einrichten, sowie einer Reihe von Cloud-Diensten für Ihre online verfügbar und lokale Benutzer können Sie Ihre Benutzer in die Cloud basierend auf Ihren Terminen und Business Bedarf verschieben.

Sie können beispielsweise Beibehaltung der lokalen PSTN-Anbindung Remote Call Control über Microsoft Telefonsystem in der Cloud abrufen. Sie können auch andere Cloud-Dienste wie Cloud Voicemail und rufen Sie Data Connector nutzen.

In diesem Thema wird die Infrastruktur und System-Anforderungen, die Sie benötigen zum Konfigurieren von hybridkonnektivität zwischen Ihre vorhandenen lokalen Skype für Business Server-Bereitstellung – mit Benutzern, die in Ihre lokale Active Directory – erstellt wurden und Skype für Business Online oder Teams.

Nachdem Sie in diesem Thema gelesen haben und zum Konfigurieren von hybridkonnektivität bereit sind, finden Sie unter [Configure hybridkonnektivität zwischen Skype für Business Server und Office 365](configure-hybrid-connectivity.md). Die Konfigurationsthemen bieten schrittweise Anweisungen zum Einrichten von hybridkonnektivität zwischen Ihrer lokalen Bereitstellung und Skype für Business Online.

(Informationen zum Konfigurieren des Lync Server 2013 oder der Lync Server 2010-Bereitstellung für hybride finden Sie unter [Lync Server 2013 Hybrid](https://go.microsoft.com/fwlink/p/?LinkId=617360).)

## <a name="split-domain-functionality"></a>Geteilte Domänenfunktionalität
<a name="BKMK_Overview"> </a>

 Hybrid-Verbindung zwischen einer lokalen Bereitstellung von Skype für Business Server und Skype für Business Online oder Teams eingerichtet können Sie einige Benutzer lokal und einige Benutzer online verwaltet.

Diese Art der Konfiguration wird manchmal als "geteilte Domäne" – Was bedeutet, dass Benutzer einer Domäne, z. B. "contoso.com" Skype für Business Server lokal und Skype für Business Online oder Teams verwenden, wie im folgenden Diagramm dargestellt aufgeteilt werden bezeichnet:

![Skype for Business mit hybrider Konnektivität – geteilte Domäne](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

Mit einer domänenumgebung Teilen:

- Benutzer, die lokal verwaltet werden interagieren mit lokalen Skype für Unternehmensserver. Sie haben auch Zugriff auf online Services wie Cloud Voicemail.

- Benutzer, die online verwaltet werden möglicherweise Skype für Business oder Teams Onlinedienste interagieren.

- Benutzer aus beiden Umgebungen können miteinander mithilfe von Instant Messaging, teilnehmen an Telefonkonferenzen oder VoIP-Anrufe, Zusammenarbeit und so weiter.

- Azure Active Directory verbinden wird verwendet, um das lokale Verzeichnis mit Office 365 synchronisieren.

Die lokale Active Directory-Instanz ist autoritativ. Daher müssen Sie mit den folgenden Schritten sicherstellen, dass lokale Benutzer und Onlinebenutzer sich gegenseitig ermitteln können:

- Alle Benutzer sollten zunächst in die lokale Active Directory erstellt, und klicken Sie dann mit Azure Active Directory synchronisiert werden.

- Benutzer, die in die Cloud verschieben möchten, müssen entweder ein Skype für Business Plan 2 oder Teams Lizenz verfügen.

- Wenn Ihre Benutzer zusätzliche online-Funktionen wie Skype Besprechung übertragen oder Cloud-Voicemail nutzen möchten, müssen Sie diese die entsprechende in Office 365-Lizenz zuweisen.

- Wenn Sie den Skype for Business Online-Benutzern eine Lizenz zugewiesen haben, müssen Sie sie lokal für Skype for Business oder für Enterprise-VoIP aktivieren. Weitere Informationen finden Sie unter [Aktivieren der Benutzer für Enterprise-VoIP lokal](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises.md). Weitere Informationen zu Anforderungen für Hybrid-VoIP finden Sie unter [Planen von Telefonsystem in Office 365 mit lokalen PSTN-Konnektivität in Skype für Business Server](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md).


## <a name="infrastructure-requirements"></a>Infrastrukturanforderungen
<a name="BKMK_Infrastructure"> </a>

Um hybridkonnektivität zwischen Ihrer lokalen Umgebung und Office 365 Kommunikationsdienste zu implementieren, müssen Sie die folgenden infrastrukturanforderungen erfüllen.

- Ein einzelnes lokale Bereitstellung von Skype für Business Server oder Lync Server, die in einer unterstützten Topologie bereitgestellt wird. Finden Sie in diesem Thema in der [topologieanforderungen](plan-hybrid-connectivity.md#BKMK_Topology) .

- Microsoft Office 365-Mandanten mit der Skype für Business Online aktiviert werden soll.

    > [!NOTE]
    > Sie können nur einen einzelnen Mandanten für eine Hybridkonfiguration mit Ihrer lokalen Bereitstellung verwenden.

- Skype für Business Server-Verwaltungstools. (Wenn Sie Lync Server 2013 oder Lync Server 2010 verwenden, können Sie die Verwaltungstools von Lync Server 2013 verwenden. Weitere Informationen finden Sie unter [Lync Server 2013 Hybrid](https://go.microsoft.com/fwlink/p/?LinkId=617360).)

- Azure Active Directory Connect zum Synchronisieren Ihres lokalen Verzeichnisses mit Office 365. Weitere Informationen finden Sie unter [Azure AD-Connect: Konten und Berechtigungen](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions).

    Wenn Sie einmaliges Anmelden mit Office 365 unterstützen möchten, damit Benutzer die gleichen Anmeldeinformationen wie für die lokale Bereitstellung verwenden können, können Sie die Kennwortsynchronisierungsfunktionen von Azure Active Directory (AAD) Connect nutzen. Sie können auch die Active Directory Federation Services (AD FS) für das einmalige Anmelden mit Office 365 verwenden.

Um hybridkonnektivität zu konfigurieren, müssen Sie auch Partnerverbund zwischen Ihrer lokalen und online-Umgebung einrichten und Konfigurieren von Ihrer Skype für Business Online Mandanten für einen freigegebenen Adressraum Session Initiation Protocol (SIP). Weitere Informationen über die erforderlichen Schritte zum Konfigurieren von hybridkonnektivität finden Sie unter [Configure hybridkonnektivität](configure-hybrid-connectivity.md).

Nachdem Sie hybridkonnektivität konfiguriert haben, können Sie Benutzer in Skype für Business Online oder Teams verschieben. Weitere Informationen finden Sie unter [Verschieben von Benutzern aus lokal zu Skype für Business Online](move-users-from-on-premises-to-skype-for-business-online.md) und [Verschieben von Benutzern aus lokalen Teams](move-users-from-on-premises-to-teams.md).

## <a name="multi-forest-support"></a>Unterstützung für mehrere Gesamtstrukturen
<a name="BKMK_MultiForest"> </a>

Wenn die folgenden Anforderungen erfüllt sind, können Benutzer auf Skype for Business-Funktionen in einer anderen Gesamtstruktur zugreifen:

- Die Benutzer werden ordnungsgemäß mit der Gesamtstruktur synchronisiert, in der Skype for Business gehostet wird: In Hybridkonfigurationen bedeutet dies, dass die Benutzer als deaktivierte Benutzerobjekte synchronisiert werden müssen.

- Die Gesamtstruktur, in der Skype for Business gehostet wird, muss der Gesamtstruktur, in der sich die Benutzer befinden, vertrauen.

Ausführliche Informationen zum hybridszenarien mit mehreren Gesamtstrukturen finden Sie unter [Konfigurieren einer Umgebung mit mehreren Gesamtstrukturen für hybride Skype für Unternehmen](configure-a-multi-forest-environment-for-hybrid.md).

## <a name="administrator-credentials"></a>Administratoranmeldeinformationen
<a name="BKMK_Credentials"> </a>

Wenn Sie gefragt werden, um Ihren Administratoranmeldeinformationen bereitzustellen, verwenden Sie den Benutzernamen und das Kennwort für das Administratorkonto für Ihre Office 365-Mandanten. Verwenden Sie diese Anmeldeinformationen auch, wenn Sie Azure Active Directory für den Verbund, verzeichnissynchronisierung, einmaliges Anmelden und Benutzer zu Skype für Business Online konfigurieren.

## <a name="skype-for-business-online-powershell"></a>Skype for Business Online-PowerShell
<a name="BKMK_PowerShell"> </a>

Administratoren haben jetzt die Möglichkeit, mithilfe von Windows PowerShell zum Verwalten von Skype für Business Online und ihre Skype für Business Online Benutzerkonten. Zu diesem Zweck müssen Sie zuerst herunterladen und installieren Sie die Skype für Business Online Connectormodul aus dem Microsoft Download Center. Weitere Informationen zum Herunterladen, installieren und verwenden die Skype für Business Online Connectormodul, und Informationen zur Verwendung von Windows PowerShell zum Verwalten von Skype für Business Online finden Sie unter [Einrichten des Computers für Windows PowerShell](https://technet.microsoft.com/library/dn362831.aspx).

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

Bevor Sie sich entschließen, in dem Sie Privatbenutzer in Ihrer Organisation möchten, sollten Sie den [Desktopclient Featurevergleich für Skype für Unternehmen](../../sfbserver/plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) zum Bestimmen der Client-Unterstützung für die verschiedenen Konfigurationen der Skype für Business Server überprüfen. Siehe auch:

- [Planen für Clients und Geräte](../../sfbserver/plan-your-deployment/clients-and-devices/clients-and-devices.md)

- [Mobiler Client Featurevergleich für Skype für Unternehmen](../../sfbserver/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)

## <a name="topology-requirements"></a>Topologieanforderungen
<a name="BKMK_Topology"> </a>

Um die für hybride Bereitstellung mit Skype für Business Online zu konfigurieren, müssen Sie einen der folgenden unterstützten Topologien aufweisen:

- Eine Skype für die Bereitstellung mit allen Servern mit Skype für Business Server 2015 Business Server 2015.

- Ein Lync Server 2013-Bereitstellung mit allen Servern mit Lync Server 2013.

    Hybrid-VoIP-Konnektivität muss der Edge-Server, die als Schnittstelle für den Verbund vorgesehen ist Skype für Business 2015; der Rand erfordert auch eine Skype für Business Server-Back-End. Sie können einen Pool verwenden, der keine Benutzer enthält.

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

Die Liste der zugelassenen Domänen enthält Domänen, für die ein Partner-Edge-FQDN (vollqualifizierter Domänenname) konfiguriert ist. Diese werden mitunter als zulässige Partnerserver oder direkte Verbundpartner bezeichnet. Sie sollten mit dem Unterschied zwischen einem öffentlichen Partnerverbund und einem geschlossenen Partnerverbund vertraut sein, der in lokalen Bereitstellungen als Partnerermittlung bzw. Liste der zulässigen Partnerdomänen bezeichnet wird.

Die folgenden Anforderungen müssen erfüllt sein, um eine Hybridbereitstellung erfolgreich zu konfigurieren:

- Der Domänenabgleich muss für die lokale Bereitstellung und den Office 365-Mandanten identisch konfiguriert sein. Wenn die Partnerermittlung für die lokale Bereitstellung aktiviert ist, muss der öffentliche Partnerverbund für den Onlinemandaten konfiguriert sein. Wenn die Partnerermittlung nicht aktiviert ist, muss für den Onlinemandanten der geschlossene Partnerverbund konfiguriert sein.

- Die Liste der blockierten Domänen in der lokalen Bereitstellung muss genau mit der Liste der blockierten Domänen für den Onlinemandanten übereinstimmen.

- Die Liste der zugelassenen Domänen in der lokalen Bereitstellung muss genau mit der Liste der zugelassenen Domänen für den Onlinemandanten übereinstimmen.

- Für die externen Kommunikation für den Mandanten online, die mithilfe der Skype für Business Online-Systemsteuerung konfiguriert ist, muss den Verbund aktiviert sein.

## <a name="dns-settings"></a>DNS-Einstellungen
<a name="BKMK_DNS"> </a>

Beim Erstellen von DNS-Einträgen für hybridbereitstellungen sollten alle Skype für Business externe DNS-Einträge für die lokale Infrastruktur verweisen. Informationen zu den erforderlichen DNS-Einträgen finden Sie unter [DNS-Anforderungen für Skype für Business Server](../../sfbserver/plan-your-deployment/network-requirements/dns.md).

Darüber hinaus müssen Sie sicherstellen, dass die DNS-Auflösung in der folgenden Tabelle beschriebenen in Ihrer lokalen Bereitstellung funktioniert:

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


|**Protokoll**|**TCP oder UDP**|**Quell-IP**|**Ziel-IP**|**Quellport**|**Zielport**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|SIP (MTLS)  <br/> |TCP  <br/> |Zugriffs-Edge  <br/> |Office 365  <br/> |Beliebig  <br/> |5061  <br/> |Signalisierung  <br/> |
|SIP (MTLS)  <br/> |TCP  <br/> |Office 365  <br/> |Zugriffs-Edge  <br/> |Beliebig  <br/> |5061  <br/> |Signalisierung  <br/> |
|STUN  <br/> |TCP  <br/> |A/V-Edge  <br/> |Office 365  <br/> |50000–59999  <br/> |443, 50000–59999  <br/> |Geöffnet für Audio-, Video- und Anwendungsfreigabesitzungen  <br/> |
|STUN  <br/> |TCP  <br/> |Office 365  <br/> |A/V-Edge  <br/> |443  <br/> |50000–59999  <br/> |Geöffnet für Audio-, Video- und Anwendungsfreigabesitzungen  <br/> |
|STUN  <br/> |UDP  <br/> |A/V-Edge  <br/> |Office 365  <br/> |3478  <br/> |3478  <br/> |Geöffnet für Audio- und Videositzungen  <br/> |
|STUN  <br/> |UDP  <br/> |Office 365  <br/> |A/V-Edge  <br/> |3478  <br/> |3478  <br/> |Geöffnet für Audio- und Videositzungen  <br/> |

Weitere Informationen zu Ports und Planen von Edge-Server-Firewall finden Sie unter [umgebungsanforderungen in Skype für Business Server Edge-Server](../../sfbserver/plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md). Siehe auch [Ports und Protokolle-Anforderungen für Server](../../sfbserver/plan-your-deployment/network-requirements/ports-and-protocols.md) und das [Protokoll Arbeitslasten Diagramm](https://go.microsoft.com/fwlink/p/?LinkId=550989).

## <a name="user-accounts-and-data"></a>Benutzerkonten und -daten
<a name="BKMK_UserAccounts"> </a>

In einer hybridbereitstellung muss jeder Benutzer, die Sie online home möchten zunächst in die lokale Bereitstellung erstellt werden, so, dass das Benutzerkonto in Active Directory-Domänendienste erstellt wird. Sie können den Benutzer zu Skype für Online Business verschieben, die Kontaktliste des Benutzers verschoben werden.

Beim Synchronisieren von Benutzerkonten zwischen Ihrer Bereitstellung in lokalen und online-Mandanten mit AAD verbinden, müssen Sie, auch wenn der Benutzer nicht online in verschoben werden die Active Directory-Konten für alle Skype für Business oder Lync-Benutzer in Ihrer Organisation zu synchronisieren. Wenn Sie nicht alle Benutzer synchronisieren, funktioniert die Kommunikation zwischen lokalen und Onlinebenutzern in Ihrem Unternehmen möglicherweise nicht erwartungsgemäß.

> [!IMPORTANT]
> Benutzerverwaltung für alle, einschließlich der Benutzer wechselt zwischen lokalen und Skype für Online Business vorgenommen werden mit der neuesten installierten Version der Verwaltungstools. Auf einem separaten Server, die Zugriff mit der vorhandenen lokalen Bereitstellung und mit dem Internet verbunden wurde, müssen die Verwaltungstools installiert werden. Das Cmdlet, um Benutzer aus der lokalen Bereitstellung nach Skype für Online Business [Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser?view=skype-ps), verschieben, muss über die Verwaltung für Ihre lokale Bereitstellung verbunden ausgeführt werden. Weitere Informationen zum Verschieben von Benutzern finden Sie unter [Verschieben von Benutzern aus lokal zu Skype für Business Online](move-users-from-on-premises-to-skype-for-business-online.md).

Sie sollten auch die folgenden benutzerbezogenen Probleme bei der Planung für eine hybridbereitstellung:

- **Benutzerkontakte** Der Grenzwert für Kontakte für Lync Online-Benutzer ist 250. Kontakte über diese Nummer werden aus der Kontaktliste des Benutzers entfernt werden, wenn das Konto zu Lync Online verschoben wird.

- **Instant Messaging und Anwesenheit** Kontaktlisten der Benutzer, Gruppen und Zugriffssteuerungslisten (ACLs) werden mit dem Benutzerkonto migriert.

- **Konferenzdaten, Besprechungsinhalte, und geplante Besprechungen** Dieser Inhalt wird nicht mit dem Benutzerkonto migriert. Benutzer müssen Besprechungen neu planen, nachdem ihre Konten zu Lync Online migriert wurden.

## <a name="user-policies-and-features"></a>Benutzerrichtlinien und Funktionen
<a name="BKMK_UserPolicies"> </a>

- In einer Hybridumgebung können Benutzer entweder lokal oder online für Chats und Konferenzen (Besprechungen) aktiviert werden. Beides gleichzeitig ist nicht möglich.

- **Clientunterstützung** Einige Benutzer eine neue Clientversion erfordern möglicherweise, wenn sie in Skype für Business Online verschoben werden. Für Office Communications Server 2007 R2 müssen Benutzer in einen Skype für Business Server oder für Lync Server 2013-Pool vor der Migration zu Skype für Business Online verschoben werden.

- **Lokale Richtlinien und Konfiguration (nicht-Benutzer)** Online und lokalen Richtlinien erfordern getrennte Konfiguration. Sie können keine globalen Richtlinien festlegen, die für beide Umgebungen gelten.
