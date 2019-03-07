---
title: Gastzugriff in Microsoft Teams
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/25/2018
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
search.appverid: MET150
description: Gastzugriff in Microsoft Teams ermöglicht Teams in Ihrer Organisation, mit Personen außerhalb Ihrer Organisation zusammenzuarbeiten, indem ihnen Zugriff auf Teams und Kanäle gewährt wird.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 59cd4e06d3a5a98298d67fcfbb785efb371fe0f0
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "30458828"
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="960dd-103">Gastzugriff in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="960dd-103">Guest access in Microsoft Teams</span></span>
======================================

## <a name="guest-access-overview"></a><span data-ttu-id="960dd-104">Übersicht über den Datenzugriff Gast</span><span class="sxs-lookup"><span data-stu-id="960dd-104">Guest access overview</span></span>

<span data-ttu-id="960dd-105">Gastzugriff ist eines der Features, die für die meisten Kunden hatten.</span><span class="sxs-lookup"><span data-stu-id="960dd-105">Guest access is one of the features customers asked for the most.</span></span> <span data-ttu-id="960dd-106">Hier wird, wie Sie mit den Fortschritt auf Gast Access halten und teilen Sie uns Ihre Meinung:</span><span class="sxs-lookup"><span data-stu-id="960dd-106">Here’s how you can keep up with our progress on guest access and tell us your thoughts:</span></span>

- <span data-ttu-id="960dd-107">Wenn Sie Probleme mit dem Gastzugriff haben, lesen Sie [Bekannte Probleme für Microsoft Teams](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="960dd-107">If you’re having trouble with Guest Access, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="960dd-108">Informationen zu geplanten neuen oder aktualisierten Funktionen finden Sie in der [Microsoft Teams-Roadmap](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="960dd-108">Find out about upcoming new or updated features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="960dd-109">Teilen Sie uns auf der [Microsoft Teams-UserVoice](https://aka.ms/TeamsUserVoice)-Website Ihre Wünsche mit.</span><span class="sxs-lookup"><span data-stu-id="960dd-109">Tell us what you want in  [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>
- <span data-ttu-id="960dd-110">Berichten Sie unten im Abschnitt „Kommentare“ über Ihre Erfahrungen.</span><span class="sxs-lookup"><span data-stu-id="960dd-110">Share your experience in the Comments section below.</span></span>

<span data-ttu-id="960dd-111">Gast Access ermöglicht Teams in Ihrer Organisation für die Zusammenarbeit mit Personen außerhalb Ihrer Organisation durch gewähren sie Zugriff auf vorhandenen Teams und Kanäle in einem oder mehreren Mandanten.</span><span class="sxs-lookup"><span data-stu-id="960dd-111">Guest access allows teams in your organization to collaborate with people outside your organization by granting them access to existing teams and channels on one or more of your tenants.</span></span> <span data-ttu-id="960dd-112">Alle Benutzer, die über ein E-Mail-Konto für Geschäftsbenutzer oder Heimanwender (z. B. Outlook, Gmail usw.) verfügen, können als Gäste in Microsoft Teams teilnehmen und erhalten Vollzugriff auf Chats, Besprechungen und Dateien des Teams.</span><span class="sxs-lookup"><span data-stu-id="960dd-112">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span>

<span data-ttu-id="960dd-113">Gastzugriff ist in allen Office 365 Business Premium, Office 365 Enterprise und Office 365 Education Abonnements mit keine zusätzliche Lizenzierung Anforderung enthalten.</span><span class="sxs-lookup"><span data-stu-id="960dd-113">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions with no additional licensing requirement.</span></span> <span data-ttu-id="960dd-114">Sie können bis zu 5 Gäste pro lizenzierten Benutzer bei Ihrem Mandanten haben.</span><span class="sxs-lookup"><span data-stu-id="960dd-114">You can have up to 5 guests per licensed user on your tenant.</span></span> <span data-ttu-id="960dd-115">Weitere Informationen zur Lizenzierung finden Sie unter [Azure Active Directory B2B Zusammenarbeit Lizenzierung Anweisungen](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="960dd-115">For more information about licensing, see [Azure Active Directory B2B collaboration licensing guidance](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance).</span></span> 

<span data-ttu-id="960dd-116">Der Gastzugriff ist eine Einstellung auf Mandantenebene in Microsoft Teams, die standardmäßig deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="960dd-116">Guest access is a tenant-level setting in Microsoft Teams and is turned off by default.</span></span> <span data-ttu-id="960dd-117">Gast Access unterliegt Azure AD und Einschränkungen für Office 365-Dienst.</span><span class="sxs-lookup"><span data-stu-id="960dd-117">Guest access is subject to Azure AD and Office 365 service limits.</span></span>

> [!NOTE]
> <span data-ttu-id="960dd-118">Benutzer in Ihrer Organisation mit Office 365-Abonnement-Plänen nur, wie Exchange Online – Plan 2, können nicht als Gäste zu Ihrer Organisation eingeladen werden, da Teams betrachtet diese Benutzer in derselben Organisation angehören.</span><span class="sxs-lookup"><span data-stu-id="960dd-118">Users in your organization who have standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="960dd-119">Für diese Benutzer zu Teams verwenden müssen sie ein Office 365 Business Premium, Office 365 Enterprise oder Office 365 Education-Abonnement zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="960dd-119">For these users to use Teams, they must be assigned an Office 365 Business Premium, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="who-is-a-guest"></a><span data-ttu-id="960dd-120">Wer ist Gastsystem?</span><span class="sxs-lookup"><span data-stu-id="960dd-120">Who is a guest?</span></span>

<span data-ttu-id="960dd-121">Ein Gast ist kein Mitarbeiter, Schüler/Student oder Mitglied Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="960dd-121">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="960dd-122">Er verfügt über kein Geschäfts-, Schul- oder Unikonto bei Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="960dd-122">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="960dd-123">Gäste können beispielsweise Partner, Hersteller, Lieferanten oder Berater sein.</span><span class="sxs-lookup"><span data-stu-id="960dd-123">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="960dd-124">Jeder Benutzer, der nicht Teil Ihrer Organisation ist, kann als Gast in Teams hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="960dd-124">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="960dd-125">Dies bedeutet, dass jeder Benutzer mit einer Business-Konto (d. h., ein Azure Active Directory-Konto) oder die Consumer e-Mail-Konto (mit Outlook.com, Gmail.com oder andere) als Gast in Teams, mit Vollzugriff auf den Teams teilnehmen kann und Channel guter.</span><span class="sxs-lookup"><span data-stu-id="960dd-125">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span></span> <span data-ttu-id="960dd-126">(Sie können über Gast Einschränkungen in [Access Gast autorisieren Microsoft-Teams](teams-dependencies.md)lesen.) Alle Gäste in Teams unterliegen den gleichen Einhaltung von Vorschriften und Überwachung Schutz als den Rest von Office 365 und in Azure AD sicher verwaltet werden können.</span><span class="sxs-lookup"><span data-stu-id="960dd-126">(You can read about guest restrictions in [Authorize guest access in Microsoft Teams](teams-dependencies.md).) All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and can be managed securely within Azure AD.</span></span>

## <a name="why-use-guest-access"></a><span data-ttu-id="960dd-127">Gründe für die Verwendung von Access Gast</span><span class="sxs-lookup"><span data-stu-id="960dd-127">Why use guest access?</span></span>
      
<span data-ttu-id="960dd-128">Mit Gast Access können Organisationen, mit denen Teams externen Zugriff auf Teams, Dokumente in Kanäle, Ressourcen, Chats und an ihre Partner Applications Beibehaltung vollständige Kontrolle über ihre eigenen Unternehmensdaten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="960dd-128">With guest access, organizations that use Teams can provide external access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> <span data-ttu-id="960dd-129">Alle Gäste in Teams unterliegen den gleichen Einhaltung von Vorschriften und Überwachung Schutz als den Rest von Office 365 und Gäste in Azure AD sicher verwaltet werden können.</span><span class="sxs-lookup"><span data-stu-id="960dd-129">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure AD.</span></span>  

<span data-ttu-id="960dd-130">Teams basiert auf Office 365-Gruppen und bietet eine neue Möglichkeit zum Zugriff auf gemeinsame Elemente für ein Office 365-Gruppe.</span><span class="sxs-lookup"><span data-stu-id="960dd-130">Teams is built on Office 365 Groups and provides a new way to access shared assets for an Office 365 group.</span></span> <span data-ttu-id="960dd-131">Teams ist die beste Lösung für beständigen Chat zwischen Gruppen- bzw. Teammitgliedern.</span><span class="sxs-lookup"><span data-stu-id="960dd-131">Teams is the best solution for persistent chat among group/team members.</span></span> <span data-ttu-id="960dd-132">Office 365-Gruppen ist ein Dienst, der anwendungsübergreifende Mitgliedschaft für bestimmte freigegebene Teamressourcen (beispielsweise eine SharePoint-Website oder ein Power BI-Dashboard) bietet, damit das Team effektiv und sicher zusammenarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="960dd-132">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span></span> 

## <a name="how-does-guest-access-compare-to-external-access-federation"></a><span data-ttu-id="960dd-133">Wie Vergleich Access Gast im zu den externen Zugriff (Verbund)?</span><span class="sxs-lookup"><span data-stu-id="960dd-133">How does guest access compare to external access (federation)?</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="960dd-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="960dd-134">More information</span></span>
    
[<span data-ttu-id="960dd-135">Supportressourcen für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="960dd-135">Support resources for Microsoft Teams</span></span>](support-resources.md)  
[<span data-ttu-id="960dd-136">Gast Access in Office 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="960dd-136">Guest access in Office 365 Groups</span></span>](https://support.office.com/en-us/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
|  |  |
|---------|---------|
|<span data-ttu-id="960dd-137">Einführung in Access Gast</span><span class="sxs-lookup"><span data-stu-id="960dd-137">Introduction to to guest access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/D8DW2Urv5y8" frameborder="0" allowfullscreen></iframe>   |
|<span data-ttu-id="960dd-138">Ausführliche Behandlung von Gastzugriff</span><span class="sxs-lookup"><span data-stu-id="960dd-138">Deep dive into guest access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/vaJRRSjBxxY" frameborder="0" allowfullscreen></iframe>   |
| <span data-ttu-id="960dd-139">Hinzufügen von Gäste in Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="960dd-139">Adding guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
    

