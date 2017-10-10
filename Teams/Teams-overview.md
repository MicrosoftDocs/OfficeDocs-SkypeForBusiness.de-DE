---
title: "Übersicht über Microsoft Teams | Microsoft-Support"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Hier erhalten Sie Informationen zu Microsoft Teams, zur Infrastruktur und zur Verwendung von Teams mit Office 365."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 7f28dc24baab9ba3d61b3181c05a09d108c320f3
ms.sourcegitcommit: e0efee5350da54a1f1ae1c317f8613652c820bc6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2017
---
<a name="overview-of-microsoft-teams"></a><span data-ttu-id="c1cfe-103">Übersicht über Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c1cfe-103">Overview of Microsoft Teams</span></span>
===========================
|  |  |
|---------|---------|
|<iframe width="560" height="315" src="https://www.youtube.com/embed/FFQszYALS_A" frameborder="0" allowfullscreen></iframe> | |

<span data-ttu-id="c1cfe-p101">Microsoft Teams vereint den vollen Funktionsumfang von Office 365 in einem wirklich chatbasierten Hub für Teamarbeit und gibt Kunden die Gelegenheit, eine offenere, flüssigere und digitale Umgebung zu schaffen. Microsoft Teams basiert auf vorhandenen Microsoft-Technologien, die durch Office 365-Gruppen verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="c1cfe-p101">Microsoft Teams brings together the full breadth and depth of Office 365, to provide a true chat-based hub for teamwork and give customers the opportunity to create a more open, fluid, and digital environment. Microsoft Teams is built on existing Microsoft technologies woven together by Office 365 Groups.</span></span> 

<span data-ttu-id="c1cfe-106">Teams nutzt standardmäßig die in Azure Active Directory (Azure AD) gespeicherten Identitäten und wird in die anderen Dienste in Office 365 integriert, um für jedes erstellte Team eine SharePoint Online-Website und ein Exchange Online-Gruppenpostfach zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c1cfe-106">Out of the box, Microsoft Teams leverages identities stored in Azure Active Directory (Azure AD) and integrates with the other services within Office 365, to create a SharePoint online site and an Exchange Online group mailbox for each team created.</span></span>

<span data-ttu-id="c1cfe-107">Beständiger Chat wird in Teams durch einen Chatdienst bereitgestellt, der mit Office 365 interagiert und viele der integrierten Office 365-Funktionen (z. B. Archivierung und eDiscovery) für die in Teams ausgetauschten Daten verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="c1cfe-107">Microsoft Teams persistent chat capability is provided by a chat service that interacts with the Office 365 substrate, surfacing many of the built-in Office 365 capabilities, such as archiving and eDiscovery to the data being exchanged in Microsoft Teams.</span></span>

<span data-ttu-id="c1cfe-108">Teams bietet darüber hinaus Anruf- und Besprechungsfunktionen auf der Grundlage der cloudbasierten Infrastruktur der nächsten Generation, die auch von Skype und Skype for Business genutzt wird.</span><span class="sxs-lookup"><span data-stu-id="c1cfe-108">Microsoft Teams also provides a calling and meetings experience that is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business. These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="c1cfe-109">Zu diesen Technologieinvestitionen gehören Azure-basierte Clouddienste für Medienverarbeitung und Signalisierung, der Videocodec H.264, die Audiocodecs SILK und Opus, Netzwerkresilienz, Telemetrie und Qualitätsdiagnose.</span><span class="sxs-lookup"><span data-stu-id="c1cfe-109">Microsoft Teams also provides a calling and meetings experience that is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business. These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span>

<span data-ttu-id="c1cfe-110">Zum Erweitern der Funktionen von Teams stehen Connectors, Registerkarten und Bots als [Apps](https://go.microsoft.com/fwlink/?linkid=854629) zur Verfügung, mit denen externe Informationen, Inhalte und Interaktionen mit intelligenten Bots in Teams integriert werden können.</span><span class="sxs-lookup"><span data-stu-id="c1cfe-110">To extend Microsoft Teams capabilities, Connectors, Tabs, and Bots are available as [Apps](https://go.microsoft.com/fwlink/?linkid=854629) to bring external information, content, and intelligent bots’ interactions to Microsoft Teams.</span></span>

<a name="microsoft-teams-infrastructure"></a><span data-ttu-id="c1cfe-111">Infrastruktur von Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c1cfe-111">Microsoft Teams infrastructure</span></span>
------------------------------

<span data-ttu-id="c1cfe-112">Teams basiert auf vorhandenen Microsoft-Technologien, die durch Office 365-Gruppen verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="c1cfe-112">Teams is built on existing Microsoft technologies, woven together by Office 365 Groups.</span></span> <span data-ttu-id="c1cfe-113">Unterstützt von der Cloud von Microsoft können Organisationen exzellente Leistung und Zuverlässigkeit erwarten, wenn sie Teams als Bestandteil ihrer Zusammenarbeitslösung nutzen.</span><span class="sxs-lookup"><span data-stu-id="c1cfe-113">Microsoft Teams is built on existing Microsoft technologies woven together by Office 365 Groups. Powered by Microsoft’s cloud, organizations can expect excellent performance and reliability when leveraging Microsoft Teams as part of their collaboration story.</span></span>

<span data-ttu-id="c1cfe-114">Standardmäßig wird für ein in Teams erstelltes Team jeweils eine Office 365-Gruppe mit der zugehörigen SharePoint Online-Website erstellt – einschließlich einer Dokumentbibliothek und eines Exchange Online-Gruppenpostfachs, das von Teams zum Speichern von Informationen wie zum Beispiel Besprechungseinladungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c1cfe-114">Out of the box, a team created in Teams will create an Office 365 Group, a SharePoint Online site (complete with a document library), and an Exchange Online group mailbox, which will be used by Teams to store information such as meeting invites.</span></span> <span data-ttu-id="c1cfe-115">Ein Team kann mithilfe vorhandener Office 365-Gruppen erstellt werden, sodass vorhandene Gruppenmitgliedschaften und Inhalte, die in SharePoint Online und Exchange Online gespeichert sind, nach Teams portiert werden können.</span><span class="sxs-lookup"><span data-stu-id="c1cfe-115">A team can be created using existing Office 365 Groups, allowing existing group memberships, and contents stored in SharePoint Online and Exchange Online to be ported to Teams.</span></span>

<span data-ttu-id="c1cfe-116">Beständiger Chat wird in Teams durch einen Chatdienst bereitgestellt, der mit dem Office 365-Substrat interagiert und viele der integrierten Office 365-Funktionen (z. B. Archivierung und eDiscovery) für die in Teams ausgetauschten Daten verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="c1cfe-116">Microsoft Teams persistent chat capability is provided by a chat service that interacts with the Office 365 substrate, surfacing many of the built-in Office 365 capabilities, such as archiving and eDiscovery to the data being exchanged in Microsoft Teams.</span></span>

<span data-ttu-id="c1cfe-117">Als Ergänzung zu Teams als Board für beständigen Chat, auf dem formlose Echtzeitunterhaltungen stattfinden können, bietet Teams außerdem Besprechungsfunktionen auf der Grundlage der cloudbasierten Infrastruktur der nächsten Generation, die auch von Skype und Skype for Business genutzt wird.</span><span class="sxs-lookup"><span data-stu-id="c1cfe-117">To complement Microsoft Teams capability as a persistent chat board where informal, real-time, conversations around very focused topics or specific sub-groups within the group take place, Teams also provides a meeting’s experience built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business. These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="c1cfe-118">Zu diesen Technologieinvestitionen gehören Azure-basierte Clouddienste für Medienverarbeitung und Signalisierung, der Videocodec H.264, die Audiocodecs SILK und Opus, Netzwerkresilienz, Telemetrie und Qualitätsdiagnose.</span><span class="sxs-lookup"><span data-stu-id="c1cfe-118">Microsoft Teams also provides a calling and meetings experience that is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business. These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span>

<span data-ttu-id="c1cfe-119">Office 365-Gruppen nutzen in Azure Active Directory (Azure AD) gespeicherte Identitäten. Damit sind alle Authentifizierungs- und Autorisierungsfunktionen in Azure AD wie Unterstützung für mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) direkt zur Verwendung durch Teams verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c1cfe-119">Office 365 Groups leverage identities stored in Azure Active Directory (Azure AD) and as such, all authentication and authorization capabilities in Azure AD, such as support for multi-factor authentication (MFA), is readily available for use by Microsoft Teams.</span></span>


<a name="microsoft-teams-and-office-365"></a><span data-ttu-id="c1cfe-120">Microsoft Teams und Office 365</span><span class="sxs-lookup"><span data-stu-id="c1cfe-120">Microsoft Teams and Office 365</span></span>
------------------------------

<span data-ttu-id="c1cfe-121">Verschiedene Gruppen haben unterschiedliche Anforderungen, die auf ihrer jeweiligen funktionalen Rolle und Arbeitsweise basieren.</span><span class="sxs-lookup"><span data-stu-id="c1cfe-121">Different groups have various needs, based on their functional role and workstyle.</span></span> <span data-ttu-id="c1cfe-122">Office 365 ist für die individuelle Arbeitsweise jeder Gruppe konzipiert und umfasst speziell entwickelte integrierte Anwendungen wie zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c1cfe-122">Different groups have various needs based on their functional role and workstyle. Office 365 is designed for the unique workstyle of every group and includes purpose-built, integrated applications, such as:</span></span>

-   <span data-ttu-id="c1cfe-123">Outlook für E-Mail auf Unternehmensniveau, jetzt mit Gruppenfunktionen</span><span class="sxs-lookup"><span data-stu-id="c1cfe-123">Outlook for enterprise-grade email, now with groups functionality.</span></span>

-   <span data-ttu-id="c1cfe-124">SharePoint für Websites und Portale, intelligente Inhaltsdienste, Automatisierung von Geschäftsprozessen und Unternehmenssuche</span><span class="sxs-lookup"><span data-stu-id="c1cfe-124">SharePoint for sites and portals, intelligent content services, business process automation and enterprise search.</span></span>

-   <span data-ttu-id="c1cfe-125">Yammer zum Knüpfen firmenweiter Verbindungen</span><span class="sxs-lookup"><span data-stu-id="c1cfe-125">Yammer for driving company-wide connections</span></span>

-   <span data-ttu-id="c1cfe-126">Skype for Business als Backbone für Enterprise-VoIP und Video</span><span class="sxs-lookup"><span data-stu-id="c1cfe-126">Skype for Business as the backbone for enterprise voice and video.</span></span>

-   <span data-ttu-id="c1cfe-127">Und jetzt auch Microsoft Teams, den neuen chatbasierten Arbeitsbereich in Office 365</span><span class="sxs-lookup"><span data-stu-id="c1cfe-127">And now, Microsoft Teams, the new chat-based workspace in Office 365.</span></span>

<span data-ttu-id="c1cfe-p107">Hier sind gängige Anwendungsfälle für die einzelnen Anwendungen in Office 365. Einen detaillierten Leitfaden zur Verwendung finden Sie unter [FastTrack Productivity Library](https://go.microsoft.com/fwlink/?linkid=854630).</span><span class="sxs-lookup"><span data-stu-id="c1cfe-p107">Here are common use cases for each application in Office 365. For detailed usage guidance, visit the [FastTrack Productivity Library](https://go.microsoft.com/fwlink/?linkid=854630).</span></span>

![](media/Overview_of_Microsoft_Teams_image1.png)

-   <span data-ttu-id="c1cfe-130">Wird von Benutzern und Teams genutzt, die in Echtzeit mit dem gleichen Personenkreis zusammenarbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="c1cfe-130">Leveraged by users and teams who are looking to collaborate in real-time with the same group of people.</span></span>

-   <span data-ttu-id="c1cfe-131">Hilft Teams, die ein Projekt schnell durchlaufen und dabei Dateien freigeben und zusammen an freigegebenen Projektdokumenten arbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="c1cfe-131">Helps teams looking to iterate quickly on a project while sharing files and collaborating on shared deliverables.</span></span>

-   <span data-ttu-id="c1cfe-132">Ermöglicht Benutzern das Einbinden einer breiten Palette von Tools in ihren Arbeitsbereich (z. B. Planner, Power BI, GitHub usw.).</span><span class="sxs-lookup"><span data-stu-id="c1cfe-132">Allows Users looking to connect a wide range of tools into their workspace (such as Planner, Power BI, GitHub, etc.).</span></span>

![](media/Overview_of_Microsoft_Teams_image2.png)

-   <span data-ttu-id="c1cfe-133">Wird von Benutzern genutzt, die es vorziehen, in der vertrauten Umgebung mit E-Mail und/oder formeller und strukturierter zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="c1cfe-133">Leveraged by users who prefer to collaborate in the familiar environment of email and/or a more formal, structured manner.</span></span>

-   <span data-ttu-id="c1cfe-134">Bietet spezifische Geschäftsprozesse, die die Verwendung von E-Mail zum Übertragen von Dokumenten und Informationen innerhalb und außerhalb der Unternehmensgrenzen erfordern.</span><span class="sxs-lookup"><span data-stu-id="c1cfe-134">Provides specific business processes that require email usage to transmit documents and information inside and outside corporate boundaries.</span></span>

-   <span data-ttu-id="c1cfe-135">Kommuniziert und unterhält Verbindungen mit Benutzern außerhalb unmittelbarer Arbeitsgruppen oder Organisationen.</span><span class="sxs-lookup"><span data-stu-id="c1cfe-135">Communicates and connects with users who are outside of immediate workgroups or organizations.</span></span>

![](media/Overview_of_Microsoft_Teams_image3.png)

-   <span data-ttu-id="c1cfe-136">Wird genutzt, um Benutzer aus der gesamten Organisation miteinander zu verbinden, praxisbezogene Communitys zu bilden und bewährte Methoden auszutauschen.</span><span class="sxs-lookup"><span data-stu-id="c1cfe-136">Leveraged to help connect users across the organization to organize around communities of practice and share best practices.</span></span>

-   <span data-ttu-id="c1cfe-137">Verbessert funktionsübergreifende Workflows durch eine offene und transparente feedbasierte Plattform.</span><span class="sxs-lookup"><span data-stu-id="c1cfe-137">Improves cross-functional workflows through an open and transparent feed-based platform</span></span>

-   <span data-ttu-id="c1cfe-138">Fördert den Austausch zwischen Führungskräften und Mitarbeitern durch bidirektionale Unterhaltungen zwischen der Führung und der breiteren Mitarbeiterbasis.</span><span class="sxs-lookup"><span data-stu-id="c1cfe-138">Fosters executive-employee engagement with two-way conversations between leadership and the wider employee base</span></span>

-   <span data-ttu-id="c1cfe-139">Regt Ihre an vorderster Front stehenden Mitarbeiter dazu an, Wissen und Fachkenntnisse weiterzugeben und zu erwerben.</span><span class="sxs-lookup"><span data-stu-id="c1cfe-139">Ignites your frontline workforce to share and receive knowledge and expertise</span></span>

![](media/Overview_of_Microsoft_Teams_image4.png)

-   <span data-ttu-id="c1cfe-140">Wird für Echtzeitkommunikation und Zusammenarbeit, intern und extern mit Kunden bzw. Partnern, genutzt.</span><span class="sxs-lookup"><span data-stu-id="c1cfe-140">Leveraged for real-time communication and collaboration both internally and externally with customers/partners.</span></span>

-   <span data-ttu-id="c1cfe-141">Ermöglicht Besprechungen mit Audio, Video und Inhalten in kleinen oder großen Teams (einschließlich Mitarbeiterversammlungen mit bis zu 10.000 Teilnehmern).</span><span class="sxs-lookup"><span data-stu-id="c1cfe-141">Provides meetings with audio, video and content with small or large teams (including Town Halls with up to 10,000 participants).</span></span>

-   <span data-ttu-id="c1cfe-142">Bietet Telefoniefunktionen für Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="c1cfe-142">Offers enterprise telephony functionality.</span></span>


![](media/Overview_of_Microsoft_Teams_image5.png)

-   <span data-ttu-id="c1cfe-143">Wird für Websites und Portale genutzt (zum Beispiel Firmennachrichten und -ankündigungen, Suche und Zusammenarbeit an Dokumenten).</span><span class="sxs-lookup"><span data-stu-id="c1cfe-143">Leveraged for sites and portals (e.g. company news & announcements, search, and document collaboration).</span></span>

-   <span data-ttu-id="c1cfe-144">Implementiert Automatisierung von Geschäftsprozessen in Dokumentbibliotheken und Informationslisten durch Integration von Microsoft Flow und PowerApps.</span><span class="sxs-lookup"><span data-stu-id="c1cfe-144">Implements business process automation on document libraries and lists of information by integrating Microsoft Flow and PowerApps.</span></span>

-   <span data-ttu-id="c1cfe-145">Eine SharePoint-Teamwebsite mit vollem Funktionsumfang für Dateispeicherung, Teamnachrichten, Seiten, Listen und vieles mehr wird automatisch für jedes Team in Microsoft Teams bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c1cfe-145">Full-powered SharePoint team site automatically provisioned for every Microsoft Team for file storage, team news, pages, lists and more.</span></span>

-   <span data-ttu-id="c1cfe-146">Weitere Informationen finden Sie unter [Interaktion von SharePoint Online und OneDrive for Business mit Teams](SharePoint-OneDrive-interact.md)</span><span class="sxs-lookup"><span data-stu-id="c1cfe-146">See [How SharePoint Online and OneDrive for Business interact with Teams](SharePoint-OneDrive-interact.md)</span></span>
