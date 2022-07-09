---
title: Planen der hybriden Konnektivität | Skype for Business Server und Teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
search.appverid: MET150
description: Planen Sie die Implementierung einer Hybridkonnektivität zwischen Skype for Business Server und Teams, indem Sie Skype for Business Hybridmodus konfigurieren.
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: a73b14a3642a216ff9cbbe919b586979aabf6a81
ms.sourcegitcommit: 15ec17eff4ad4c962d00b8683513f9b269d82917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2022
ms.locfileid: "66695048"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>Planen der Hybridverbindung zwischen Skype for Business Server und Teams

> [!Important]
> Obwohl Skype for Business Online seit 2021 eingestellt wurde, werden die lokalen Produkte Skype for Business Server 2019, Skype for Business Server 2015 und Lync Server 2013 weiterhin unterstützt. Darüber hinaus unterstützt Microsoft Hybridumgebungen zwischen diesen lokalen Produkten und Microsoft Teams. Auf diese Weise können Organisationen mit diesen lokalen Bereitstellungen ihre Benutzer zu TeamsOnly migrieren.  Schließlich wird die Cloud Connector Edition von Skype for Business Server nicht mehr unterstützt. Kunden, die eine lokale PSTN-Konnektivität benötigen, sollten [Direct Routing](/MicrosoftTeams/direct-routing-landing-page) verwenden.


In diesem Thema erfahren Sie, wie Sie die Hybridkonnektivität zwischen Skype for Business Server oder Lync Server 2013 und Teams planen. Das Einrichten der Hybridkonnektivität ist der erste Schritt bei der Umstellung Ihrer lokalen Umgebung auf eine reine Microsoft Teams-Umgebung in der Cloud.

Bei einer lokalen Bereitstellung von Skype for Business Server können Benutzer von Skype for Business auch Teams verwenden, aber nicht alle Teams-Funktionen stehen benutzern zur Verfügung, solange sie für die Verwendung der lokalen Skype for Business Server-Bereitstellung konfiguriert sind. Diese Benutzer werden als lokal "verwaltet" bezeichnet, und bestimmte Teams-Funktionen sind nicht verfügbar, während diese Benutzer lokal verwaltet werden, z. B.:

- Verbundanrufe und Chats über den Teams-Client des Benutzers mit Benutzern in anderen Organisationen sind nicht verfügbar.
- Interopkommunikation über den Teams-Client des Benutzers mit anderen Benutzern in der Organisation, die Skype for Business Client verwenden.
- PSTN-Anruffunktion (wenn dem Benutzer eine Telefonsystemlizenz zugewiesen ist).

Um vollständige Teams-Funktionen zu erhalten, müssen diese Benutzer von Skype for Business lokal in die Cloud verschoben werden, wodurch der Benutzer zu TeamsOnly wird. Durch das Verschieben eines Benutzers aus der lokalen Umgebung in die Cloud wird der Koexistenzmodus des Benutzers auf TeamsOnly festgelegt. Sobald Benutzer in die Cloud und TeamsOnly verschoben wurden, werden alle eingehenden Chats und Anrufe in ihrem Teams-Client angezeigt (im Gegensatz zur parallelen Verwendung von Teams).  Weitere Informationen finden Sie unter [Teams-Koexistenz mit Skype for Business sowie Anleitungen zur Migration](/microsoftteams/coexistence-chat-calls-presence) und [Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](/microsoftteams/migration-interop-guidance-for-teams-with-skype).

Das Verschieben von Benutzern zwischen der lokalen Umgebung und TeamsOnly in der Cloud erfordert die Konfiguration Skype for Business Hybridmodus. Darüber hinaus verschieben Sie vor der Außerbetriebnahme Ihrer lokalen Skype for Business Bereitstellung alle Benutzer von der lokalen in die Cloud.   Sobald die Hybridkonnektivität eingerichtet ist, können Sie Ihre Benutzer entsprechend Ihres Zeitplans und Ihrer geschäftlichen Anforderungen in die Cloud verschieben.  Bei der direkten Weiterleitung können Sie Ihre lokale Sprachinfrastruktur nutzen, sowohl während Sie in die Cloud verschieben als auch nach Abschluss der Migration.

In diesem Thema werden die Infrastruktur- und Systemanforderungen beschrieben, die Sie zum Konfigurieren der Hybridverbindung zwischen Ihrer vorhandenen lokalen Skype for Business Server-Bereitstellung und Teams benötigen.

Nachdem Sie dieses Thema gelesen haben und bereit zum Konfigurieren der Hybridkonnektivität sind, lesen [Sie "Konfigurieren der Hybridkonnektivität zwischen Skype for Business Server und Teams](configure-hybrid-connectivity.md)". Die Konfigurationsthemen bieten schrittweise Anleitungen zum Einrichten der Hybridkonnektivität zwischen Ihrer lokalen Bereitstellung und Teams.


## <a name="implications-of-the-retirement-of-skype-for-business-online"></a>Auswirkungen der Einstellung von Skype for Business Online
Es ist wichtig, daran zu denken, dass sowohl vor als auch nach der Einstellung von Skype for Business Online Benutzer, die in Skype for Business Server lokal verwaltet werden, Teams verwenden können, aber nicht TeamsOnly sein können. (Lokale Benutzer befinden sich standardmäßig im Inselmodus und werden jedem anderen Modus als TeamsOnly zugewiesen). Benutzer können nur die vollen Vorteile von Teams, insbesondere des Partnerverbunds, des PSTN-Supports, nutzen und sicher sein, dass alle eingehenden Chats und Anrufe in Teams landen, sobald sie sich im TeamsOnly-Modus befinden. 

Die Einstellung von Skype for Business Online hat keine Auswirkungen auf den bestehenden Supportlebenszyklus von Skype for Business Server oder Lync Server 2013.  Die Einstellung von Skype for Business Online wirkte sich jedoch auf bestimmte Aspekte aus, **wie** Benutzer in Organisationen mit lokalen Skype for Business Server oder Lync Server 2013 zu *TeamsOnly werden*, einschließlich vorhandener Hybridorganisationen. Die Verwendung von Hybrid als Voraussetzung für den Übergang von der lokalen zur Cloud (z. B. TeamsOnly) bleibt unverändert.

Vor der Einstellung von Skype for Business Online könnten Hybridorganisationen aus drei grundlegenden Typen von Benutzern bestehen: 
- Lokale Benutzer (die Teams verwenden können oder nicht, aber nicht im Modus "Nur Teams") 
- Onlinebenutzer mit einem anderen Koexistenzmodus als TeamsOnly
- TeamsOnly-Benutzer.

Nach der Einstellung von Skype for Business Online können Hybridorganisationen jedoch nur noch aus zwei grundlegenden Benutzertypen bestehen: 
- Lokale Benutzer (Wer darf Teams verwenden, aber nicht im TeamsOnly-Modus)
- Nur Teams-Benutzer. 

Damit Organisationen von Skype for Business Server oder Lync Server 2013 zu Teams wechseln können, müssen sie die Hybridbereitstellung weiterhin mit demselben Toolset einrichten und konfigurieren, *genau wie vor der Einstellung*. Beim Verschieben eines Benutzers von der lokalen Umgebung zu TeamsOnly ist es nicht mehr erforderlich, den `-MoveToTeams` Schalter in `Move-CsUser`anzugeben. Wenn diese Option zuvor nicht angegeben wurde, wurden Benutzer von Skype for Business Server lokal zu Skype for Business Online umgestellt, und ihr Modus blieb unverändert. Da Skype Business Online jedoch eingestellt wurde, weist das Verschieben eines Benutzers aus der lokalen Umgebung in die Cloud `Move-CsUser` *automatisch* den TeamsOnly-Modus zu und initiiert die Konvertierung seiner Besprechungen von lokalen zu Teams-Besprechungen, unabhängig davon, ob der `-MoveToTeams` Wechsel angegeben ist. Dies bedeutet auch, dass Organisationen mit Lync Server 2013, die noch nie über den `MoveToTeams` Wechsel verfügten, Benutzer direkt von lokal zu TeamsOnly verschieben können. 

Wenn ein neuer Benutzer direkt in Microsoft 365 und nicht lokal erstellt wird, verfügt dieser Benutzer unabhängig vom Mandantenmodus automatisch über den Modus "Nur Teams". Beachten Sie, dass in einer Hybridorganisation mit mindestens einem lokalen Benutzer neue Benutzer im lokales Active Directory erstellt (und dann mit Microsoft 365 synchronisiert) werden sollten, anstatt direkt einen Benutzer in Microsoft 365 zu erstellen, um sicherzustellen, dass lokale Benutzer an den neuen Benutzer weitergeleitet werden können, *auch wenn Sie beabsichtigen, dass der neue Benutzer ein Cloudbenutzer ist*. Nachdem sie im lokalen Verzeichnis erstellt wurden, müssen diese neuen Benutzer *in der lokalen* Skype for Business Bereitstellung sipfähig sein und dann bei Bedarf in die Cloud verschoben werden, um TeamsOnly zu werden. 

Koexistenzmodi bestehen nach der Einstellung von Skype for Business Online weiterhin. Wie zuvor können Benutzern mit Konten, die in Skype for Business Server lokal verwaltet werden, alle Koexistenzmodus mit Ausnahme von TeamsOnly zugewiesen werden. Nach der Einstellung können Benutzer, die online verwaltet werden, nur TeamsOnly sein. Es ist nicht mehr möglich, einem Benutzer, der online verwaltet wird, einen anderen Modus als TeamsOnly zuzuweisen.


> [!Important]
> Vorhandene Hybridorganisationen mit Benutzern in Skype for Business Online, die NICHT TeamsOnly sind, sollten sich so schnell wie möglich auf das Upgrade dieser Benutzer auf den Modus "Nur Teams" konzentrieren. Wenn In Ihrer Organisation weiterhin Benutzer in Skype for Business *Online* verwaltet werden, die nicht TeamsOnly sind, wird ein Von Microsoft unterstütztes Upgrade geplant, um diese Benutzer auf TeamsOnly umzustellen. **Von Microsoft unterstützte Upgrades wirken sich nicht auf Benutzer aus, die in Skype for Business Server lokal verwaltet werden.** Terminplanungsbenachrichtigungen werden vorab an Hybridkunden mit Benutzern gesendet, die in Skype for Business Online verwaltet werden, bevor diese Onlinebenutzer, die keine TeamsOnly-Benutzer sind, auf Teams aktualisiert werden.

## <a name="about-shared-sip-address-space-functionality"></a>Informationen zur Funktion "Freigegebener SIP-Adressraum"

<a name="BKMK_Overview"> </a>

Mit hybrider Konnektivität, die zwischen einer lokalen Bereitstellung von Skype for Business Server und Teams eingerichtet ist, können Einige Benutzer lokal verwaltet und einige Benutzer online verwaltet werden.

Diese Art von Konfiguration basiert auf der Funktion des gemeinsam genutzten SIP-Adressraums und wird manchmal als "geteilte Domäne" bezeichnet, d. h. Benutzer einer Domäne, z. B. contoso.com, werden zwischen der Verwendung Skype for Business Server lokal und Teams aufgeteilt, wie im folgenden Diagramm dargestellt:

![Skype for Business Hybrid-Konnektivität – geteilte Domäne.](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

Wenn freigegebener SIP-Adressraum konfiguriert ist:

- Azure Active Directory Connect wird verwendet, um Ihr lokales Verzeichnis mit Microsoft 365 zu synchronisieren.
- Benutzer, die lokal verwaltet werden, interagieren mit lokalen Skype for Business Servern.
- Benutzer, die online verwaltet werden, interagieren mit Teams.
- Benutzer aus beiden Umgebungen können miteinander kommunizieren.
- Die lokales Active Directory ist autoritativ. Alle Benutzer sollten zuerst im lokales Active Directory erstellt und dann mit Azure AD synchronisiert werden. Auch wenn Sie beabsichtigen, dass der Benutzer online verwaltet wird, müssen Sie zuerst den Benutzer in der lokalen Umgebung erstellen und den Benutzer dann in die Onlineumgebung verschieben, um sicherzustellen, dass der Benutzer von lokalen Benutzern erkannt wird.

Bevor ein Benutzer online verschoben werden kann, muss dem Benutzer eine Teams-Lizenz sowie Skype for Business Online (Plan 2) zugewiesen werden. **Die Zuweisung der Skype for Business Online-Lizenz ist auch nach der Einstellung von Skype for Business Online erforderlich.** Wenn Ihre Benutzer zusätzliche Onlinefeatures wie Audiokonferenzen oder Telefonsystem nutzen möchten, müssen Sie ihnen die entsprechende Lizenz in Microsoft 365 zuweisen.

## <a name="hybrid-connectivity-infrastructure-requirements"></a>Anforderungen an die Hybridverbindungsinfrastruktur

<a name="BKMK_Infrastructure"> </a>

Um eine Hybridverbindung zwischen Ihrer lokalen Umgebung und Microsoft 365-Kommunikationsdiensten zu implementieren, müssen Sie die folgenden Infrastrukturanforderungen erfüllen:

- Eine einzelne lokale Bereitstellung von Skype for Business Server oder Lync Server, die in einer unterstützten Topologie bereitgestellt wird. Siehe [Topologieanforderungen](plan-hybrid-connectivity.md#BKMK_Topology) in diesem Thema.

- Eine Microsoft 365-Organisation mit Teams.
    > [!NOTE]
    > Sie können nur einen einzelnen Mandanten für eine Hybridkonfiguration mit Ihrer lokalen Bereitstellung verwenden.
    
- Azure Active Directory Connect zum Synchronisieren Ihres lokalen Verzeichnisses mit Microsoft 365. Weitere Informationen finden Sie unter [Azure AD Connect: Konten und Berechtigungen](/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions).

- Skype for Business Server Verwaltungstools. Diese sind erforderlich, um Benutzer aus der lokalen Umgebung in die Cloud zu verschieben. Diese Tools müssen auf einem Server mit Zugriff auf die lokale Bereitstellung und das Internet installiert werden.
- Online-Verwaltungstools. Sie können entweder das Teams Admin Center oder Windows PowerShell verwenden, um Teams zu verwalten. Um PowerShell zum Verwalten von Teams zu verwenden, laden Sie das Microsoft Teams PowerShell-Modul herunter, und installieren Sie es. (Der Skype for Business Online Connector wurde eingestellt).
- Der freigegebene SIP-Adressraum muss aktiviert sein, und Ihre lokale Bereitstellung muss so konfiguriert sein, dass Microsoft 365 als Hostinganbieter verwendet wird. Weitere Informationen zu den Erforderlichen Schritten zum Konfigurieren der Hybridkonnektivität finden [Sie unter Konfigurieren der Hybridkonnektivität](configure-hybrid-connectivity.md).

Nachdem Sie die Hybridkonnektivität konfiguriert haben, können Sie Benutzer nach Teams verschieben. Weitere Informationen finden Sie unter ["Verschieben von Benutzern aus der lokalen Umgebung zu Teams](move-users-from-on-premises-to-teams.md)".

## <a name="server-version-requirements"></a>Serverversionsanforderungen

<a name="BKMK_Topology"> </a>

Um Ihre Bereitstellung für die Hybridbereitstellung mit **Teams** zu konfigurieren, benötigen Sie eine der folgenden unterstützten Topologien:

- Eine Skype for Business Server 2019-Bereitstellung mit allen Servern, auf denen Skype for Business Server 2019 ausgeführt wird.
- Eine Skype for Business Server 2015-Bereitstellung mit allen Servern, auf denen Skype for Business Server 2015 ausgeführt wird.
- Eine Lync Server 2013-Bereitstellung mit allen Servern, auf denen Lync Server 2013 ausgeführt wird.  Wenn jedoch hybride Sprachkonnektivität erforderlich ist, müssen Sie eine Topologie mit gemischten Versionen verwenden, wie unten beschrieben.
- Eine Bereitstellung mit maximal 2 verschiedenen Serverversionen, wie unten aufgeführt:
  - Skype for Business Server 2015 und Skype for Business Server 2019
  - Lync Server 2013 und Skype for Business Server 2019
  - Lync Server 2013 und Skype for Business Server 2015
- Zum Verschieben von Benutzern zwischen einer lokalen Bereitstellung und der Cloud müssen Sie ab dem 31. Juli 2022 die folgenden Mindestversionen von Skype for Business Server oder Lync Server verwenden:
</br>

|Lokales Produkt|Erforderliche Mindestversion|Erforderlicher Mindestbuild|
|---|---|---|
|Skype for Business Server 2019| CU6 |7.0.2046.385|
|Skype for Business Server 2015| CU12|6.0.9319.619|
|Lync Server 2013| CU10 mit Hotfix 7|5.0.8308.1182|

</br>

> [!NOTE] 
> Lync Server 2010 wird von Teams nicht unterstützt.


## <a name="multi-forest-support"></a>Unterstützung mehrerer Gesamtstrukturen

<a name="BKMK_MultiForest"> </a>

Microsoft unterstützt die folgenden Arten von Hybridszenarien mit mehreren Gesamtstrukturen:

- **Topologie der Ressourcengesamtstruktur.** In dieser Art von Topologie gibt es eine Gesamtstruktur, die Skype for Business Server (die Ressourcengesamtstruktur) hostet, und es gibt eine oder mehrere zusätzliche Gesamtstrukturen, die Kontoidentitäten hosten, die auf die Skype for Business Server in der Ressourcengesamtstruktur zugreifen. Im Allgemeinen können Benutzer auf Skype for Business-Funktionen in einer anderen Gesamtstruktur zugreifen, wenn die folgenden Anforderungen erfüllt sind:
  - Benutzer werden ordnungsgemäß mit der Gesamtstruktur synchronisiert, die Skype for Business hostet. In Hybridkonfigurationen bedeutet dies, dass Benutzer als deaktivierte Benutzerobjekte synchronisiert werden müssen.
  - Die Gesamtstruktur, die Skype for Business hostet, muss der Gesamtstruktur vertrauen, die die Benutzer enthält.
    Ausführliche Informationen zu Hybridszenarien für die Ressourcengesamtstruktur finden [Sie unter Bereitstellen einer Ressourcengesamtstrukturtopologie für hybride Skype for Business](configure-a-multi-forest-environment-for-hybrid.md).

- **Mehrere Bereitstellungen von Skype for Business Server in mehreren Gesamtstrukturen.** Diese Konfiguration kann durch Fusions- und Akquisitionsszenarien sowie in komplexeren Unternehmen entstehen. Die Konsolidierung aller Benutzer von der lokalen zur Cloud in einer einzigen Microsoft 365-Organisation kann für jede Organisation mit mehreren Skype for Business-Bereitstellungen erreicht werden, sofern die folgenden wichtigen Anforderungen erfüllt sind:
  - Es muss höchstens eine Microsoft 365-Organisation beteiligt sein. Die Konsolidierung in Szenarien mit mehr als einer Organisation wird nicht unterstützt.
  - Zu einem bestimmten Zeitpunkt kann sich nur eine lokale Skype for Business-Umgebung im Hybrid-Modus befinden (gemeinsamer SIP-Adressraum). Alle anderen lokalen Skype for Business Wälder müssen vollständig vor Ort bleiben (und vermutlich miteinander verbunden sein). Beachten Sie, dass diese anderen lokalen Organisationen bei Bedarf mit neuen Funktionen mit AAD synchronisiert werden können, um ab Dezember 2018 verfügbare [Online-SIP-Domänen zu deaktivieren](/powershell/module/skype/disable-csonlinesipdomain) .

    Kunden mit Bereitstellungen von Skype for Business in mehreren Gesamtstrukturen müssen jede Skype for Business Gesamtstruktur vollständig einzeln in die Microsoft 365-Organisation migrieren, indem sie funktionen für geteilte Domänen (Shared SIP Address Space) verwenden. Nach Abschluss der Gesamtstrukturmigration müssen Kunden die Hybridbereitstellung mit der lokalen Bereitstellung deaktivieren, bevor sie mit der Migration der nächsten lokalen Skype for Business-Bereitstellung fortfahren. Darüber hinaus verbleiben lokale Benutzer vor der Migration in die Cloud in einem Verbundzustand mit allen Benutzern, die nicht im lokalen Verzeichnis desselben Benutzers dargestellt werden. Weitere Informationen finden Sie unter [Cloudkonsolidierung für Teams und Skype for Business](cloud-consolidation.md).

## <a name="federation-requirements"></a>Verbundanforderungen

<a name="BKMK_Federation"> </a>

Beim Konfigurieren Skype for Business Hybridmodus müssen Sie sicherstellen, dass Ihre lokalen und Onlineumgebungen miteinander verbunden werden können.  Die Onlineumgebung verfügt standardmäßig über einen offenen Partnerverbund. In der lokalen Umgebung ist der Partnerverbund häufig standardmäßig geschlossen.  

Die folgenden Anforderungen müssen erfüllt sein, um eine Hybridbereitstellung erfolgreich konfigurieren zu können:

- Der Domänenabgleich muss für Ihre lokale Bereitstellung und Ihre Microsoft 365-Organisation gleich konfiguriert sein. Wenn die Partnerermittlung in der lokalen Bereitstellung aktiviert ist, muss der offene Partnerverbund für Ihre Onlineorganisation konfiguriert werden. Wenn die Partnerermittlung nicht aktiviert ist, muss der geschlossene Partnerverbund für Ihre Onlineorganisation konfiguriert werden.
- Die Liste blockierter Domänen in der lokalen Bereitstellung muss genau mit der Liste blockierter Domänen für Ihren Onlinemandanten übereinstimmen.
- Die Liste der zulässigen Domänen in der lokalen Bereitstellung muss genau mit der Liste der zulässigen Domänen für Ihren Onlinemandanten übereinstimmen.
- Der Partnerverbund muss für die externe Kommunikation für den Onlinemandanten aktiviert sein.

## <a name="network-considerations"></a>Überlegungen zum Netzwerk

In den folgenden Abschnitten werden Überlegungen zu folgenden Themen beschrieben:

- DNS-Einstellungen
- Überlegungen zur Firewall

### <a name="dns-settings-for-hybrid-deployments"></a>DNS-Einstellungen für Hybridbereitstellungen

<a name="BKMK_DNS"> </a>

Bei der Erstellung von DNS-Einträgen für hybride Bereitstellungen sollten alle externen DNS-Einträge von Skype for Business auf die lokale Infrastruktur verweisen. Ausführliche Informationen zu den erforderlichen DNS-Einträgen finden Sie in den [DNS-Anforderungen für Skype for Business Server](../../sfbserver/plan-your-deployment/network-requirements/dns.md).

Außerdem müssen Sie sicherstellen, dass die in der folgenden Tabelle beschriebene DNS-Auflösung in Ihrer lokalen Bereitstellung funktioniert. (Wenn Sie bereits Federation für On-Premises konfiguriert haben, verfügen Sie höchstwahrscheinlich bereits über diese Funktionen).

|DNS-Eintrag  <br/> |Auflösbar durch  <br/> |DNS-Anforderung  <br/> |
|:-----|:-----|:-----|
|DNS SRV-Eintrag für _sipfederationtls._tcp.\<sipdomain.com\> für alle unterstützten SIP-Domänen, die in externe IP(n) von Access Edge aufgelöst werden  <br/> |Edge Server(s)  <br/> |Ermöglichen Sie die Kommunikation im Verbund in einer hybriden Konfiguration. Der Edgeserver muss wissen, wo der Verbunddatenverkehr für die SIP-Domäne weitergeleitet werden soll, die zwischen lokal und online aufgeteilt ist.  <br/> Muss einen strengen DNS-Namensabgleich zwischen der Domäne im Benutzernamen und dem SRV-Eintrag verwenden.  <br/> |
|DNS A-Eintrag(e) für Edge-Webkonferenzdienst-FQDN, z. B. webcon.contoso.com Auflösen in externe IP(n) des Webkonferenz-Edges  <br/> |Mit dem internen Unternehmensnetzwerk verbundene Computer der Benutzer  <br/> |Ermöglichen Sie Online-Benutzern die Präsentation oder Anzeige von Inhalten in gehosteten Meetings vor Ort. Zu den Inhalten gehören PowerPoint-Dateien, Whiteboards, Umfragen und gemeinsame Notizen.  <br/> |

Je nachdem, wie DNS in Ihrem Unternehmen konfiguriert ist, müssen Sie diese Datensätze möglicherweise zur internen gehosteten DNS-Zone für die entsprechende(n) SIP-Domäne(n) hinzufügen, um eine interne DNS-Auflösung für diese Datensätze zu ermöglichen.

### <a name="firewall-considerations-for-hybrid-deployments"></a>Überlegungen zur Firewall für Hybridbereitstellungen

<a name="BKMK_Firewall"> </a>

Die Computer in Ihrem Netz müssen in der Lage sein, standardmäßige DNS-Abfragen im Internet durchzuführen. Wenn diese Computer Standard-Internetwebsites erreichen können, erfüllt Ihr Netzwerk diese Anforderung.

Abhängig vom Standort Ihres Microsoft Online Services-Rechenzentrums müssen Sie auch Ihre Netzwerkfirewallgeräte so konfigurieren, dass Verbindungen basierend auf Platzhalterdomänennamen akzeptiert werden (z. B. der gesamte Datenverkehr von \*.outlook.com). Wenn die Firewalls Ihres Unternehmens keine Wildcard-Namenskonfigurationen unterstützen, müssen Sie die IP-Adressbereiche, die Sie zulassen möchten, und die angegebenen Ports manuell festlegen.

Weitere Informationen, einschließlich Details zu Ports und Protokollanforderungen, finden Sie unter [UrLs und IP-Adressbereiche von Microsoft 365](/microsoft-365/enterprise/urls-and-ip-address-ranges).
