---
title: Einführung von Microsoft Teams
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
description: Verwenden Sie diese Anleitungen, um Microsoft Teams als Ihre erste Microsoft 365- oder Office 365-Arbeitsauslastung zu verwenden.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: a30d5bed9443df3077ab7384cd8266d2f049148d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909479"
---
# <a name="roll-out-microsoft-teams-first"></a>Einführung von Microsoft Teams

Microsoft Teams kann Ihren Mitarbeitern helfen, in Verbindung zu bleiben und miteinander zusammenzuarbeiten, insbesondere in der aktuell beispiellosen Zeit, in der Remotearbeit eine Realität von Mitarbeitern auf der ganzen Welt ist. Wenn Sie in Teams chatten, Videobesprechungen anberaumen und an Office-Dokumenten zusammenarbeiten, können Sie Unternehmen dabei helfen, produktiv zu bleiben. Ganz gleich, ob Sie ein kleines Unternehmen, eine gemeinnützige Organisation oder eine große Organisation sind, Sie können mit Teams als erste Arbeitsauslastung innerhalb der Microsoft 365- oder Office 365-Suite beginnen, bevor Sie eine andere Office-App oder einen anderen Dienst bereitstellen.

In diesem Artikel werden die Überlegungen erläutert, die Sie mit dem Ansatz "Teams First" berücksichtigen müssen.

> [!IMPORTANT]
> Teams kann zwar die erste in der Cloud bereitgestellte Arbeitsauslastung Ihrer Organisation sein, aber die Bereitstellung von Teams sollte Teil Ihrer gesamten Cloudbereitstellungsstrategie sein.

Wenn Sie bereits ein Rollout anderer Microsoft 365- oder Office 365-Dienste durchgeführt haben und Teams Ihre nächste Arbeitsauslastung ist ( statt der ersten), beginnen Sie mit dem Rollout von [Teams.](How-to-roll-out-teams.md)

## <a name="start-here"></a>Hier geht’s los

Für die ersten Schritte mit Ihrer Bereitstellung von Teams müssen Sie mindestens einige Voraussetzungen erfüllen. Die folgende Liste zeigt, was sie für Ihre Organisation an Ort und Stelle haben muss, bevor Teams aktiviert werden kann:

1.  Eine Mit Ihrem Domänennamen konfigurierte Microsoft 365- oder Office 365-Organisation

2.  Azure Active Directory-Konnektivität (AAD Connect) oder ähnliche Cloudidentitätssynchronisierungslösung – mit allen erforderlichen Attributen, die mit Ihrem Mandanten synchronisiert werden  
    Informationen zu den mit der AAD-Synchronisierung synchronisierten Attributen finden Sie unter [Azure AD Connect-Synchronisierung: Mit Azure Active Directory synchronisierte Attribute](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)

3.  Für Teams zugewiesene geeignete Benutzerlizenzen  
    Informationen zur Lizenzierung von Microsoft Teams finden Sie in [der Beschreibung des Microsoft Teams-Diensts.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

4.  Organisationsnetzwerk für Teams vorbereitet  
    Informationen zur Netzwerkvorbereitung erhalten Sie unter "Vorbereiten des Netzwerks [Ihrer Organisation für Teams".](prepare-network.md)

5.  Netzwerkzugriff auf Exchange, SharePoint und OneDrive for Business in Microsoft 365 oder Office 365 zulassen: URLs und #A0 von [Office 365.](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)

> [!NOTE]
> Mandanten, die nach dem 1. September 2019 erstellt wurden, werden im Nur-Teams-Modus bereitgestellt.
> 
> [!IMPORTANT]
> Wenn Sie Skype for Business Server bereitgestellt haben und Ihr Mandant nach dem 1. September 2019 bereitgestellt wurde, wenden Sie sich bitte an den Support, um Koexistenzfunktionen für Teams zu aktivieren. Stellen Sie sicher, dass Ihre "Organisationsweite Upgraderichtlinie" auf "Inselmodus" <span class="underline"></span> festgelegt ist, bevor Sie einem Benutzer Lizenzen für Teams zuweisen.

## <a name="migration-starting-points"></a>Ausgangspunkte der Migration

Ihr Weg zu Microsoft 365 oder Office 365 und den in Teams verfügbaren Features hängt von Ihrem Ausgangspunkt und dem Vorhandensein eines lokalen Skype for Business- oder Lync -Servers ab. In den folgenden Abschnitten werden zusätzlich zu den vorstehenden Voraussetzungen grundlegende Funktionen und Konfigurationsoptionen aufgeführt. Wir haben die Ausgangsszenarien in die folgenden Themen gebrochen:

**Konfiguration von Mandantenteams:** Mandanten- und Benutzermodi werden verwendet, um das Verhalten des Empfängers zu steuern. Diese Einstellungen können auf Mandanten- oder Benutzerebene in einer Organisation zugewiesen werden. Weitere Informationen finden Sie unter ["Koexistenz mit Skype for Business".](coexistence-chat-calls-presence.md)

**Chat/Externe Kommunikation in Teams:** Chatdienste beziehen sich auf Peer-zu Peer- oder Gruppenchatunterhaltungen innerhalb und organisation bzw. extern in der Organisation. Externe Kommunikation wird in Skype for Business auch als Verbund bezeichnet.

**Erstellen und Anzeigen von** Besprechungen in Teams: Ein Benutzer kann immer Onlinebesprechungen über das Outlook Teams-Add-In erstellen, und das PstN-Einwählen ist in allen Szenarien verfügbar, sobald der Benutzer über eine Lizenz verfüge. In Teams und Skype for Business werden Kalenderinformationen im Exchange-Postfach des Benutzers gespeichert. Der lokale Exchange Server muss Exchange Server 2016 CU3 oder höher ausgeführt werden, damit der Teamclient mit dem Postfach des Benutzers interagieren kann. Ohne Zugriff auf das Exchange-Postfach wird das Kalendersymbol in Teams nicht angezeigt, und die Benutzer können keine Besprechungen im Teamclient anzeigen, erstellen oder ändern.

**Anruffeatures VoIP/PSTN in Teams:** Anrufe können VoIP (Voice over IP) oder PstN (Public Switched Telephone Network) sein. Die VoIP-Konnektivität erfolgt systemeigene zwischen Teams-Clients, während die PSTN-Konnektivität erfolgt, wenn ein Benutzer eine externe Telefonnummer wählt.  

Teams unterstützen zwei Arten von PSTN-Konnektivität. Microsoft Calling Plan, when Microsoft provides telephony infrastructure including the phone number for a user, or Direct Routing configuration, where the customer provides the telephony connectivity over a Session Border Controller (SBC) for the Teams user.  
Weitere Informationen finden Sie unter ["Welcher Anrufplan ist für](calling-plan-landing-page.md) Sie am richtigen?" und ["Direktes Telefonsystem-Routing".](direct-routing-landing-page.md)

**Zusammenarbeit in** Teams und Kanälen: In Teams sind Teams Gruppen von Personen, die für die Arbeit, für Projekte oder für gemeinsame Interessen zusammenarbeiten. Teams besteht aus Kanälen. Jeder Kanal ist um ein Thema herum aufgebaut, z. B. "Teamereignisse", ein Abteilungsname oder nur zum Spaß. In Kanälen können Sie Besprechungen halten, Unterhaltungen führen und gemeinsam an Dateien arbeiten. Während der Zusammenarbeit

**OneDrive for Business (P2P-Dateifreigabe) in Teams:** Außerhalb von Teams und Kanälen können #A0 Dateien mithilfe von OneDrive for Business oder anderen #A1 für die Freigabe von Dateien wie Etwa -Dateien, DropBox, Box und Google Drive freigeben. Für OneDrive for Business muss einem Benutzer eine SharePoint #A0 zugewiesen sein.

**Anwendungsplattform:** Apps stellen bereits Einsatztools für Ihre Organisation bereit, um Teams besser nutzen zu können. Diese Apps kombinieren die Funktionalität von Registerkarten, Messaging-Erweiterungen, Connectors und Bots, die von Microsoft, von Drittanbietern oder von Entwicklern in Ihrer Organisation entwickelt wurden, bereitgestellt werden.

**Sicherheits- und Compliancefeatures:** Teams bietet eine Breite Palette von Informationen, die Ihnen in Compliancebereichen helfen, darunter Aufbewahrungsrichtlinien, Schutz vor Datenverlust (Data Loss Protection, DLP), eDiscovery und gesetzliche Aufbewahrung für Kanäle, Chats und Dateien, Überwachungsprotokollsuche. Weitere Informationen finden Sie unter ["Sicherheit und Compliance in Microsoft Teams".](security-compliance-overview.md)  

> [!NOTE]
> Für advance eDiscovery-Features ist eine E5-Lizenzierung erforderlich.

[Vergleichen Sie die Lizenzierungsoptionen.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)

Lesen [Sie, wie Exchange und Microsoft Teams interagieren,](exchange-teams-interact.md) um zu erfahren, welche Compliancefeatures in Ihrem Szenario verfügbar sind.

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>Organisationen **<span class="underline">ohne</span>** Skype for Business oder Lync Server

Bei diesem Ausgangspunkt wird davon ausgegangen, dass Ihre Organisation Skype for Business oder Lync Server derzeit nicht nutzt und Teams Ihre erste Anwendung in Microsoft 365 oder Office 365 ist. In der folgenden Tabelle sind die Funktionen für die Konfiguration auf hoher Ebene und die Endbenutzerfunktionen für Teams für die wichtigsten Dienste aufgeführt.

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
<td>Nur-Teams-Modus, alle Chat- und Anruffeatures sind nur in Teams verfügbar.</td>
</tr>
<tr class="even">
<td>Chat/ Externe Kommunikation in Teams</td>
<td><p>Interne Kommunikation (innerhalb einer Microsoft 365- oder Office 365-Organisation) und Kommunikation mit externen Chats, die über Teams möglich ist.</p>
<p><em>Hinweis: Die DNS-Einträge müssen für den externen Zugriff konfiguriert werden. Skype for Business-DNS-Einträge sind erforderlich, auch wenn Sie Skype for Business nicht lokal oder in Microsoft 365 oder Office 365 nicht installiert haben, um einen Verbund mit Lync- und Skype for Business-Umgebungen zu ermöglichen:<br />
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">Externe Domain Name System-Einträge</a></em></p></td>
</tr>
<tr class="odd">
<td>Erstellen und Anzeigen von Besprechungen in Teams</td>
<td><p>Sie können interne und externe Besprechungen über das Outlook-Add-In erstellen.</p>
<p>Die Funktion "PstN-Einwahl" und "Auswählen" ist mit den Lizenzen für Audiokonferenzen verfügbar.</p>
<p>Der Zugriff auf den Kalender in Teams setzt Exchange 2016 CU3+ voraus, das mit einer eingerichteten Exchange-Hybridbereitstellung bereitgestellt wird: Erstellen einer Hybridbereitstellung mit dem <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Hybridkonfigurations-Assistenten.</a> </p>
<p>Richten Sie zusätzlich zur Exchange-Hybridkonfiguration die Exchange-OAuth-Authentifizierung ein: Konfigurieren der <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help"> OAuth-Authentifizierung zwischen Exchange und Exchange Online-Organisationen".</p>

</p></td>
</tr>
<tr class="even">
<td>Anruffeatures<br />
VoIP/PSTN in Teams</td>
<td><p>Interne und externe VoIP für den Mandanten ist verfügbar.</p>
<p>PstN-Dienste können über das Microsoft Phone System konfiguriert werden und zusätzlich einen Anrufplan von Microsoft oder direktes Routing hinzufügen.</p></td>
</tr>
<tr class="odd">
<td>Zusammenarbeit an Teams und Kanälen in Teams</td>
<td><p>Für eine vollständige Erfahrung, einschließlich Compliancefunktionen, muss dem Benutzer eine SharePoint Online-Lizenz zugewiesen werden.</p>
<p>Die Migration von vorhandenen lokalen SharePoint-Websites ist nicht erforderlich.</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (P2P-Dateifreigabe)</td>
<td>OneDrive for Business erfordert, dass einem Benutzer eine SharePoint #A0 zugewiesen ist. Ohne diese Lizenz ist die Peer-zu-Peer-Dateifreigabe nicht möglich.</td>
</tr>
<tr class="odd">
<td>Anwendungsplattform</td>
<td>Benutzer können die Apps verwenden, die gemäß den Richtlinien Ihres Unternehmens für sie verfügbar sind.<br />
Weitere Informationen finden Sie hier: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Administratoreinstellungen für Apps in Teams</a></td>
</tr>
<tr class="even">
<td>Sicherheits- und Compliancefeatures</td>
<td><ul>
<li><p>Aufbewahrungsrichtlinien sind verfügbar.</p></li>
<li><p>eDiscovery und gesetzliches Halten von Compliance für Kanalnachrichten werden unterstützt.</p></li>
<li><p>Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) sind verfügbar.</p></li>
</ul>
<p>Vollständiger Featuresatz, der in Exchange Online verfügbar ist; Die meisten dieser Features werden von der lokalen Exchange-Version unterstützt. Eine vollständige Liste finden Sie unter <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">"Interaktion von Exchange und Teams".</a></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>Aktivierungsschritte für Organisationen ohne Skype for Business oder Lync Server

1.  Voraussetzungen erfüllen, die oben im Abschnitt "Start hier" beschrieben sind

2.  Wechseln Des Mandanten in den Modus "Nur für Teams" (nur für vorhandene [Mandanten): Festlegen der Koexistenz- und Upgradeeinstellungen.](setting-your-coexistence-and-upgrade-settings.md)

3.  Konfigurieren Sie Ihren Mandanten gemäß den Geschäfts-/Unternehmensrichtlinien Ihres Unternehmens: Verwalten Sie [die Microsoft Teams-Einstellungen für Ihre Organisation.](enable-features-office-365.md)

4.  Bereitstellen des Teams-Clients für Ihre Benutzer: [Kunden für Teams erhalten](get-clients.md)

5.  Starten Sie Ihr Einführungsprogramm  
    [Einführen von Microsoft Teams](adopt-microsoft-teams-landing-page.md)
    
    [Prüfliste für den Schnellstart der Microsoft Teams-Einführung](teams-adoption-quick-start-checklist.md)

6.  Beginnen Sie mit der Planung des Verschiebens anderer Arbeitslasten nach Microsoft 365 oder Office 365

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>Organisationen **<span class="underline">mit</span>** Skype for Business- oder Lync Server

Bei diesem Ausgangspunkt wird davon ausgegangen, dass Ihre Organisation lokal Skype for Business 2019 oder 2015+ oder Lync 2013+ verwendet. Wir verfügen bereits über umfassende Anleitungen für Organisationen, die von lokalen Servern zu Teams migrieren, und sie sollten für diese Szenarien befolgt werden. Dieser Leitfaden ist spezifisch für das Szenario, in dem Teams die erste Anwendung ist, die Sie in Microsoft 365 oder Office 365 verwenden. In der folgenden Tabelle sind die Funktionen für die Konfiguration auf hoher Ebene und die Endbenutzerfunktionen für Teams für die wichtigsten Dienste aufgeführt.

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
<td>"Islands-Modus" aus.</td>
</tr>
<tr class="even">
<td>Chat/ Externe Kommunikation in Teams</td>
<td>Nur intern innerhalb Ihres eigenen Mandanten erfolgt die externe Kommunikation (Verbund) über Ihre Skype for Business- oder Lync Server-Bereitstellung.</td>
</tr>
<tr class="odd">
<td>Erstellen und Anzeigen von Besprechungen in Teams</td>
<td><p>Sie können interne und externe Besprechungen über das Outlook-Add-In erstellen.</p>
<p>Die Funktion zum Ein- und Abwählen über das Festnetz ist mit den Lizenzen für Audiokonferenzen verfügbar.</p>
<p>Der Zugriff auf den Kalender in Teams setzt Exchange 2016 CU3+ voraus, das mit einer eingerichteten Exchange-Hybridbereitstellung bereitgestellt wird:<br />
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Erstellen Sie eine Hybridbereitstellung mit dem Hybridkonfigurations-Assistenten.</a></p>
<p>Der Administrator kann das Skype for Business Outlook-Add-In über das Attribut "PreferredMeetingProviderForIslandsMode" der Besprechungsrichtlinie steuern:<a href="https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy.</a></p> 
</td>
</tr>
<tr class="even">
<td>Anruffeatures<br />
VoIP/PSTN in Teams</td>
<td><p>Interne VoIP für den Mandanten ist verfügbar.</p>
<p>PstN- oder Anrufplandienste sind erst verfügbar, wenn der Benutzer in die Teams Only Experience verschoben wird.</p></td>
</tr>
<tr class="odd">
<td>Zusammenarbeit an Teams und Kanälen in Teams</td>
<td><p>Für eine vollständige Erfahrung, einschließlich Compliancefunktionen, muss dem Benutzer eine SharePoint Online-Lizenz zugewiesen werden.</p>
<p>Die Migration von vorhandenen lokalen SharePoint-Websites ist nicht erforderlich.</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (P2P-Dateifreigabe)</td>
<td>OneDrive for Business erfordert, dass einem Benutzer eine SharePoint #A0 zugewiesen ist. Ohne diese Lizenz für die Peer-zu-Peer-Dateifreigabe ist keine Freigabe möglich.</td>
</tr>
<tr class="odd">
<td>Anwendungsplattform</td>
<td>Benutzer können die Apps verwenden, die gemäß den Richtlinien Ihres Unternehmens für sie verfügbar sind.<br />
Weitere Informationen finden Sie hier: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Administratoreinstellungen für Apps in Teams</a></td>
</tr>
<tr class="even">
<td>Sicherheits- und Compliancefeatures</td>
<td><ul>
<li><p>Aufbewahrungsrichtlinien sind verfügbar.</p></li>
<li><p>eDiscovery und gesetzliches Halten von Compliance für Kanalnachrichten werden unterstützt.</p></li>
<li><p>Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) sind verfügbar.</p></li>
</ul>
<p>Vollständiger Featuresatz, der in Exchange Online verfügbar ist; Die meisten dieser Features werden von der lokalen Exchange-Version unterstützt. Eine vollständige Liste finden Sie unter <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">"Interaktion von Exchange und Teams".</a></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>Aktivierungsschritte für Organisationen mit Skype for Business Server  

1.  Erfüllen Sie die Voraussetzungen im vorstehenden Abschnitt "Hier beginnen".

2.  Wechseln des Mandanten in den Islands-Modus (für Mandanten, die nach dem 01.09.2019 bereitgestellt werden, wenden Sie sich bitte an den Support, um diese Änderung zu ändern)  
    [Festlegen Ihrer Einstellungen für Koexistenz und Upgrades](setting-your-coexistence-and-upgrade-settings.md)

3.  Konfigurieren Des Mandanten gemäß den Geschäfts-/Unternehmensrichtlinien Ihres Unternehmens  
    [Verwalten von Microsoft Teams-Einstellungen in Ihrer Organisation](enable-features-office-365.md)

4.  Bereitstellen des Teams-Clients  
    [Beziehen von Clients für Teams](get-clients.md)

5.   Starten Sie Ihr Einführungsprogramm  
    [Einführen von Microsoft Teams](adopt-microsoft-teams-landing-page.md)<br/>
    [Prüfliste für den Schnellstart der Microsoft Teams-Einführung](teams-adoption-quick-start-checklist.md)

6.  Beginnen Sie mit der Planung des Verschiebens anderer Arbeitslasten nach Microsoft 365 oder Office 365

7.  Einrichten einer Skype for Business-Hybridbereitstellung und Folgen der empfohlenen Upgradepfade für Skype for Business- und Lync-Server  
    [Upgrade von der lokalen Skype for Business-Version auf Teams](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>Abschlusserklärung

Microsoft Teams kann eine Möglichkeit für Ihre Organisation sein, alle Mitarbeiter, Informationsarbeiter und Mitarbeiter in der Frontline auf einer einzigen Plattform zusammenzubringen. Sie können [noch heute beginnen.](https://products.office.com/microsoft-teams/group-chat-software) Hier können Sie mit allen unseren neuesten Ankündigungen und monatlichen Produktupdates in Kontakt [bleiben.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)

Darüber hinaus haben wir, da Unternehmen auf der ganzen Welt die aktuelle CoVID-19-Situation verwalten, eine Reihe von Inhalten erstellt, die Ihnen helfen, Teams für die größtmögliche Wirkung in Ihrer Organisation zu nutzen.

  - Unser [Engagement für Kunden während COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)

  - [2 Wochen in diesem Thema: Was wir über Remotearbeit gelernt haben](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [Onlinebesprechungen und -ereignisse](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [Unterstützung für kleine und mittelständische Unternehmen bei der Remotearbeit mit Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [Digitale Transformation von Liveereignissen: Beobachtungen von Bob Bejan von der Frontlinie](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [Die 9 wichtigsten Methoden, mit denen Microsoft IT die Remotearbeit für die Mitarbeiter ermöglicht](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [Remote arbeiten, Sicherheit gewährleisten – Tipps für IHNEN](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [Helfen von Lehrkräften und Schülern beim Umstieg auf Fernunterricht](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [Bleiben Sie produktiv, während Sie remote mit Microsoft Teams arbeiten](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>Referenz zu Supportdiensten

Teams basiert auf Exchange Online, SharePoint Online, OneDrive for Business und Microsoft 365-Gruppen, um Ihren Benutzern eine vollständig integrierte Microsoft 365- oder Office 365-Benutzererfahrung zu bieten. Wie oben erwähnt, funktioniert Teams ohne vollständige Bereitstellung dieser Dienste – mit eingeschränkten Funktionen. Weitere Informationen zu Teams und deren Voraussetzungen finden Sie hier: [Willkommen bei Teams.](teams-overview.md)

Spezifische Informationen zu den oben aufgeführten Diensten finden Sie unter den folgenden Links:

  - Exchange Online wird zum Speichern von Kalenderfeatures und zum Speichern von Peer-to-Peer-Nachrichten in Teams verwendet. Weitere Informationen finden Sie unter ["Interaktion von Exchange und Teams"](exchange-teams-interact.md)

> [!IMPORTANT]
> Für die Inaktivität von Teams mit der lokalen Exchange-Authentifizierung müssen Sie das neue Exchange -OAuth-Authentifizierungsprotokoll konfigurieren, wie unter "Konfigurieren der OAuth-Authentifizierung zwischen Exchange- und [Exchange Online-Organisationen" beschrieben.](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

  - SharePoint wird für die Dateifreigabe in Kanälen verwendet, während /OneDrive for Business für die Dateifreigabe in 1:1- oder Gruppenchats verwendet wird. Weitere Informationen finden Sie unter ["Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams".](sharepoint-onedrive-interact.md)

  - [Microsoft 365-Gruppen](office-365-groups.md) werden für die Team- und Kanalerstellung/-verwaltung verwendet.


## <a name="related-topics"></a>Verwandte Themen

[Microsoft Teams IT-Architektur- und Telefonielösungen Poster](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[Planen der Hybridkonnektivität zwischen Skype for Business Server und Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[Unterstützen von Remotemitarbeitern mithilfe von Teams](support-remote-work-with-teams.md)

[Remote arbeiten mit Microsoft 365](https://aka.ms/remote-work)
