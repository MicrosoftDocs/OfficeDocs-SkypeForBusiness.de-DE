---
title: Microsoft Teams zuerst Ausrollen
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
description: Verwenden Sie diese Anleitung, um Microsoft Teams als erste Office 365-Arbeitsauslastung zu verwenden.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2cd8fc92d3f46df8bcfaa07a96b69b84790750aa
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44041712"
---
# <a name="roll-out-microsoft-teams-first"></a>Microsoft Teams zuerst Ausrollen

Microsoft Teams können Ihren Mitarbeitern helfen, in Verbindung zu bleiben und miteinander zusammenzuarbeiten, insbesondere in der aktuellen, noch nie dagewesenen Zeit, in der Remote-Arbeit eine Realität von Mitarbeitern in aller Welt ist. Die Möglichkeit zum chatten, für Videobesprechungen und für die Zusammenarbeit an Office-Dokumenten innerhalb von Teams kann Unternehmen dabei helfen, produktiv zu bleiben. Unabhängig davon, ob Sie ein kleines Unternehmen, eine gemeinnützige Organisation oder eine große Organisation sind, können Sie die ersten Schritte mit Microsoft Teams als erste Arbeitsauslastung in Office 365 Suite ausführen, bevor Sie eine andere Office-App oder einen anderen Dienst bereitstellen.

In diesem Artikel werden die Überlegungen erläutert, die Sie mit dem Ansatz "Teams First" vornehmen müssen.

> [!IMPORTANT]
> Während Teams die erste in der Cloud bereitgestellte Arbeitsauslastung in Ihrer Organisation sein können, sollten die Bereitstellung von Teams Teil ihrer allgemeinen Cloud-Bereitstellungsstrategie sein.

Wenn Sie bereits andere Office 365-Dienste und-Teams für die nächste Arbeitsauslastung bereitstellen (statt der ersten), beginnen Sie mit dem [Rollout von Teams](How-to-roll-out-teams.md).

## <a name="start-here"></a>Hier geht’s los

Für den Einstieg in die erste Bereitstellung Ihrer Teams müssen Sie mindestens einige Voraussetzungen erfüllen. In der folgenden Liste wird gezeigt, was für Ihre Organisation vorhanden sein muss, bevor Teams aktiviert werden können:

1.  Eine Office 365-Organisation, die mit Ihrem Domänennamen konfiguriert ist

2.  Azure Active Directory Connectivity (AAD Connect) oder ähnliche Cloud Identity Sync-Lösung – mit allen erforderlichen Attributen, die mit Ihrem Mandanten synchronisiert sind  
    Informationen zu den mit der Aad-Synchronisierung synchronisierten Attributen finden Sie unter [Azure AD Connect-Synchronisierung: Attribute, die mit Azure Active Directory synchronisiert](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized) werden.

3.  Für Teams zugewiesene Benutzerlizenzen  
    Wenn Sie die Lizenzierung von Teams verstehen möchten, lesen Sie [Microsoft Teams-Dienstbeschreibung](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).

4.  Netzwerk der Organisation für Teams vorbereitet  
    Wenn Sie die Netzwerk Vorbereitung verstehen möchten, lesen Sie [Vorbereiten des Netzwerks Ihrer Organisation für Teams](prepare-network.md).

5.  Erlauben Sie den Netzwerkzugriff auf Exchange, SharePoint und OneDrive for Business in Office 365: [Office 365-URLs und IP-Adressbereiche](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).

> [!NOTE]
> Mandanten, die nach dem 1. September 2019 erstellt wurden, werden im Modus "nur für Teams" bereitgestellt.
> 
> [!IMPORTANT]
> Wenn Sie über Skype for Business Server verfügen und Ihr Mandant nach dem 1. September 2019 bereitgestellt wurde, wenden Sie sich bitte an den Support, um koexistenzfunktionen für Teams zu ermöglichen. Stellen Sie sicher, dass Ihre "organisationsweite Upgrade-Richtlinie" auf "inselmodus" gesetzt ist, <span class="underline">bevor</span> Sie einem Benutzer Teams-Lizenzen zuweisen.

## <a name="migration-starting-points"></a>Migrations Ausgangspunkte

Ihre Reise zu Office 365 und Features, die in Teams je nach Ausgangspunkt und vorhanden sein von Skype for Business-oder lync Server-Räumlichkeiten verfügbar sind. In den folgenden Abschnitten werden die grundlegenden Funktionen und Konfigurationsoptionen zusätzlich zu den oben genannten Voraussetzungen ausführlich erläutert. Wir haben die Ausgangs Szenarien für die folgenden Themen aufgeschlüsselt:

**Mandanten Teams-Konfiguration**: Mandanten-und Benutzermodi werden verwendet, um das Verhalten des Empfängers zu steuern. Diese Einstellungen können auf der Mandantenebene oder auf der Benutzerebene einer Organisation zugewiesen werden. Weitere Informationen finden Sie unter [Koexistenz mit Skype for Business](coexistence-chat-calls-presence.md).

**Chat/externe Kommunikation in Teams**: Chat Dienste beziehen sich auf Peer-to-Peer-oder Gruppen-Chat Unterhaltungen innerhalb und Organisation oder extern an die Organisation. Externe Kommunikation wird auch als "Föderation" in Skype for Business bezeichnet.

**Erstellen und Anzeigen von Besprechungen in Teams**: ein Benutzer kann immer Onlinebesprechungen über das Outlook Teams-Add-in erstellen, und die PSTN-Einwahl ist in allen Szenarien verfügbar, nachdem der Benutzer lizenziert wurde. Teams und Skype for Business speichern Kalenderinformationen im Exchange-Postfach des Benutzers. Auf dem lokalen Exchange-Server muss Exchange Server 2016 CU3 oder höher sein, damit der Team-Client mit dem Postfach des Benutzers interagieren kann. Ohne Zugriff auf Exchange-Postfächer das Kalendersymbol in Teams wird nicht angezeigt, und der Benutzer kann keine Besprechungen im Team-Client anzeigen, erstellen oder ändern.

**Anruffunktionen VoIP/PSTN in Teams**: Anrufe können VoIP (Voice over IP) oder PSTN (Public Switched Telephone Network) sein. VoIP-Konnektivität erfolgt nativ zwischen Teams-Clients, während PSTN-Konnektivität eintritt, wenn ein Benutzer eine externe Telefonnummer anwählt.  

Teams unterstützen zwei Arten von PSTN-Konnektivität. Microsoft-Anrufplan, wenn Microsoft eine Telefonie-Infrastruktur einschließlich der Telefonnummer für einen Benutzer oder eine direkte Routing Konfiguration bereitstellt, in der der Kunde die telefonieverbindung über einen Session Border Controller (SBC) für den Teams-Benutzer bereitstellt.  
Wenn Sie mehr darüber erfahren möchten, lesen Sie, [welcher Anrufplan für Sie die richtige ist?](calling-plan-landing-page.md) und [Direktes Routing für Telefonsysteme](direct-routing-landing-page.md).

**Zusammenarbeit in Teams und Kanälen in Teams**: Teams sind Gruppen von Personen, die für Arbeit, Projekte oder gemeinsame Interessen zusammengeführt werden. Teams bestehen aus Kanälen. Jeder Kanal basiert auf einem Thema, wie "Team-Events", einem Abteilungsnamen oder einfach nur zum Spaß. Kanäle sind die Orte, an denen Sie Besprechungen abhalten, Konversationen führen und an Dateien zusammenarbeiten können. Während der Zusammenarbeit

**OneDrive for Business (P2P-Dateifreigabe) in Teams**: außerhalb von Teams und Kanälen können Benutzer von Teams Peer-to-Peer-Dateien mit OneDrive for Business oder anderen P2P-Freigabe Datei Programmen wie Citrix-Dateien, Dropbox, Box und Google Drive freigeben. Für OneDrive for Business muss einem Benutzer die SharePoint Online-Lizenz zugewiesen sein.

**Anwendungsplattform**: Apps bieten integrierte Tools für Ihre Organisation, um die Teams optimal zu nutzen. Diese apps kombinieren die Funktionalität von Registerkarten, Messaging Erweiterungen, Connectors und Bots, die von Microsoft bereitgestellt werden, die von einem Drittanbieter oder von Entwicklern in Ihrer Organisation erstellt wurden.

**Sicherheits-und Compliance-Features:** Teams verfügt über eine breite Palette von Informationen, die Ihnen bei Compliance-Bereichen helfen, darunter Aufbewahrungsrichtlinien, Datenverlust Schutz (DLP), eDiscovery und rechtliche Aufbewahrung für Kanäle, Chats und Dateien, Überwachungsprotokoll Suche. Weitere Informationen finden Sie unter [Sicherheit und Compliance in Microsoft Teams](security-compliance-overview.md).  

> [!NOTE]
> Voraus-eDiscovery-Features erfordern E5-Lizenzierung.

[Vergleichen von Lizenzierungsoptionen](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)

Lesen Sie, [wie Exchange und Microsoft Teams interagieren](exchange-teams-interact.md) , um zu erfahren, welche Kompatibilitätsfeatures in Ihrem Szenario zur Verfügung stehen.

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>Organisationen **<span class="underline">ohne</span>** Skype for Business oder lync Server

Bei diesem Ausgangspunkt wird davon ausgegangen, dass Ihre Organisation Skype for Business oder lync Server zurzeit nicht verwendet und Teams ihre erste Anwendung in Office 365 sein werden. In der folgenden Tabelle sind die Funktionen für Konfiguration und Endbenutzer auf hoher Ebene für Teams für Core Services detailliert beschrieben.

<table>
<thead>
<tr class="header">
<th>Element</th>
<th>Hinweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Mandanten Teams-Konfiguration</td>
<td>Nur für Teams, alle Chat-und Anruffunktionen sind nur in Teams verfügbar</td>
</tr>
<tr class="even">
<td>Chat/externe Kommunikation in Teams</td>
<td><p>Interne (Intra Office 365 Organization) und externe Chat Kommunikation von Teams aus möglich</p>
<p><em>Hinweis: DNS-Einträge müssen für den externen Zugriff konfiguriert sein. Skype for Business-DNS-Einträge werden benötigt, auch wenn Sie nicht über Skype for Business lokal oder in Office 365 verfügen, um eine Föderation mit lync-und Skype for Business-Umgebungen zu ermöglichen.<br />
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">Externe Domänennamen-System Einträge für Office 365</a></em></p></td>
</tr>
<tr class="odd">
<td><em>Erstellen und Anzeigen von Besprechungen in Teams</em></td>
<td><p><em>Möglichkeit zum Erstellen von Besprechungen über das Outlook-Add-in</em></p>
<p><em>Die PSTN-Wähl-und-Wählfunktion ist mit den Audiokonferenz-Lizenzen verfügbar.<br />
Hinweis: der Zugriff auf den Kalender von Teams erfordert Exchange 2016 CU3 + lokal bereitgestellt mit Exchange-Hybrid <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Einrichtung: Erstellen einer hybridbereitstellung mit dem Hybrid-Konfigurations-Assistenten</a><br />
Zusätzlich zur Exchange-Hybrid Konfiguration müssen Sie die Exchange-OAuth-Authentifizierung einrichten: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Konfigurieren der OAuth-Authentifizierung zwischen Exchange und Exchange Online-Organisationen</a></em></p></td>
</tr>
<tr class="even">
<td>Anruffunktionen<br />
VoIP/PSTN in Teams</td>
<td><p>VoIP intern und extern für den Mandanten verfügbar</p>
<p>PSTN-Dienste können über das Microsoft Phone-System konfiguriert werden sowie einen Microsoft-Anrufplan oder ein direktes Routing hinzufügen.</p></td>
</tr>
<tr class="odd">
<td>Zusammenarbeit in Teams und Kanälen in Teams</td>
<td><p>Für die vollständige Nutzung, einschließlich der Kompatibilitätsfeatures, muss dem Benutzer eine SharePoint Online-Lizenz zugewiesen werden.</p>
<p>Die Migration vorhandener lokales SharePoint-Websites ist nicht erforderlich.</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (P2P-Dateifreigabe)</td>
<td>Für OneDrive for Business muss ein Benutzer eine SharePoint Online-Lizenz zuweisen. Ohne diese Lizenz ist eine Peer-to-Peer-Dateiübertragung nicht möglich.</td>
</tr>
<tr class="odd">
<td>Anwendungsplattform</td>
<td>Die Benutzer können die für Sie verfügbaren apps entsprechend den Richtlinien Ihres Unternehmens verwenden.<br />
Weitere Informationen finden Sie hier: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Administratoreinstellungen für apps in Microsoft Teams</a></td>
</tr>
<tr class="even">
<td>Features für Sicherheit und Compliance</td>
<td><ul>
<li><p>Aufbewahrungsrichtlinien sind verfügbar</p></li>
<li><p>eDiscovery und rechtliche Aufbewahrung für Compliance bei Kanal Nachrichten werden unterstützt</p></li>
<li><p>Datenverlust-Präventions Richtlinien (DLP) sind verfügbar</p></li>
</ul>
<p>Vollständige Funktionsgruppe, die in Exchange Online zur Verfügung steht, unterstützt Exchange lokal die meisten dieser Features, finden Sie unter</p>
<p><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Interaktion von Exchange und Teams</a></p>
<p>vollständige Liste</p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>Aktivierungsschritte für Organisationen ohne Skype for Business oder lync Server

1.  Erfüllen der Voraussetzungen, die im Abschnitt Start hier oben beschrieben sind

2.  Wechseln des Mandanten in den Modus nur in Teams (nur für vorhandene Mandanten): [Festlegen der Einstellungen für Koexistenz und Upgrade](setting-your-coexistence-and-upgrade-settings.md)

3.  Konfigurieren Sie Ihren Mandanten in Übereinstimmung mit den Geschäfts-und Unternehmensrichtlinien Ihres Unternehmens: [Verwalten von Microsoft Teams-Einstellungen für Ihre Organisation](enable-features-office-365.md).

4.  Bereitstellen des Teams-Clients für Ihre Benutzer: [Abrufen von Clients für Teams](get-clients.md)

5.  Fahren Sie Ihr Adoptionsprogramm  
    [Einführen von Microsoft Teams](adopt-microsoft-teams-landing-page.md)
    
    [Prüfliste für den Schnellstart der Microsoft Teams-Einführung](teams-adoption-quick-start-checklist.md)

6.  Planen des Verschiebens anderer Arbeitslasten in Office 365

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>Organisationen **<span class="underline">mit</span>** Skype for Business oder lync Server

Dieser Ausgangspunkt setzt voraus, dass Ihre Organisation Skype for Business 2019 oder 2015 + oder lync 2013 + Server lokal verwendet. Wir verfügen bereits über umfassende Anleitungen für Organisationen, die von lokalen Servern zu Teams migrieren, und es sollte für diese Szenarien befolgt werden. Diese Anleitung beruht auf dem Szenario, in dem Teams die erste Anwendung sind, die Sie in Office 365 verwenden. In der folgenden Tabelle sind die Funktionen für Konfiguration und Endbenutzer auf hoher Ebene für Teams für Core Services detailliert beschrieben.

<table>
<thead>
<tr class="header">
<th>Element</th>
<th>Hinweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Mandanten Teams-Konfiguration</td>
<td>Modus "Inseln"</td>
</tr>
<tr class="even">
<td>Chat/externe Kommunikation in Teams</td>
<td>Intern nur innerhalb Ihres eigenen Mandanten, externe Kommunikation (Federation) erfolgt über Ihre Skype for Business-oder lync Server-Bereitstellung</td>
</tr>
<tr class="odd">
<td>Erstellen und Anzeigen von Besprechungen in Teams</td>
<td><p>Möglichkeit zum Erstellen von Besprechungen über das Outlook-Add-in</p>
<p>Die PSTN-Wähl-und-Wählfunktion ist mit den Audiokonferenz-Lizenzen verfügbar.<br />
Für den Zugriff auf den Kalender von Teams ist Exchange 2016 CU3 + lokal mit Exchange-Hybrid Einrichtung bereitgestellt:<br />
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Erstellen einer hybridbereitstellung mit dem Hybrid-Konfigurations-Assistenten</a></p></td>
</tr>
<tr class="even">
<td>Anruffunktionen<br />
VoIP/PSTN in Teams</td>
<td><p>VoIP ist intern für den Mandanten verfügbar</p>
<p>PSTN-oder Anruf Plan Dienste stehen erst zur Verfügung, wenn der Benutzer in Teams nur in Erfahrung gebracht wird.</p></td>
</tr>
<tr class="odd">
<td>Zusammenarbeit in Teams und Kanälen in Teams</td>
<td><p>Für die vollständige Nutzung, einschließlich der Kompatibilitätsfeatures, muss dem Benutzer eine SharePoint Online-Lizenz zugewiesen werden.</p>
<p>Die Migration vorhandener lokales SharePoint-Websites ist nicht erforderlich.</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (P2P-Dateifreigabe)</td>
<td>Für OneDrive for Business muss ein Benutzer eine SharePoint Online-Lizenz zuweisen. Ohne diese Lizenz ist die Dateifreigabe per Peer nicht möglich.</td>
</tr>
<tr class="odd">
<td>Anwendungsplattform</td>
<td>Die Benutzer können die für Sie verfügbaren apps entsprechend den Richtlinien Ihres Unternehmens verwenden.<br />
Weitere Informationen finden Sie hier: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Administratoreinstellungen für apps in Microsoft Teams</a></td>
</tr>
<tr class="even">
<td>Features für Sicherheit und Compliance</td>
<td><ul>
<li><p>Aufbewahrungsrichtlinien sind verfügbar</p></li>
<li><p>eDiscovery und rechtliche Aufbewahrung für Compliance bei Kanal Nachrichten werden unterstützt</p></li>
<li><p>Datenverlust-Präventions Richtlinien (DLP) sind verfügbar</p></li>
</ul>
<p>Vollständige Funktionsgruppe, die in Exchange Online zur Verfügung steht, unterstützt Exchange lokal die meisten dieser Features, finden Sie unter</p>
<p><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Interaktion von Exchange und Teams</a></p>
<ul>
<li><p>vollständige Liste</p></li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>Aktivierungsschritte für Organisationen mit Skype for Business Server  

1.  Erfüllen Sie die Voraussetzungen, die im Abschnitt Start hier oben beschrieben sind.

2.  Wechseln des Mandanten in den Inseln-Modus (für Mandanten, die nach 9/1/2019 bereitgestellt werden, wenden Sie sich bitte an den Support, um diese Änderung vorzunehmen).  
    [Festlegen Ihrer Einstellungen für Koexistenz und Upgrades](setting-your-coexistence-and-upgrade-settings.md)

3.  Konfigurieren Ihres Mandanten in Übereinstimmung mit den Geschäfts-und Unternehmensrichtlinien Ihres Unternehmens  
    [Verwalten von Microsoft Teams-Einstellungen in Ihrer Organisation](enable-features-office-365.md)

4.  Bereitstellen des Teams-Clients  
    [Beziehen von Clients für Teams](get-clients.md)

5.   Fahren Sie Ihr Adoptionsprogramm  
    [Einführen von Microsoft Teams](adopt-microsoft-teams-landing-page.md)
    
    [Prüfliste für den Schnellstart der Microsoft Teams-Einführung](teams-adoption-quick-start-checklist.md)

6.  Planen des Verschiebens anderer Arbeitslasten in Office 365

7.  Einrichten von Skype for Business-Hybriden und befolgen der empfohlenen Upgrade-Pfade für Skype for Business-und lync-Server  
    [Upgrade von Skype for Business lokal in Teams](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>Closing-Anweisung

Microsoft Teams kann eine Möglichkeit für Ihre Organisation sein, alle Mitarbeiter, Information Worker und First-work-Mitarbeiter auf einer einzigen Plattform zusammenzubringen. Sie können jetzt [beginnen](https://products.office.com/microsoft-teams/group-chat-software) . [Hier](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)können Sie mit unseren neuesten Ankündigungen und monatlichen Produktupdates in Verbindung bleiben.

Darüber hinaus haben wir als Unternehmen in der ganzen Welt die aktuelle COVID-19-Situation verwaltet, und wir haben eine Reihe von Inhalten erstellt, die Ihnen helfen, Teams für die maximale Auswirkung in Ihrer Organisation zu verwenden.

  - Unser [Engagement für Kunden während COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)

  - [2 Wochen in: was wir über Remote-Arbeit gelernt haben](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [Bereitstellen von Onlinebesprechungen und-Ereignissen](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [Unterstützung für kleine und mittelständische Unternehmen bei der Remotearbeit mit Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [Digitale Transformation von Live-Events: Bob bejans Beobachtungen von der Front](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [Die 9 wichtigsten Methoden, mit denen Microsoft IT die Remotearbeit für die Mitarbeiter ermöglicht](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [Remote arbeiten, sicher bleiben – Tipps für CISOs](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [Unterstützung von Lehrern und Schülern beim Umstieg auf Remote Learning](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [Bleiben Sie produktiv, während Sie mit Microsoft Teams Remote arbeiten](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>Referenz zu Support Diensten

Teams sind auf Exchange Online, SharePoint Online, OneDrive for Business und Microsoft 365-Gruppen angewiesen, um Ihren Benutzern eine vollständig integrierte Office 365-Benutzeroberfläche bereitzustellen. Wie bereits erwähnt, funktionieren Teams ohne vollständige bereitstellungdieser Dienste – mit eingeschränkten Funktionen. Weitere Informationen zu Teams und seinen Voraussetzungen finden Sie hier: [Willkommen bei Teams](teams-overview.md).

Einzelheiten zu den oben aufgeführten Diensten finden Sie unter den folgenden Links:

  - Exchange Online wird für Kalenderfeatures und das Speichern von Peer-to-Peer-Nachrichten in Teams verwendet. Weitere Informationen finden Sie unter [Interaktion zwischen Exchange und Teams](exchange-teams-interact.md)

> [!IMPORTANT]
> Für Teams-Interop mit Exchange lokal müssen Sie das neue Exchange OAuth-Authentifizierungsprotokoll konfigurieren, wie unter [Konfigurieren der OAuth-Authentifizierung zwischen Exchange und Exchange Online-Organisationen](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)beschrieben.

  - SharePoint wird für die Dateifreigabe in Kanälen verwendet, während/OneDrive for Business für die Dateifreigabe in 1:1 oder Gruppen-Chat verwendet wird. Weitere Informationen finden Sie unter [Interaktion zwischen SharePoint Online und OneDrive for Business mit Microsoft Teams](sharepoint-onedrive-interact.md).

  - [Microsoft 365-Gruppen](office-365-groups.md) werden für die Erstellung und Verwaltung von Teams und Kanälen verwendet.


## <a name="related-topics"></a>Verwandte Themen

[Microsoft Teams IT-Architektur- und Telefonielösungen Poster](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[Planen der Hybridkonnektivität zwischen Skype for Business Server und Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[Unterstützen von Remotemitarbeitern mithilfe von Teams](support-remote-work-with-teams.md)

[Remotearbeit mit Office 365](https://aka.ms/remote-work)
