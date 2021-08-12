---
title: Erstes Microsoft Teams
author: LaszloSomi
ms.author: lsomi
manager: swerth
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: lsomi
localization_priority: Normal
search.appverid: MET150
description: Mithilfe dieses Leitfadens können Sie Microsoft Teams ihrer ersten Arbeitsauslastung Microsoft 365 Office 365 nutzen.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: ddc107db668a582ad164e20f3b3ded169bd5d86125d949fe45d4d2f89090a8f7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312573"
---
# <a name="roll-out-microsoft-teams-first"></a>Erstes Microsoft Teams

Microsoft Teams können Ihren Mitarbeitern helfen, in Verbindung zu bleiben und miteinander zusammenzuarbeiten, insbesondere in der aktuell beispiellosen Zeit, in der Remotearbeit eine Realität von Mitarbeitern auf der ganzen Welt ist. Wenn Sie chatten, Videobesprechungen anberaumen und Office Dokumenten in einem Dokument zusammenarbeiten Teams können Sie Unternehmen dabei helfen, produktiv zu bleiben. Ganz gleich, ob Sie ein kleines Unternehmen, eine gemeinnützige Organisation oder eine große Organisation sind, Sie können mit Teams als erste Arbeitsauslastung innerhalb von Microsoft 365 oder Office 365 Suite beginnen, bevor Sie andere Arbeitslasten oder Dienste Office-App bereitstellen.

In diesem Artikel werden die Überlegungen erläutert, die Sie mit dem Ansatz "Teams Erstes" an müssen.

> [!IMPORTANT]
> Während Teams die erste in der Cloud bereitgestellte Workloads Ihrer Organisation sein kann, sollte Teams Bereitstellung teil Ihrer gesamten Cloudbereitstellungsstrategie sein.

Wenn Sie bereits ein Rollout anderer Microsoft 365- oder Office 365-Dienste durchgeführt haben und Teams die nächste Arbeitsauslastung (anstelle der ersten) ausgeführt wird, beginnen Sie mit Rollout von [Teams.](./deploy-overview.md)

## <a name="start-here"></a>Beginnen Sie hier

Für die ersten Schritte Teams Bereitstellung müssen Sie mindestens einige Voraussetzungen erfüllen. Die folgende Liste zeigt, was für Ihre Organisation vorhanden sein muss, bevor Teams aktiviert werden kann:

1.  Eine Microsoft 365 oder Office 365, die mit Ihrem Domänennamen konfiguriert ist

2.  Azure Active Directory -Konnektivität (AAD Connect) oder ähnliche Cloud-Identitätssynchronisierungslösung – mit allen erforderlichen Attributen, die mit Ihrem Mandanten synchronisiert werden  
    Informationen zu den mit der AAD-Synchronisierung synchronisierten Attributen Verbinden [Azure AD-](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized) und Azure Active Directory

3.  Entsprechende Benutzerlizenzen für Teams  
    Informationen zur Lizenzierung Teams Sie unter [Microsoft Teams Dienstbeschreibung.](/office365/servicedescriptions/teams-service-description)

4.  Organisationsnetzwerk für die Teams  
    Informationen zur Netzwerkvorbereitung erhalten Sie unter Vorbereiten [des Unternehmensnetzwerks für Teams.](prepare-network.md)

5.  Netzwerkzugriff auf Exchange, SharePoint und OneDrive for Business in Microsoft 365 oder Office 365: Office 365 URLs und [IP-Adressbereiche zulassen.](/office365/enterprise/urls-and-ip-address-ranges)

> [!NOTE]
> Mandanten, die nach dem 1. September 2019 erstellt wurden, werden im Teams-Modus bereitgestellt.
> 
> [!IMPORTANT]
> Wenn Sie Skype for Business Server haben und Ihr Mandant NACH dem 1. September 2019 bereitgestellt wurde, wenden Sie sich bitte an den Support, um Koexistenzfunktionen für die Teams. Stellen Sie sicher, dass Ihre "Organisationsweite Upgraderichtlinie" auf "Inselmodus" <span class="underline"></span> festgelegt ist, bevor Sie einem Teams Lizenzen zuweisen.

## <a name="migration-starting-points"></a>Ausgangspunkte der Migration

Ihre Reise zu Microsoft 365 oder Office 365 features, die in Teams verfügbar sind, abhängig von Ihrem Ausgangspunkt und dem Vorhandensein eines lokalen Skype for Business oder Lync-Servers. In den folgenden Abschnitten werden neben den oben genannten Voraussetzungen auch die grundlegenden Funktionen und Konfigurationsoptionen aufgeführt. Wir haben die Startszenarien in die folgenden Themen aufgeschlüsselt:

**Tenant Teams Configuration:** Tenant and user modes are used to control the recipient's behavior. Diese Einstellungen können auf Mandantenebene oder Benutzerebene in einer Organisation zugewiesen werden. Weitere Informationen finden Sie unter [Koexistenz mit Skype for Business.](coexistence-chat-calls-presence.md)

**Chat/ Externe Kommunikation in Teams:** Chatdienste beziehen sich auf Peer-zu-Peer- oder Gruppenchatunterhaltungen innerhalb und organisationlich oder extern zur Organisation. Die externe Kommunikation wird in Skype for Business.

Erstellen und Anzeigen von Besprechungen **in Teams:** Benutzer können Onlinebesprechungen jederzeit über das Outlook Teams-Add-In erstellen, und das PSTN-Einwählen ist in allen Szenarien verfügbar, sobald der Benutzer über eine Lizenz verfüge. Teams und Skype for Business Kalenderinformationen im Postfach des Benutzers Exchange speichern. Der lokale Exchange-Server muss Exchange Server 2016 CU3 oder höher vorhanden sein, damit der Teams-Client mit dem Postfach des Benutzers interagieren kann. Ohne Exchange Postfachzugriff wird das Kalendersymbol in Teams nicht angezeigt, und die Benutzer können keine Besprechungen im Client des Teams anzeigen, erstellen oder ändern.

**Anruffunktionen VoIP/PSTN in Teams:** Anrufe können VoIP (Voice over IP) oder PstN (Public Switched Telephone Network) sein. VoIP-Konnektivität erfolgt nativ zwischen Teams, während PSTN-Konnektivität erfolgt, wenn ein Benutzer eine externe Telefonnummer wählt.  

Teams unterstützen zwei Arten von PSTN-Konnektivität. Microsoft Calling Plan, wenn Microsoft Telefonieinfrastruktur (einschließlich der Telefonnummer für einen Benutzer) oder eine Direct Routing-Konfiguration bietet, bei der der Kunde die Telefoniekonnektivität über einen Session Border Controller (SBC) für den Teams-Benutzer bietet.  
Weitere Informationen finden Sie unter [Welcher Anrufplan ist für](calling-plan-landing-page.md) Sie am richtigen? und Telefonsystem [Direct-Routing.](direct-routing-landing-page.md)

**Teams** Zusammenarbeit in Teams Kanälen: In Teams sind Teams Gruppen von Personen, die für die Arbeit, für Projekte oder gemeinsame Interessen zusammenkommen. Teams besteht aus Kanälen. Jeder Kanal ist für ein Thema, z. B. "Teamereignisse", einen Abteilungsnamen oder einfach nur zum Spaß aufgebaut. In Kanälen halten Sie Besprechungen ab, führen Unterhaltungen und arbeiten gemeinsam an Dateien. Während der Zusammenarbeit

**OneDrive for Business (P2P-Dateifreigabe) in Teams:** Außerhalb von Teams und Kanälen können Teams-Benutzer Dateien mithilfe von OneDrive For Business oder anderen P2P-Freigabedateiprogrammen wie Citrix-Dateien, DropBox, Box und Google Drive freigeben. Für OneDrive Business muss einem Benutzer eine SharePoint Onlinelizenz zugewiesen sein.

**Anwendungsplattform:** Apps stellen bereits einsatz bereite Tools für Ihre Organisation bereit, um Ihre App besser Teams. Diese Apps kombinieren die Funktionen von Registerkarten, Messaging-Erweiterungen, Connectors und Bots, die von Microsoft, von Drittanbietern oder von Entwicklern in Ihrer Organisation entwickelt wurden, bereitgestellt werden.

**Sicherheits- und Compliancefeatures:** Teams bietet eine breite Palette von Informationen, die Ihnen in Compliancebereichen helfen, einschließlich Aufbewahrungsrichtlinien, Schutz vor Datenverlust (Data Loss Protection, DLP), eDiscovery und gesetzliche Aufbewahrung für Kanäle, Chats und Dateien, Überwachungsprotokollsuche. Weitere Informationen finden Sie unter [Sicherheit und Compliance in Microsoft Teams.](security-compliance-overview.md)  

> [!NOTE]
> Für die weiteren eDiscovery-Features ist eine E5-Lizenzierung erforderlich.

[Vergleichen Sie die Lizenzierungsoptionen.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)

Lesen [Sie Wie Exchange und Microsoft Teams interagieren,](exchange-teams-interact.md) um zu erfahren, welche Compliancefeatures in Ihrem Szenario verfügbar sind.

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>Organisationen **<span class="underline">ohne</span>** Skype for Business oder Lync Server

Bei diesem Ausgangspunkt wird davon ausgegangen, dass Ihre Organisation derzeit weder Skype for Business noch Lync Server nutzt und Teams in Microsoft 365 oder Office 365. Die folgende Tabelle enthält Details zur Konfiguration auf hoher Ebene und zu Denkfunktionen Teams Kerndiensten.

<table>
<thead>
<tr class="header">
<th>Element</th>
<th>Hinweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Tenant Teams configuration</td>
<td>Teams Nur der Modus, alle Chat- und Anruffunktionen sind in Teams verfügbar.</td>
</tr>
<tr class="even">
<td>Chatten/Externe Kommunikation in Teams</td>
<td><p>Interne (interne Microsoft 365 Oder Office 365 Organisation) und externe Chatkommunikation über Teams.</p>
<p><em>Hinweis: DNS-Einträge müssen für den externen Zugriff konfiguriert werden. Skype for Business DNS-Einträge sind erforderlich, auch wenn Sie Skype for Business nicht lokal oder in Microsoft 365 oder Office 365 haben, um einen Verbund mit Lync- und Skype for Business-Umgebungen zu ermöglichen:<br />
<a href="/office365/enterprise/external-domain-name-system-records">Externe Domain Name System-Einträge</a></em></p></td>
</tr>
<tr class="odd">
<td>Erstellen und Anzeigen von Besprechungen in Teams</td>
<td><p>Sie können interne und externe Besprechungen über Outlook-Add-In erstellen.</p>
<p>Die PstN-Funktionen "Einwählen" und "Auswählen" sind mit den Lizenzen für Audiokonferenzen verfügbar.</p>
<p>Teams Kalenderzugriff erfordert Exchange 2016 CU3+ lokal bereitgestellt mit Exchange eingerichteter Hybridbereitstellung: Erstellen einer Hybridbereitstellung mit dem <a href="/exchange/hybrid-deployment/deploy-hybrid">Hybridkonfigurations-Assistenten.</a> </p>

Richten Sie zusätzlich Exchange Hybridkonfiguration eine Exchange OAuth-Authentifizierung ein: Konfigurieren der OAuth-Authentifizierung zwischen Exchange [und Exchange Online Organisationen.](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help) 

</p></td>
</tr>
<tr class="even">
<td>Anruffeatures<br />
VoIP/PSTN in Teams</td>
<td><p>Interne und externe VoIP für den Mandanten ist verfügbar.</p>
<p>PSTN-Dienste können über das Microsoft-Telefon konfiguriert werden und zusätzlich einen Microsoft-Anrufplan oder Direct Routing hinzufügen.</p></td>
</tr>
<tr class="odd">
<td>Teams Zusammenarbeit an Kanälen und Kanälen in Teams</td>
<td><p>Um umfassende Funktionen einschließlich Compliancefunktionen nutzen zu können, muss dem benutzer SharePoint eine Online-Lizenz zugewiesen werden.</p>
<p>Die Migration von vorhandenen lokalen SharePoint ist nicht erforderlich.</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (P2P-Dateifreigabe)</td>
<td>OneDrive for Business muss einem Benutzer eine Lizenz SharePoint Online zugewiesen sein. Ohne diese Lizenz ist die Peer-zu-Peer-Dateifreigabe nicht möglich.</td>
</tr>
<tr class="odd">
<td>Anwendungsplattform</td>
<td>Benutzer können die Apps verwenden, die entsprechend den Richtlinien Ihres Unternehmens für sie verfügbar sind.<br />
Weitere Informationen finden Sie hier: <a href="/microsoftteams/admin-settings">Administratoreinstellungen für Apps in Teams</a></td>
</tr>
<tr class="even">
<td>Sicherheits- und Compliancefeatures</td>
<td><ul>
<li><p>Aufbewahrungsrichtlinien sind verfügbar.</p></li>
<li><p>eDiscovery und gesetzliches Halten von Compliance für Kanalnachrichten werden unterstützt.</p></li>
<li><p>Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) sind verfügbar.</p></li>
</ul>
<p>Vollständiger Featuresatz, der mit der Exchange Online; Exchange lokal unterstützt die meisten dieser Features. Eine vollständige Liste finden Sie unter So <a href="/MicrosoftTeams/exchange-teams-interact">Exchange und Teams Interaktion.</a></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>Aktivierungsschritte für Organisationen ohne Skype for Business Lync Server

1.  Erfüllen der Voraussetzungen, die im vorstehenden Abschnitt "Hier beginnen" beschrieben sind

2.  Wechseln des Mandanten Teams in den Nur-Modus (nur für vorhandene [Mandanten): Festlegen der Koexistenz- und Upgradeeinstellungen.](setting-your-coexistence-and-upgrade-settings.md)

3.  Konfigurieren Sie Ihren Mandanten gemäß den Unternehmens-/Unternehmensrichtlinien: Verwalten Microsoft Teams [Einstellungen für Ihre Organisation.](enable-features-office-365.md)

4.  Bereitstellen des Teams-Clients für Ihre Benutzer: [Kunden für die Teams](get-clients.md)

5.  Treiben Sie Ihr Einführungsprogramm vor  
    [Einführen von Microsoft Teams](adopt-microsoft-teams-landing-page.md)
    
    [Prüfliste für den Schnellstart der Microsoft Teams-Einführung](teams-adoption-quick-start-checklist.md)

6.  Beginnen Sie mit der Planung des Verschiebens anderer Arbeitslasten Microsoft 365 Arbeitsauslastungen Office 365

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>Organisationen **<span class="underline">mit Skype for Business</span>** oder Lync-Server

Bei diesem Ausgangspunkt wird davon ausgegangen, dass Ihre Organisation lokal Skype for Business 2019 oder 2015+ oder Lync 2013+ verwendet. Wir verfügen bereits über umfassende Anleitungen für Organisationen, die von lokalen Servern zu lokalen Servern Teams und diese sollten für diese Szenarien befolgt werden. Dieser Leitfaden ist speziell für das Szenario Teams, das Sie als erste In-App Microsoft 365 oder Office 365. Die folgende Tabelle enthält Details zur Konfiguration auf hoher Ebene und zu Denkfunktionen Teams Kerndiensten.

<table>
<thead>
<tr class="header">
<th>Element</th>
<th>Hinweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Tenant Teams configuration</td>
<td>Islands-Modus.</td>
</tr>
<tr class="even">
<td>Chatten/Externe Kommunikation in Teams</td>
<td>Nur intern innerhalb Ihres eigenen Mandanten erfolgt die externe Kommunikation (Verbund) über Ihre Skype for Business oder Lync Server-Bereitstellung.</td>
</tr>
<tr class="odd">
<td>Erstellen und Anzeigen von Besprechungen in Teams</td>
<td><p>Sie können interne und externe Besprechungen über Outlook-Add-In erstellen.</p>
<p>Die PstN-Funktionen "Einwählen" und "Auswählen" sind mit den Lizenzen für Audiokonferenzen verfügbar.</p>
<p>Teams Kalenderzugriff erfordert Exchange 2016 CU3+ – lokal bereitgestellt mit Exchange eingerichteten Hybridbereitstellung:<br />
<a href="/exchange/hybrid-deployment/deploy-hybrid">Erstellen Sie eine Hybridbereitstellung mit dem Hybridkonfigurations-Assistenten.</a></p>
<p>Der Administrator kann das Skype for Business Outlook-Add-In über das PreferredMeetingProviderForIslandsMode-Attribut der Teams-Besprechungsrichtlinie steuern:<a href="/powershell/module/skype/set-csteamsmeetingpolicy"> set-csteamsmeetingpolicy</a>.</p> 
</td>
</tr>
<tr class="even">
<td>Anruffeatures<br />
VoIP/PSTN in Teams</td>
<td><p>Interne VoIP für den Mandanten ist verfügbar.</p>
<p>PstN- oder Anrufplandienste sind erst verfügbar, wenn der Benutzer auf die Benutzeroberfläche Teams verschoben wird.</p></td>
</tr>
<tr class="odd">
<td>Teams Zusammenarbeit an Kanälen und Kanälen in Teams</td>
<td><p>Um umfassende Funktionen einschließlich Compliancefunktionen nutzen zu können, muss dem benutzer SharePoint eine Online-Lizenz zugewiesen werden.</p>
<p>Die Migration von vorhandenen lokalen SharePoint ist nicht erforderlich.</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (P2P-Dateifreigabe)</td>
<td>OneDrive for Business muss einem Benutzer eine Lizenz SharePoint Online zugewiesen sein. Ohne diese Lizenz für die Peer-zu-Peer-Dateifreigabe ist keine Dateifreigabe möglich.</td>
</tr>
<tr class="odd">
<td>Anwendungsplattform</td>
<td>Benutzer können die Apps verwenden, die entsprechend den Richtlinien Ihres Unternehmens für sie verfügbar sind.<br />
Weitere Informationen finden Sie hier: <a href="/microsoftteams/admin-settings">Administratoreinstellungen für Apps in Teams</a></td>
</tr>
<tr class="even">
<td>Sicherheits- und Compliancefeatures</td>
<td><ul>
<li><p>Aufbewahrungsrichtlinien sind verfügbar.</p></li>
<li><p>eDiscovery und gesetzliches Halten von Compliance für Kanalnachrichten werden unterstützt.</p></li>
<li><p>Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) sind verfügbar.</p></li>
</ul>
<p>Vollständiger Featuresatz, der mit der Exchange Online; Exchange lokal unterstützt die meisten dieser Features. Eine vollständige Liste finden Sie unter So <a href="/MicrosoftTeams/exchange-teams-interact">Exchange und Teams Interaktion.</a></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>Aktivierungsschritte für Organisationen mit Skype for Business Server  

1.  Erfüllen Sie die Voraussetzungen, die Sie oben im Abschnitt "Hier beginnen" ausführlich beschrieben haben.

2.  Wechseln des Mandanten in den Islands-Modus (für Mandanten, die NACH dem 01.09.2019 bereitgestellt wurden, wenden Sie sich an den Support, um diese Änderung zu ändern)  
    [Festlegen Ihrer Einstellungen für Koexistenz und Upgrades](setting-your-coexistence-and-upgrade-settings.md)

3.  Konfigurieren Ihres Mandanten gemäß den Unternehmens-/Unternehmensrichtlinien  
    [Verwalten von Microsoft Teams-Einstellungen in Ihrer Organisation](enable-features-office-365.md)

4.  Bereitstellen des Teams Clients  
    [Beziehen von Clients für Teams](get-clients.md)

5.   Treiben Sie Ihr Einführungsprogramm vor  
    [Einführen von Microsoft Teams](adopt-microsoft-teams-landing-page.md)<br/>
    [Prüfliste für den Schnellstart der Microsoft Teams-Einführung](teams-adoption-quick-start-checklist.md)

6.  Beginnen Sie mit der Planung des Verschiebens anderer Arbeitslasten Microsoft 365 Arbeitsauslastungen Office 365

7.  Einrichten Skype for Business Hybridbereitstellung und Folgen der empfohlenen Upgradepfade für Skype for Business Lync-Server  
    [Upgrade von Skype for Business lokalen Lokalen auf Teams](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>Abschlusserklärung

Microsoft Teams können es Ihrer Organisation ermöglichen, alle Mitarbeiter, Information-Workers und Frontline-Mitarbeiter auf einer einzigen Plattform zusammenzubringen. Sie können [noch heute beginnen.](https://products.office.com/microsoft-teams/group-chat-software) Hier können Sie mit allen unseren neuesten Ankündigungen und monatlichen Produktupdates [in Kontakt bleiben.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)

Darüber hinaus haben wir, da Unternehmen auf der ganzen Welt die aktuelle Situation COVID-19 verwalten, eine Reihe von Inhalten erstellt, die Ihnen helfen, Teams für die größtmögliche Auswirkung auf Ihre Organisation zu nutzen.

  - Unsere [Verpflichtung gegenüber Kunden während COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)

  - [In zwei Wochen: Das haben wir über Remotearbeit gelernt](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [Onlinebesprechungen und -ereignisse bereitstellen](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [Unterstützung für kleine und mittelständische Unternehmen bei der Remotearbeit mit Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [Digitale Transformation von Liveereignissen: Beobachtungen von Bob Bejan von der Frontlinie](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [Die 9 wichtigsten Methoden, mit denen Microsoft IT die Remotearbeit für die Mitarbeiter ermöglicht](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [Remote arbeiten, Sicherheit gewährleisten – Tipps für IHNEN](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [Helfen von Lehrkräften und Kursteilnehmern beim Umstieg auf Fernunterricht](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [Bleiben Sie produktiv, während Sie remote mit Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>Referenz zu Supportdiensten

Teams verwendet Exchange Online-, SharePoint Online-, OneDrive for Business- und Microsoft 365-Gruppen, um den Benutzern eine vollständig integrierte Microsoft 365- oder Office 365 bieten. Wie bereits erwähnt, Teams ohne vollständige Bereitstellung dieser Dienste mit eingeschränkten Funktionen funktionieren. Weitere Informationen zu Teams und deren Voraussetzungen finden Sie hier: [Willkommen bei Teams.](teams-overview.md)

Spezifische Informationen zu den oben aufgeführten Diensten finden Sie unter den folgenden Links:

  - Exchange Online wird für Kalenderfeatures und das Speichern von Peer-zu-Peer-Nachrichten in Teams. Weitere Informationen finden Sie unter So [wird's Exchange und Teams Interaktion](exchange-teams-interact.md)

> [!IMPORTANT]
> Damit Teams mit Exchange lokal zusammenarbeiten können, müssen Sie das neue OAuth-Authentifizierungsprotokoll Exchange konfigurieren, wie unter Konfigurieren der OAuth-Authentifizierung zwischen Exchange und [Exchange Online Organisationen beschrieben.](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

  - SharePoint wird für die Dateifreigabe in Kanälen verwendet, während /OneDrive for Business für die Dateifreigabe in 1:1- oder Gruppenchats verwendet wird. Weitere Informationen finden Sie unter So [SharePoint Online und OneDrive for Business Interaktion mit Microsoft Teams.](sharepoint-onedrive-interact.md)

  - [Microsoft 365 Gruppen](office-365-groups.md) werden für die Team- und Kanalerstellung/-verwaltung verwendet.


## <a name="related-topics"></a>Verwandte Themen

[Microsoft Teams IT-Architektur- und Telefonielösungen Poster](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[Planen der Hybridkonnektivität zwischen Skype for Business Server und Office 365](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[Unterstützen von Remotemitarbeitern mithilfe Teams](support-remote-work-with-teams.md)

[Remote arbeiten mit Microsoft 365](https://aka.ms/remote-work)
