---
title: Gastzugriff in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 11/25/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
audience: admin
search.appverid: MET150
description: Gastzugriff in Microsoft Teams ermöglicht Teams in Ihrer Organisation, mit Personen außerhalb Ihrer Organisation zusammenzuarbeiten, indem ihnen Zugriff auf Teams und Kanäle gewährt wird.
localization_priority: Priority
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: adf4f9068cffa2fa3af5026f1003075e57d98bfc
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244082"
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="6153a-103">Gastzugriff in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6153a-103">Guest access in Microsoft Teams</span></span>
======================================

<span data-ttu-id="6153a-104">Bei Gastzugriff handelt es sich um eine der meistgewünschten Funktionen.</span><span class="sxs-lookup"><span data-stu-id="6153a-104">Guest access is one of the features customers asked for the most.</span></span> <span data-ttu-id="6153a-105">So können Sie sich über unsere Fortschritte beim Gastzugriff auf dem Laufenden halten und uns Ihre Meinung sagen:</span><span class="sxs-lookup"><span data-stu-id="6153a-105">Here’s how you can keep up with our progress on guest access and tell us your thoughts:</span></span>

- <span data-ttu-id="6153a-106">Wenn Sie Probleme mit dem Gastzugriff haben, lesen Sie [Bekannte Probleme für Microsoft Teams](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6153a-106">If you’re having trouble with Guest Access, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="6153a-107">Informationen zu geplanten neuen oder aktualisierten Funktionen finden Sie in der [Microsoft Teams-Roadmap](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="6153a-107">Find out about upcoming new or updated features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="6153a-108">Teilen Sie uns auf der [Microsoft Teams-UserVoice](https://aka.ms/TeamsUserVoice)-Website Ihre Wünsche mit.</span><span class="sxs-lookup"><span data-stu-id="6153a-108">Tell us what you want in  [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>
- <span data-ttu-id="6153a-109">Berichten Sie unten im Abschnitt „Kommentare“ über Ihre Erfahrungen.</span><span class="sxs-lookup"><span data-stu-id="6153a-109">Share your experience in the Comments section below.</span></span>

## <a name="guest-access-overview"></a><span data-ttu-id="6153a-110">Übersicht Über Gastzugriff</span><span class="sxs-lookup"><span data-stu-id="6153a-110">Guest access overview</span></span>

<span data-ttu-id="6153a-111">Gastzugriff ermöglicht Teams in Ihrer Organisation, mit Personen außerhalb der Organisation zusammenzuarbeiten, indem ihnen Zugriff auf vorhandene Teams und Kanäle auf einem oder mehreren Ihrer Mandanten gewährt wird.</span><span class="sxs-lookup"><span data-stu-id="6153a-111">Guest access allows teams in your organization to collaborate with people outside your organization by granting them access to existing teams and channels on one or more of your tenants.</span></span> <span data-ttu-id="6153a-112">Alle Benutzer, die über ein E-Mail-Konto für Geschäftsbenutzer oder Heimanwender (z. B. Outlook, Gmail usw.) verfügen, können als Gäste in Microsoft Teams teilnehmen und erhalten Vollzugriff auf Chats, Besprechungen und Dateien des Teams.</span><span class="sxs-lookup"><span data-stu-id="6153a-112">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span>

<span data-ttu-id="6153a-113">Bei vielen Office 365-Abonnements ist der Gastzugriff ohne zusätzliche Lizenzierungsanforderung enthalten.</span><span class="sxs-lookup"><span data-stu-id="6153a-113">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions with no additional licensing requirement.</span></span> <span data-ttu-id="6153a-114">Weitere Informationen zu Lizenzierung finden Sie unter [Lizenzierungsanleitung zur Azure Active Directory B2B-Zusammenarbeit](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="6153a-114">For more information about licensing, see [Azure Active Directory B2B collaboration licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>

<span data-ttu-id="6153a-115">Der Gastzugriff ist eine Einstellung auf Mandantenebene in Microsoft Teams, die standardmäßig deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="6153a-115">Guest access is a tenant-level setting in Microsoft Teams and is turned off by default.</span></span> <span data-ttu-id="6153a-116">Gastzugriff unterliegt Azure AD- und Office 365-Dienstbegrenzungen.</span><span class="sxs-lookup"><span data-stu-id="6153a-116">Guest access is subject to Azure AD and Office 365 service limits.</span></span>

> [!NOTE]
> <span data-ttu-id="6153a-117">Benutzer in Ihrer Organisation, die nur über eigenständige Office 365-Abonnementpläne verfügen, z. B. Exchange Online Plan 2, können nicht als Gäste zu Ihrer Organisation eingeladen werden, da Teams diese Benutzer als derselben Organisation angehörig betrachtet.</span><span class="sxs-lookup"><span data-stu-id="6153a-117">Users in your organization who have standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="6153a-118">Damit diese Benutze Teams verwenden können, müssen Sie über ein Office 365 Business Premium-, Office 365 Enterprise- oder Office 365 Education-Abonnement verfügen.</span><span class="sxs-lookup"><span data-stu-id="6153a-118">For these users to use Teams, they must be assigned an Office 365 Business Premium, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="who-is-a-guest"></a><span data-ttu-id="6153a-119">Wer ist ein Gast?</span><span class="sxs-lookup"><span data-stu-id="6153a-119">Who is a guest?</span></span>

<span data-ttu-id="6153a-120">Ein Gast ist kein Mitarbeiter, Schüler/Student oder Mitglied Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="6153a-120">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="6153a-121">Er verfügt über kein Geschäfts-, Schul- oder Unikonto bei Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="6153a-121">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="6153a-122">Gäste können beispielsweise Partner, Hersteller, Lieferanten oder Berater sein.</span><span class="sxs-lookup"><span data-stu-id="6153a-122">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="6153a-123">Jede Person, die nicht Teil Ihrer Organisation ist, kann als Gast in Teams hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="6153a-123">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="6153a-124">Dies bedeutet, dass jeder Benutzer mit einem Business-Konto (d. h. ein Azure Active Directory-Konto) oder E-Mail-Consumer-Konto (mit Outlook.com, Gmail.com oder einer sonstigen Adresse) als Gast in Teams teilnehmen kann – mit vollständigem Zugriff auf Team- und Kanalfunktionen.</span><span class="sxs-lookup"><span data-stu-id="6153a-124">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span></span> <span data-ttu-id="6153a-125">(Informationen zu Gastbeschränkungen finden Sie unter [Autorisieren des Gastzugriffs in Microsoft Teams](teams-dependencies.md).) Für alle Gäste in Microsoft Teams gelten die gleichen Compliance- und Überwachungsmaßnahmen wie überall in Office 365. Gäste können in Azure AD sicher verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="6153a-125">(You can read about guest restrictions in [Authorize guest access in Microsoft Teams](teams-dependencies.md).) All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and can be managed securely within Azure AD.</span></span>

## <a name="why-use-guest-access"></a><span data-ttu-id="6153a-126">Warum Gastzugriff verwenden?</span><span class="sxs-lookup"><span data-stu-id="6153a-126">Why use guest access?</span></span>

<span data-ttu-id="6153a-127">Mit Gastzugriff können Organisationen, die Teams verwenden, ihren Partnern externen Zugriff auf Teams, Dokumente in Kanälen, Ressourcen, Chats und Anwendungen gewähren und gleichzeitig die vollständige Kontrolle über ihre eigenen Unternehmensdaten behalten.</span><span class="sxs-lookup"><span data-stu-id="6153a-127">With guest access, organizations that use Teams can provide external access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> <span data-ttu-id="6153a-128">Für alle Gäste in Microsoft Teams gelten die gleichen Compliance- und Überwachungsmaßnahmen wie überall in Office 365. Gäste können in Azure AD sicher verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="6153a-128">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure AD.</span></span>  

<span data-ttu-id="6153a-129">Teams basiert auf Office 365-Gruppen und bietet neue Möglichkeiten, auf freigegebene Ressourcen für eine Office 365-Gruppe zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="6153a-129">Teams is built on Office 365 Groups and provides a new way to access shared assets for an Office 365 group.</span></span> <span data-ttu-id="6153a-130">Teams ist die beste Lösung für beständigen Chat zwischen Gruppen- bzw. Teammitgliedern.</span><span class="sxs-lookup"><span data-stu-id="6153a-130">Teams is the best solution for persistent chat among group/team members.</span></span> <span data-ttu-id="6153a-131">Office 365-Gruppen ist ein Dienst, der anwendungsübergreifende Mitgliedschaft für bestimmte freigegebene Teamressourcen (beispielsweise eine SharePoint-Website oder ein Power BI-Dashboard) bietet, damit das Team effektiv und sicher zusammenarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="6153a-131">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span></span> 

## <a name="how-does-guest-access-compare-to-external-access-federation"></a><span data-ttu-id="6153a-132">Inwiefern unterscheidet sich der Gastzugriff von externem Zugriff (Verbund)?</span><span class="sxs-lookup"><span data-stu-id="6153a-132">How does guest access compare to external access (federation)?</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="6153a-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6153a-133">More information</span></span>

[<span data-ttu-id="6153a-134">Kontakt mit dem Support für Geschäftsprodukte aufnehmen – Administratorhilfe</span><span class="sxs-lookup"><span data-stu-id="6153a-134">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)  
[<span data-ttu-id="6153a-135">Gastzugriff in Office 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="6153a-135">Guest access in Office 365 Groups</span></span>](https://support.office.com/de-DE/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
