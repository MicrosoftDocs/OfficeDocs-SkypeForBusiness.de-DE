---
title: Plan Hybrid Connect | Skype for Business Server 2019 und Microsoft 365 oder Office 365 Integration
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
description: Planungsüberlegungen für die Implementierung einer hybriden Konnektivität zwischen Skype for Business Server und Skype for Business Online oder Teams.
ms.openlocfilehash: 38c44dbbb60ed541ab3a5b830c130dcb37eb86e0
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359061"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-microsoft-365-or-office-365"></a>Planen der Hybrid Konnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365

## <a name="overview"></a>Übersicht

In diesem Thema erfahren Sie, wie Sie die hybride Konnektivität zwischen Skype for Business Server und Microsoft Teams oder Skype for Business Online planen. Das Einrichten von Hybridverbindungen ist der erste Schritt beim Migrieren Ihrer lokalen Umgebung zur Cloud.

Wenn Sie über lokale Skype for Business-Benutzer verfügen, die (parallel) auch Microsoft Teams verwenden, können diese Benutzer von ihrem Teams-Client aus nicht mit Skype for Business-Benutzern interagieren oder mit Benutzern in Verbundorganisationen kommunizieren. Um diese Funktionalität in Teams freizuschalten, müssen diese Benutzer von der lokalen Skype for Business-Umgebung in die Cloud verschoben werden, und dies erfordert die Konfiguration des Skype for Business-Hybridmodus. Darüber hinaus sollten diese Benutzer für eine optimale Benutzerfreundlichkeit im nur-Teams-Modus ausgeführt werden, sodass alle eingehenden Anrufe und Chats von beliebigen Benutzern im Team-Client des Benutzers landen.

Außerdem müssen Sie die Hybridkonnektivität einrichten und alle Benutzer in die Cloud verschieben, bevor Sie Ihre lokale Skype for Business-Bereitstellung außer Betrieb nehmen.  Sobald die Hybridkonnektivität eingerichtet ist, können Sie Ihre Benutzer entsprechend Ihres Zeitplans und Ihrer geschäftlichen Anforderungen in die Cloud verschieben. Bei der direkten Weiterleitung können Sie Ihre lokale Sprachinfrastruktur nutzen, sowohl während Sie in die Cloud verschieben als auch nach Abschluss der Migration.

In diesem Thema werden die Infrastruktur-und Systemanforderungen beschrieben, die Sie zum Konfigurieren der Hybrid Konnektivität zwischen Ihrer vorhandenen lokalen Skype for Business Server-Bereitstellung und Microsoft Teams oder Skype for Business Online benötigen.

Nachdem Sie dieses Thema gelesen und die Hybrid Konnektivität konfiguriert haben, finden Sie weitere Informationen unter [Konfigurieren der Hybrid Konnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](configure-hybrid-connectivity.md). Die Konfigurationsthemen bieten eine Schritt-für-Schritt-Anleitung zum Einrichten einer hybriden Konnektivität zwischen Ihrer lokalen Bereitstellung und Teams oder Skype for Business Online.

> [!Important]
> Skype for Business Online werden am 31. Juli 2021 zurückgezogen, nach dem der Zugriff auf den Dienst nicht mehr möglich ist.  Darüber hinaus wird die PSTN-Konnektivität zwischen Ihrer lokalen Umgebung unabhängig davon, ob über Skype for Business Server oder Cloud Connector Edition und Skype for Business Online nicht mehr unterstützt.  Hier erfahren Sie, wie Sie Ihr lokales Telefonie-Netzwerk mithilfe des [direkten Routings](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)mit Microsoft Teams verbinden.

## <a name="about-shared-sip-address-space-functionality"></a>Informationen zu freigegebenen SIP-Adressraum Funktionen

<a name="BKMK_Overview"> </a>

 Da die Hybrid Konnektivität zwischen einer lokalen Bereitstellung von Skype for Business Server und Teams oder Skype for Business Online eingerichtet ist, können einige Benutzer lokal verwaltet werden, und einige Benutzer werden online verwaltet.

Dieser Konfigurationstyp basiert auf freigegebener SIP-Adressraum Funktionalität und wird manchmal als "geteilte Domäne" bezeichnet – was bedeutet, dass Benutzer einer Domäne wie contoso.com zwischen der Verwendung von Skype for Business Server lokal und Microsoft Teams oder Skype for Business Online aufgeteilt sind, wie im folgenden Diagramm dargestellt:

![SFB-Hybrid Konnektivität – geteilte Domäne](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

Wenn der freigegebene SIP-Adressraum konfiguriert ist:

- Azure Active Directory Connect wird verwendet, um Ihr lokales Verzeichnis mit Microsoft 365 oder Office 365 zu synchronisieren.
- Benutzer, die lokal verwaltet werden, interagieren mit lokalen Skype for Business Servern.
- Benutzer, die Online verwaltet werden, können mit Skype for Business Online-oder Microsoft Teams-Diensten interagieren.
- Benutzer aus beiden Umgebungen können miteinander kommunizieren.
- Die lokale Active Directory ist autorisierend. Alle Benutzer sollten zuerst im lokalen Active Directory erstellt und dann mit Azure AD synchronisiert werden. Selbst wenn Sie beabsichtigen, dass der Benutzer online verwaltet werden soll, müssen Sie zuerst den Benutzer in der lokalen Umgebung erstellen und dann den Benutzer in Online stellen, um sicherzustellen, dass der Benutzer von lokalen Benutzern erkannt werden kann.

Bevor ein Benutzer online verschoben werden kann, muss dem Benutzer eine Skype for Business Online Lizenz (Plan 2) zugewiesen werden. Wenn der Benutzer Teams verwendet, muss dem Benutzer auch eine Microsoft Teams-Lizenz zugewiesen werden (und die Skype for Business Lizenz muss aktiviert bleiben). Wenn Ihre Benutzer zusätzliche Online Features wie Audiokonferenz oder Telefon System nutzen möchten, müssen Sie Ihnen die entsprechende Lizenz in Microsoft 365 oder Office 365 zuweisen.

## <a name="infrastructure-requirements"></a>Infrastrukturanforderungen

<a name="BKMK_Infrastructure"> </a>

Um eine hybride Verbindung zwischen Ihrer lokalen Umgebung und Microsoft 365-oder Office 365-Kommunikationsdiensten zu implementieren, müssen Sie die folgenden Infrastrukturanforderungen erfüllen:

- Eine einzelne lokale Bereitstellung von Skype for Business Server oder lync Server, die in einer unterstützten Topologie bereitgestellt wird. Siehe [Topologie-Anforderungen](plan-hybrid-connectivity.md#BKMK_Topology) in diesem Thema.

- Eine Microsoft 365-oder Office 365-Organisation mit aktivierter Skype for Business Online.
    > [!NOTE]
    > Sie können nur einen einzelnen Mandanten für eine Hybrid Konfiguration mit Ihrer lokalen Bereitstellung verwenden.
    
- Azure Active Directory Connect, um Ihr lokales Verzeichnis mit Microsoft 365 oder Office 365 zu synchronisieren. Weitere Informationen finden Sie unter [Azure AD Connect: Accounts and Permissions](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions).

- Skype for Business Server Verwaltungstools.  Diese sind erforderlich, um Benutzer von der lokalen in die Cloud zu migrieren. Diese Tools müssen auf einem Server mit Zugriff auf die lokale Bereitstellung und das Internet installiert werden.
- Online Verwaltungstools.  Sie können entweder das Teamadministrator Center oder Windows PowerShell verwenden, um Teams und Skype for Business Online zu verwalten. Wenn Sie PowerShell zum Verwalten von Teams oder Skype for Business Online verwenden möchten, laden Sie den Skype for Business Online Connector herunter, und installieren Sie ihn.
- Der freigegebene SIP-Adressraum muss aktiviert sein, und Ihre lokale Bereitstellung muss für die Verwendung von Microsoft 365 oder Office 365 als Hostinganbieter konfiguriert sein. Weitere Informationen zu den Schritten, die zum Konfigurieren von Hybrid Konnektivität erforderlich sind, finden Sie unter [configure Hybrid Connectivity](configure-hybrid-connectivity.md).

Nachdem Sie die Hybrid Konnektivität konfiguriert haben, können Sie Benutzer in Teams oder Skype for Business Online migrieren. Weitere Informationen finden Sie unter [Migrieren von Benutzern von lokalen zu Teams](move-users-from-on-premises-to-teams.md) und [Migrieren von Benutzern von lokal in Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md).

## <a name="server-version-requirements"></a>Server Versionsanforderungen

<a name="BKMK_Topology"> </a>

Wenn Sie Ihre Bereitstellung für eine hybridbereitstellung mit **Teams oder Skype for Business Online**konfigurieren möchten, müssen Sie über eine der folgenden unterstützten Topologien verfügen:

- Eine Skype for Business Server 2019-Bereitstellung mit allen Servern, auf denen Skype for Business Server 2019 ausgeführt wird.
- Eine Skype for Business Server 2015-Bereitstellung mit allen Servern, auf denen Skype for Business Server 2015 ausgeführt wird.
- Eine lync Server 2013 Bereitstellung mit allen Servern, auf denen lync Server 2013 läuft.  Wenn jedoch eine hybride VoIP-Konnektivität erforderlich ist, müssen Sie eine Topologie mit gemischten Versionen wie unten beschrieben verwenden.
- Eine Bereitstellung mit maximal 2 verschiedenen Server Versionen, wie unten aufgeführt:
  - Skype for Business Server 2015 und Skype for Business Server 2019
  - Lync Server 2013 und Skype for Business Server 2019
  - Lync Server 2013 und Skype for Business Server 2015

*Wenn Hybrid-VoIP in einer beliebigen Topologie gewünscht wird*, muss sowohl der Edgeserver als Verbund Edge als auch der mit dem SIP-Partnerverbund verknüpfte Pool Skype for Business 2015 oder höher installiert sein. Benutzer können in einem lync 2013 Pool verbleiben, falls vorhanden. Weitere Informationen finden Sie unter [Plan Phone System with PSTN Connectivity in Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity).

Die folgenden Topologien, die **lync Server 2010 umfassen, werden mit Skype for Business Online** für Chatnachrichten und Besprechungen unterstützt.  Topologien, die **lync Server 2010 enthalten, werden für Hybrid-VoIP und-Teams nicht unterstützt**.

- Eine gemischte lync Server 2010-und Skype for Business Server 2015-Bereitstellung
- Eine gemischte lync Server 2010-und lync Server 2013-Bereitstellung
- Eine lync Server 2010 Bereitstellung mit allen Servern, auf denen lync Server 2010 mit den neuesten kumulativen Updates läuft.

Der Verbund Edgeserver und der Server für den nächsten Hop aus dem Verbund Edgeserver müssen lync Server 2010 mit den neuesten kumulativen Updates laufen. Die Skype for Business Server 2015-oder lync Server 2013-Verwaltungs Tools müssen auf mindestens einem Server oder einer Verwaltungsarbeitsstation installiert sein.

## <a name="multi-forest-support"></a>Unterstützung mehrerer Gesamtstrukturen

<a name="BKMK_MultiForest"> </a>

Microsoft unterstützt die folgenden Typen von Hybrid Szenarien mit mehreren Gesamtstrukturen:

- **Ressourcengesamtstruktur-Topologie.** In dieser Art von Topologie gibt es eine Gesamtstruktur, in der Skype for Business Server (die Ressourcengesamtstruktur) gehostet wird, und es gibt eine oder mehrere zusätzliche Gesamtstrukturen, die Konto Identitäten hosten, die auf die Skype for Business Server in der Ressourcengesamtstruktur zugreifen. Im Allgemeinen können Benutzer auf Skype for Business Funktionalität in einer anderen Gesamtstruktur zugreifen, wenn die folgenden Anforderungen erfüllt sind:
  - Benutzer werden ordnungsgemäß mit der Gesamtstruktur synchronisiert, die Skype for Business hostet. In Hybridkonfigurationen bedeutet dies, dass Benutzer als deaktivierte Benutzerobjekte synchronisiert werden müssen.
  - Die Gesamtstruktur-Host Skype for Business muss der Gesamtstruktur vertrauen, die die Benutzer enthält.
    Ausführliche Informationen zu Hybrid Szenarien für die Ressourcengesamtstruktur finden Sie unter [Deploy a Resource Forest Topology for Hybrid Skype for Business](configure-a-multi-forest-environment-for-hybrid.md).

- **Mehrere Bereitstellungen von Skype for Business Server in mehreren Gesamtstrukturen.** Diese Konfiguration kann infolge von Fusions-und Akquisitions Szenarien sowie in komplexeren Unternehmen auftreten. Die Konsolidierung aller Benutzer von lokal in der Cloud in einer einzelnen Microsoft 365-oder Office 365-Organisation kann für jede Organisation mit mehreren Skype for Business-Bereitstellungen erreicht werden, vorausgesetzt, dass die folgenden Hauptanforderungen erfüllt sind:
  - Es muss höchstens eine Microsoft 365-oder Office 365-Organisation beteiligt sein. Die Konsolidierung in Szenarien mit mehr als einer Organisation wird nicht unterstützt.
  - Zu einem bestimmten Zeitpunkt kann sich nur eine lokale Skype for Business Gesamtstruktur im Hybrid Modus befinden (freigegebener SIP-Adressraum). Alle anderen lokalen Skype for Business Gesamtstrukturen müssen vollständig lokal (und vermutlich miteinander verbunden) bleiben. Beachten Sie, dass diese anderen lokalen Organisationen mit Aad, falls gewünscht, mit [neuen Funktionen synchronisiert werden können, um Online-SIP-Domänen zu deaktivieren](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain) , die ab Dezember 2018 verfügbar sind.

    Kunden mit Bereitstellungen von Skype for Business in mehreren Gesamtstrukturen müssen jede Skype for Business Gesamtstruktur einzeln in die Microsoft 365-oder Office 365-Organisation mithilfe von Split-Domain-Funktionen (Shared SIP Address Space) migrieren und anschließend die hybridbereitstellung mit der lokalen Bereitstellung deaktivieren, bevor Sie mit der Migration der nächsten lokalen Skype for Business-Bereitstellung fortfahren. Darüber hinaus verbleiben lokale Benutzer vor der Migration in die Cloud in einem Verbund Staat mit allen Benutzern, die nicht im lokalen Verzeichnis des Benutzers dargestellt werden. Weitere Informationen finden Sie unter [Cloud Consolidation for Teams and Skype for Business](cloud-consolidation.md).

## <a name="federation-requirements"></a>Verbund Anforderungen

<a name="BKMK_Federation"> </a>

Wenn Sie Hybrid konfigurieren, müssen Sie sicherstellen, dass Ihre lokalen und Online-Umgebungen miteinander verbündet werden können.  Die Online Umgebung hat standardmäßig einen offenen Verbund; die lokale Umgebung verfügt häufig standardmäßig über einen geschlossenen Partnerverbund.  

Die folgenden Anforderungen müssen erfüllt sein, um eine hybridbereitstellung erfolgreich zu konfigurieren:

- Domänen Abgleich muss für Ihre lokale Bereitstellung und Ihre Microsoft 365-oder Office 365-Organisation identisch konfiguriert werden. Wenn die Partner Ermittlung für die lokale Bereitstellung aktiviert ist, muss Open Federation für Ihre Online Organisation konfiguriert sein. Wenn die Partner Ermittlung nicht aktiviert ist, muss Closed Federation für Ihre Online Organisation konfiguriert werden.
- Die Liste blockierter Domänen in der lokalen Bereitstellung muss genau mit der Liste der blockierten Domänen für den Online Mandanten übereinstimmen.
- Die Liste der zugelassenen Domänen in der lokalen Bereitstellung muss genau mit der Liste der zugelassenen Domänen für den Online Mandanten übereinstimmen.
- Der Partnerverbund muss für die externe Kommunikation für den Online Mandanten aktiviert sein.

## <a name="network-considerations"></a>Überlegungen zum Netzwerk

In den folgenden Abschnitten werden Überlegungen für Folgendes beschrieben:

- DNS-Einstellungen
- Überlegungen zur Firewall

### <a name="dns-settings"></a>DNS-Einstellungen

<a name="BKMK_DNS"> </a>

Beim Erstellen von DNS-Einträgen für hybridbereitstellungen sollten alle Skype for Business externen DNS-Einträge auf die lokale Infrastruktur hinweisen. Ausführliche Informationen zu den erforderlichen DNS-Einträgen finden Sie unter [DNS Requirements for Skype for Business Server](../../sfbserver/plan-your-deployment/network-requirements/dns.md).

Darüber hinaus müssen Sie sicherstellen, dass die in der folgenden Tabelle beschriebene DNS-Auflösung in Ihrer lokalen Bereitstellung funktioniert. (Wenn Sie den Verbund bereits für die lokale Konfiguration konfiguriert haben, verfügen Sie wahrscheinlich bereits über diese.)

|DNS-Eintrag  <br/> |Auflösbar durch  <br/> |DNS-Anforderung  <br/> |
|:-----|:-----|:-----|
|DNS-SRV-Eintrag für _sipfederationtls. _tcp.\<sipdomain.com\> für alle unterstützten SIP-Domänen, die auf Edge-externe IP (s) zugreifen  <br/> |Edgeserver (s)  <br/> |Aktivieren Sie die Verbundkommunikation in einer Hybrid Konfiguration. Die Edgeserver müssen wissen, wo der Verbunddatenverkehr für die SIP-Domäne, die zwischen lokal und Online aufgeteilt ist, weitergeleitet werden soll.  <br/> Es muss strikte DNS-Namensübereinstimmung zwischen der Domäne im Benutzernamen und dem SRV-Eintrag verwendet werden.  <br/> |
|DNS-A-Einträge für den FQDN des Edge-Webkonferenz Diensts, beispielsweise webcon.contoso.com auflösen in Webkonferenz-Edge-externe IP (s)  <br/> |Interne Unternehmensnetzwerk verbundene Benutzer Computer  <br/> |Ermöglichen Sie Online-Benutzern das präsentieren oder Anzeigen von Inhalten in lokalen gehosteten Besprechungen. Der Inhalt enthält PowerPoint-Dateien, Whiteboards, Umfragen und freigegebene Notizen.  <br/> |

Je nachdem, wie DNS in Ihrer Organisation konfiguriert ist, müssen Sie diese Einträge möglicherweise der internen gehosteten DNS-Zone für die entsprechenden SIP-Domänen hinzufügen, um die interne DNS-Auflösung für diese Einträge bereitzustellen.

### <a name="firewall-considerations"></a>Überlegungen zur Firewall

<a name="BKMK_Firewall"> </a>

Computer in Ihrem Netzwerk müssen in der Lage sein, standardmäßige Internet-DNS-Lookups durchzuführen. Wenn diese Computer Standard-Internetwebsites erreichen können, erfüllt Ihr Netzwerk diese Anforderung.

Je nach Speicherort Ihres Microsoft Online Services-Rechenzentrums müssen Sie auch die Netzwerkfirewall-Geräte so konfigurieren, dass Verbindungen basierend auf Platzhalterdomänen Namen akzeptiert werden (beispielsweise der gesamte Datenverkehr von \* . Outlook.com). Wenn die Firewalls Ihrer Organisation keine Platzhalternamen Konfigurationen unterstützen, müssen Sie die IP-Adressbereiche, die Sie zulassen möchten, und die angegebenen Ports manuell bestimmen.

Weitere Informationen, einschließlich Details zu Ports und Protokollanforderungen, finden Sie unter [Microsoft 365-und Office 365-URLs und IP-Adressbereiche](https://go.microsoft.com/fwlink/p/?LinkId=252942).
