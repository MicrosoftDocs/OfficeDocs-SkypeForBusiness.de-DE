---
title: Upgrade auf Teams über eine lokale Skype for Business-Bereitstellung – Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
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
ms.openlocfilehash: cf034969c2b6ca030eede72ff358a517fafe501f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533592"
---
# <a name="upgrade-considerations-for-organizations-with-skype-for-business-server-on-premises-mdash-for-it-administrators"></a><span data-ttu-id="5a3a4-103">Upgrade-Überlegungen für Organisationen mit Skype for Business Server lokal &mdash; für IT-Administratoren</span><span class="sxs-lookup"><span data-stu-id="5a3a4-103">Upgrade considerations for organizations with Skype for Business Server on-premises &mdash; for IT administrators</span></span>

<span data-ttu-id="5a3a4-104">In diesem Artikel werden weitere Überlegungen für Organisationen beschrieben, die Skype for Business Server lokal nutzen.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-104">This article describes additional considerations for organizations with Skype for Business Server on-premises.</span></span> <span data-ttu-id="5a3a4-105">Dieser Artikel ist der vierte von mehreren, die Upgrade-Konzepte und Implementierung für IT-Administratoren beschreiben.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-105">This article is the fourth of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="5a3a4-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="5a3a4-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="5a3a4-107">Upgrade-Methoden</span><span class="sxs-lookup"><span data-stu-id="5a3a4-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="5a3a4-108">Tools zum Verwalten des Upgrades</span><span class="sxs-lookup"><span data-stu-id="5a3a4-108">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- <span data-ttu-id="5a3a4-109">**Weitere Überlegungen für Organisationen mit Skype for Business lokal** (dieser Artikel)</span><span class="sxs-lookup"><span data-stu-id="5a3a4-109">**Additional considerations for organizations with Skype for Business on-premises** (this article)</span></span>
- [<span data-ttu-id="5a3a4-110">Implementieren des Upgrades</span><span class="sxs-lookup"><span data-stu-id="5a3a4-110">Implementing your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="5a3a4-111">Überlegungen zum Public Switched Telephone Network (PSTN)</span><span class="sxs-lookup"><span data-stu-id="5a3a4-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="5a3a4-112">Darüber hinaus werden in den folgenden Artikeln wichtige Upgrade-Konzepte und Koexistenz-Verhaltensweisen beschrieben:</span><span class="sxs-lookup"><span data-stu-id="5a3a4-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="5a3a4-113">Koexistenz von Teams und Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5a3a4-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="5a3a4-114">Koexistenzmodus – Referenz</span><span class="sxs-lookup"><span data-stu-id="5a3a4-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="5a3a4-115">Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen</span><span class="sxs-lookup"><span data-stu-id="5a3a4-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)



## <a name="considerations-for-organizations-with-skype-for-business-server-on-premises"></a><span data-ttu-id="5a3a4-116">Überlegungen für Organisationen mit Skype for Business Server lokal</span><span class="sxs-lookup"><span data-stu-id="5a3a4-116">Considerations for organizations with Skype for Business Server on-premises</span></span>

- <span data-ttu-id="5a3a4-117">Das Einrichten von Skype for Business-Hybriden ist eine Voraussetzung für die Migration in den TeamsOnly-Modus.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-117">Setting up Skype for Business hybrid is a prerequisite to migrate to TeamsOnly mode.</span></span> <span data-ttu-id="5a3a4-118">Obwohl es möglich ist, Teams im Modus "Inseln" ohne Hybrid zu verwenden, kann der Übergang in den TeamsOnly-Modus erst dann erfolgen, wenn der Benutzer von Skype for Business lokal zu Skype for Business Online (mit [Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)) verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-118">While it is possible to use Teams in Islands mode without hybrid, the transition to TeamsOnly mode cannot be made until the user is moved from Skype for Business on-premises to Skype for Business Online (using [Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)).</span></span> <span data-ttu-id="5a3a4-119">Weitere Informationen finden Sie unter [Konfigurieren der Hybrid Konnektivität](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity).</span><span class="sxs-lookup"><span data-stu-id="5a3a4-119">For more information, see [Configure hybrid connectivity](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity).</span></span>

- <span data-ttu-id="5a3a4-120">Wenn Ihre Organisation über Skype for Business Server verfügt und Sie keine Hybrid Konnektivität konfiguriert haben, aber weiterhin Teams verwenden möchten, müssen Sie ein Administratorkonto verwenden, das über eine onmicrosoft.com-Domäne verfügt.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-120">If your organization has Skype for Business Server and you have not configured hybrid connectivity, but you still want to use Teams, to administer Teams functionality, you must use an administrative account that has an .onmicrosoft.com domain.</span></span> 

- <span data-ttu-id="5a3a4-121">Benutzer von Teams, die ein Skype for Business-Konto lokal haben (das heißt, dass Sie mit Move-CsUser noch nicht in die Cloud verschoben wurden), können nicht mit Skype for Business-Benutzern zusammenarbeiten und können auch nicht mit externen Benutzern zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-121">Teams users who have a Skype for Business account on-premises (that is, they have not yet been moved to the cloud by using Move-CsUser) cannot interoperate with any Skype for Business users, nor can they federate with external users.</span></span> <span data-ttu-id="5a3a4-122">Diese Funktion steht nur zur Verfügung, wenn die Benutzer in die Cloud verschoben werden (entweder im Modus "Inseln" oder als TeamsOnly-Benutzer).</span><span class="sxs-lookup"><span data-stu-id="5a3a4-122">This functionality is only available once the users are moved to the cloud (either in Islands mode, or as TeamsOnly users).</span></span> 

- <span data-ttu-id="5a3a4-123">Wenn Sie über Benutzer mit Skype for Business-Konten lokal verfügen, können Sie den TeamsOnly-Modus auf Mandantenebene nicht zuweisen.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-123">If you have any users with Skype for Business accounts on-premises, you cannot assign TeamsOnly mode at the tenant level.</span></span> <span data-ttu-id="5a3a4-124">Sie müssen zunächst alle Benutzer mit lokalen Skype for Business-Konten in die Cloud verschieben, indem Sie die `Move-CsUser` [Migration in die Cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)mithilfe und dann deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-124">You must first move all  users with on-premises Skype for Business accounts to the cloud using `Move-CsUser` and then [disable hybrid to complete migration to the cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).</span></span>  <span data-ttu-id="5a3a4-125">`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` funktioniert nicht auf Mandantenebene, wenn ein lyncdiscover-DNS-Eintrag erkannt wird, der auf einen anderen Speicherort als Office 365 verweist.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-125">`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` will not work at the tenant level if a lyncdiscover DNS record is detected that points to a location other than Office 365.</span></span>

- <span data-ttu-id="5a3a4-126">Sie müssen sicherstellen, dass Ihre Benutzer mit den korrekten Skype for Business-Attributen richtig in Azure AD synchronisiert sind.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-126">You must ensure your users are properly synchronized into Azure AD with the correct Skype for Business attributes.</span></span> <span data-ttu-id="5a3a4-127">Diese Attribute sind alle Präfixe mit "Attribut msRTCSIP-".</span><span class="sxs-lookup"><span data-stu-id="5a3a4-127">These attributes are all prefixes with “msRTCSIP-”.</span></span> <span data-ttu-id="5a3a4-128">Wenn Benutzer nicht ordnungsgemäß mit Azure AD synchronisiert werden, können die Verwaltungstools in Microsoft Teams diese Benutzer nicht verwalten.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-128">If users are not synchronized properly to Azure AD, the management tools in Teams will not be able to manage these users.</span></span> <span data-ttu-id="5a3a4-129">(Sie können beispielsweise keine Teamrichtlinien für lokale Benutzer zuweisen, es sei denn, Sie synchronisieren diese Attribute ordnungsgemäß.) Weitere Informationen finden Sie unter [Konfigurieren von Azure AD Connect für Teams und Skype for Business](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).</span><span class="sxs-lookup"><span data-stu-id="5a3a4-129">(For example, you won’t be able to assign Teams policies to on-premises users unless you are properly syncing these attributes.) For more information, see [Configure Azure AD Connect for Teams and Skype for Business](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).</span></span>

- <span data-ttu-id="5a3a4-130">Wenn Sie einen neuen TeamsOnly-oder Skype for Business Online-Benutzer in einer Hybrid Organisation erstellen möchten, *müssen Sie zunächst den Benutzer in Skype for Business Server lokal aktivieren*und den Benutzer dann mithilfe von Move-CsUser von lokal in die Cloud verschieben.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-130">To create a new TeamsOnly or Skype for Business Online user in a hybrid organization, *you must first enable the user in Skype for Business Server on-premises*, and then move the user from on-premises to the cloud using Move-CsUser.</span></span>  <span data-ttu-id="5a3a4-131">Durch das Erstellen des Benutzers im lokalen Bereich wird zunächst sichergestellt, dass andere verbleibende lokale Skype for Business-Benutzer an den neu erstellten Benutzer weiterleiten können.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-131">Creating the user in on-premises first ensures that any other remaining on-premises Skype for Business users will be able route to the newly created user.</span></span> <span data-ttu-id="5a3a4-132">Nachdem alle Benutzer online verschoben wurden, ist es nicht mehr notwendig, Benutzer zunächst lokal zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-132">Once all users have been moved online, it is no longer necessary to first enable users in on-premises.</span></span>

- <span data-ttu-id="5a3a4-133">Wenn ein Benutzer von lokal in die Cloud verschoben wird, werden Besprechungen, die von diesem Benutzer organisiert werden, entweder in Skype for Business Online oder in Teams migriert – je nachdem, ob der-MoveToTeams-Schalter angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-133">When a user is moved from on-premises to the cloud, meetings organized by that user are migrated to either Skype for Business Online or Teams--depending on whether or not the -MoveToTeams switch is specified.</span></span>

- <span data-ttu-id="5a3a4-134">Wenn Sie Benachrichtigungen im Skype for Business-Client für lokale Benutzer anzeigen möchten, müssen Sie im lokalen Toolset TeamsUpgradePolicy verwenden.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-134">If you would like display notifications in the Skype for Business client for on-premises users, you must use TeamsUpgradePolicy in the on-premises toolset.</span></span> <span data-ttu-id="5a3a4-135">Nur der NotifySfbUsers-Parameter ist für lokale Benutzer relevant.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-135">Only the NotifySfbUsers parameter is relevant for on-premises users.</span></span>  <span data-ttu-id="5a3a4-136">Lokale Benutzer erhalten Ihren Modus aus den Online Instanzen von TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-136">On-premises users receive their mode from the online instances of TeamsUpgradePolicy.</span></span> <span data-ttu-id="5a3a4-137">Sehen Sie sich die Notizen in [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="5a3a4-137">See the notes in [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span></span> 

>[!NOTE]
> <span data-ttu-id="5a3a4-138">Alle neuen Mandanten, die nach dem 3. September erstellt wurden, werden als TeamsOnly-Mandanten erstellt, es sei denn 2019, die Organisation verfügt bereits über eine lokale Bereitstellung von Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-138">Any new tenants created after Sept 3, 2019 are created as TeamsOnly tenants unless the organization already has an on-premises deployment of Skype for Business Server.</span></span> <span data-ttu-id="5a3a4-139">Microsoft verwendet DNS-Einträge, um lokale Skype for Business Server-Organisationen zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-139">Microsoft uses DNS records to identify on-premises Skype for Business Server organizations.</span></span> <span data-ttu-id="5a3a4-140">Wenn Ihre Organisation über lokale Skype for Business-Server ohne öffentliche DNS-Einträge verfügt, müssen Sie den Microsoft-Support anrufen, damit Ihr neuer Mandant heruntergestuft wird.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-140">If your organization has on-premises Skype for Business Server with no public DNS entries, you will need to call Microsoft Support to have your new tenant downgraded.</span></span> 













## <a name="related-links"></a><span data-ttu-id="5a3a4-141">Verwandte Links</span><span class="sxs-lookup"><span data-stu-id="5a3a4-141">Related links</span></span>

[<span data-ttu-id="5a3a4-142">Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden</span><span class="sxs-lookup"><span data-stu-id="5a3a4-142">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="5a3a4-143">Konfigurieren der Hybrid Konnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365</span><span class="sxs-lookup"><span data-stu-id="5a3a4-143">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="5a3a4-144">Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud</span><span class="sxs-lookup"><span data-stu-id="5a3a4-144">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="5a3a4-145">Festlegen Ihrer Einstellungen für Koexistenz und Upgrades</span><span class="sxs-lookup"><span data-stu-id="5a3a4-145">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="5a3a4-146">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="5a3a4-146">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="5a3a4-147">Verwenden des Besprechungs Migrations Diensts (MMS)</span><span class="sxs-lookup"><span data-stu-id="5a3a4-147">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

