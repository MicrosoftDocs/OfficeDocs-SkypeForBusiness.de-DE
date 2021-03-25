---
title: Rollout von Microsoft Teams First
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
description: Verwenden Sie diese Anleitung zum Rollout von Microsoft Teams als erste Microsoft 365- oder Office 365-Workload.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 81ecf9a0f963a1be577149c585424c140df2abd5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119354"
---
# <a name="roll-out-microsoft-teams-first"></a>Rollout von Microsoft Teams First

Microsoft Teams kann Ihre Mitarbeiter dabei unterstützen, in Verbindung zu bleiben und miteinander zusammenzuarbeiten, insbesondere in der aktuellen beispiellosen Zeit, in der Remotearbeit eine Realität für Mitarbeiter auf der ganzen Welt ist. Die Möglichkeit, in Teams zu chatten, Videobesprechungen zu unternehmen und an Office-Dokumenten zusammenzuarbeiten, kann Unternehmen dabei helfen, produktiv zu bleiben. Ganz gleich, ob Sie ein kleines Unternehmen, ein gemeinnütziges Unternehmen oder eine große Organisation sind, Sie können mit Teams als erste Arbeitsauslastung in Microsoft 365 oder Office 365-Suite beginnen, bevor Sie eine andere Office-App oder einen anderen Dienst bereitstellen.

In diesem Artikel werden die Überlegungen erläutert, die Sie mit dem Ansatz "Teams First" berücksichtigen müssen.

> [!IMPORTANT]
> Obwohl Teams die erste in der Cloud bereitgestellte Workload Ihrer Organisation sein kann, sollte die Bereitstellung von Teams Teil Ihrer allgemeinen Cloudbereitstellungsstrategie sein.

Wenn Sie bereits andere Microsoft 365- oder Office 365-Dienste installiert haben und Teams Ihre nächste Arbeitslast ist, die Sie (anstelle der ersten) rollouten müssen, beginnen Sie mit So wird's gemacht: Rollout [von Teams](./deploy-overview.md).

## <a name="start-here"></a>Beginnen Sie hier

Um mit Ihrer Teams First-Bereitstellung zu beginnen, müssen Sie mindestens einige Voraussetzungen erfüllen. Die folgende Liste zeigt, was für Ihre Organisation vorhanden sein muss, bevor Teams aktiviert werden kann:

1.  Eine Microsoft 365- oder Office 365-Organisation, die mit Ihrem Domänennamen konfiguriert ist

2.  Azure Active Directory-Konnektivität (AAD-Verbindung) oder ähnliche Cloudidentitätssynchronisierungslösung – mit allen erforderlichen Attributen, die mit Ihrem Mandanten synchronisiert wurden  
    Informationen zu den mit der AAD-Synchronisierung synchronisierten Attributen finden Sie unter [Azure AD Connect-Synchronisierung: Mit Azure Active Directory synchronisierte Attribute.](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)

3.  Für Teams zugewiesene geeignete Benutzerlizenzen  
    Informationen zur Microsoft Teams-Lizenzierung finden Sie unter [Microsoft Teams-Dienstbeschreibung](/office365/servicedescriptions/teams-service-description).

4.  Für Teams vorbereitetes Netzwerk der Organisation  
    Informationen zur Netzwerkvorbereitung erhalten Sie unter Vorbereiten des Netzwerks [Ihrer Organisation für Teams.](prepare-network.md)

5.  Zulassen des Netzwerkzugriffs auf Exchange, Sharepoint und OneDrive for Business in Microsoft 365 oder Office 365: [Office 365-URLs und #A0](/office365/enterprise/urls-and-ip-address-ranges).

> [!NOTE]
> Mandanten, die nach dem 1. September 2019 erstellt wurden, werden im Modus "Nur Teams" bereitgestellt.
> 
> [!IMPORTANT]
> Wenn Sie Skype for Business Server bereitgestellt haben und Ihr Mandant nach dem 1. September 2019 bereitgestellt wurde, wenden Sie sich an den Support, um Koexistenzfunktionen für Teams zu aktivieren. Stellen Sie sicher, dass Ihre "Organisationsweite Upgraderichtlinie" auf "Inselmodus" <span class="underline"></span> festgelegt ist, bevor Sie einem Benutzer Teams-Lizenzen zuweisen.

## <a name="migration-starting-points"></a>Migrationsstartpunkte

Ihre Reise zu Microsoft 365 oder Office 365 und die in Teams verfügbaren Features sind abhängig von Ihrem Ausgangspunkt und dem Vorhandensein eines lokalen Skype for Business- oder Lync-Servers. In den folgenden Abschnitten werden die grundlegenden Funktionen und Konfigurationsoptionen zusätzlich zu den oben genannten Voraussetzungen erläutert. Wir haben die Ausgangspunktszenarien auf die folgenden Themen aufschlüsselt:

**Konfiguration von Mandantenteams:** Mandanten- und Benutzermodi werden verwendet, um das Verhalten des Empfängers zu steuern. Diese Einstellungen können auf Mandanten- oder Benutzerebene in einer Organisation zugewiesen werden. Weitere Informationen finden Sie unter [Koexistenz mit Skype for Business](coexistence-chat-calls-presence.md).

**Chat/ Externe Kommunikation in Teams:** Chatdienste beziehen sich auf Peer-zu-Peer- oder Gruppenchatunterhaltungen innerhalb und Organisation oder extern an die Organisation. Externe Kommunikation wird in Skype for Business auch als Verbund bezeichnet.

**Erstellen und Anzeigen von** Besprechungen in Teams: Ein Benutzer kann immer Onlinebesprechungen über das Outlook Teams-Add-In erstellen, und die PSTN-Einwahl ist in allen Szenarien verfügbar, sobald der Benutzer lizenziert wurde. In Teams und Skype for Business werden Kalenderinformationen im Exchange-Postfach des Benutzers gespeichert. Der lokale Exchange-Server muss Exchange Server 2016 CU3 oder höher sein, damit der Teams-Client mit dem Postfach des Benutzers interagieren kann. Ohne Zugriff auf das Exchange-Postfach wird das Kalendersymbol in Teams nicht angezeigt, und der Benutzer kann Besprechungen im Teams-Client nicht anzeigen, erstellen oder ändern.

**Anruffunktionen VoIP /PSTN in Teams:** Anrufe können Voice over IP (VoIP) oder Public Switched Telephone Network (PSTN) sein. Die VoIP-Konnektivität erfolgt systemeigene zwischen Teams-Clients, während die PSTN-Konnektivität erfolgt, wenn ein Benutzer eine externe Telefonnummer wählt.  

Teams unterstützt zwei Arten von PSTN-Konnektivität. Microsoft Calling Plan, wenn Microsoft eine Telefonieinfrastruktur einschließlich der Telefonnummer für einen Benutzer oder eine Direct Routing-Konfiguration bietet, bei der der Kunde die Telefonieverbindung über einen Session Border Controller (SBC) für den Benutzer von Teams bietet.  
Weitere Informationen finden Sie unter [Welcher Anrufplan ist für](calling-plan-landing-page.md) Sie richtig? und [Direktes Telefonsystemrouting.](direct-routing-landing-page.md)

Zusammenarbeit von Teams und **Kanälen in Teams:** In Teams sind Teams Gruppen von Personen, die für Arbeit, Projekte oder gemeinsame Interessen zusammengebracht werden. Teams sind aus Kanälen. Jeder Kanal ist auf einem Thema wie "Teamereignisse", einem Abteilungsnamen oder einfach nur aus Spaß aufgebaut. Kanäle sind der Ort, an dem Sie Besprechungen halten, Unterhaltungen führen und gemeinsam an Dateien arbeiten. Während der Zusammenarbeit

**OneDrive for Business (P2P-Dateifreigabe) in Teams:** Außerhalb von Teams und Kanälen können #A1 Dateien mithilfe von OneDrive for Business oder anderen P2P-Freigabedateiprogrammen wie Citrix-Dateien, DropBox, Box und Google Drive freigeben. Für OneDrive for Business muss einem Benutzer eine SharePoint #A0 zugewiesen sein.

**Anwendungsplattform:** Apps bieten ihnen tools für Ihre Organisation, um Teams besser nutzen zu können. Diese Apps kombinieren die Funktionen von Registerkarten, Nachrichtenerweiterungen, Connectors und Bots, die von Microsoft bereitgestellt werden, die von einem Drittanbieter oder von Entwicklern in Ihrer Organisation erstellt wurden.

**Sicherheits- und Compliancefeatures:** Teams verfügt über eine breite Palette von Informationen, die Ihnen bei Compliancebereichen helfen, einschließlich Aufbewahrungsrichtlinien, Schutz vor Datenverlust (Data Loss Protection, DLP), eDiscovery und rechtlichem Haltebereich für Kanäle, Chats und Dateien, Überwachungsprotokollsuche. Weitere Informationen finden Sie unter [Sicherheit und Compliance in Microsoft Teams.](security-compliance-overview.md)  

> [!NOTE]
> Für die vorab benötigten eDiscovery-Features ist eine E5-Lizenzierung erforderlich.

[Vergleichen von Lizenzierungsoptionen](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).

Lesen [Sie Wie Exchange und Microsoft Teams interagieren,](exchange-teams-interact.md) um zu erfahren, welche Compliancefeatures in Ihrem Szenario verfügbar sind.

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>Organisationen **<span class="underline">ohne</span>** Skype for Business oder Lync Server

Dieser Ausgangspunkt setzt voraus, dass Ihre Organisation Skype for Business oder Lync Server derzeit nicht nutzt und Teams Ihre erste Anwendung in Microsoft 365 oder Office 365 ist. In der folgenden Tabelle werden die Konfiguration auf hoher Ebene und die Endbenutzerfunktionen für Teams für Kerndienste aufgeführt.

<table>
<thead>
<tr class="header">
<th>Element</th>
<th>Hinweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Konfiguration von Mandantenteams</td>
<td>Der Modus "Nur Teams" enthält alle Chat- und Anruffeatures nur in Teams.</td>
</tr>
<tr class="even">
<td>Chatten / Externe Kommunikation in Teams</td>
<td><p>Interne (interne Microsoft 365- oder Office 365-Organisation) und externe Chatkommunikation von Teams möglich.</p>
<p><em>Hinweis: DNS-Einträge müssen für den externen Zugriff konfiguriert sein. Skype for Business-DNS-Einträge sind erforderlich, auch wenn Sie nicht über Skype for Business lokal oder in Microsoft 365 oder Office 365 verfügen, um eine Verbindung mit Lync- und Skype for Business-Umgebungen zu ermöglichen:<br />
<a href="/office365/enterprise/external-domain-name-system-records">Externe Domänennamensystemeinträge</a></em></p></td>
</tr>
<tr class="odd">
<td>Erstellen und Anzeigen von Besprechungen in Teams</td>
<td><p>In der Lage, interne und externe Besprechungen über das Outlook-Add-In zu erstellen.</p>
<p>Die PstN-Ein- und Abwahlfunktion ist mit den Lizenzen für Audiokonferenzen verfügbar.</p>
<p>Für den Zugriff auf Den Kalender von Teams muss Exchange 2016 CU3+ lokal bereitgestellt werden, und die Exchange-Hybridbereitstellung wurde eingerichtet: Erstellen einer Hybridbereitstellung mit dem <a href="/exchange/hybrid-deployment/deploy-hybrid">Assistenten für Hybridkonfiguration.</a> </p>
<p>Richten Sie zusätzlich zur Exchange-Hybridkonfiguration die Exchange-OAuth-Authentifizierung ein: Konfigurieren der <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help"> OAuth-Authentifizierung zwischen Exchange- und Exchange Online-Organisationen".</p>

</p></td>
</tr>
<tr class="even">
<td>Anruffeatures<br />
VoIP /PSTN in Teams</td>
<td><p>VoIP intern und extern für den Mandanten ist verfügbar.</p>
<p>PSTN-Dienste können über Das Microsoft Phone System konfiguriert werden, außerdem können Sie einen Microsoft-Anrufplan oder ein Direktes Routing hinzufügen.</p></td>
</tr>
<tr class="odd">
<td>Zusammenarbeit von Teams und Kanälen in Teams</td>
<td><p>Für die vollständige Benutzererfahrung, einschließlich Compliancefeatures, muss dem Benutzer eine SharePoint Online-Lizenz zugewiesen werden.</p>
<p>Die Migration vorhandener lokal vorhandener SharePoint-Websites ist nicht erforderlich.</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (P2P-Dateifreigabe)</td>
<td>OneDrive for Business erfordert, dass einem Benutzer eine SharePoint #A0 zugewiesen ist. Ohne diese Lizenz ist die Peer-zu-Peer-Dateifreigabe nicht möglich.</td>
</tr>
<tr class="odd">
<td>Anwendungsplattform</td>
<td>Die Benutzer können die apps verwenden, die gemäß den Unternehmensrichtlinien für sie verfügbar sind.<br />
Weitere Informationen finden Sie hier: <a href="/microsoftteams/admin-settings">Administratoreinstellungen für Apps in Teams</a></td>
</tr>
<tr class="even">
<td>Sicherheits- und Compliancefeatures</td>
<td><ul>
<li><p>Aufbewahrungsrichtlinien sind verfügbar.</p></li>
<li><p>eDiscovery und Legal Hold für die Compliance für Kanalnachrichten werden unterstützt.</p></li>
<li><p>Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) sind verfügbar.</p></li>
</ul>
<p>Vollständiger Funktionssatz, der in Exchange Online verfügbar ist; Die meisten dieser Features werden von Exchange lokal unterstützt. Eine vollständige Liste finden Sie unter <a href="/MicrosoftTeams/exchange-teams-interact">So interagieren Exchange und Teams.</a></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>Aktivierungsschritte für Organisationen ohne Skype for Business oder Lync Server

1.  Erfüllen der Voraussetzungen im Abschnitt "Hier starten" oben

2.  Wechseln des Mandanten in den Modus "Nur Teams" (nur für vorhandene Mandanten): [Festlegen der Koexistenz- und Upgradeeinstellungen](setting-your-coexistence-and-upgrade-settings.md).

3.  Konfigurieren Sie Ihren Mandanten gemäß den Geschäfts-/Unternehmensrichtlinien Ihres Unternehmens: [Verwalten von Microsoft Teams-Einstellungen für Ihre Organisation.](enable-features-office-365.md)

4.  Bereitstellen des Teams-Clients für Ihre Benutzer: [Clients für Teams erhalten](get-clients.md)

5.  Starten Ihres Einführungsprogramms  
    [Einführen von Microsoft Teams](adopt-microsoft-teams-landing-page.md)
    
    [Prüfliste für den Schnellstart der Microsoft Teams-Einführung](teams-adoption-quick-start-checklist.md)

6.  Planen des Verschiebens anderer Arbeitslasten auf Microsoft 365 oder Office 365

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>Organisationen **<span class="underline">mit</span>** Skype for Business- oder Lync-Server

Bei diesem Ausgangspunkt wird davon ausgegangen, dass Ihre Organisation lokal Skype for Business 2019 oder 2015+ oder Lync 2013+-Server verwendet. Wir haben bereits umfassende Anleitungen für Organisationen, die von lokalen Servern zu Teams migrieren, und es sollte für diese Szenarien befolgt werden. Diese Anleitung gilt speziell für das Szenario, in dem Teams die erste Anwendung ist, die Sie in Microsoft 365 oder Office 365 verwenden. In der folgenden Tabelle werden die Konfiguration auf hoher Ebene und die Endbenutzerfunktionen für Teams für Kerndienste aufgeführt.

<table>
<thead>
<tr class="header">
<th>Element</th>
<th>Hinweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Konfiguration von Mandantenteams</td>
<td>Modus "Inseln".</td>
</tr>
<tr class="even">
<td>Chatten / Externe Kommunikation in Teams</td>
<td>Nur intern innerhalb Ihres eigenen Mandanten erfolgt die externe Kommunikation (Federation) über Ihre Skype for Business- oder Lync-Serverbereitstellung.</td>
</tr>
<tr class="odd">
<td>Erstellen und Anzeigen von Besprechungen in Teams</td>
<td><p>In der Lage, interne und externe Besprechungen über das Outlook-Add-In zu erstellen.</p>
<p>Die PstN-Ein- und Abwahlfunktion ist mit den Lizenzen für Audiokonferenzen verfügbar.</p>
<p>Für den Zugriff auf Den Kalender von Teams ist Exchange 2016 CU3+ lokal erforderlich, die mit einer Exchange-Hybridbereitstellung bereitgestellt wird:<br />
<a href="/exchange/hybrid-deployment/deploy-hybrid">Erstellen Sie eine Hybridbereitstellung mit dem Assistenten für Hybridkonfiguration.</a></p>
<p>Der Administrator kann das Skype for Business Outlook-Add-In über das PreferredMeetingProviderForIslandsMode-Attribut der Teams-Besprechungsrichtlinie steuern:<a href="/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy</a>.</p> 
</td>
</tr>
<tr class="even">
<td>Anruffeatures<br />
VoIP /PSTN in Teams</td>
<td><p>VoIP intern für den Mandanten ist verfügbar.</p>
<p>PstN- oder Anrufplandienste sind erst verfügbar, wenn der Benutzer in die Erfahrung nur für Teams verschoben wird.</p></td>
</tr>
<tr class="odd">
<td>Zusammenarbeit von Teams und Kanälen in Teams</td>
<td><p>Für die vollständige Benutzererfahrung, einschließlich Compliancefeatures, muss dem Benutzer eine SharePoint Online-Lizenz zugewiesen werden.</p>
<p>Die Migration vorhandener lokal vorhandener SharePoint-Websites ist nicht erforderlich.</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (P2P-Dateifreigabe)</td>
<td>OneDrive for Business erfordert, dass einem Benutzer eine SharePoint #A0 zugewiesen ist. Ohne diese Lizenz pro Peer ist die Dateifreigabe nicht möglich.</td>
</tr>
<tr class="odd">
<td>Anwendungsplattform</td>
<td>Die Benutzer können die apps verwenden, die gemäß den Unternehmensrichtlinien für sie verfügbar sind.<br />
Weitere Informationen finden Sie hier: <a href="/microsoftteams/admin-settings">Administratoreinstellungen für Apps in Teams</a></td>
</tr>
<tr class="even">
<td>Sicherheits- und Compliancefeatures</td>
<td><ul>
<li><p>Aufbewahrungsrichtlinien sind verfügbar.</p></li>
<li><p>eDiscovery und Legal Hold für die Compliance für Kanalnachrichten werden unterstützt.</p></li>
<li><p>Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) sind verfügbar.</p></li>
</ul>
<p>Vollständiger Funktionssatz, der in Exchange Online verfügbar ist; Die meisten dieser Features werden von Exchange lokal unterstützt. Eine vollständige Liste finden Sie unter <a href="/MicrosoftTeams/exchange-teams-interact">So interagieren Exchange und Teams.</a></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>Aktivierungsschritte für Organisationen mit Skype for Business Server  

1.  Erfüllen Sie die Voraussetzungen, die im Abschnitt "Hier beginnen" oben beschrieben sind.

2.  Wechseln des Mandanten in den Inselmodus (für Mandanten, die nach dem 01.09.2019 bereitgestellt wurden, wenden Sie sich an den Support, um diese Änderung zu ändern)  
    [Festlegen Ihrer Einstellungen für Koexistenz und Upgrades](setting-your-coexistence-and-upgrade-settings.md)

3.  Konfigurieren Ihres Mandanten gemäß den Geschäfts-/Unternehmensrichtlinien Ihres Unternehmens  
    [Verwalten von Microsoft Teams-Einstellungen in Ihrer Organisation](enable-features-office-365.md)

4.  Bereitstellen des Teams-Clients  
    [Beziehen von Clients für Teams](get-clients.md)

5.   Starten Ihres Einführungsprogramms  
    [Einführen von Microsoft Teams](adopt-microsoft-teams-landing-page.md)<br/>
    [Prüfliste für den Schnellstart der Microsoft Teams-Einführung](teams-adoption-quick-start-checklist.md)

6.  Planen des Verschiebens anderer Arbeitslasten auf Microsoft 365 oder Office 365

7.  Einrichten einer Skype for Business-Hybridlösung und Befolgen der empfohlenen Upgradepfade für Skype for Business- und Lync-Server  
    [Upgrade von Skype for Business lokal auf Teams](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>Schließende Anweisung

Microsoft Teams kann ein Enabler für Ihre Organisation sein, um alle Mitarbeiter, Informationsarbeiter und Frontlinemitarbeiter auf einer einzigen Plattform zusammenzubringen. Sie können [heute mit den ersten Schritte](https://products.office.com/microsoft-teams/group-chat-software) beginnen. Hier können Sie mit allen unseren neuesten Ankündigungen und monatlichen Produktupdates [in Kontakt bleiben.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)

Da Unternehmen auf der ganzen Welt die aktuelle COVID-19-Situation verwalten, haben wir außerdem eine Reihe von Inhalten erstellt, die Ihnen helfen, Teams für die größtmögliche Wirkung in Ihrer Organisation zu nutzen.

  - Unser [Engagement für Kunden während COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)

  - [2 Wochen in: Was wir über Remotearbeit gelernt haben](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [Bereitstellen von Onlinebesprechungen und -ereignissen](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [Unterstützung für kleine und mittelständische Unternehmen bei der Remotearbeit mit Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [Digitale Transformation von Liveereignissen: Bob Bejans Beobachtungen von der Frontlinie](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [Die 9 wichtigsten Methoden, mit denen Microsoft IT die Remotearbeit für die Mitarbeiter ermöglicht](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [Remotearbeit, Sicherheit – Tipps für ZISOS](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [Unterstützung von Lehrkräften und Schülern beim Umstieg auf Remotelernen](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [Bleiben Sie produktiv, während Sie remote mit Microsoft Teams arbeiten](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>Referenz zu Supportdiensten

Teams basiert auf Exchange Online, SharePoint Online, OneDrive for Business und Microsoft 365-Gruppen, um Ihren Benutzern eine voll integrierte Microsoft 365- oder Office 365-Erfahrung zu bieten. Wie oben erwähnt, funktioniert Teams ohne vollständige Bereitstellung dieser Dienste – mit eingeschränkten Funktionen. Weitere Informationen zu Teams und deren Voraussetzungen finden Sie hier: [Willkommen bei Teams.](teams-overview.md)

Spezifische Informationen zu den oben aufgeführten Diensten finden Sie unter den folgenden Links:

  - Exchange Online wird für Kalenderfunktionen und das Speichern von Peer-to-Peer-Nachrichten in Teams verwendet. Weitere Informationen finden Sie unter [So interagieren Exchange und Teams](exchange-teams-interact.md)

> [!IMPORTANT]
> Wenn Teams lokal mit Exchange in Verbindung stehen soll, müssen Sie das neue Exchange OAuth-Authentifizierungsprotokoll konfigurieren, wie unter Konfigurieren der OAuth-Authentifizierung zwischen Exchange- und [Exchange Online-Organisationen beschrieben.](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

  - SharePoint wird für die Dateifreigabe in Kanälen verwendet, während /OneDrive for Business für die Dateifreigabe in 1:1 oder im Gruppenchat verwendet wird. Weitere Informationen finden Sie unter [So interagieren SharePoint Online und OneDrive for Business mit Microsoft Teams.](sharepoint-onedrive-interact.md)

  - [Microsoft 365-Gruppen](office-365-groups.md) werden für die Team- und Kanalerstellung/-verwaltung verwendet.


## <a name="related-topics"></a>Verwandte Themen

[Microsoft Teams IT-Architektur- und Telefonielösungen Poster](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[Planen der Hybridkonnektivität zwischen Skype for Business Server und Office 365](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[Unterstützen von Remotemitarbeitern mit Teams](support-remote-work-with-teams.md)

[Remotearbeit mit Microsoft 365](https://aka.ms/remote-work)