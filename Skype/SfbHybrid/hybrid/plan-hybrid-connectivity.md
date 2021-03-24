---
title: Planen von hybriden | Skype for Business Server 2019- und Microsoft 365- oder Office 365-Integration
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Planen Sie, hybride Verbindungen zwischen Skype for Business Server und Teams oder Skype for Business Online zu implementieren, indem Sie den Skype for Business-Hybridmodus konfigurieren.
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 1a43243f4b5ce827a7c688c1aad1983466aa6ca7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110261"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-microsoft-365-or-office-365"></a>Planen der Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365

In diesem Thema erfahren Sie, wie Sie die Hybridkonnektivität zwischen Skype for Business Server und Teams oder Skype for Business Online planen. Das Einrichten von Hybridverbindungen ist der erste Schritt beim Migrieren Ihrer lokalen Umgebung zur Cloud.

Wenn Sie über lokale Skype for Business-Benutzer verfügen, die (parallel) auch Microsoft Teams verwenden, können diese Benutzer von ihrem Teams-Client aus nicht mit Skype for Business-Benutzern interagieren oder mit Benutzern in Verbundorganisationen kommunizieren. Um diese Funktionalität in Teams freizuschalten, müssen diese Benutzer von der lokalen Skype for Business-Umgebung in die Cloud verschoben werden, und dies erfordert die Konfiguration des Skype for Business-Hybridmodus. Außerdem sollten sich diese Benutzer zur bestmöglichen Benutzererfahrung im Modus "Nur Teams" befinden, der sicherstellt, dass alle eingehenden Anrufe und Chats von jedem Benutzer im Teams-Client des Benutzers landen.

Außerdem müssen Sie die Hybridkonnektivität einrichten und alle Benutzer in die Cloud verschieben, bevor Sie Ihre lokale Skype for Business-Bereitstellung außer Betrieb nehmen.  Sobald die Hybridkonnektivität eingerichtet ist, können Sie Ihre Benutzer entsprechend Ihres Zeitplans und Ihrer geschäftlichen Anforderungen in die Cloud verschieben. Bei der direkten Weiterleitung können Sie Ihre lokale Sprachinfrastruktur nutzen, sowohl während Sie in die Cloud verschieben als auch nach Abschluss der Migration.

In diesem Thema werden die Infrastruktur- und Systemanforderungen beschrieben, die Sie zum Konfigurieren der Hybridkonnektivität zwischen Ihrer vorhandenen lokalen Skype for Business Server-Bereitstellung und Teams oder Skype for Business Online benötigen.

Nachdem Sie dieses Thema gelesen haben und die Hybridkonnektivität konfigurieren können, lesen Sie Konfigurieren der Hybridkonnektivität zwischen Skype for Business Server und [Microsoft 365 oder Office 365](configure-hybrid-connectivity.md). Die Konfigurationsthemen bieten schrittweise Anleitungen zum Einrichten einer Hybridkonnektivität zwischen Ihrer lokalen Bereitstellung und Teams oder Skype for Business Online.

> [!Important]
> Skype for Business Online wird am 31. Juli 2021 eingestellt, nachdem der Zugriff auf den Dienst nicht mehr möglich ist.  Darüber hinaus wird die PSTN-Verbindung zwischen Ihrer lokalen Umgebung über Skype for Business Server oder Cloud Connector Edition und Skype for Business Online nicht mehr unterstützt.  Erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mithilfe von Direct Routing mit Teams [verbinden.](/MicrosoftTeams/direct-routing-landing-page)

## <a name="about-shared-sip-address-space-functionality"></a>Informationen zur Funktionalität des freigegebenen SIP-Adressraums

<a name="BKMK_Overview"> </a>

 Durch die Einrichtung einer Hybridkonnektivität zwischen einer lokalen Bereitstellung von Skype for Business Server und Teams oder Skype for Business Online können einige Benutzer lokal und einige Benutzer online als homed festgelegt werden.

Diese Art von Konfiguration basiert auf der Funktionalität des gemeinsam genutzten SIP-Adressraums und wird manchmal als "geteilte Domäne" bezeichnet. Dies bedeutet, dass Benutzer einer Domäne, z. B. contoso.com, zwischen der lokalen Verwendung von Skype for Business Server und Teams oder Skype for Business Online aufgeteilt werden, wie im folgenden Diagramm dargestellt:

![Skype for Business Hybrid-Konnektivität – geteilte Domäne](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

Wenn freigegebener SIP-Adressraum konfiguriert ist:

- Azure Active Directory Connect wird verwendet, um Ihr lokales Verzeichnis mit Microsoft 365 oder Office 365 zu synchronisieren.
- Lokale Benutzer interagieren mit lokalen Skype for Business-Servern.
- Benutzer, die online zu Hause sind, können mit Skype for Business Online- oder Teams-Diensten interagieren.
- Benutzer aus beiden Umgebungen können miteinander kommunizieren.
- Das lokale Active Directory ist autorisierend. Alle Benutzer sollten zuerst im lokalen Active Directory erstellt und dann mit Azure AD synchronisiert werden. Auch wenn Sie beabsichtigen, dass der Benutzer online zu Hause ist, müssen Sie den Benutzer zunächst in der lokalen Umgebung erstellen und dann ins Internet verschieben, um sicherzustellen, dass der Benutzer von lokalen Benutzern ermittelt werden kann.

Bevor ein Benutzer online verschoben werden kann, muss dem Benutzer eine Skype for Business Online (Plan 2)-Lizenz zugewiesen werden. Wenn der Benutzer Teams verwendet, muss dem Benutzer auch eine Teams-Lizenz zugewiesen werden (und die Skype for Business-Lizenz muss aktiviert bleiben). Wenn Ihre Benutzer zusätzliche Onlinefeatures wie Audiokonferenzen oder Telefonsystem nutzen möchten, müssen Sie ihnen die entsprechende Lizenz in Microsoft 365 oder Office 365 zuweisen.

## <a name="hybrid-connectivity-infrastructure-requirements"></a>Anforderungen an die Hybridkonnektivitätsinfrastruktur

<a name="BKMK_Infrastructure"> </a>

Zum Implementieren der Hybridkonnektivität zwischen Ihrer lokalen Umgebung und Microsoft 365- oder Office 365-Kommunikationsdiensten müssen Sie die folgenden Infrastrukturanforderungen erfüllen:

- Eine einzelne lokale Bereitstellung von Skype for Business Server oder Lync Server, die in einer unterstützten Topologie bereitgestellt wird. Weitere Informationen finden Sie unter [Topologieanforderungen](plan-hybrid-connectivity.md#BKMK_Topology) in diesem Thema.

- Eine Microsoft 365- oder Office 365-Organisation mit aktivierter Skype for Business Online-Funktion.
    > [!NOTE]
    > Sie können nur einen einzelnen Mandanten für eine Hybridkonfiguration mit Ihrer lokalen Bereitstellung verwenden.
    
- Azure Active Directory Connect zum Synchronisieren Ihres lokalen Verzeichnisses mit Microsoft 365 oder Office 365. Weitere Informationen finden Sie unter [Azure AD Connect: Konten und Berechtigungen](/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions).

- Skype for Business Server-Verwaltungstools. Diese sind erforderlich, um Benutzer von der lokalen in die Cloud zu verschieben. Diese Tools müssen auf einem Server mit Zugriff auf die lokale Bereitstellung und das Internet installiert werden.
- Online-Verwaltungstools. Sie können entweder das Teams Admin Center oder Windows PowerShell Teams und Skype for Business Online verwalten. Um PowerShell zum Verwalten von Teams oder Skype for Business Online zu verwenden, laden Sie den Skype for Business Online Connector herunter und installieren diesen.
- Freigegebener SIP-Adressraum muss aktiviert sein, und Ihre lokale Bereitstellung muss für die Verwendung von Microsoft 365 oder Office 365 als Hostinganbieter konfiguriert sein. Weitere Informationen zu den schritten, die zum Konfigurieren der Hybridkonnektivität erforderlich sind, finden Sie unter [Configure hybrid connectivity](configure-hybrid-connectivity.md).

Nachdem Sie die Hybridkonnektivität konfiguriert haben, können Sie Benutzer zu Teams oder Skype for Business Online verschieben. Weitere Informationen finden Sie unter [Move users from on-premises to Teams](move-users-from-on-premises-to-teams.md) and Move users from on premises to Skype for Business [Online](move-users-from-on-premises-to-skype-for-business-online.md).

## <a name="server-version-requirements"></a>Serverversionsanforderungen

<a name="BKMK_Topology"> </a>

Um Ihre Bereitstellung für die Hybridbereitstellung mit Teams oder **Skype for Business Online** zu konfigurieren, benötigen Sie eine der folgenden unterstützten Topologien:

- Eine Skype for Business Server 2019-Bereitstellung mit allen Servern, auf denen Skype for Business Server 2019 ausgeführt wird.
- Eine Skype for Business Server 2015-Bereitstellung mit allen Servern, auf denen Skype for Business Server 2015 ausgeführt wird.
- Eine Lync Server 2013-Bereitstellung mit allen Servern mit Lync Server 2013.  Wenn jedoch hybride Sprachverbindungen erforderlich sind, müssen Sie eine Topologie mit gemischten Versionen verwenden, wie unten erwähnt.
- Eine Bereitstellung mit maximal 2 verschiedenen Serverversionen wie unten aufgeführt:
  - Skype for Business Server 2015 und Skype for Business Server 2019
  - Lync Server 2013 und Skype for Business Server 2019
  - Lync Server 2013 und Skype for Business Server 2015

Wenn *hybride Sprachsteuerung in* einer beliebigen Topologie gewünscht wird, müssen sowohl der als Verbund-Edge festgelegte Edgeserver als auch der dem SIP-Verbund zugeordnete Pool Skype for Business 2015 oder höher ausführen. Benutzer können in einem Lync 2013-Pool verbleiben, sofern vorhanden. Weitere Informationen finden Sie unter [Plan Phone System with PSTN Connectivity in Skype for Business Server](../../SfbServer/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md).

Die folgenden Topologien, die **Lync Server 2010** enthalten, werden mit Skype for Business Online für Chats und Besprechungen unterstützt. Topologien, die **Lync Server 2010** enthalten, werden weder für Hybrid voice noch für Teams unterstützt.

- Eine gemischte Lync Server 2010- und Skype for Business Server 2015-Bereitstellung
- Eine gemischte Lync Server 2010- und Lync Server 2013-Bereitstellung
- Eine Lync Server 2010-Bereitstellung mit allen Servern mit Lync Server 2010 mit den neuesten kumulativen Updates.

Der Edgeserver des Verbunds und der nächste Hopserver des Verbund-Edgeservers müssen Lync Server 2010 mit den neuesten kumulativen Updates ausführen. Die Skype for Business Server 2015- oder Lync Server 2013-Verwaltungstools müssen auf mindestens einem Server oder einer Verwaltungsarbeitsstation installiert sein.

## <a name="multi-forest-support"></a>Unterstützung mehrerer Gesamtstrukturen

<a name="BKMK_MultiForest"> </a>

Microsoft unterstützt die folgenden Typen von Hybridszenarien mit mehreren Gesamtstrukturen:

- **Topologie der Ressourcen gesamtstruktur.** In dieser Art von Topologie gibt es eine Gesamtstruktur, die Skype for Business Server hostet (die Ressourcen gesamtstruktur), und es gibt eine oder mehrere zusätzliche Gesamtstrukturen, die Kontoidentitäten hosten, die auf Skype for Business Server in der Ressourcen gesamtstruktur zugreifen. Im Allgemeinen können Benutzer auf Skype for Business-Funktionen in einer anderen Gesamtstruktur zugreifen, wenn die folgenden Anforderungen erfüllt sind:
  - Benutzer werden ordnungsgemäß mit der Gesamtstruktur synchronisiert, in der Skype for Business hostet. In Hybridkonfigurationen bedeutet dies, dass Benutzer als deaktivierte Benutzerobjekte synchronisiert werden müssen.
  - Die Gesamtstruktur, in der Skype for Business hosten, muss der Gesamtstruktur vertrauen, die die Benutzer enthält.
    Weitere Informationen zu Hybridszenarien der Ressourcen gesamtstruktur finden Sie unter [Deploy a resource forest topology for hybrid Skype for Business](configure-a-multi-forest-environment-for-hybrid.md).

- **Mehrere Bereitstellungen von Skype for Business Server in mehreren Gesamtstrukturen.** Diese Konfiguration kann durch Fusions- und Übernahmeszenarien sowie in komplexeren Unternehmen entstehen. Die Konsolidierung aller Benutzer von der lokalen in die Cloud in einer einzelnen Microsoft 365- oder Office 365-Organisation kann für jede Organisation mit mehreren Skype for Business-Bereitstellungen erreicht werden, sofern die folgenden zentralen Anforderungen erfüllt sind:
  - Es muss mindestens eine Microsoft 365- oder Office 365-Organisation beteiligt sein. Die Konsolidierung in Szenarien mit mehreren Organisationen wird nicht unterstützt.
  - Zu einem bestimmten Zeitpunkt kann sich nur eine lokale Skype for Business-Gesamtstruktur im Hybridmodus befinden (freigegebener SIP-Adressraum). Alle anderen lokalen Skype for Business-Gesamtstrukturen müssen vollständig lokal bleiben (und vermutlich miteinander verbundenen). Beachten Sie, dass diese anderen lokalen Organisationen AAD bei Bedarf mit neuen Funktionen synchronisieren können, um ab Dezember 2018 verfügbare [Online-SIP-Domänen](/powershell/module/skype/disable-csonlinesipdomain) zu deaktivieren.

    Kunden mit Bereitstellungen von Skype for Business in mehreren Gesamtstrukturen müssen jede Skype for Business-Gesamtstruktur vollständig einzeln in die Microsoft 365- oder Office 365-Organisation migrieren, indem sie funktionen für die geteilte Domäne (shared SIP Address Space) verwenden, und dann die Hybridbereitstellung mit der lokalen Bereitstellung deaktivieren, bevor sie mit der nächsten lokalen Skype for Business-Bereitstellung migrieren. Darüber hinaus verbleiben lokale Benutzer vor der Migration in die Cloud im Verbundstatus mit allen Benutzern, die nicht im lokalen Verzeichnis desselben Benutzers dargestellt sind. Weitere Informationen finden Sie unter [Cloudkonsolidierung für Teams und Skype for Business](cloud-consolidation.md).

## <a name="federation-requirements"></a>Verbundanforderungen

<a name="BKMK_Federation"> </a>

Beim Konfigurieren des Skype for Business-Hybridmodus müssen Sie sicherstellen, dass Ihre lokalen und Onlineumgebungen miteinander zusammenarbeiten können.  Die Onlineumgebung verfügt standardmäßig über einen offenen Verbund. In der lokalen Umgebung ist der Verbund häufig standardmäßig geschlossen.  

Die folgenden Anforderungen müssen erfüllt sein, um eine Hybridbereitstellung erfolgreich zu konfigurieren:

- Der Domänenabgleich muss für Ihre lokale Bereitstellung und Ihre Microsoft 365- oder Office 365-Organisation identisch konfiguriert werden. Wenn die Partnerermittlung in der lokalen Bereitstellung aktiviert ist, muss der offene Partnerverbund für Ihre Onlineorganisation konfiguriert werden. Wenn die Partnerermittlung nicht aktiviert ist, muss der geschlossene Partnerverbund für Ihre Onlineorganisation konfiguriert werden.
- Die Liste blockierter Domänen in der lokalen Bereitstellung muss genau mit der Liste blockierter Domänen für Ihren Online-Mandanten übereinstimmen.
- Die Liste Zugelassene Domänen in der lokalen Bereitstellung muss genau mit der Liste zugelassener Domänen für Ihren Online-Mandanten übereinstimmen.
- Der Verbund muss für die externe Kommunikation für den Online-Mandanten aktiviert sein.

## <a name="network-considerations"></a>Überlegungen zum Netzwerk

In den folgenden Abschnitten werden Überlegungen zu folgenden Themen beschrieben:

- DNS-Einstellungen
- Überlegungen zur Firewall

### <a name="dns-settings-for-hybrid-deployments"></a>DNS-Einstellungen für Hybridbereitstellungen

<a name="BKMK_DNS"> </a>

Beim Erstellen von DNS-Einträgen für Hybridbereitstellungen sollten alle externen Skype for Business-DNS-Einträge auf die lokale Infrastruktur verweisen. Weitere Informationen zu den erforderlichen DNS-Einträgen finden Sie unter [DNS-Anforderungen für Skype for Business Server](../../sfbserver/plan-your-deployment/network-requirements/dns.md).

Darüber hinaus müssen Sie sicherstellen, dass die in der folgenden Tabelle beschriebene DNS-Auflösung in Ihrer lokalen Bereitstellung funktioniert. (Wenn Sie den Verbund bereits für lokal konfiguriert haben, verfügen Sie wahrscheinlich bereits über diese.)

|DNS-Eintrag  <br/> |Resolvable by  <br/> |DNS-Anforderung  <br/> |
|:-----|:-----|:-----|
|DNS-SRV-Eintrag für _sipfederationtls._tcp.\<sipdomain.com\> für alle unterstützten SIP-Domänen, die zu externen ACCESS Edge-IP-Adressen aufgelöst werden  <br/> |Edgeserver  <br/> |Aktivieren sie die Verbundkommunikation in einer Hybridkonfiguration. Der Edgeserver muss wissen, wo der Verbunddatenverkehr für die SIP-Domäne, die zwischen lokal und online aufgeteilt wird, umroutet werden soll.  <br/> Muss einen strikten DNS-Namensabgleich zwischen der Domäne im Benutzernamen und dem SRV-Eintrag verwenden.  <br/> |
|DNS A record(s) for Edge Web Conferencing Service FQDN, z. B. webcon.contoso.com resolving to Web Conferencing Edge external IP(s)  <br/> |Computer der verbundenen Benutzer des internen Unternehmensnetzwerks  <br/> |Ermöglichen Sie Onlinebenutzern, Inhalte in lokalen gehosteten Besprechungen anzuzeigen oder anzuzeigen. Der Inhalt umfasst PowerPoint-Dateien, Whiteboards, Umfragen und freigegebene Notizen.  <br/> |

Je nachdem, wie DNS in Ihrer Organisation konfiguriert ist, müssen Sie diese Einträge möglicherweise der internen gehosteten DNS-Zone hinzufügen, damit die entsprechenden SIP-Domänen interne DNS-Auflösung für diese Einträge bereitstellen können.

### <a name="firewall-considerations-for-hybrid-deployments"></a>Firewallüberlegungen für Hybridbereitstellungen

<a name="BKMK_Firewall"> </a>

Computer in Ihrem Netzwerk müssen in der Lage sein, standardmäßige Internet-DNS-Suchen durchzuführen. Wenn diese Computer Standard-Internetwebsites erreichen können, erfüllt Ihr Netzwerk diese Anforderung.

Je nach Standort ihres Microsoft Online Services-Rechenzentrums müssen Sie ihre Netzwerkfirewallgeräte auch so konfigurieren, dass Verbindungen basierend auf Platzhalterdomänennamen akzeptiert werden (z. B. der \* outlook.com). Wenn die Firewalls Ihrer Organisation keine Konfigurationen von Platzhalternamen unterstützen, müssen Sie die zu erlaubenden IP-Adressbereiche und die angegebenen Ports manuell bestimmen.

Weitere Informationen, einschließlich Details zu Ports und Protokollanforderungen, finden Sie unter UrLs und IP-Adressbereiche von [Microsoft 365 und Office 365.](/microsoft-365/enterprise/urls-and-ip-address-ranges)