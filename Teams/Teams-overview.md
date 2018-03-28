---
title: Übersicht über Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: Hier erhalten Sie Informationen zu Microsoft Teams, zur Infrastruktur und zur Verwendung von Teams mit Office 365.
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: cbbd2cad0b84ccdcc887d5bcdf272c1556c9c546
ms.sourcegitcommit: 39228142658557890b2173c41db9661eb502b946
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
<a name="overview-of-microsoft-teams"></a><span data-ttu-id="ad0ff-103">Übersicht über Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ad0ff-103">Overview of Microsoft Teams</span></span>
===========================

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=ccf507a4-4ec4-4d61-9fb0-c86b5f1fc2a6&AutoPlayVideo=false] 


<span data-ttu-id="ad0ff-p101">Microsoft Teams vereint den vollen Funktionsumfang von Office 365 in einem wirklich chatbasierten Hub für Teamarbeit und gibt Kunden die Gelegenheit, eine offenere, flüssigere und digitale Umgebung zu schaffen. Microsoft Teams basiert auf vorhandenen Microsoft-Technologien, die durch Office 365-Gruppen verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-p101">Microsoft Teams brings together the full breadth and depth of Office 365, to provide a true chat-based hub for teamwork and give customers the opportunity to create a more open, fluid, and digital environment. Microsoft Teams is built on existing Microsoft technologies woven together by Office 365 Groups.</span></span> 

<span data-ttu-id="ad0ff-106">Teams nutzt standardmäßig die in Azure Active Directory (Azure AD) gespeicherten Identitäten und wird in die anderen Dienste in Office 365 integriert, um für jedes erstellte Team eine SharePoint Online-Website und ein Exchange Online-Gruppenpostfach zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-106">Out of the box, Teams leverages identities stored in Azure Active Directory (Azure AD) and integrates with the other services within Office 365, to create a SharePoint online site and an Exchange Online group mailbox for each team created.</span></span>

<span data-ttu-id="ad0ff-107">Jeder Benutzer mit einer Business "oder" Consumer e-Mail-Konto, wie Outlook, Google Mail oder andere, kann als Gast in Teams teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-107">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span> <span data-ttu-id="ad0ff-108">Alle Gäste in Teams unterliegen den gleichen Einhaltung von Vorschriften und Überwachung Schutz als den Rest von Office 365 und Gäste in Azure AD sicher verwaltet werden können.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-108">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure AD.</span></span> <span data-ttu-id="ad0ff-109">Administratoren können zentral verwalten wie Gäste innerhalb ihrer Office 365-Umgebung teilnehmen und auf einfache Weise anzeigen, hinzufügen oder widerrufen des Gastsystem Zugriff auf den Host-Mandanten.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-109">Admins can centrally manage how guests participate within their Office 365 environment and easily view, add, or revoke a guest’s access to the host tenant.</span></span>

<span data-ttu-id="ad0ff-110">Microsoft Teams bietet Funktionen für beständigen Chat, Anrufe und Besprechungen, einfachen Zugriff auf andere Komponenten von Office 365 sowie robuste Erweiterungsmöglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-110">Teams provides a persistent chat capability, calling and meetings, easy access to other components of Office 365 as well as a robust extensibility story.</span></span>  <span data-ttu-id="ad0ff-111">Dadurch entsteht ein Hub für Teamarbeit, der sich für die verschiedensten Organisationsgrößen eignet – von Großunternehmen bis hin zu kleinen Organisationen.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-111">This provides a hub for teamwork that is appropriate for enterprise companies, small organizations and everyone in between.</span></span>  

<span data-ttu-id="ad0ff-112">Zum Erweitern der Funktionen von Teams stehen Connectors, Registerkarten und Bots als [Apps](https://go.microsoft.com/fwlink/?linkid=854629) zur Verfügung, mit denen externe Informationen, Inhalte und Interaktionen mit intelligenten Bots in Teams integriert werden können.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-112">To extend Teams capabilities, use Connectors, Tabs, and Bots - available as [Apps](https://go.microsoft.com/fwlink/?linkid=854629), to bring external information, content, and intelligent bot interactions to Teams.</span></span>  

<a name="microsoft-teams-infrastructure"></a><span data-ttu-id="ad0ff-113">Infrastruktur von Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ad0ff-113">Microsoft Teams infrastructure</span></span>
------------------------------

<span data-ttu-id="ad0ff-114">Teams basiert auf vorhandenen Microsoft-Technologien, die durch Office 365-Gruppen verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-114">Teams is built on existing Microsoft technologies, woven together by Office 365 Groups.</span></span> <span data-ttu-id="ad0ff-115">Unterstützt von der Cloud von Microsoft können Organisationen exzellente Leistung und Zuverlässigkeit erwarten, wenn sie Teams als Bestandteil ihrer Zusammenarbeitslösung nutzen.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-115">Powered by the Microsoft cloud, organizations can expect excellent performance and reliability when leveraging Teams as part of their collaboration story.</span></span>

<span data-ttu-id="ad0ff-116">Standardmäßig wird für ein in Teams erstelltes Team jeweils eine Office 365-Gruppe mit der zugehörigen SharePoint Online-Website erstellt – einschließlich einer Dokumentbibliothek und eines Exchange Online-Gruppenpostfachs, das von Teams zum Speichern von Informationen wie zum Beispiel Besprechungseinladungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-116">Out of the box, a team created in Teams will create an Office 365 Group, a SharePoint Online site (complete with a document library), and an Exchange Online group mailbox, which will be used by Teams to store information such as meeting invites.</span></span> <span data-ttu-id="ad0ff-117">Ein Team kann mithilfe vorhandener Office 365-Gruppen erstellt werden, sodass vorhandene Gruppenmitgliedschaften und Inhalte, die in SharePoint Online und Exchange Online gespeichert sind, nach Teams portiert werden können.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-117">A team can be created using existing Office 365 Groups, allowing existing group memberships, and contents stored in SharePoint Online and Exchange Online to be ported to Teams.</span></span>

<span data-ttu-id="ad0ff-118">Als Ergänzung zu Teams als Board für beständigen Chat, auf dem formlose Echtzeitunterhaltungen stattfinden können, bietet Teams außerdem Besprechungsfunktionen auf der Grundlage der cloudbasierten Infrastruktur der nächsten Generation, die auch von Skype und Skype for Business genutzt wird.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-118">To complement the Teams capability as a persistent chat board where informal, real-time conversations take place, Teams also provides a meeting experience built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="ad0ff-119">Zu diesen Technologieinvestitionen gehören Azure-basierte Clouddienste für Medienverarbeitung und Signalisierung, der Videocodec H.264, die Audiocodecs SILK und Opus, Netzwerkresilienz, Telemetrie und Qualitätsdiagnose.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-119">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span>

<span data-ttu-id="ad0ff-120">Office 365-Gruppen nutzen in Azure Active Directory (Azure AD) gespeicherte Identitäten. Damit sind alle Authentifizierungs- und Autorisierungsfunktionen in Azure AD wie Unterstützung für mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) direkt zur Verwendung durch Teams verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-120">Office 365 Groups leverage identities stored in Azure Active Directory (Azure AD) and as such, all authentication and authorization capabilities in Azure AD, such as support for multi-factor authentication (MFA), are readily available for use by Teams.</span></span>

<span data-ttu-id="ad0ff-121">Teams bietet darüber hinaus Anruf- und Besprechungsfunktionen auf der Grundlage der cloudbasierten Infrastruktur der nächsten Generation, die auch von Skype und Skype for Business genutzt wird.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-121">Teams also provides a calling and meetings experience that is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="ad0ff-122">Zu diesen Technologieinvestitionen gehören Azure-basierte Clouddienste für Medienverarbeitung und Signalisierung, der Videocodec H.264, die Audiocodecs SILK und Opus, Netzwerkresilienz, Telemetrie und Qualitätsdiagnose.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-122">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span>

> [!NOTE]
> <span data-ttu-id="ad0ff-123">Basierend auf Feedback von Kunden, neue Office 365 Gruppen infolge einer erstellen ein Team in Microsoft-Teams, nicht mehr in Outlook standardmäßig angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-123">Based on customer feedback, new Office 365 Groups generated as a result of creating a team in Microsoft Teams will no longer show in Outlook by default.</span></span> <span data-ttu-id="ad0ff-124">Für Kunden, die das vorhandene Verhalten der mit diesen Gruppen in Outlook fortsetzen möchten, wird die Gruppe die für die benutzerfreundlichkeit von Outlook ermöglichen können ein Exchange Online PowerShell-Cmdlet bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-124">For customers that want to continue with the existing behavior of showing these groups in Outlook, an Exchange Online PowerShell cmdlet will be provided which can enable the group for the Outlook experience.</span></span> <span data-ttu-id="ad0ff-125">Gruppen über Outlook erstellt und dann später für Teams aktiviert werden weiterhin in Outlook und Teams angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-125">Groups created through Outlook and then later enabled for Teams will continue to show in both Outlook and Teams.</span></span> <span data-ttu-id="ad0ff-126">Dieses Update wird schrittweise Roll out über Outlook und Teams in den nächsten Monaten.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-126">This update will gradually roll out across Outlook and Teams in the coming months.</span></span>


<a name="microsoft-teams-and-office-365"></a><span data-ttu-id="ad0ff-127">Microsoft Teams und Office 365</span><span class="sxs-lookup"><span data-stu-id="ad0ff-127">Microsoft Teams and Office 365</span></span>
------------------------------

<span data-ttu-id="ad0ff-128">Verschiedene Gruppen haben unterschiedliche Anforderungen, die auf ihrer jeweiligen funktionalen Rolle und Arbeitsweise basieren.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-128">Different groups have various needs, based on their functional role and workstyle.</span></span> <span data-ttu-id="ad0ff-129">Office 365 ist für die individuelle Arbeitsweise jeder Gruppe konzipiert und umfasst speziell entwickelte integrierte Anwendungen wie zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ad0ff-129">Office 365 is designed for the unique workstyle of every group and includes purpose-built, integrated applications, including:</span></span>

-   <span data-ttu-id="ad0ff-130">Outlook für E-Mail auf Unternehmensniveau, jetzt mit Gruppenfunktionen</span><span class="sxs-lookup"><span data-stu-id="ad0ff-130">Outlook for enterprise-grade email, now with groups functionality</span></span>

-   <span data-ttu-id="ad0ff-131">SharePoint für Websites und Portale, intelligente Inhaltsdienste, Automatisierung von Geschäftsprozessen und Unternehmenssuche</span><span class="sxs-lookup"><span data-stu-id="ad0ff-131">SharePoint for sites and portals, intelligent content services, business process automation and enterprise search</span></span>

-   <span data-ttu-id="ad0ff-132">Yammer zum Knüpfen firmenweiter Verbindungen</span><span class="sxs-lookup"><span data-stu-id="ad0ff-132">Yammer for driving company-wide connections</span></span>

-   <span data-ttu-id="ad0ff-133">Skype for Business als Backbone für Enterprise-VoIP und Video</span><span class="sxs-lookup"><span data-stu-id="ad0ff-133">Skype for Business as the backbone for enterprise voice and video</span></span>

-   <span data-ttu-id="ad0ff-134">Und jetzt auch Microsoft Teams, den neuen chatbasierten Arbeitsbereich in Office 365</span><span class="sxs-lookup"><span data-stu-id="ad0ff-134">And now, Microsoft Teams, the new chat-based workspace in Office 365</span></span>

<span data-ttu-id="ad0ff-p110">Hier sind gängige Anwendungsfälle für die einzelnen Anwendungen in Office 365. Einen detaillierten Leitfaden zur Verwendung finden Sie unter [FastTrack Productivity Library](https://go.microsoft.com/fwlink/?linkid=854630).</span><span class="sxs-lookup"><span data-stu-id="ad0ff-p110">Here are common use cases for each application in Office 365. For detailed usage guidance, visit the [FastTrack Productivity Library](https://go.microsoft.com/fwlink/?linkid=854630).</span></span>

![Microsoft Teams-Symbol](media/Overview_of_Microsoft_Teams_image1.png)

-   <span data-ttu-id="ad0ff-138">Wird von Benutzern und Teams genutzt, die in Echtzeit mit dem gleichen Personenkreis zusammenarbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-138">Leveraged by users and teams who are looking to collaborate in real-time with the same group of people.</span></span>

-   <span data-ttu-id="ad0ff-139">Hilft Teams, die ein Projekt schnell durchlaufen und dabei Dateien freigeben und zusammen an freigegebenen Projektdokumenten arbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-139">Helps teams looking to iterate quickly on a project while sharing files and collaborating on shared deliverables.</span></span>

-   <span data-ttu-id="ad0ff-140">Ermöglicht Benutzern die Verbindung eine Vielzahl von Tools in den Arbeitsbereich (beispielsweise Planner, Power BI, GitHub usw.).</span><span class="sxs-lookup"><span data-stu-id="ad0ff-140">Allows users to connect a wide range of tools into their workspace (such as Planner, Power BI, GitHub, etc.).</span></span>

![Microsoft Outlook-Symbol](media/Overview_of_Microsoft_Teams_image2.png)

-   <span data-ttu-id="ad0ff-142">Wird von Benutzern genutzt, die es vorziehen, in der vertrauten Umgebung mit E-Mail und/oder formeller und strukturierter zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-142">Leveraged by users who prefer to collaborate in the familiar environment of email and/or a more formal, structured manner.</span></span>

-   <span data-ttu-id="ad0ff-143">Bietet spezifische Geschäftsprozesse, die die Verwendung von E-Mail zum Übertragen von Dokumenten und Informationen innerhalb und außerhalb der Unternehmensgrenzen erfordern.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-143">Provides specific business processes that require email usage to transmit documents and information inside and outside corporate boundaries.</span></span>

-   <span data-ttu-id="ad0ff-144">Kommuniziert und unterhält Verbindungen mit Benutzern außerhalb unmittelbarer Arbeitsgruppen oder Organisationen.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-144">Communicates and connects with users who are outside of immediate workgroups or organizations.</span></span>

![Yammer-Symbol](media/Overview_of_Microsoft_Teams_image3.png)

-   <span data-ttu-id="ad0ff-146">Wird genutzt, um Benutzer aus der gesamten Organisation miteinander zu verbinden, praxisbezogene Communitys zu bilden und bewährte Methoden auszutauschen.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-146">Leveraged to help connect users across the organization to organize around communities of practice and share best practices.</span></span>

-   <span data-ttu-id="ad0ff-147">Verbessert funktionsübergreifende Workflows durch eine offene und transparente feedbasierte Plattform.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-147">Improves cross-functional workflows through an open and transparent feed-based platform</span></span>

-   <span data-ttu-id="ad0ff-148">Fördert den Austausch zwischen Führungskräften und Mitarbeitern durch bidirektionale Unterhaltungen zwischen der Führung und der breiteren Mitarbeiterbasis.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-148">Fosters executive-employee engagement with two-way conversations between leadership and the wider employee base</span></span>

-   <span data-ttu-id="ad0ff-149">Regt Ihre an vorderster Front stehenden Mitarbeiter dazu an, Wissen und Fachkenntnisse weiterzugeben und zu erwerben.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-149">Ignites your frontline workforce to share and receive knowledge and expertise</span></span>

![Skype for Business-Symbol](media/Overview_of_Microsoft_Teams_image4.png)

-   <span data-ttu-id="ad0ff-151">Wird für Echtzeitkommunikation und Zusammenarbeit, intern und extern mit Kunden bzw. Partnern, genutzt.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-151">Leveraged for real-time communication and collaboration both internally and externally with customers/partners.</span></span>

-   <span data-ttu-id="ad0ff-152">Ermöglicht Besprechungen mit Audio, Video und Inhalten in kleinen oder großen Teams (einschließlich Mitarbeiterversammlungen mit bis zu 10.000 Teilnehmern).</span><span class="sxs-lookup"><span data-stu-id="ad0ff-152">Provides meetings with audio, video and content with small or large teams (including Town Halls with up to 10,000 participants).</span></span>

-   <span data-ttu-id="ad0ff-153">Bietet Telefoniefunktionen für Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-153">Offers enterprise telephony functionality.</span></span>


![Microsoft SharePoint-Symbol](media/Overview_of_Microsoft_Teams_image5.png)

-   <span data-ttu-id="ad0ff-155">Wird für Websites und Portale genutzt (zum Beispiel Firmennachrichten und -ankündigungen, Suche und Zusammenarbeit an Dokumenten).</span><span class="sxs-lookup"><span data-stu-id="ad0ff-155">Leveraged for sites and portals (e.g. company news & announcements, search, and document collaboration).</span></span>

-   <span data-ttu-id="ad0ff-156">Implementiert Automatisierung von Geschäftsprozessen in Dokumentbibliotheken und Informationslisten durch Integration von Microsoft Flow und PowerApps.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-156">Implements business process automation on document libraries and lists of information by integrating Microsoft Flow and PowerApps.</span></span>

-   <span data-ttu-id="ad0ff-157">Eine SharePoint-Teamwebsite mit vollem Funktionsumfang für Dateispeicherung, Teamnachrichten, Seiten, Listen und vieles mehr wird automatisch für jedes Team in Microsoft Teams bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-157">Full-powered SharePoint team site automatically provisioned for every Microsoft Team for file storage, team news, pages, lists and more.</span></span>

-   <span data-ttu-id="ad0ff-158">Weitere Informationen finden Sie unter [Interaktion von SharePoint Online und OneDrive for Business mit Teams](SharePoint-OneDrive-interact.md)</span><span class="sxs-lookup"><span data-stu-id="ad0ff-158">See [How SharePoint Online and OneDrive for Business interact with Teams](SharePoint-OneDrive-interact.md)</span></span>

## <a name="teams-known-issuesknown-issuesmd"></a>[<span data-ttu-id="ad0ff-159">Bekannte Probleme für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ad0ff-159">Teams known issues</span></span>](Known-issues.md)

## <a name="teams-client-release-noteshttpssupportofficecomarticlerelease-notes-for-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de"></a>[<span data-ttu-id="ad0ff-160">Anmerkungen zu dieser Version des Microsoft Teams-Clients</span><span class="sxs-lookup"><span data-stu-id="ad0ff-160">Teams client release notes</span></span>](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)

## <a name="what-happened-to-the-teams-admin-faq"></a><span data-ttu-id="ad0ff-161">Was ist mit den häufig gestellten Fragen für Microsoft Teams-Administratoren geschehen?</span><span class="sxs-lookup"><span data-stu-id="ad0ff-161">What happened to the Teams admin FAQ?</span></span>

<span data-ttu-id="ad0ff-162">Die häufig gestellten Fragen für Microsoft Teams-Administratoren waren anfangs bei der Veröffentlichung von Microsoft Teams praktisch. Sie sind aber schnell so unübersichtlich geworden, dass es schwer war, etwas Bestimmtes zu finden.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-162">While the Teams Admin FAQ was handy when we first released Teams, it quickly became a "junk drawer" that made it hard to find anything specific.</span></span> <span data-ttu-id="ad0ff-163">Daher haben wir die häufig gestellten Fragen aufgeteilt und diese wertvollen Informationen in die Microsoft Teams-Dokumentation integriert, die Sie gerade lesen.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-163">So we busted apart the FAQ and incorporated its valuable information into the Teams documentation that you're looking at right now.</span></span> <span data-ttu-id="ad0ff-164">In dieser Dokumentation finden Sie alle Informationen aus den häufig gestellten Fragen im entsprechenden Kontext.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-164">You'll find all the information that was in the FAQ in this documentation, in context.</span></span>

<span data-ttu-id="ad0ff-165">Wenn Sie nach einem Thema suchen, die Sie hier nicht finden können, teilen Sie uns darüber im Abschnitt **Feedback** .</span><span class="sxs-lookup"><span data-stu-id="ad0ff-165">If you're looking for something that you can't find here, please tell us about it in the **Feedback** section below.</span></span> <span data-ttu-id="ad0ff-166">Versuchen wir, innerhalb von 24 Stunden auf Ihr Feedback zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="ad0ff-166">We try to respond to your feedback within 24 hours.</span></span>

<span data-ttu-id="ad0ff-167">Übrigens **gibt** es nach wie vor häufig gestellte Fragen zur [Reise von Skype for Business zu Microsoft Teams](FAQ-journey.md).</span><span class="sxs-lookup"><span data-stu-id="ad0ff-167">By the way, we **do** still have an FAQ for the [Journey from Skype for Business to Microsoft Teams](FAQ-journey.md).</span></span> 
