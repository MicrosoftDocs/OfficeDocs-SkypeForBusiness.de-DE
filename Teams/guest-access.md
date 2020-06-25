---
title: Gastzugriff in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
audience: admin
search.appverid: MET150
description: Gastzugriff in Microsoft Teams ermöglicht Teams in Ihrer Organisation, mit Personen außerhalb Ihrer Organisation zusammenzuarbeiten, indem ihnen Zugriff auf Teams und Kanäle gewährt wird.
localization_priority: Priority
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c025e408842c3d883112b7c99d930fc77db47435
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "44867972"
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="d58e4-103">Gastzugriff in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d58e4-103">Guest access in Microsoft Teams</span></span>
======================================

<span data-ttu-id="d58e4-104">Mit Gastzugriff können Sie einzelne Benutzer von außerhalb Ihrer Organisation zu Ihren Teams und Kanälen in Microsoft Teams hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d58e4-104">Guest access lets you add individual users from outside your organization to your teams and channels in Microsoft Teams.</span></span> 

<span data-ttu-id="d58e4-105">Wenn Sie den externen Zugriff (Partnerverbund) mit Gastzugriff vergleichen möchten (und entscheiden, welchen Sie verwenden sollten), lesen Sie [Kommunizieren mit Benutzern aus anderen Organisationen in Teams](communicate-with-users-from-other-organizations.md).</span><span class="sxs-lookup"><span data-stu-id="d58e4-105">To compare external access (federation) with guest access (and decide which one you should use), read [Communicate with users from other organizations in Teams](communicate-with-users-from-other-organizations.md).</span></span>

<span data-ttu-id="d58e4-106">Wenn Sie bereit sind, den Gastzugriff in Ihrer Organisation zu aktivieren, starten Sie mit der [Checkliste für den Gastzugriff](guest-access-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="d58e4-106">If you're ready to turn on guest access in your organization, start with the [Guest access checklist](guest-access-checklist.md).</span></span>

## <a name="guest-access-overview"></a><span data-ttu-id="d58e4-107">Übersicht über Gastzugriff</span><span class="sxs-lookup"><span data-stu-id="d58e4-107">Guest access overview</span></span>

<span data-ttu-id="d58e4-108">Gastzugriff ermöglicht Teams in Ihrer Organisation, mit Personen außerhalb Ihrer Organisation zusammenzuarbeiten, indem ihnen Zugriff auf vorhandene Teams und Kanäle in Teams gewährt wird.</span><span class="sxs-lookup"><span data-stu-id="d58e4-108">Guest access allows teams in your organization to collaborate with people outside your organization by granting them access to existing teams and channels in Teams.</span></span> <span data-ttu-id="d58e4-109">Alle Benutzer, die über ein E-Mail-Konto für Geschäftsbenutzer oder Heimanwender (z. B. Outlook, Gmail usw.) verfügen, können als Gäste in Microsoft Teams teilnehmen und erhalten Vollzugriff auf Chats, Besprechungen und Dateien des Teams.</span><span class="sxs-lookup"><span data-stu-id="d58e4-109">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span> <span data-ttu-id="d58e4-110">Als Teams-Administrator können Sie steuern, welche Funktionen Gäste in Teams verwenden (und welche nicht). Informieren Sie sich unter [ Verwalten des Gastzugriffs](manage-guests.md).</span><span class="sxs-lookup"><span data-stu-id="d58e4-110">As the Teams admin, you control which features guests can (and can't) use in Teams - check out [Manage guest access](manage-guests.md).</span></span>

<span data-ttu-id="d58e4-111">Der Gastzugriff ist eine organisationsweite Einstellung in Teams, die standardmäßig deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d58e4-111">Guest access is an org-wide setting in Teams and is turned off by default.</span></span> <span data-ttu-id="d58e4-112">Gastzugriff unterliegt Azure AD- und Microsoft 365- oder Office 365-Dienstbegrenzungen.</span><span class="sxs-lookup"><span data-stu-id="d58e4-112">Guest access is subject to Azure AD and Microsoft 365 or Office 365 service limits.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="d58e4-113">Gastbenutzer folgen den organisationsweiten Einstellungen in Teams für den Upgrade-Modus.</span><span class="sxs-lookup"><span data-stu-id="d58e4-113">Guest users follow Teams Org-wide settings for the coexistence Upgrade mode.</span></span> <span data-ttu-id="d58e4-114">Dies kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="d58e4-114">This can't be changed.</span></span>

## <a name="licensing-for-guest-access"></a><span data-ttu-id="d58e4-115">Lizenzierung für Gastzugriff</span><span class="sxs-lookup"><span data-stu-id="d58e4-115">Licensing for guest access</span></span>

<span data-ttu-id="d58e4-116">Der Gastzugang ist in allen Abonnements von Microsoft 365 Business Standard, Office 365 Enterprise und Office 365 Education enthalten.</span><span class="sxs-lookup"><span data-stu-id="d58e4-116">Guest access is included with all Microsoft 365 Business Standard, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="d58e4-117">Eine zusätzliche Microsoft 365- oder Office 365-Lizenz ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d58e4-117">No additional Microsoft 365 or Office 365 license is necessary.</span></span> <span data-ttu-id="d58e4-118">Die Anzahl von Gästen, die Sie hinzufügen können, ist in Teams nicht beschränkt.</span><span class="sxs-lookup"><span data-stu-id="d58e4-118">Teams doesn't restrict the number of guests you can add.</span></span> <span data-ttu-id="d58e4-119">Allerdings basiert die Gesamtzahl der Gäste, die Ihrem Mandanten hinzugefügt werden können, darauf, was gemäß Ihrer Azure AD-Lizenzierung zulässig ist – in der Regel 5 Gäste pro lizenziertem Benutzer.</span><span class="sxs-lookup"><span data-stu-id="d58e4-119">However, the total number of guests that can be added to your tenant is based on what your Azure AD licensing allows - usually 5 guests per licensed user.</span></span> <span data-ttu-id="d58e4-120">Weitere Informationen finden Sie unter [Lizenzierung für die Azure AD B2B-Zusammenarbeit](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="d58e4-120">For more information, see [Azure AD B2B collaboration licensing](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>


> [!NOTE]
> <span data-ttu-id="d58e4-121">Benutzer in Ihrer Organisation, die nur über eigenständige Microsoft 365- oder Office 365-Abonnementpläne verfügen, z. B. Exchange Online Plan 2, können nicht als Gäste zu Ihrer Organisation eingeladen werden, da Teams diese Benutzer als derselben Organisation angehörig betrachtet.</span><span class="sxs-lookup"><span data-stu-id="d58e4-121">Users in your organization who have standalone Microsoft 365 or Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="d58e4-122">Damit diese Benutzer Teams verwenden können, muss ihnen ein Abonnement für Microsoft 365 Business Standard, Office 365 Enterprise oder Office 365 Education zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="d58e4-122">For these users to use Teams, they must be assigned an Microsoft 365 Business Standard, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="who-is-a-guest"></a><span data-ttu-id="d58e4-123">Wer ist ein Gast?</span><span class="sxs-lookup"><span data-stu-id="d58e4-123">Who is a guest?</span></span>

<span data-ttu-id="d58e4-124">Ein Gast ist kein Mitarbeiter, Schüler/Student oder Mitglied Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="d58e4-124">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="d58e4-125">Er verfügt über kein Geschäfts-, Schul- oder Unikonto bei Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="d58e4-125">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="d58e4-126">Gäste können beispielsweise Partner, Hersteller, Lieferanten oder Berater sein.</span><span class="sxs-lookup"><span data-stu-id="d58e4-126">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="d58e4-127">Jede Person, die nicht Teil Ihrer Organisation ist, kann als Gast in Teams hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d58e4-127">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="d58e4-128">Dies bedeutet, dass jeder Benutzer mit einem Business-Konto (d. h. ein Azure Active Directory-Konto) oder E-Mail-Consumer-Konto (mit Outlook.com, Gmail.com oder einer sonstigen Adresse) als Gast in Teams teilnehmen kann – mit vollständigem Zugriff auf Team- und Kanalfunktionen.</span><span class="sxs-lookup"><span data-stu-id="d58e4-128">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span></span>

<span data-ttu-id="d58e4-129">Um zu erfahren, welche Berechtigungen Gäste haben, lesen Sie [Autorisieren des Gastzugriffs in Microsoft Teams](teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="d58e4-129">To learn more about what a guest can and can't do, read [Authorize guest access in Microsoft Teams](teams-dependencies.md).</span></span> <span data-ttu-id="d58e4-130">Oder sehen Sie sich die Tabelle [Vergleich von Funktionen für Teammitglieder und Gäste](guest-experience.md#comparison-of-team-member-and-guest-capabilities) an.</span><span class="sxs-lookup"><span data-stu-id="d58e4-130">Or check out the [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities) table.</span></span> 

<span data-ttu-id="d58e4-131">Für alle Gäste in Teams gelten letztlich dieselben Compliance- und Überwachungsmaßnahmen wie überall in Microsoft 365 und Office 365. Sie können in Azure AD sicher verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="d58e4-131">Finally, all guests in Teams are covered by the same compliance and auditing protection as the rest of Microsoft 365 and Office 365, and can be managed securely within Azure AD.</span></span>

## <a name="why-use-guest-access"></a><span data-ttu-id="d58e4-132">Warum Gastzugriff verwenden?</span><span class="sxs-lookup"><span data-stu-id="d58e4-132">Why use guest access?</span></span>

<span data-ttu-id="d58e4-133">Mit Gastzugriff können Organisationen, die Teams verwenden, ihren Partnern Zugriff auf Teams, Dokumente in Kanälen, Ressourcen, Chats und Anwendungen gewähren und gleichzeitig die vollständige Kontrolle über ihre eigenen Unternehmensdaten behalten.</span><span class="sxs-lookup"><span data-stu-id="d58e4-133">With guest access, organizations that use Teams can provide access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> <span data-ttu-id="d58e4-134">Für alle Gäste in Teams gelten dieselben Compliance- und Überwachungsmaßnahmen wie überall in Microsoft 365 und Office 365 und die Gäste können in Azure AD sicher verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="d58e4-134">All guests in Teams are covered by the same compliance and auditing protection as the rest of Microsoft 365 and Office 365, and guests can be managed securely within Azure AD.</span></span>  

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="d58e4-135">Grundlegendes zu den Einschränkungen für Gäste</span><span class="sxs-lookup"><span data-stu-id="d58e4-135">Understand the limitations for guests</span></span>

<span data-ttu-id="d58e4-136">Die Gastumgebung hat Beschränkungen, die beabsichtigt sind.</span><span class="sxs-lookup"><span data-stu-id="d58e4-136">The guest experience has limitations by design.</span></span> <span data-ttu-id="d58e4-137">Stellen Sie sicher, dass Sie die Gastumgebung verstehen, damit Sie nicht versuchen, ein Problem zu beheben, das keines ist.</span><span class="sxs-lookup"><span data-stu-id="d58e4-137">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="d58e4-138">Hier finden Sie beispielsweise eine Liste der Funktionen, die für einen Gast in Microsoft Teams nicht verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="d58e4-138">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="d58e4-139">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="d58e4-139">OneDrive for Business</span></span>
- <span data-ttu-id="d58e4-140">Personensuche außerhalb von Teams</span><span class="sxs-lookup"><span data-stu-id="d58e4-140">People search outside of Teams</span></span>
- <span data-ttu-id="d58e4-141">Kalender, geplante Besprechungen oder Besprechungsdetails</span><span class="sxs-lookup"><span data-stu-id="d58e4-141">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="d58e4-142">Telefonfestnetz (PSTN)</span><span class="sxs-lookup"><span data-stu-id="d58e4-142">PSTN</span></span>
- <span data-ttu-id="d58e4-143">Organigramm</span><span class="sxs-lookup"><span data-stu-id="d58e4-143">Organization chart</span></span>
- <span data-ttu-id="d58e4-144">Erstellen oder Überarbeiten eines Teams</span><span class="sxs-lookup"><span data-stu-id="d58e4-144">Create or revise a team</span></span>
- <span data-ttu-id="d58e4-145">Suche nach Teams</span><span class="sxs-lookup"><span data-stu-id="d58e4-145">Browse for a team</span></span>
- <span data-ttu-id="d58e4-146">Hochladen von Dateien in einen persönlichen Chat</span><span class="sxs-lookup"><span data-stu-id="d58e4-146">Upload files to a person-to-person chat</span></span>
- <span data-ttu-id="d58e4-147">Derzeit unterstützt Teams nur die Gastbenutzer vom Typ "Zustand 1" und "Zustand 2" [gemäß der Definition durch Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span><span class="sxs-lookup"><span data-stu-id="d58e4-147">Currently, Teams supports only State 1 and State 2 types of guest users [as defined by Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)</span></span>

<span data-ttu-id="d58e4-148">Eine vollständige Liste dessen, was ein Gast in Teams tun kann und was nicht, finden Sie in der Tabelle [Vergleich der Funktionen von Teammitgliedern und Gästen](guest-experience.md#comparison-of-team-member-and-guest-capabilities).</span><span class="sxs-lookup"><span data-stu-id="d58e4-148">For a full list of what a guest can and can't do in Teams, see the [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities) table.</span></span> <span data-ttu-id="d58e4-149">Wenn Sie mehr über den Gastzugriff auf der Microsoft 365- und Office 365-Ebene wissen möchten, lesen Sie [Hinzufügen von Gästen zu Microsoft 365-Gruppen](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span><span class="sxs-lookup"><span data-stu-id="d58e4-149">To learn more about guest access at the Microsoft 365 and Office 365 levels, read [Adding guests to Microsoft 365 Groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>


## <a name="more-information"></a><span data-ttu-id="d58e4-150">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d58e4-150">More information</span></span>

[<span data-ttu-id="d58e4-151">Kontakt mit dem Support für Geschäftsprodukte aufnehmen – Administratorhilfe</span><span class="sxs-lookup"><span data-stu-id="d58e4-151">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)  
[<span data-ttu-id="d58e4-152">Gastzugriff in Microsoft 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="d58e4-152">Guest access in Microsoft 365 Groups</span></span>](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
