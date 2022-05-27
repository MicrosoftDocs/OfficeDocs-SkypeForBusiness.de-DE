---
title: Rollout Microsoft Teams First
author: LaszloSomi
ms.author: lsomi
manager: swerth
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: lsomi
ms.localizationpriority: medium
search.appverid: MET150
description: Verwenden Sie diese Anleitung, um Microsoft Teams als ihre erste Microsoft 365- oder Office 365-Workload zu veröffentlichen.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2621ea94e2a35e7de9eed3dac2994f9b1932b0bb
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681726"
---
# <a name="roll-out-microsoft-teams-first"></a>Rollout Microsoft Teams First

Microsoft Teams können Ihren Mitarbeitern helfen, in Verbindung zu bleiben und miteinander zusammenzuarbeiten, insbesondere in der aktuellen beispiellosen Zeit, in der Remotearbeit eine Realität von Mitarbeitern auf der ganzen Welt ist. Die Möglichkeit, innerhalb Teams zu chatten, Videobesprechungen zu führen und an Office Dokumenten zusammenzuarbeiten, kann Unternehmen dabei helfen, produktiv zu bleiben. Unabhängig davon, ob Sie ein kleines Unternehmen, eine gemeinnützige Organisation oder eine große Organisation sind, können Sie mit Teams als erster Workload innerhalb Microsoft 365 oder Office 365 Suite beginnen, bevor Sie andere Office-App oder Dienste bereitstellen.

In diesem Artikel werden die Überlegungen beschrieben, die Sie beim Ansatz "Teams Erste" berücksichtigen müssen.

> [!IMPORTANT]
> Obwohl Teams die erste in der Cloud bereitgestellte Workload Ihrer Organisation sein kann, sollte die Bereitstellung Teams Teil Ihrer allgemeinen Cloudbereitstellungsstrategie sein.

Wenn Sie bereits andere Microsoft 365- oder Office 365-Dienste eingeführt haben und Teams ihre nächste Workload für das Rollout ist (anstelle der ersten), beginnen Sie mit dem [Rollout Teams](./deploy-overview.md).

## <a name="start-here"></a>Beginnen Sie hier

Um mit Ihrer Teams First-Bereitstellung zu beginnen, müssen Sie mindestens einige Voraussetzungen erfüllen. Die folgende Liste zeigt, was Sie für Ihre Organisation benötigen, bevor Teams aktiviert werden kann:

1.  Eine Microsoft 365 oder Office 365 Organisation, die mit Ihrem Domänennamen konfiguriert ist

2.  Azure Active Directory-Konnektivität (AAD Connect) oder eine ähnliche Cloudidentitätssynchronisierungslösung – mit allen erforderlichen Attributen, die mit Ihrem Mandanten synchronisiert werden  
    Um die attributes synchronized with AAD sync, read [Azure AD Verbinden sync: Attribute synchronized to Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)

3.  Für Teams zugewiesene Benutzerlizenzen  
    Um Teams Lizenzierung zu verstehen, lesen Sie [Microsoft Teams Dienstbeschreibung](/office365/servicedescriptions/teams-service-description).

4.  Das Netzwerk der Organisation, das für Teams vorbereitet ist  
    Informationen zur Netzwerkvorbereitung finden Sie unter [Vorbereiten des Netzwerks Ihrer Organisation für Teams](prepare-network.md).

5.  Zulassen des Netzwerkzugriffs auf Exchange, SharePoint und OneDrive for Business in Microsoft 365 oder Office 365: [Office 365 URLs und IP-Adressbereichen](/office365/enterprise/urls-and-ip-address-ranges).

> [!NOTE]
> Mandanten, die nach dem 1. September 2019 erstellt wurden, werden im Modus "Nur" Teams bereitgestellt.
> 
> [!IMPORTANT]
> Wenn Sie Skype for Business Server bereitgestellt haben und Ihr Mandant nach dem 1. September 2019 bereitgestellt wurde, wenden Sie sich bitte an den Support, um Koexistenzfunktionen für Teams zu aktivieren. Stellen Sie sicher, dass Ihre "organisationsweite Upgraderichtlinie" auf "Inselmodus" festgelegt ist, <span class="underline">bevor</span> Sie einem Benutzer Teams Lizenzen zuweisen.

## <a name="migration-starting-points"></a>Migrationsstartpunkte

Ihre Reise zu Microsoft 365 oder Office 365 und Features, die in Teams verfügbar sind, abhängig von Ihrem Ausgangspunkt und dem Vorhandensein eines lokalen Skype for Business oder Lync-Servers. In den folgenden Abschnitten werden die grundlegenden Funktionen und Konfigurationsoptionen zusätzlich zu den oben genannten Voraussetzungen beschrieben. Wir haben die Ausgangspunktszenarien auf die folgenden Themen aufgeschlüsselt:

**Mandanten-Teams-Konfiguration**: Mandanten- und Benutzermodi werden verwendet, um das Verhalten des Empfängers zu steuern. Diese Einstellungen können auf Mandanten- oder Benutzerebene in einer Organisation zugewiesen werden. Weitere Informationen finden Sie [unter Koexistenz mit Skype for Business](coexistence-chat-calls-presence.md).

**Chat/Externe Kommunikation in Teams**: Chatdienste beziehen sich auf Peer-zu-Peer- oder Gruppenchatunterhaltungen innerhalb und Organisation oder extern in der Organisation. Externe Kommunikation wird in Skype for Business auch als Verbund bezeichnet.

**Erstellen und Anzeigen von Besprechungen in Teams**: Ein Benutzer kann immer Onlinebesprechungen über das Outlook Teams-Add-In erstellen, und die PSTN-Einwahl ist in allen Szenarien verfügbar, sobald der Benutzer lizenziert ist. Teams und Skype for Business Kalenderinformationen im Exchange Postfach des Benutzers speichern. Der lokale Exchange Server muss Exchange Server 2016 CU3 oder höher sein, damit der Teams-Client mit dem Postfach des Benutzers interagieren kann. Ohne Exchange Postfach wird das Kalendersymbol in Teams nicht angezeigt, und der Benutzer kann Besprechungen im Teams Client nicht anzeigen, erstellen oder ändern.

**Anruffunktionen VoIP/PSTN in Teams**: Anrufe können VoIP (Voice over IP) oder PSTN (Public Switched Telephone Network) sein. VoIP-Konnektivität erfolgt systemintern zwischen Teams Clients, während die PSTN-Konnektivität erfolgt, wenn ein Benutzer eine externe Telefonnummer wählt.  

Teams unterstützen zwei Arten von PSTN-Verbindungen. Microsoft-Anrufplan, wenn Microsoft die Telefonieinfrastruktur einschließlich der Telefonnummer für einen Benutzer oder die Direct Routing-Konfiguration bereitstellt, bei der der Kunde die Telefoniekonnektivität über einen Session Border Controller (SBC) für den Teams Benutzer bereitstellt.  
Um mehr zu erfahren, lesen [Sie, welcher Anrufplan für Sie geeignet ist?](calling-plan-landing-page.md) und [Telefonsystem Direct Routing](direct-routing-landing-page.md).

**Teams- und Kanalzusammenarbeit in Teams**: In Teams sind Teams Gruppen von Personen, die für Arbeit, Projekte oder gemeinsame Interessen zusammengeführt werden. Teams bestehen aus Kanälen. Jeder Kanal basiert auf einem Thema, z. B. "Teamereignisse", einem Abteilungsnamen oder einfach nur zum Spaß. Kanäle sind der Ort, an dem Sie Besprechungen abhalten, Unterhaltungen führen und gemeinsam an Dateien arbeiten. Während der Zusammenarbeit

**OneDrive for Business (P2P-Dateifreigabe) in Teams**: Außerhalb von Teams und Kanälen können Teams Benutzer Dateien peer-to-peer mithilfe von OneDrive für Unternehmen oder anderen P2P-Freigabedateiprogrammen wie Citrix Files, DropBox, Box und Google Drive freigeben. Für OneDrive business muss einem Benutzer SharePoint Online-Lizenz zugewiesen sein.

**Anwendungsplattform**: Apps bieten out-of-the-box-Tools für Ihre Organisation, um mehr aus Teams herauszuholen. Diese Apps kombinieren die Funktionen von Registerkarten, Messaging-Erweiterungen, Connectors und Bots, die von Microsoft bereitgestellt werden, die von einem Drittanbieter oder von Entwicklern in Ihrer Organisation erstellt wurden.

**Sicherheits- und Compliancefeatures:** Teams verfügt über eine breite Palette von Informationen, die Sie bei Compliance-Bereichen unterstützen, einschließlich Aufbewahrungsrichtlinien, Verhinderung von Datenverlust (Data Loss Prevention, DLP), eDiscovery und gesetzliche Aufbewahrung für Kanäle, Chats und Dateien, Überwachungsprotokollsuche. Weitere Informationen finden Sie [unter Sicherheit und Compliance in Microsoft Teams](security-compliance-overview.md).  

> [!NOTE]
> Advance eDiscovery-Features erfordern E5-Lizenzierung.

[Vergleich der Lizenzierungsoptionen](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).

Lesen Sie[, wie Exchange und Microsoft Teams interagieren](exchange-teams-interact.md), um zu erfahren, welche Compliancefeatures in Ihrem Szenario verfügbar sind.

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>Organisationen **<span class="underline">ohne</span>** Skype for Business oder Lync Server

Bei diesem Ausgangspunkt wird davon ausgegangen, dass Ihre Organisation derzeit weder Skype for Business noch Lync Server nutzt, und Teams ihre erste Anwendung in Microsoft 365 oder Office 365 ist. In der folgenden Tabelle sind allgemeine Konfigurations- und Endbenutzerfunktionen für Teams für Kerndienste aufgeführt.

<table>
<thead>
<tr class="header">
<th>Element</th>
<th>Hinweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Mandanten-Teams-Konfiguration</td>
<td>Teams Modus "Nur" befinden sich alle Chat- und Anruffunktionen nur in Teams.</td>
</tr>
<tr class="even">
<td>Chat / Externe Kommunikation in Teams</td>
<td><p>Interne (innerhalb Microsoft 365 oder Office 365 Organisation) und externe Chatkommunikation von Teams möglich.</p>
<p><em>Hinweis: DNS-Einträge müssen für den externen Zugriff konfiguriert werden. Skype for Business DNS-Einträge sind erforderlich, auch wenn Sie nicht über Skype for Business lokal oder in Microsoft 365 oder Office 365 verfügen, um einen Partnerverbund mit Lync- und Skype for Business-Umgebungen zu ermöglichen:<br />
<a href="/office365/enterprise/external-domain-name-system-records">Einträge des externen Domänennamensystems</a></em></p></td>
</tr>
<tr class="odd">
<td>Erstellen und Anzeigen von Besprechungen in Teams</td>
<td><p>In der Lage, interne und externe Besprechungen über Outlook-Add-In zu erstellen.</p>
<p>PSTN-Einwahl- und -Auswahlfunktion ist mit den Audiokonferenz-Lizenzen verfügbar.</p>
<p>Teams Kalenderzugriff erfordert Exchange 2016 CU3+ lokal bereitgestellt mit Exchange hybrid eingerichtet: <a href="/exchange/hybrid-deployment/deploy-hybrid">Erstellen einer Hybridbereitstellung mit dem Assistenten für die Hybridkonfiguration.</a> </p>

Richten Sie neben Exchange Hybridkonfiguration Exchange OAuth-Authentifizierung ein: [Konfigurieren der OAuth-Authentifizierung zwischen Exchange und Exchange Online Organisationen](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help). 

</p></td>
</tr>
<tr class="even">
<td>Anruffunktionen<br />
VoIP/PSTN in Teams</td>
<td><p>VoIP intern und extern für den Mandanten ist verfügbar.</p>
<p>PSTN-Dienste können über Microsoft-Telefon System konfiguriert werden sowie einen Microsoft-Anrufplan oder Direct Routing hinzufügen.</p></td>
</tr>
<tr class="odd">
<td>zusammenarbeit Teams und Kanäle in Teams</td>
<td><p>Für vollständige Erfahrung, einschließlich Compliance-Features, muss dem Benutzer eine SharePoint Online-Lizenz zugewiesen werden.</p>
<p>Die Migration vorhandener lokaler SharePoint Websites ist nicht erforderlich.</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (P2P-Dateifreigabe)</td>
<td>OneDrive for Business erfordert, dass einem Benutzer eine SharePoint Onlinelizenz zugewiesen ist. Ohne diese Lizenz ist die Peer-to-Peer-Dateifreigabe nicht möglich.</td>
</tr>
<tr class="odd">
<td>Anwendungsplattform</td>
<td>Benutzer können die Apps verwenden, die gemäß Ihren Unternehmensrichtlinien für sie verfügbar sind.<br />
Weitere Informationen finden Sie hier: <a href="/microsoftteams/admin-settings">Admin Einstellungen für Apps in Teams</a></td>
</tr>
<tr class="even">
<td>Sicherheits- und Compliancefeatures</td>
<td><ul>
<li><p>Aufbewahrungsrichtlinien sind verfügbar.</p></li>
<li><p>eDiscovery und gesetzliche Aufbewahrungspflicht für Die Einhaltung von Kanalnachrichten wird unterstützt.</p></li>
<li><p>Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention Policies, DLP) sind verfügbar.</p></li>
</ul>
<p>Vollständige Featuregruppe verfügbar mit Exchange Online; Exchange lokal unterstützt die meisten dieser Features. Eine vollständige Liste finden Sie unter <a href="/MicrosoftTeams/exchange-teams-interact">Interaktion zwischen Exchange und Teams</a>.</p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>Aktivierungsschritte für Organisationen ohne Skype for Business oder Lync Server

1.  Erfüllen Sie die Voraussetzungen, die im Abschnitt "Hier beginnen" oben beschrieben sind.

2.  Mandanten in Teams Modus "Nur" (nur für vorhandene Mandanten): [Festlegen ihrer Koexistenz- und Upgradeeinstellungen](setting-your-coexistence-and-upgrade-settings.md).

3.  Konfigurieren Sie Ihren Mandanten gemäß den Geschäfts-/Unternehmensrichtlinien Ihres Unternehmens: [Verwalten sie Microsoft Teams Einstellungen für Ihre Organisation](enable-features-office-365.md).

4.  Bereitstellen des Teams-Clients für Ihre Benutzer: [Abrufen von Clients für Teams](get-clients.md)

5.  Fördern Ihres Einführungsprogramms  
    [Einführen von Microsoft Teams](adopt-microsoft-teams-landing-page.md)
    
    [Prüfliste für den Schnellstart der Microsoft Teams-Einführung](teams-adoption-quick-start-checklist.md)

6.  Beginnen Sie mit der Planung des Verschiebens anderer Workloads in Microsoft 365 oder Office 365

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>Organisationen **<span class="underline">mit</span>** Skype for Business oder Lync-Server

Bei diesem Ausgangspunkt wird davon ausgegangen, dass Ihre Organisation Skype for Business Server 2019 oder 2015+ oder Lync 2013+ lokal nutzt. Wir haben bereits umfangreiche Anleitungen für Organisationen, die von lokalen Servern zu Teams migrieren, und dies sollte für diese Szenarien befolgt werden. Diese Anleitung ist spezifisch für das Szenario, in dem Teams die erste Anwendung ist, die Sie in Microsoft 365 oder Office 365 verwenden. In der folgenden Tabelle sind allgemeine Konfigurations- und Endbenutzerfunktionen für Teams für Kerndienste aufgeführt.

<table>
<thead>
<tr class="header">
<th>Element</th>
<th>Hinweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Mandanten-Teams-Konfiguration</td>
<td>Inselmodus.</td>
</tr>
<tr class="even">
<td>Chat / Externe Kommunikation in Teams</td>
<td>Die externe Kommunikation (Partnerverbund) erfolgt nur intern innerhalb Ihres eigenen Mandanten über Ihre Skype for Business- oder Lync-Serverbereitstellung.</td>
</tr>
<tr class="odd">
<td>Erstellen und Anzeigen von Besprechungen in Teams</td>
<td><p>In der Lage, interne und externe Besprechungen über Outlook-Add-In zu erstellen.</p>
<p>PSTN-Einwahl- und -Auswahlfunktion ist mit den Audiokonferenz-Lizenzen verfügbar.</p>
<p>Teams kalenderzugriff erfordert Exchange 2016 CU3+ lokal bereitgestellt mit Exchange Hybrid eingerichtet:<br />
<a href="/exchange/hybrid-deployment/deploy-hybrid">Erstellen Sie eine Hybridbereitstellung mit dem Assistenten für die Hybridkonfiguration.</a></p>
<p>Der Administrator kann das Skype for Business Outlook-Add-In über das PreferredMeetingProviderForIslandsMode-Attribut der Teams Besprechungsrichtlinie steuern:<a href="/powershell/module/skype/set-csteamsmeetingpolicy"> set-csteamsmeetingpolicy</a>.</p> 
</td>
</tr>
<tr class="even">
<td>Anruffunktionen<br />
VoIP/PSTN in Teams</td>
<td><p>VoIP intern für den Mandanten ist verfügbar.</p>
<p>PSTN- oder Anrufplandienste sind erst verfügbar, wenn der Benutzer in Teams Nur-Erfahrung verschoben wird.</p></td>
</tr>
<tr class="odd">
<td>zusammenarbeit Teams und Kanäle in Teams</td>
<td><p>Für vollständige Erfahrung, einschließlich Compliance-Features, muss dem Benutzer eine SharePoint Online-Lizenz zugewiesen werden.</p>
<p>Die Migration vorhandener lokaler SharePoint Websites ist nicht erforderlich.</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (P2P-Dateifreigabe)</td>
<td>OneDrive for Business erfordert, dass einem Benutzer eine SharePoint Onlinelizenz zugewiesen ist. Ohne diese Lizenz ist die Freigabe von Dateien pro Peer nicht möglich.</td>
</tr>
<tr class="odd">
<td>Anwendungsplattform</td>
<td>Benutzer können die Apps verwenden, die gemäß Ihren Unternehmensrichtlinien für sie verfügbar sind.<br />
Weitere Informationen finden Sie hier: <a href="/microsoftteams/admin-settings">Admin Einstellungen für Apps in Teams</a></td>
</tr>
<tr class="even">
<td>Sicherheits- und Compliancefeatures</td>
<td><ul>
<li><p>Aufbewahrungsrichtlinien sind verfügbar.</p></li>
<li><p>eDiscovery und gesetzliche Aufbewahrungspflicht für Die Einhaltung von Kanalnachrichten wird unterstützt.</p></li>
<li><p>Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) sind verfügbar.</p></li>
</ul>
<p>Vollständige Featuregruppe verfügbar mit Exchange Online; Exchange lokal unterstützt die meisten dieser Features. Eine vollständige Liste finden Sie unter <a href="/MicrosoftTeams/exchange-teams-interact">Interaktion zwischen Exchange und Teams.</a></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>Aktivierungsschritte für Organisationen mit Skype for Business Server  

1.  Erfüllen Sie die Voraussetzungen, die im Abschnitt "Hier beginnen" oben beschrieben sind.

2.  Wechseln des Mandanten in den Inselmodus (für Mandanten, die nach dem 01.09.2019 bereitgestellt wurden, wenden Sie sich bitte an den Support, um diese Änderung vorzunehmen)  
    [Festlegen Ihrer Einstellungen für Koexistenz und Upgrades](setting-your-coexistence-and-upgrade-settings.md)

3.  Konfigurieren Ihres Mandanten in Übereinstimmung mit den Geschäfts-/Unternehmensrichtlinien Ihres Unternehmens  
    [Verwalten von Microsoft Teams-Einstellungen in Ihrer Organisation](enable-features-office-365.md)

4.  Bereitstellen des Teams-Clients  
    [Beziehen von Clients für Teams](get-clients.md)

5.   Fördern Ihres Einführungsprogramms  
    [Einführen von Microsoft Teams](adopt-microsoft-teams-landing-page.md)<br/>
    [Prüfliste für den Schnellstart der Microsoft Teams-Einführung](teams-adoption-quick-start-checklist.md)

6.  Beginnen Sie mit der Planung des Verschiebens anderer Workloads in Microsoft 365 oder Office 365

7.  Einrichten Skype for Business Hybridbereitstellung und Befolgen der empfohlenen Upgradepfade für Skype for Business- und Lync-Server  
    [Upgrade von Skype for Business lokal auf Teams](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>Closing-Anweisung

Microsoft Teams kann ein Enabler für Ihre Organisation sein, um alle Mitarbeiter, Information Worker und Mitarbeiter in Service und Produktion auf einer einzigen Plattform zusammenzubringen. Sie können heute [loslegen](https://products.office.com/microsoft-teams/group-chat-software) . Hier können Sie mit allen unseren neuesten Ankündigungen und monatlichen [Produktupdates](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog) in Kontakt bleiben.

Darüber hinaus haben wir, da Unternehmen auf der ganzen Welt die aktuelle COVID-19-Situation verwalten, eine Reihe von Inhalten erstellt, die Ihnen helfen, Teams für die maximale Auswirkung in Ihrer Organisation zu nutzen.

  - Unser [Engagement für Kunden während COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)

  - [2 Wochen: Was wir über Remotearbeit gelernt haben](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [Bereitstellen von Onlinebesprechungen und -ereignissen](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [Unterstützung für kleine und mittelständische Unternehmen bei der Remotearbeit mit Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [Digitale Transformation von Live-Events: Bob Bejans Beobachtungen aus der Front](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [Die 9 wichtigsten Methoden, mit denen Microsoft IT die Remotearbeit für die Mitarbeiter ermöglicht](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [Remotearbeit, Sicherheit – Tipps für CISOs](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [Unterstützung von Lehrern und Schülern beim Umstieg auf Fernunterricht](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [Produktiv bleiben und remote mit Microsoft Teams arbeiten](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>Referenz zu Supportdiensten

Teams setzt auf Exchange Online, SharePoint Online, OneDrive for Business und Microsoft 365-Gruppen, um Ihren Benutzern eine vollständig integrierte Microsoft 365 oder Office 365 Erfahrung. Wie oben erwähnt, funktioniert Teams ohne vollständige Bereitstellung dieser Dienste – mit eingeschränkten Funktionen. Weitere Informationen zu Teams und deren Voraussetzungen finden Sie hier: [Willkommen bei Teams](teams-overview.md).

Einzelheiten zu den einzelnen oben aufgeführten Diensten finden Sie unter den folgenden Links:

  - Exchange Online wird zum Kalendern von Features und zum Speichern von Peer-zu-Peer-Nachrichten in Teams verwendet. Weitere Informationen finden Sie unter [Interaktion zwischen Exchange und Teams](exchange-teams-interact.md)

> [!IMPORTANT]
> Für Teams Interoperabilität mit Exchange lokal müssen Sie das neue OAuth-Authentifizierungsprotokoll Exchange konfigurieren, wie unter [Konfigurieren der OAuth-Authentifizierung zwischen Exchange und Exchange Online Organisationen](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help) beschrieben.

  - SharePoint wird für die Dateifreigabe in Kanälen verwendet, während /OneDrive for Business für die Dateifreigabe im 1:1- oder Gruppenchat verwendet wird. Weitere Informationen finden Sie unter ["Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams](sharepoint-onedrive-interact.md)".

  - [Microsoft 365-Gruppen](office-365-groups.md) werden für die Erstellung/Verwaltung von Teams und Kanälen verwendet.


## <a name="related-topics"></a>Verwandte Themen

[Microsoft Teams IT-Architektur- und Telefonielösungen Poster](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[Planen der Hybridkonnektivität zwischen Skype for Business Server und Office 365](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[Unterstützen von Remotemitarbeitern mithilfe von Teams](support-remote-work-with-teams.md)

[Remotearbeit mit Microsoft 365](https://aka.ms/remote-work)
