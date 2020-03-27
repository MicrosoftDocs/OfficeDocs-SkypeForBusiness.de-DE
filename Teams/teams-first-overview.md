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
ms.openlocfilehash: 79607004c8f750ceed0325733c8c52a4873e9cdc
ms.sourcegitcommit: 89a7c0427a5abbef838a17ae7eac6934c6176a35
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2020
ms.locfileid: "42982155"
---
# <a name="roll-out-microsoft-teams-first"></a><span data-ttu-id="1cf1e-103">Microsoft Teams zuerst Ausrollen</span><span class="sxs-lookup"><span data-stu-id="1cf1e-103">Roll out Microsoft Teams First</span></span>

<span data-ttu-id="1cf1e-104">Microsoft Teams können Ihren Mitarbeitern helfen, in Verbindung zu bleiben und miteinander zusammenzuarbeiten, insbesondere in der aktuellen, noch nie dagewesenen Zeit, in der Remote-Arbeit eine Realität von Mitarbeitern in aller Welt ist.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-104">Microsoft Teams can help your employees stay connected and collaborate with each other, especially in the current unprecedented time where remote work is a reality of employees around the world.</span></span> <span data-ttu-id="1cf1e-105">Die Möglichkeit zum chatten, für Videobesprechungen und für die Zusammenarbeit an Office-Dokumenten innerhalb von Teams kann Unternehmen dabei helfen, produktiv zu bleiben.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-105">Being able to chat, do video meetings and collaborate on Office documents within Teams can help companies stay productive.</span></span> <span data-ttu-id="1cf1e-106">Unabhängig davon, ob Sie ein kleines Unternehmen, eine gemeinnützige Organisation oder eine große Organisation sind, können Sie die ersten Schritte mit Microsoft Teams als erste Arbeitsauslastung in Office 365 Suite ausführen, bevor Sie eine andere Office-App oder einen anderen Dienst bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-106">Whether you are a small business, a non-profit or a large organization, you can get started with Teams as the first workload within Office 365 suite before deploying any other Office app or service.</span></span>

<span data-ttu-id="1cf1e-107">In diesem Artikel werden die Überlegungen erläutert, die Sie mit dem Ansatz "Teams First" vornehmen müssen.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-107">This article details the considerations you must make with the "Teams First" approach.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1cf1e-108">Während Teams die erste in der Cloud bereitgestellte Arbeitsauslastung in Ihrer Organisation sein können, sollten die Bereitstellung von Teams Teil ihrer allgemeinen Cloud-Bereitstellungsstrategie sein.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-108">While Teams can be your organization's first cloud deployed workload, deploying Teams should be part of your overall cloud deployment strategy.</span></span>

<span data-ttu-id="1cf1e-109">Wenn Sie bereits andere Office 365-Dienste und-Teams für die nächste Arbeitsauslastung bereitstellen (statt der ersten), beginnen Sie mit dem [Rollout von Teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="1cf1e-109">If you have already rolled out other Office 365 services and Teams is your next workload to roll out (instead of the first), start with [How to roll out  Teams](How-to-roll-out-teams.md).</span></span>

## <a name="start-here"></a><span data-ttu-id="1cf1e-110">Hier geht’s los</span><span class="sxs-lookup"><span data-stu-id="1cf1e-110">Start here</span></span>

<span data-ttu-id="1cf1e-111">Für den Einstieg in die erste Bereitstellung Ihrer Teams müssen Sie mindestens einige Voraussetzungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-111">To get started with your Teams First deployment you will need to meet at minimum some pre-requisites.</span></span> <span data-ttu-id="1cf1e-112">In der folgenden Liste wird gezeigt, was für Ihre Organisation vorhanden sein muss, bevor Teams aktiviert werden können:</span><span class="sxs-lookup"><span data-stu-id="1cf1e-112">The following list will show what you must have in place for your organization before Teams can be enabled:</span></span>

1.  <span data-ttu-id="1cf1e-113">Ein Office 365-Mandant, der mit Ihrem Domänennamen konfiguriert ist</span><span class="sxs-lookup"><span data-stu-id="1cf1e-113">An Office 365 tenant configured with your domain name</span></span>

2.  <span data-ttu-id="1cf1e-114">Azure Active Directory Connectivity (AAD Connect) oder ähnliche Cloud Identity Sync-Lösung – mit allen erforderlichen Attributen, die mit Ihrem Mandanten synchronisiert sind</span><span class="sxs-lookup"><span data-stu-id="1cf1e-114">Azure Active Directory connectivity (AAD connect) or similar cloud identity sync solution – with all required attributes synched with your tenant</span></span>  
    <span data-ttu-id="1cf1e-115">Informationen zu den mit der Aad-Synchronisierung synchronisierten Attributen finden Sie unter [Azure AD Connect-Synchronisierung: Attribute, die mit Azure Active Directory synchronisiert](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized) werden.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-115">To understand the attributes synchronized with AAD sync, read [Azure AD Connect sync: Attributes synchronized to Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span></span>

3.  <span data-ttu-id="1cf1e-116">Für Teams zugewiesene Benutzerlizenzen</span><span class="sxs-lookup"><span data-stu-id="1cf1e-116">Appropriate user licenses assigned for Teams</span></span>  
    <span data-ttu-id="1cf1e-117">Informationen zum Verständnis der Teams-Lizenzierung finden Sie unter [Office 365-Lizenzierung für Microsoft Teams](office-365-licensing.md) .</span><span class="sxs-lookup"><span data-stu-id="1cf1e-117">To understand Teams licensing, read [Office 365 licensing for Microsoft Teams](office-365-licensing.md)</span></span>

4.  <span data-ttu-id="1cf1e-118">Netzwerk der Organisation für Teams vorbereitet</span><span class="sxs-lookup"><span data-stu-id="1cf1e-118">Organization's network prepared for Teams</span></span>  
    <span data-ttu-id="1cf1e-119">Wenn Sie die Netzwerk Vorbereitung verstehen möchten, lesen Sie [Vorbereiten des Netzwerks Ihrer Organisation für Teams](prepare-network.md).</span><span class="sxs-lookup"><span data-stu-id="1cf1e-119">To understand network preparation, read [Prepare your organization's network for Teams](prepare-network.md).</span></span>

5.  <span data-ttu-id="1cf1e-120">Erlauben Sie den Netzwerkzugriff auf Exchange, SharePoint und OneDrive for Business in Office 365: [Office 365-URLs und IP-Adressbereiche](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="1cf1e-120">Allow network access to Exchange, Sharepoint, and OneDrive for Business in Office 365: [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="1cf1e-121">Mandanten, die nach dem 1. September 2019 erstellt wurden, werden im Modus "nur für Teams" bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-121">Tenants created after September 1, 2019 are provisioned in Teams Only mode.</span></span>
> 
> [!IMPORTANT]
> <span data-ttu-id="1cf1e-122">Wenn Sie über Skype for Business Server verfügen und Ihr Mandant nach dem 1. September 2019 bereitgestellt wurde, wenden Sie sich bitte an den Premier-Support, um die koexistenzfunktionen für Teams zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-122">If you have Skype for Business Server deployed, and your tenant was provisioned AFTER September 1, 2019, please contact premier support to enable coexistence capabilities for Teams.</span></span> <span data-ttu-id="1cf1e-123">Stellen Sie sicher, dass Ihre "organisationsweite Upgrade-Richtlinie" auf "inselmodus" gesetzt ist, <span class="underline">bevor</span> Sie einem Benutzer Teams-Lizenzen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-123">Make sure your 'Organization wide upgrade policy' is set to 'Island mode' <span class="underline">before</span> you assign any Teams licenses to a user.</span></span>

## <a name="migration-starting-points"></a><span data-ttu-id="1cf1e-124">Migrations Ausgangspunkte</span><span class="sxs-lookup"><span data-stu-id="1cf1e-124">Migration Starting points</span></span>

<span data-ttu-id="1cf1e-125">Ihre Reise zu Office 365 und Features, die in Teams je nach Ausgangspunkt und vorhanden sein von Skype for Business-oder lync Server-Räumlichkeiten verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-125">Your journey to Office 365 and features available in Teams depending on your starting point and the existence of on premises Skype for Business or Lync server.</span></span> <span data-ttu-id="1cf1e-126">In den folgenden Abschnitten werden die grundlegenden Funktionen und Konfigurationsoptionen zusätzlich zu den oben genannten Voraussetzungen ausführlich erläutert.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-126">The following sections will detail basic capabilities and configuration options in addition to the pre-requisites above.</span></span> <span data-ttu-id="1cf1e-127">Wir haben die Ausgangs Szenarien für die folgenden Themen aufgeschlüsselt:</span><span class="sxs-lookup"><span data-stu-id="1cf1e-127">We have broken down the starting point scenarios to the following topics:</span></span>

<span data-ttu-id="1cf1e-128">**Mandanten Teams-Konfiguration**: Mandanten-und Benutzermodi werden verwendet, um das Verhalten des Empfängers zu steuern.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-128">**Tenant Teams Configuration**: Tenant and user modes are used to control the recipient's behavior.</span></span> <span data-ttu-id="1cf1e-129">Diese Einstellungen können auf der Mandantenebene oder auf der Benutzerebene einer Organisation zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-129">These settings can be assigned on the tenant level or the user level in an organization.</span></span> <span data-ttu-id="1cf1e-130">Weitere Informationen finden Sie unter [Koexistenz mit Skype for Business](coexistence-chat-calls-presence.md).</span><span class="sxs-lookup"><span data-stu-id="1cf1e-130">To learn more, read [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>

<span data-ttu-id="1cf1e-131">**Chat/externe Kommunikation in Teams**: Chat Dienste beziehen sich auf Peer-to-Peer-oder Gruppen-Chat Unterhaltungen innerhalb und Organisation oder extern an die Organisation.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-131">**Chat / External communication in Teams**: Chat services refer to peer to peer or group chat conversations within and organization or externally to the organization.</span></span> <span data-ttu-id="1cf1e-132">Externe Kommunikation wird auch als "Föderation" in Skype for Business bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-132">External communication is also referred to as federation in Skype for Business.</span></span>

<span data-ttu-id="1cf1e-133">**Erstellen und Anzeigen von Besprechungen in Teams**: ein Benutzer kann immer Onlinebesprechungen über das Outlook Teams-Add-in erstellen, und die PSTN-Einwahl ist in allen Szenarien verfügbar, nachdem der Benutzer lizenziert wurde.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-133">**Create and view meetings in Teams**: A user can always create online meetings via the Outlook Teams add-in and PSTN dial-in is available in all scenarios once the user is licensed.</span></span> <span data-ttu-id="1cf1e-134">Teams und Skype for Business speichern Kalenderinformationen im Exchange-Postfach des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-134">Teams and Skype for Business store calendaring information in the user's Exchange mailbox.</span></span> <span data-ttu-id="1cf1e-135">Auf dem lokalen Exchange-Server muss Exchange Server 2016 CU3 oder höher sein, damit der Team-Client mit dem Postfach des Benutzers interagieren kann.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-135">On premises Exchange server must be Exchange Server 2016 CU3 or above for the Teams client to be able to interact with the user's mailbox.</span></span> <span data-ttu-id="1cf1e-136">Ohne Zugriff auf Exchange-Postfächer das Kalendersymbol in Teams wird nicht angezeigt, und der Benutzer kann keine Besprechungen im Team-Client anzeigen, erstellen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-136">Without Exchange mailbox access the Calendar icon in Teams will not appear and they user will not be able to view, create or modify meetings in the Teams client.</span></span>

<span data-ttu-id="1cf1e-137">**Anruffunktionen VoIP/PSTN in Teams**: Anrufe können VoIP (Voice over IP) oder PSTN (Public Switched Telephone Network) sein.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-137">**Calling features VoIP / PSTN in Teams**: Calling can be Voice over IP (VoIP) or Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="1cf1e-138">VoIP-Konnektivität erfolgt nativ zwischen Teams-Clients, während PSTN-Konnektivität eintritt, wenn ein Benutzer eine externe Telefonnummer anwählt.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-138">VoIP connectivity happens natively between Teams clients, while PSTN connectivity happen when a user dials an outside phone number.</span></span>  

<span data-ttu-id="1cf1e-139">Teams unterstützen zwei Arten von PSTN-Konnektivität.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-139">Teams support two types of PSTN connectivity.</span></span> <span data-ttu-id="1cf1e-140">Microsoft-Anrufplan, wenn Microsoft eine Telefonie-Infrastruktur einschließlich der Telefonnummer für einen Benutzer oder eine direkte Routing Konfiguration bereitstellt, in der der Kunde die telefonieverbindung über einen Session Border Controller (SBC) für den Teams-Benutzer bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-140">Microsoft Calling Plan, when Microsoft provides telephony infrastructure including the phone number for a user, or Direct Routing configuration, where the customer provides the telephony connectivity over a Session Border Controller (SBC) for the Teams user.</span></span>  
<span data-ttu-id="1cf1e-141">Wenn Sie mehr darüber erfahren möchten, lesen Sie, [welcher Anrufplan für Sie die richtige ist?](calling-plan-landing-page.md) und [Direktes Routing für Telefonsysteme](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="1cf1e-141">To learn more, read [Which Calling Plan is right for you?](calling-plan-landing-page.md) and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="1cf1e-142">**Zusammenarbeit in Teams und Kanälen in Teams**: Teams sind Gruppen von Personen, die für Arbeit, Projekte oder gemeinsame Interessen zusammengeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-142">**Teams and Channels collaboration in Teams**: In Teams, teams are groups of people brought together for work, projects, or common interests.</span></span> <span data-ttu-id="1cf1e-143">Teams bestehen aus Kanälen.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-143">Teams are made up of channels.</span></span> <span data-ttu-id="1cf1e-144">Jeder Kanal basiert auf einem Thema, wie "Team-Events", einem Abteilungsnamen oder einfach nur zum Spaß.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-144">Each channel is built around a topic, like "Team Events," a department name, or just for fun.</span></span> <span data-ttu-id="1cf1e-145">Kanäle sind die Orte, an denen Sie Besprechungen abhalten, Konversationen führen und an Dateien zusammenarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-145">Channels are where you hold meetings, have conversations, and work on files together.</span></span> <span data-ttu-id="1cf1e-146">Während der Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="1cf1e-146">During collaboration</span></span>

<span data-ttu-id="1cf1e-147">**OneDrive for Business (P2P-Dateifreigabe) in Teams**: außerhalb von Teams und Kanälen können Benutzer von Teams Peer-to-Peer-Dateien mit OneDrive for Business oder anderen P2P-Freigabe Datei Programmen wie Citrix-Dateien, Dropbox, Box und Google Drive freigeben.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-147">**OneDrive for Business (P2P file sharing) in Teams**: Outside of Teams and Channels, Teams users can share files peer-to-peer using OneDrive for business or other P2P sharing file programs such as Citrix Files, DropBox, Box and Google Drive.</span></span> <span data-ttu-id="1cf1e-148">Für OneDrive for Business muss einem Benutzer die SharePoint Online-Lizenz zugewiesen sein.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-148">For OneDrive for business a user must have SharePoint Online license assigned.</span></span>

<span data-ttu-id="1cf1e-149">**Anwendungsplattform**: Apps bieten integrierte Tools für Ihre Organisation, um die Teams optimal zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-149">**Application Platform**: Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="1cf1e-150">Diese apps kombinieren die Funktionalität von Registerkarten, Messaging Erweiterungen, Connectors und Bots, die von Microsoft bereitgestellt werden, die von einem Drittanbieter oder von Entwicklern in Ihrer Organisation erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-150">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="1cf1e-151">**Sicherheits-und Compliance-Features:** Teams verfügt über eine breite Palette von Informationen, die Ihnen bei Compliance-Bereichen helfen, darunter Aufbewahrungsrichtlinien, Datenverlust Schutz (DLP), eDiscovery und rechtliche Aufbewahrung für Kanäle, Chats und Dateien, Überwachungsprotokoll Suche.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-151">**Security and Compliance features:** Teams has a wide range of information to help you with compliance areas, including retention policies, Data Loss Protection (DLP), eDiscovery and legal hold for channels, chats and files, audit log search.</span></span> <span data-ttu-id="1cf1e-152">Weitere Informationen finden Sie unter [Sicherheit und Compliance in Microsoft Teams](security-compliance-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1cf1e-152">To learn more, read [Security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="1cf1e-153">Voraus-eDiscovery-Features erfordern E5-Lizenzierung.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-153">Advance eDiscovery features require E5 licensing.</span></span>

<span data-ttu-id="1cf1e-154">[Vergleichen von Lizenzierungsoptionen](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)</span><span class="sxs-lookup"><span data-stu-id="1cf1e-154">[Compare licensing options](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>

<span data-ttu-id="1cf1e-155">Lesen Sie, [wie Exchange und Microsoft Teams interagieren](exchange-teams-interact.md) , um zu erfahren, welche Kompatibilitätsfeatures in Ihrem Szenario zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-155">Read [How Exchange and Microsoft Teams interact](exchange-teams-interact.md) to learn which compliance features are available in your scenario.</span></span>

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a><span data-ttu-id="1cf1e-156">Organisationen **<span class="underline">ohne</span>** Skype for Business oder lync Server</span><span class="sxs-lookup"><span data-stu-id="1cf1e-156">Organizations **<span class="underline">without</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="1cf1e-157">Bei diesem Ausgangspunkt wird davon ausgegangen, dass Ihre Organisation Skype for Business oder lync Server zurzeit nicht verwendet und Teams ihre erste Anwendung in Office 365 sein werden.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-157">This starting point assumes that your organization does not utilize Skype for Business or Lync server currently and Teams will be your first application in Office 365.</span></span> <span data-ttu-id="1cf1e-158">In der folgenden Tabelle sind die Funktionen für Konfiguration und Endbenutzer auf hoher Ebene für Teams für Core Services detailliert beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-158">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="1cf1e-159">Element</span><span class="sxs-lookup"><span data-stu-id="1cf1e-159">Item</span></span></th>
<th><span data-ttu-id="1cf1e-160">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1cf1e-160">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="1cf1e-161">Mandanten Teams-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="1cf1e-161">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="1cf1e-162">Nur für Teams, alle Chat-und Anruffunktionen sind nur in Teams verfügbar</span><span class="sxs-lookup"><span data-stu-id="1cf1e-162">Teams Only mode, all chat and calling features are in Teams Only</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="1cf1e-163">Chat/externe Kommunikation in Teams</span><span class="sxs-lookup"><span data-stu-id="1cf1e-163">Chat / External Communication in Teams</span></span></td>
<td><p><span data-ttu-id="1cf1e-164">Interne (Intra Office 365-Mandant) und externe Chat-Kommunikation aus Teams möglich</span><span class="sxs-lookup"><span data-stu-id="1cf1e-164">Internal (intra Office 365 tenant) and external chat communication possible from Teams</span></span></p>
<p><span data-ttu-id="1cf1e-165"><em>Hinweis: DNS-Einträge müssen für den externen Zugriff konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-165"><em>Note: DNS entries must be configured for external access.</span></span> <span data-ttu-id="1cf1e-166">Skype for Business-DNS-Einträge werden benötigt, auch wenn Sie nicht über Skype for Business lokal oder in Office 365 verfügen, um eine Föderation mit lync-und Skype for Business-Umgebungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-166">Skype for Business DNS records are needed even though you don't have Skype for Business on-premises or in Office 365 to allow federation with Lync and Skype for Business environments.</span></span><br /><span data-ttu-id="1cf1e-167">
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">Externe Domänennamen-System Einträge für Office 365</a></em></span><span class="sxs-lookup"><span data-stu-id="1cf1e-167">
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">External Domain Name System records for Office 365</a></em></span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="1cf1e-168"><em>Erstellen und Anzeigen von Besprechungen in Teams</em></span><span class="sxs-lookup"><span data-stu-id="1cf1e-168"><em>Create and view Meetings in Teams</em></span></span></td>
<td><p><span data-ttu-id="1cf1e-169"><em>Möglichkeit zum Erstellen von Besprechungen über das Outlook-Add-in</em></span><span class="sxs-lookup"><span data-stu-id="1cf1e-169"><em>Able to create meetings via Outlook add-in</em></span></span></p>
<p><span data-ttu-id="1cf1e-170"><em>Die PSTN-Wähl-und-Wählfunktion ist mit den Audiokonferenz-Lizenzen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-170"><em>PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span><br />
<span data-ttu-id="1cf1e-171">Hinweis: der Zugriff auf den Kalender von Teams erfordert Exchange 2016 CU3 + lokal bereitgestellt mit Exchange-Hybrid <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Einrichtung: Erstellen einer hybridbereitstellung mit dem Hybrid-Konfigurations-Assistenten</a></span><span class="sxs-lookup"><span data-stu-id="1cf1e-171">Note: Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established: <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard</a></span></span><br />
<span data-ttu-id="1cf1e-172">Zusätzlich zur Exchange-Hybrid Konfiguration müssen Sie die Exchange-OAuth-Authentifizierung einrichten: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Konfigurieren der OAuth-Authentifizierung zwischen Exchange und Exchange Online-Organisationen</a></em></span><span class="sxs-lookup"><span data-stu-id="1cf1e-172">In addition to Exchange hybrid configuration, establish Exchange OAuth authentication: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Configure OAuth authentication between Exchange and Exchange Online organizations</a></em></span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="1cf1e-173">Anruffunktionen</span><span class="sxs-lookup"><span data-stu-id="1cf1e-173">Calling Features</span></span><br />
<span data-ttu-id="1cf1e-174">VoIP/PSTN in Teams</span><span class="sxs-lookup"><span data-stu-id="1cf1e-174">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="1cf1e-175">VoIP intern und extern für den Mandanten verfügbar</span><span class="sxs-lookup"><span data-stu-id="1cf1e-175">VoIP internally and externally to the tenant is available</span></span></p>
<p><span data-ttu-id="1cf1e-176">PSTN-Dienste können über das Microsoft Phone-System konfiguriert werden sowie einen Microsoft-Anrufplan oder ein direktes Routing hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-176">PSTN services can be configured via Microsoft Phone System, plus adding a Microsoft Calling Plan or Direct Routing.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="1cf1e-177">Zusammenarbeit in Teams und Kanälen in Teams</span><span class="sxs-lookup"><span data-stu-id="1cf1e-177">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="1cf1e-178">Für die vollständige Nutzung, einschließlich der Kompatibilitätsfeatures, muss dem Benutzer eine SharePoint Online-Lizenz zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-178">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="1cf1e-179">Die Migration vorhandener lokales SharePoint-Websites ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-179">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="1cf1e-180">OneDrive for Business (P2P-Dateifreigabe)</span><span class="sxs-lookup"><span data-stu-id="1cf1e-180">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="1cf1e-181">Für OneDrive for Business muss ein Benutzer eine SharePoint Online-Lizenz zuweisen.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-181">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="1cf1e-182">Ohne diese Lizenz ist eine Peer-to-Peer-Dateiübertragung nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-182">Without this license peer-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="1cf1e-183">Anwendungsplattform</span><span class="sxs-lookup"><span data-stu-id="1cf1e-183">Application platform</span></span></td>
<td><span data-ttu-id="1cf1e-184">Die Benutzer können die für Sie verfügbaren apps entsprechend den Richtlinien Ihres Unternehmens verwenden.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-184">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="1cf1e-185">Weitere Informationen finden Sie hier: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Administratoreinstellungen für apps in Microsoft Teams</a></span><span class="sxs-lookup"><span data-stu-id="1cf1e-185">Learn more here: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="1cf1e-186">Features für Sicherheit und Compliance</span><span class="sxs-lookup"><span data-stu-id="1cf1e-186">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="1cf1e-187">Aufbewahrungsrichtlinien sind verfügbar</span><span class="sxs-lookup"><span data-stu-id="1cf1e-187">Retention policies are available</span></span></p></li>
<li><p><span data-ttu-id="1cf1e-188">eDiscovery und rechtliche Aufbewahrung für Compliance bei Kanal Nachrichten werden unterstützt</span><span class="sxs-lookup"><span data-stu-id="1cf1e-188">eDiscovery and Legal Hold for compliance on channel messages is supported</span></span></p></li>
<li><p><span data-ttu-id="1cf1e-189">Datenverlust-Präventions Richtlinien (DLP) sind verfügbar</span><span class="sxs-lookup"><span data-stu-id="1cf1e-189">Data Loss Prevention policies (DLP) are available</span></span></p></li>
</ul>
<p><span data-ttu-id="1cf1e-190">Vollständige Funktionsgruppe, die in Exchange Online zur Verfügung steht, unterstützt Exchange lokal die meisten dieser Features, finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="1cf1e-190">Full feature set available with Exchange Online, Exchange on-premises supports most of these features, see</span></span></p>
<p><span data-ttu-id="1cf1e-191"><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Interaktion von Exchange und Teams</a></span><span class="sxs-lookup"><span data-stu-id="1cf1e-191"><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a></span></span></p>
<p><span data-ttu-id="1cf1e-192">vollständige Liste</span><span class="sxs-lookup"><span data-stu-id="1cf1e-192">for full list</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a><span data-ttu-id="1cf1e-193">Aktivierungsschritte für Organisationen ohne Skype for Business oder lync Server</span><span class="sxs-lookup"><span data-stu-id="1cf1e-193">Enablement steps for organizations without Skype for Business or Lync Server</span></span>

1.  <span data-ttu-id="1cf1e-194">Erfüllen der Voraussetzungen, die im Abschnitt Start hier oben beschrieben sind</span><span class="sxs-lookup"><span data-stu-id="1cf1e-194">Meet pre-requisites detailed in the Start Here section above</span></span>

2.  <span data-ttu-id="1cf1e-195">Wechseln des Mandanten in den Modus nur in Teams (nur für vorhandene Mandanten): [Festlegen der Einstellungen für Koexistenz und Upgrade](setting-your-coexistence-and-upgrade-settings.md)</span><span class="sxs-lookup"><span data-stu-id="1cf1e-195">Switch tenant into Teams Only mode (for existing tenants only): [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

3.  <span data-ttu-id="1cf1e-196">Konfigurieren Sie Ihren Mandanten in Übereinstimmung mit den Geschäfts-und Unternehmensrichtlinien Ihres Unternehmens: [Verwalten von Microsoft Teams-Einstellungen für Ihre Organisation](enable-features-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="1cf1e-196">Configure your tenant in accordance with your company's business/company policies: [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

4.  <span data-ttu-id="1cf1e-197">Bereitstellen des Teams-Clients für Ihre Benutzer: [Abrufen von Clients für Teams](get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="1cf1e-197">Deploy the Teams client to your users: [Get clients for Teams](get-clients.md)</span></span>

5.  <span data-ttu-id="1cf1e-198">Fahren Sie Ihr Adoptionsprogramm</span><span class="sxs-lookup"><span data-stu-id="1cf1e-198">Drive your adoption program</span></span>  
    [<span data-ttu-id="1cf1e-199">Einführen von Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1cf1e-199">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)
    
    [<span data-ttu-id="1cf1e-200">Prüfliste für den Schnellstart der Microsoft Teams-Einführung</span><span class="sxs-lookup"><span data-stu-id="1cf1e-200">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="1cf1e-201">Planen des Verschiebens anderer Arbeitslasten in Office 365</span><span class="sxs-lookup"><span data-stu-id="1cf1e-201">Begin planning moving other workloads to Office 365</span></span>

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a><span data-ttu-id="1cf1e-202">Organisationen **<span class="underline">mit</span>** Skype for Business oder lync Server</span><span class="sxs-lookup"><span data-stu-id="1cf1e-202">Organizations **<span class="underline">with</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="1cf1e-203">Dieser Ausgangspunkt setzt voraus, dass Ihre Organisation Skype for Business 2019 oder 2015 + oder lync 2013 + Server lokal verwendet.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-203">This starting point assumes that your organization utilizes Skype for Business 2019 or 2015+ or Lync 2013+ server on premises.</span></span> <span data-ttu-id="1cf1e-204">Wir verfügen bereits über umfassende Anleitungen für Organisationen, die von lokalen Servern zu Teams migrieren, und es sollte für diese Szenarien befolgt werden.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-204">We already have extensive guidance for organizations migrating from on premises servers to Teams and it should be followed for these scenarios.</span></span> <span data-ttu-id="1cf1e-205">Diese Anleitung beruht auf dem Szenario, in dem Teams die erste Anwendung sind, die Sie in Office 365 verwenden.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-205">This guidance is specific to the scenario that Teams is the first application you utilize in Office 365.</span></span> <span data-ttu-id="1cf1e-206">In der folgenden Tabelle sind die Funktionen für Konfiguration und Endbenutzer auf hoher Ebene für Teams für Core Services detailliert beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-206">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="1cf1e-207">Element</span><span class="sxs-lookup"><span data-stu-id="1cf1e-207">Item</span></span></th>
<th><span data-ttu-id="1cf1e-208">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1cf1e-208">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="1cf1e-209">Mandanten Teams-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="1cf1e-209">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="1cf1e-210">Modus "Inseln"</span><span class="sxs-lookup"><span data-stu-id="1cf1e-210">Islands mode</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="1cf1e-211">Chat/externe Kommunikation in Teams</span><span class="sxs-lookup"><span data-stu-id="1cf1e-211">Chat / External Communication in Teams</span></span></td>
<td><span data-ttu-id="1cf1e-212">Intern nur innerhalb Ihres eigenen Mandanten, externe Kommunikation (Federation) erfolgt über Ihre Skype for Business-oder lync Server-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="1cf1e-212">Internal within your own tenant only, external communication (federation) is via your Skype for Business or Lync server deployment</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="1cf1e-213">Erstellen und Anzeigen von Besprechungen in Teams</span><span class="sxs-lookup"><span data-stu-id="1cf1e-213">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="1cf1e-214">Möglichkeit zum Erstellen von Besprechungen über das Outlook-Add-in</span><span class="sxs-lookup"><span data-stu-id="1cf1e-214">Able to create meetings via Outlook add-in</span></span></p>
<p><span data-ttu-id="1cf1e-215">Die PSTN-Wähl-und-Wählfunktion ist mit den Audiokonferenz-Lizenzen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-215">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span><br />
<span data-ttu-id="1cf1e-216">Für den Zugriff auf den Kalender von Teams ist Exchange 2016 CU3 + lokal mit Exchange-Hybrid Einrichtung bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="1cf1e-216">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established:</span></span><br /><span data-ttu-id="1cf1e-217">
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Erstellen einer hybridbereitstellung mit dem Hybrid-Konfigurations-Assistenten</a></span><span class="sxs-lookup"><span data-stu-id="1cf1e-217">
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard</a></span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="1cf1e-218">Anruffunktionen</span><span class="sxs-lookup"><span data-stu-id="1cf1e-218">Calling Features</span></span><br />
<span data-ttu-id="1cf1e-219">VoIP/PSTN in Teams</span><span class="sxs-lookup"><span data-stu-id="1cf1e-219">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="1cf1e-220">VoIP ist intern für den Mandanten verfügbar</span><span class="sxs-lookup"><span data-stu-id="1cf1e-220">VoIP internally to the tenant is available</span></span></p>
<p><span data-ttu-id="1cf1e-221">PSTN-oder Anruf Plan Dienste stehen erst zur Verfügung, wenn der Benutzer in Teams nur in Erfahrung gebracht wird.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-221">PSTN or Calling Plan services are not available until the user is moved to Teams Only experience</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="1cf1e-222">Zusammenarbeit in Teams und Kanälen in Teams</span><span class="sxs-lookup"><span data-stu-id="1cf1e-222">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="1cf1e-223">Für die vollständige Nutzung, einschließlich der Kompatibilitätsfeatures, muss dem Benutzer eine SharePoint Online-Lizenz zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-223">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="1cf1e-224">Die Migration vorhandener lokales SharePoint-Websites ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-224">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="1cf1e-225">OneDrive for Business (P2P-Dateifreigabe)</span><span class="sxs-lookup"><span data-stu-id="1cf1e-225">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="1cf1e-226">Für OneDrive for Business muss ein Benutzer eine SharePoint Online-Lizenz zuweisen.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-226">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="1cf1e-227">Ohne diese Lizenz ist die Dateifreigabe per Peer nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-227">Without this license per-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="1cf1e-228">Anwendungsplattform</span><span class="sxs-lookup"><span data-stu-id="1cf1e-228">Application platform</span></span></td>
<td><span data-ttu-id="1cf1e-229">Die Benutzer können die für Sie verfügbaren apps entsprechend den Richtlinien Ihres Unternehmens verwenden.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-229">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="1cf1e-230">Weitere Informationen finden Sie hier: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Administratoreinstellungen für apps in Microsoft Teams</a></span><span class="sxs-lookup"><span data-stu-id="1cf1e-230">Learn more here: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="1cf1e-231">Features für Sicherheit und Compliance</span><span class="sxs-lookup"><span data-stu-id="1cf1e-231">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="1cf1e-232">Aufbewahrungsrichtlinien sind verfügbar</span><span class="sxs-lookup"><span data-stu-id="1cf1e-232">Retention policies are available</span></span></p></li>
<li><p><span data-ttu-id="1cf1e-233">eDiscovery und rechtliche Aufbewahrung für Compliance bei Kanal Nachrichten werden unterstützt</span><span class="sxs-lookup"><span data-stu-id="1cf1e-233">eDiscovery and Legal Hold for compliance on channel messages is supported</span></span></p></li>
<li><p><span data-ttu-id="1cf1e-234">Datenverlust-Präventions Richtlinien (DLP) sind verfügbar</span><span class="sxs-lookup"><span data-stu-id="1cf1e-234">Data Loss Prevention policies (DLP) are available</span></span></p></li>
</ul>
<p><span data-ttu-id="1cf1e-235">Vollständige Funktionsgruppe, die in Exchange Online zur Verfügung steht, unterstützt Exchange lokal die meisten dieser Features, finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="1cf1e-235">Full feature set available with Exchange Online, Exchange on-premises supports most of these features, see</span></span></p>
<p><span data-ttu-id="1cf1e-236"><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Interaktion von Exchange und Teams</a></span><span class="sxs-lookup"><span data-stu-id="1cf1e-236"><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a></span></span></p>
<ul>
<li><p><span data-ttu-id="1cf1e-237">vollständige Liste</span><span class="sxs-lookup"><span data-stu-id="1cf1e-237">for full list</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a><span data-ttu-id="1cf1e-238">Aktivierungsschritte für Organisationen mit Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="1cf1e-238">Enablement steps for organizations with Skype for Business Server</span></span>  

1.  <span data-ttu-id="1cf1e-239">Erfüllen Sie die Voraussetzungen, die im Abschnitt Start hier oben beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-239">Meet pre-requisites detailed in the Start Here section above.</span></span>

2.  <span data-ttu-id="1cf1e-240">Wechseln des Mandanten in den Inseln-Modus (für Mandanten, die nach 9/1/2019 bereitgestellt werden, wenden Sie sich bitte an den Premier-Support, um diese Änderung vorzunehmen)</span><span class="sxs-lookup"><span data-stu-id="1cf1e-240">Switch tenant into Islands mode (for tenants provisioned AFTER 9/1/2019, please contact premier support to make this change)</span></span>  
    [<span data-ttu-id="1cf1e-241">Festlegen Ihrer Einstellungen für Koexistenz und Upgrades</span><span class="sxs-lookup"><span data-stu-id="1cf1e-241">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

3.  <span data-ttu-id="1cf1e-242">Konfigurieren Ihres Mandanten in Übereinstimmung mit den Geschäfts-und Unternehmensrichtlinien Ihres Unternehmens</span><span class="sxs-lookup"><span data-stu-id="1cf1e-242">Configure your tenant in accordance with your company's business/company policies</span></span>  
    [<span data-ttu-id="1cf1e-243">Verwalten von Microsoft Teams-Einstellungen in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="1cf1e-243">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)

4.  <span data-ttu-id="1cf1e-244">Bereitstellen des Teams-Clients</span><span class="sxs-lookup"><span data-stu-id="1cf1e-244">Deploy the Teams client</span></span>  
    [<span data-ttu-id="1cf1e-245">Beziehen von Clients für Teams</span><span class="sxs-lookup"><span data-stu-id="1cf1e-245">Get clients for Teams</span></span>](get-clients.md)

5.   <span data-ttu-id="1cf1e-246">Fahren Sie Ihr Adoptionsprogramm</span><span class="sxs-lookup"><span data-stu-id="1cf1e-246">Drive your adoption program</span></span>  
    [<span data-ttu-id="1cf1e-247">Einführen von Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1cf1e-247">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)
    
    [<span data-ttu-id="1cf1e-248">Prüfliste für den Schnellstart der Microsoft Teams-Einführung</span><span class="sxs-lookup"><span data-stu-id="1cf1e-248">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="1cf1e-249">Planen des Verschiebens anderer Arbeitslasten in Office 365</span><span class="sxs-lookup"><span data-stu-id="1cf1e-249">Begin planning moving other workloads to Office 365</span></span>

7.  <span data-ttu-id="1cf1e-250">Einrichten von Skype for Business-Hybriden und befolgen der empfohlenen Upgrade-Pfade für Skype for Business-und lync-Server</span><span class="sxs-lookup"><span data-stu-id="1cf1e-250">Establish Skype for Business hybrid and follow the recommended upgrade paths for Skype for Business and Lync servers</span></span>  
    [<span data-ttu-id="1cf1e-251">Upgrade von Skype for Business lokal in Teams</span><span class="sxs-lookup"><span data-stu-id="1cf1e-251">Upgrade from Skype for Business on-premises to Teams</span></span>](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a><span data-ttu-id="1cf1e-252">Closing-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1cf1e-252">Closing statement</span></span>

<span data-ttu-id="1cf1e-253">Microsoft Teams kann eine Möglichkeit für Ihre Organisation sein, alle Mitarbeiter, Information Worker und First-work-Mitarbeiter auf einer einzigen Plattform zusammenzubringen.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-253">Microsoft Teams can be an enabler for your organization to bring all the employees, information workers and Firstline workers, together on a single platform.</span></span> <span data-ttu-id="1cf1e-254">Sie können jetzt [beginnen](https://products.office.com/microsoft-teams/group-chat-software) .</span><span class="sxs-lookup"><span data-stu-id="1cf1e-254">You can [get started](https://products.office.com/microsoft-teams/group-chat-software) today.</span></span> <span data-ttu-id="1cf1e-255">[Hier](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)können Sie mit unseren neuesten Ankündigungen und monatlichen Produktupdates in Verbindung bleiben.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-255">You can keep in touch with all our latest announcements and monthly product updates [here](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).</span></span>

<span data-ttu-id="1cf1e-256">Darüber hinaus haben wir als Unternehmen in der ganzen Welt die aktuelle COVID-19-Situation verwaltet, und wir haben eine Reihe von Inhalten erstellt, die Ihnen helfen, Teams für die maximale Auswirkung in Ihrer Organisation zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-256">Additionally, as companies around the world are managing the current COVID-19 situation, we have created a series of content that will help you utilize Teams for the maximum impact in your organization.</span></span>

  - <span data-ttu-id="1cf1e-257">Unser [Engagement für Kunden während COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span><span class="sxs-lookup"><span data-stu-id="1cf1e-257">Our [commitment to customers during COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span></span>

  - [<span data-ttu-id="1cf1e-258">2 Wochen in: was wir über Remote-Arbeit gelernt haben</span><span class="sxs-lookup"><span data-stu-id="1cf1e-258">2 weeks in: what we've learned about remote work</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [<span data-ttu-id="1cf1e-259">Bereitstellen von Onlinebesprechungen und-Ereignissen</span><span class="sxs-lookup"><span data-stu-id="1cf1e-259">Delivering online meetings and events</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [<span data-ttu-id="1cf1e-260">Hilfe für kleine und mittelständische Unternehmen, die Remote mit Teams arbeiten</span><span class="sxs-lookup"><span data-stu-id="1cf1e-260">Helping small and medium-sized businesses work remotely with Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [<span data-ttu-id="1cf1e-261">Digitale Transformation von Live-Events: Bob bejans Beobachtungen von der Front</span><span class="sxs-lookup"><span data-stu-id="1cf1e-261">Digital transformation of live events: Bob Bejan's observations from the frontline</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [<span data-ttu-id="1cf1e-262">Die besten 9 Möglichkeiten, wie Microsoft IT die Remote Arbeit für Ihre Mitarbeiter ermöglicht</span><span class="sxs-lookup"><span data-stu-id="1cf1e-262">The top 9 ways Microsoft IT is enabling remote work for its employees</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [<span data-ttu-id="1cf1e-263">Remote arbeiten, sicher bleiben – Tipps für CISOs</span><span class="sxs-lookup"><span data-stu-id="1cf1e-263">Work remotely, stay secure—tips for CISOs</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [<span data-ttu-id="1cf1e-264">Unterstützung von Lehrern und Schülern beim Umstieg auf Remote Learning</span><span class="sxs-lookup"><span data-stu-id="1cf1e-264">Helping teachers and students make the switch to remote learning</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [<span data-ttu-id="1cf1e-265">Bleiben Sie produktiv, während Sie mit Microsoft Teams Remote arbeiten</span><span class="sxs-lookup"><span data-stu-id="1cf1e-265">Staying productive while working remotely with Microsoft Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a><span data-ttu-id="1cf1e-266">Referenz zu Support Diensten</span><span class="sxs-lookup"><span data-stu-id="1cf1e-266">Support Services reference</span></span>

<span data-ttu-id="1cf1e-267">Teams beruhen auf Exchange Online, SharePoint Online, OneDrive for Business und Office 365-Gruppen, um Ihren Benutzern eine vollständig integrierte Office 365-Benutzeroberfläche bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-267">Teams relies on Exchange Online, SharePoint Online, OneDrive for Business and Office 365 Groups to provide your users with a fully integrated Office 365 experience.</span></span> <span data-ttu-id="1cf1e-268">Wie bereits erwähnt, funktionieren Teams ohne vollständige bereitstellungdieser Dienste – mit eingeschränkten Funktionen.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-268">As noted above, Teams will work without full deploying these services – with limited capabilities.</span></span> <span data-ttu-id="1cf1e-269">Weitere Informationen zu Teams und seinen Voraussetzungen finden Sie hier: [Willkommen bei Teams](teams-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1cf1e-269">You can read more about Teams and its pre-requisites here: [Welcome to Teams](teams-overview.md).</span></span>

<span data-ttu-id="1cf1e-270">Einzelheiten zu den oben aufgeführten Diensten finden Sie unter den folgenden Links:</span><span class="sxs-lookup"><span data-stu-id="1cf1e-270">For specifics on each of the services listed above, please follow the links below:</span></span>

  - <span data-ttu-id="1cf1e-271">Exchange Online wird für Kalenderfeatures und das Speichern von Peer-to-Peer-Nachrichten in Teams verwendet.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-271">Exchange Online is used for calendaring features and storing peer to peer messages in Teams.</span></span> <span data-ttu-id="1cf1e-272">Weitere Informationen finden Sie unter [Interaktion zwischen Exchange und Teams](exchange-teams-interact.md)</span><span class="sxs-lookup"><span data-stu-id="1cf1e-272">To learn more, read [How Exchange and Teams interact](exchange-teams-interact.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1cf1e-273">Für Teams-Interop mit Exchange lokal müssen Sie das neue Exchange OAuth-Authentifizierungsprotokoll konfigurieren, wie unter [Konfigurieren der OAuth-Authentifizierung zwischen Exchange und Exchange Online-Organisationen](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-273">For Teams interop with Exchange on-premises, you must configure the new Exchange OAuth authentication protocol as described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).</span></span>

  - <span data-ttu-id="1cf1e-274">SharePoint wird für die Dateifreigabe in Kanälen verwendet, während/OneDrive for Business für die Dateifreigabe in 1:1 oder Gruppen-Chat verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-274">SharePoint is used for file sharing in channels, while /OneDrive for Business is used for file sharing in 1:1 or group chat.</span></span> <span data-ttu-id="1cf1e-275">Weitere Informationen finden Sie unter [Interaktion zwischen SharePoint Online und OneDrive for Business mit Microsoft Teams](sharepoint-onedrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="1cf1e-275">To learn more, read [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

  - <span data-ttu-id="1cf1e-276">[Office 365-Gruppen](office-365-groups.md) werden für die Erstellung und Verwaltung von Teams und Kanälen verwendet.</span><span class="sxs-lookup"><span data-stu-id="1cf1e-276">[Office 365 Groups](office-365-groups.md) are used for team and channel creation/management.</span></span>


## <a name="related-topics"></a><span data-ttu-id="1cf1e-277">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="1cf1e-277">Related topics</span></span>

[<span data-ttu-id="1cf1e-278">Microsoft Teams IT-Architektur- und Telefonielösungen Poster</span><span class="sxs-lookup"><span data-stu-id="1cf1e-278">Microsoft Teams IT architecture and telephony solutions posters</span></span>](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[<span data-ttu-id="1cf1e-279">Planen der Hybridkonnektivität zwischen Skype for Business Server und Office 365</span><span class="sxs-lookup"><span data-stu-id="1cf1e-279">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[<span data-ttu-id="1cf1e-280">Unterstützen von Remotemitarbeitern mithilfe von Teams</span><span class="sxs-lookup"><span data-stu-id="1cf1e-280">Support remote workers using Teams</span></span>](support-remote-work-with-teams.md)

[<span data-ttu-id="1cf1e-281">Remotearbeit mit Office 365</span><span class="sxs-lookup"><span data-stu-id="1cf1e-281">Work remotely with Office 365</span></span>](https://aka.ms/remote-work)