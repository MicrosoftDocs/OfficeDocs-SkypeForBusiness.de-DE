---
title: Upgrade auf Teams über eine lokale Skype for Business-Bereitstellung – Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Upgrade von Skype for Business auf Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e16e651004148645789f5e8e55df6fbbfa1dea9c
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955912"
---
# <a name="upgrade-considerations-for-organizations-with-skype-for-business-server-on-premises-mdash-for-it-administrators"></a><span data-ttu-id="a97c5-103">Upgrade-Überlegungen für Organisationen mit Skype for Business Server lokal &mdash; für IT-Administratoren</span><span class="sxs-lookup"><span data-stu-id="a97c5-103">Upgrade considerations for organizations with Skype for Business Server on-premises &mdash; for IT administrators</span></span>

<span data-ttu-id="a97c5-104">In diesem Artikel werden weitere Überlegungen für Organisationen beschrieben, die Skype for Business Server lokal nutzen.</span><span class="sxs-lookup"><span data-stu-id="a97c5-104">This article describes additional considerations for organizations with Skype for Business Server on-premises.</span></span> <span data-ttu-id="a97c5-105">Dieser Artikel ist der vierte von mehreren, die Upgrade-Konzepte und Implementierung für IT-Administratoren beschreiben.</span><span class="sxs-lookup"><span data-stu-id="a97c5-105">This article is the fourth of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="a97c5-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="a97c5-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="a97c5-107">Upgrade-Methoden</span><span class="sxs-lookup"><span data-stu-id="a97c5-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="a97c5-108">Tools zum Verwalten des Upgrades</span><span class="sxs-lookup"><span data-stu-id="a97c5-108">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- <span data-ttu-id="a97c5-109">**Weitere Überlegungen für Organisationen mit Skype for Business lokal** (dieser Artikel)</span><span class="sxs-lookup"><span data-stu-id="a97c5-109">**Additional considerations for organizations with Skype for Business on-premises** (this article)</span></span>
- [<span data-ttu-id="a97c5-110">Implementieren des Upgrades</span><span class="sxs-lookup"><span data-stu-id="a97c5-110">Implementing your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="a97c5-111">Überlegungen zum Public Switched Telephone Network (PSTN)</span><span class="sxs-lookup"><span data-stu-id="a97c5-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="a97c5-112">Darüber hinaus werden in den folgenden Artikeln wichtige Upgrade-Konzepte und Koexistenz-Verhaltensweisen beschrieben:</span><span class="sxs-lookup"><span data-stu-id="a97c5-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="a97c5-113">Koexistenz von Teams und Skype for Business</span><span class="sxs-lookup"><span data-stu-id="a97c5-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="a97c5-114">Koexistenzmodus – Referenz</span><span class="sxs-lookup"><span data-stu-id="a97c5-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="a97c5-115">Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen</span><span class="sxs-lookup"><span data-stu-id="a97c5-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)



## <a name="considerations-for-organizations-with-skype-for-business-server-on-premises"></a><span data-ttu-id="a97c5-116">Überlegungen für Organisationen mit Skype for Business Server lokal</span><span class="sxs-lookup"><span data-stu-id="a97c5-116">Considerations for organizations with Skype for Business Server on-premises</span></span>

- <span data-ttu-id="a97c5-117">Das Einrichten von Skype for Business-Hybriden ist eine Voraussetzung für die Migration in den TeamsOnly-Modus.</span><span class="sxs-lookup"><span data-stu-id="a97c5-117">Setting up Skype for Business hybrid is a prerequisite to migrate to TeamsOnly mode.</span></span> <span data-ttu-id="a97c5-118">Obwohl es möglich ist, Teams im Modus "Inseln" ohne Hybrid zu verwenden, kann der Übergang in den TeamsOnly-Modus erst dann erfolgen, wenn der Benutzer von Skype for Business lokal zu Skype for Business Online (mit [Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)) verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="a97c5-118">While it is possible to use Teams in Islands mode without hybrid, the transition to TeamsOnly mode cannot be made until the user is moved from Skype for Business on-premises to Skype for Business Online (using [Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)).</span></span> <span data-ttu-id="a97c5-119">Weitere Informationen finden Sie unter [Konfigurieren der Hybrid Konnektivität](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity).</span><span class="sxs-lookup"><span data-stu-id="a97c5-119">For more information, see [Configure hybrid connectivity](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity).</span></span>

- <span data-ttu-id="a97c5-120">Wenn Ihre Organisation über Skype for Business Server verfügt und Sie keine Hybrid Konnektivität konfiguriert haben, aber weiterhin Teams verwenden möchten, müssen Sie ein Administratorkonto verwenden, das über eine onmicrosoft.com-Domäne verfügt.</span><span class="sxs-lookup"><span data-stu-id="a97c5-120">If your organization has Skype for Business Server and you have not configured hybrid connectivity, but you still want to use Teams, to administer Teams functionality, you must use an administrative account that has an .onmicrosoft.com domain.</span></span> 

- <span data-ttu-id="a97c5-121">Benutzer von Teams, die ein Skype for Business-Konto lokal haben (das heißt, dass Sie mit Move-CsUser noch nicht in die Cloud verschoben wurden), können nicht mit Skype for Business-Benutzern zusammenarbeiten und können auch nicht mit externen Benutzern zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="a97c5-121">Teams users who have a Skype for Business account on-premises (that is, they have not yet been moved to the cloud by using Move-CsUser) cannot interoperate with any Skype for Business users, nor can they federate with external users.</span></span> <span data-ttu-id="a97c5-122">Diese Funktion steht nur zur Verfügung, wenn die Benutzer in die Cloud verschoben werden (entweder im Modus "Inseln" oder als TeamsOnly-Benutzer).</span><span class="sxs-lookup"><span data-stu-id="a97c5-122">This functionality is only available once the users are moved to the cloud (either in Islands mode, or as TeamsOnly users).</span></span> 

- <span data-ttu-id="a97c5-123">Wenn Sie Benutzer mit Skype for Business-Konten lokal haben, dürfen Sie den TeamsOnly-Modus nicht auf Mandantenebene zuweisen, es sei denn, Sie weisen allen Benutzern mit lokalen Skype for Business-Konten explizit einen anderen Modus zu.</span><span class="sxs-lookup"><span data-stu-id="a97c5-123">If you have any users with Skype for Business accounts on-premises, you must not assign TeamsOnly mode at the tenant level, unless you explicitly assign some other mode to all users with on-premises Skype for Business accounts.</span></span> 

- <span data-ttu-id="a97c5-124">Sie müssen sicherstellen, dass Ihre Benutzer mit den korrekten Skype for Business-Attributen richtig in Azure AD synchronisiert sind.</span><span class="sxs-lookup"><span data-stu-id="a97c5-124">You must ensure your users are properly synchronized into Azure AD with the correct Skype for Business attributes.</span></span> <span data-ttu-id="a97c5-125">Diese Attribute sind alle Präfixe mit "Attribut msRTCSIP-".</span><span class="sxs-lookup"><span data-stu-id="a97c5-125">These attributes are all prefixes with “msRTCSIP-”.</span></span> <span data-ttu-id="a97c5-126">Wenn Benutzer nicht ordnungsgemäß mit Azure AD synchronisiert werden, können die Verwaltungstools in Microsoft Teams diese Benutzer nicht verwalten.</span><span class="sxs-lookup"><span data-stu-id="a97c5-126">If users are not synchronized properly to Azure AD, the management tools in Teams will not be able to manage these users.</span></span> <span data-ttu-id="a97c5-127">(Sie können beispielsweise keine Teamrichtlinien für lokale Benutzer zuweisen, es sei denn, Sie synchronisieren diese Attribute ordnungsgemäß.) Weitere Informationen finden Sie unter [Konfigurieren von Azure AD Connect für Teams und Skype for Business](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).</span><span class="sxs-lookup"><span data-stu-id="a97c5-127">(For example, you won’t be able to assign Teams policies to on-premises users unless you are properly syncing these attributes.) For more information, see [Configure Azure AD Connect for Teams and Skype for Business](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).</span></span>

- <span data-ttu-id="a97c5-128">Wenn Sie einen neuen TeamsOnly-oder Skype for Business Online-Benutzer in einer Hybrid Organisation erstellen möchten, *müssen Sie zunächst den Benutzer in Skype for Business Server lokal aktivieren*und den Benutzer dann mithilfe von Move-CsUser von lokal in die Cloud verschieben.</span><span class="sxs-lookup"><span data-stu-id="a97c5-128">To create a new TeamsOnly or Skype for Business Online user in a hybrid organization, *you must first enable the user in Skype for Business Server on-premises*, and then move the user from on-premises to the cloud using Move-CsUser.</span></span>  <span data-ttu-id="a97c5-129">Durch das Erstellen des Benutzers im lokalen Bereich wird zunächst sichergestellt, dass andere verbleibende lokale Skype for Business-Benutzer an den neu erstellten Benutzer weiterleiten können.</span><span class="sxs-lookup"><span data-stu-id="a97c5-129">Creating the user in on-premises first ensures that any other remaining on-premises Skype for Business users will be able route to the newly created user.</span></span> <span data-ttu-id="a97c5-130">Nachdem alle Benutzer online verschoben wurden, ist es nicht mehr notwendig, Benutzer zunächst lokal zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a97c5-130">Once all users have been moved online, it is no longer necessary to first enable users in on-premises.</span></span>

- <span data-ttu-id="a97c5-131">Wenn ein Benutzer von lokal in die Cloud verschoben wird, werden Besprechungen, die von diesem Benutzer organisiert werden, entweder in Skype for Business Online oder in Teams migriert – je nachdem, ob der-MoveToTeams-Schalter angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="a97c5-131">When a user is moved from on-premises to the cloud, meetings organized by that user are migrated to either Skype for Business Online or Teams--depending on whether or not the -MoveToTeams switch is specified.</span></span>

- <span data-ttu-id="a97c5-132">Wenn Sie Benachrichtigungen im Skype for Business-Client für lokale Benutzer anzeigen möchten, müssen Sie im lokalen Toolset TeamsUpgradePolicy verwenden.</span><span class="sxs-lookup"><span data-stu-id="a97c5-132">If you would like display notifications in the Skype for Business client for on-premises users, you must use TeamsUpgradePolicy in the on-premises toolset.</span></span> <span data-ttu-id="a97c5-133">Nur der NotifySfbUsers-Parameter ist für lokale Benutzer relevant.</span><span class="sxs-lookup"><span data-stu-id="a97c5-133">Only the NotifySfbUsers parameter is relevant for on-premises users.</span></span>  <span data-ttu-id="a97c5-134">Lokale Benutzer erhalten Ihren Modus aus den Online Instanzen von TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="a97c5-134">On-premises users receive their mode from the online instances of TeamsUpgradePolicy.</span></span> <span data-ttu-id="a97c5-135">Sehen Sie sich die Notizen in [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="a97c5-135">See the notes in [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span></span> 

>[!NOTE]
> <span data-ttu-id="a97c5-136">Alle neuen Mandanten, die nach dem 3. September erstellt wurden, werden als TeamsOnly-Mandanten erstellt, es sei denn 2019, die Organisation verfügt bereits über eine lokale Bereitstellung von Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a97c5-136">Any new tenants created after Sept 3, 2019 are created as TeamsOnly tenants unless the organization already has an on-premises deployment of Skype for Business Server.</span></span> <span data-ttu-id="a97c5-137">Microsoft verwendet DNS-Einträge, um lokale Skype for Business Server-Organisationen zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="a97c5-137">Microsoft uses DNS records to identify on-premises Skype for Business Server organizations.</span></span> <span data-ttu-id="a97c5-138">Wenn Ihre Organisation über lokale Skype for Business-Server ohne öffentliche DNS-Einträge verfügt, müssen Sie den Microsoft-Support anrufen, damit Ihr neuer Mandant heruntergestuft wird.</span><span class="sxs-lookup"><span data-stu-id="a97c5-138">If your organization has on-premises Skype for Business Server with no public DNS entries, you will need to call Microsoft Support to have your new tenant downgraded.</span></span> 



















## <a name="related-links"></a><span data-ttu-id="a97c5-139">Verwandte Links</span><span class="sxs-lookup"><span data-stu-id="a97c5-139">Related links</span></span>

[<span data-ttu-id="a97c5-140">Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden</span><span class="sxs-lookup"><span data-stu-id="a97c5-140">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="a97c5-141">Konfigurieren der Hybrid Konnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365</span><span class="sxs-lookup"><span data-stu-id="a97c5-141">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="a97c5-142">Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud</span><span class="sxs-lookup"><span data-stu-id="a97c5-142">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="a97c5-143">Festlegen Ihrer Einstellungen für Koexistenz und Upgrades</span><span class="sxs-lookup"><span data-stu-id="a97c5-143">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="a97c5-144">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="a97c5-144">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="a97c5-145">Verwenden des Besprechungs Migrations Diensts (MMS)</span><span class="sxs-lookup"><span data-stu-id="a97c5-145">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

