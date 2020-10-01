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
description: Upgrade von Skype for Business auf Teams – Tools für das Upgrade
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 076e96ac8cf44e05e2852ca5bdf33b42e14eb731
ms.sourcegitcommit: 739ffd5893abf6d181877d1110f9dc8230b3bfd2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328194"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="9df7a-103">Tools für das Upgrade auf Teams &mdash; für IT-Administratoren</span><span class="sxs-lookup"><span data-stu-id="9df7a-103">Tools for upgrading to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="9df7a-104">In diesem Artikel werden Tools für das Upgrade auf Teams beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9df7a-104">This article describes tools for upgrading to Teams.</span></span> <span data-ttu-id="9df7a-105">Dieser Artikel ist der dritte von mehreren, die Upgrade-Konzepte und Implementierung für IT-Administratoren beschreiben.</span><span class="sxs-lookup"><span data-stu-id="9df7a-105">This article is the third of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="9df7a-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="9df7a-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="9df7a-107">Upgrade-Methoden</span><span class="sxs-lookup"><span data-stu-id="9df7a-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- <span data-ttu-id="9df7a-108">**Tools zum Verwalten des Upgrades**   (dieser Artikel)</span><span class="sxs-lookup"><span data-stu-id="9df7a-108">**Tools for managing your upgrade**   (This article)</span></span>
- [<span data-ttu-id="9df7a-109">Weitere Überlegungen für Organisationen mit Skype for Business lokal</span><span class="sxs-lookup"><span data-stu-id="9df7a-109">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- [<span data-ttu-id="9df7a-110">Implementieren des Upgrades</span><span class="sxs-lookup"><span data-stu-id="9df7a-110">Implement your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="9df7a-111">Überlegungen zum Public Switched Telephone Network (PSTN)</span><span class="sxs-lookup"><span data-stu-id="9df7a-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="9df7a-112">Darüber hinaus werden in den folgenden Artikeln wichtige Upgrade-Konzepte und Koexistenz-Verhaltensweisen beschrieben:</span><span class="sxs-lookup"><span data-stu-id="9df7a-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="9df7a-113">Koexistenz von Teams und Skype for Business</span><span class="sxs-lookup"><span data-stu-id="9df7a-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="9df7a-114">Koexistenzmodus – Referenz</span><span class="sxs-lookup"><span data-stu-id="9df7a-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="9df7a-115">Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen</span><span class="sxs-lookup"><span data-stu-id="9df7a-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="tools-for-managing-the-upgrade"></a><span data-ttu-id="9df7a-116">Tools für die Verwaltung des Upgrades</span><span class="sxs-lookup"><span data-stu-id="9df7a-116">Tools for managing the upgrade</span></span>

<span data-ttu-id="9df7a-117">Je nachdem, welche Upgrade-Methode Sie wählen, verwalten Sie für Benutzer, die bereits Skype for Business Online haben, den Übergang zu TeamsOnly mithilfe von [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), der den Koexistenzmodus eines Benutzers steuert.</span><span class="sxs-lookup"><span data-stu-id="9df7a-117">Whichever upgrade method you choose, for users that already have Skype for Business Online, you manage the transition to TeamsOnly using [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), which controls a user’s coexistence mode.</span></span> <span data-ttu-id="9df7a-118">Für Benutzer mit einem lokalen Konto in Skype for Business Server verwenden Sie auch, `Move-CsUser` um Sie in [die Cloud zu verschieben](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).</span><span class="sxs-lookup"><span data-stu-id="9df7a-118">For users with an on-premises account in Skype for Business Server, you also use `Move-CsUser` to [move them to the cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).</span></span>  <span data-ttu-id="9df7a-119">Weitere Informationen zu den einzelnen Modi finden Sie unter [Koexistenz Modi](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="9df7a-119">For more information on each of the modes, see [Coexistence modes](migration-interop-guidance-for-teams-with-skype.md).</span></span>  

<span data-ttu-id="9df7a-120">Unabhängig davon, ob Sie über den Skype for Business-Modus einen Übergang zur Auswahlfunktion ausführen oder einfach über die standardmäßige Konfiguration der Inseln auf den TeamsOnly-Modus umsteigen, ist TeamsUpgradePolicy das wichtigste Tool für Benutzer, die bereits Skype for Business Online haben.</span><span class="sxs-lookup"><span data-stu-id="9df7a-120">Whether you perform a select capabilities transition using Skype for Business modes or simply upgrade to TeamsOnly mode from the default Islands configuration, TeamsUpgradePolicy is the primary tool for users who already have Skype for Business Online.</span></span> <span data-ttu-id="9df7a-121">Wie bei allen anderen Richtlinien in Teams können Sie TeamsUpgradePolicy einem Benutzer direkt zuweisen.</span><span class="sxs-lookup"><span data-stu-id="9df7a-121">Like any other policy in Teams, you can assign TeamsUpgradePolicy directly to a user.</span></span> <span data-ttu-id="9df7a-122">Sie können die Richtlinie auch als Mandantenweite Standardeinstellung festlegen.</span><span class="sxs-lookup"><span data-stu-id="9df7a-122">You can also set the policy as the tenant-wide default.</span></span> <span data-ttu-id="9df7a-123">Jede Zuordnung zu einem Benutzer hat Vorrang vor der Standardeinstellung Mandanten.</span><span class="sxs-lookup"><span data-stu-id="9df7a-123">Any assignment to a user takes precedence over the tenant default setting.</span></span>  <span data-ttu-id="9df7a-124">Sie können die Richtlinie in der Team-Verwaltungskonsole und in PowerShell verwalten.</span><span class="sxs-lookup"><span data-stu-id="9df7a-124">You can manage the policy in the Teams Admin Console and in PowerShell.</span></span>

<span data-ttu-id="9df7a-125">Sie können den Benutzern, die in Skype for Business lokal gehostet werden, auch einen beliebigen TeamsUpgradePolicy-Modus (mit Ausnahme des TeamsOnly-Modus) zuweisen.</span><span class="sxs-lookup"><span data-stu-id="9df7a-125">You can also assign any mode of TeamsUpgradePolicy, except for TeamsOnly mode, to users homed in Skype for Business on-premises.</span></span> <span data-ttu-id="9df7a-126">Der **TeamsOnly-Modus kann nur einem Nutzer zugewiesen werden, der sich bereits in Skype for Business Online befindet**.</span><span class="sxs-lookup"><span data-stu-id="9df7a-126">**TeamsOnly mode can only be assigned to a user who is already homed in Skype for Business Online**.</span></span> <span data-ttu-id="9df7a-127">Dies liegt daran, dass Interop mit Skype for Business-Benutzern und-Föderation sowie Microsoft 365-Telefon System Funktionen nur möglich ist, wenn der Benutzer in Skype for Business Online verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="9df7a-127">This is because interop with Skype for Business users and federation as well as Microsoft 365 Phone System functionality are only possible if the user is homed in Skype for Business Online.</span></span> <span data-ttu-id="9df7a-128">Darüber hinaus **können Sie den TeamsOnly-Modus nicht als mandantenübergreifenden Standardwert zuweisen, wenn Sie über eine lokale Skype for Business-Bereitstellung verfügen** (die durch Anwesenheit eines lyncdiscover-DNS-Eintrags erkannt wird, der auf einen anderen Speicherort als Office 365 verweist.</span><span class="sxs-lookup"><span data-stu-id="9df7a-128">In addition, **you cannot assign TeamsOnly mode as the tenant-wide default if you have a Skype for Business on-premises deployment** (which is detected by presence of a lyncdiscover DNS record that points to location other than Office 365.</span></span>

<span data-ttu-id="9df7a-129">Benutzer mit Skype for Business-Konten, die sich lokal [benetzen, müssen](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) mit Move-CsUser im lokalen Skype for Business-Toolset Online (entweder in Skype for Business Online oder direkt an Teams) verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="9df7a-129">Users with Skype for Business accounts homed on-premises [must be moved online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (either to Skype for Business Online or direct to Teams) using Move-CsUser in the Skype for Business on-premises toolset.</span></span> <span data-ttu-id="9df7a-130">Diese Benutzer können in 1 oder 2 Schritten in TeamsOnly verschoben werden:</span><span class="sxs-lookup"><span data-stu-id="9df7a-130">These users can be moved to TeamsOnly in either 1 or 2 steps:</span></span>

-   <span data-ttu-id="9df7a-131">1 Schritt: Geben Sie den Schalter-MoveToTeams in Move-CsUser an.</span><span class="sxs-lookup"><span data-stu-id="9df7a-131">1 step:  Specify the -MoveToTeams switch in Move-CsUser.</span></span> <span data-ttu-id="9df7a-132">Hierfür ist Skype for Business Server 2019 oder Skype for Business Server 2015 mit CU8 oder höher erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9df7a-132">This requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span>

-   <span data-ttu-id="9df7a-133">2 Schritte: Nachdem Sie Move-CsUser ausgeführt haben, gewähren Sie dem Benutzer den TeamsOnly-Modus mithilfe von TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="9df7a-133">2 steps: After running Move-CsUser, grant TeamsOnly mode to the user using TeamsUpgradePolicy.</span></span>

<span data-ttu-id="9df7a-134">Im Gegensatz zu anderen Richtlinien ist es nicht möglich, neue Instanzen von TeamsUpgradePolicy in Microsoft 365 oder Office 365 zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9df7a-134">Unlike other policies, it is not possible to create new instances of TeamsUpgradePolicy in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="9df7a-135">Alle vorhandenen Instanzen sind in den Dienst integriert.</span><span class="sxs-lookup"><span data-stu-id="9df7a-135">All the existing instances are built into the service.</span></span>  <span data-ttu-id="9df7a-136">(Beachten Sie, dass Mode eine Eigenschaft in TeamsUpgradePolicy und nicht der Name einer Richtlinieninstanz ist.) In einigen-aber nicht in allen Fällen ist der Name der Richtlinieninstanz derselbe wie der Modus.</span><span class="sxs-lookup"><span data-stu-id="9df7a-136">(Note that mode is a property within TeamsUpgradePolicy, rather than the name of a policy instance.) In some--but not all--cases, the name of the policy instance is the same as mode.</span></span> <span data-ttu-id="9df7a-137">Um einem Benutzer den TeamsOnly-Modus zuzuweisen, erteilen Sie diesem Benutzer die Instanz "UpgradeToTeams" von TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="9df7a-137">In particular, to assign TeamsOnly mode to a user, you will grant the “UpgradeToTeams” instance of TeamsUpgradePolicy to that user.</span></span> <span data-ttu-id="9df7a-138">Um eine Liste aller Instanzen anzuzeigen, können Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="9df7a-138">To see a list of all instances, you can run the following command:</span></span>

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

<span data-ttu-id="9df7a-139">Wenn Sie einen Online Benutzer auf den TeamsOnly-Modus aktualisieren möchten, weisen Sie die "UpgradeToTeams"-Instanz zu:</span><span class="sxs-lookup"><span data-stu-id="9df7a-139">To upgrade an online user to TeamsOnly mode, assign the “UpgradeToTeams” instance:</span></span> 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

<span data-ttu-id="9df7a-140">Um einen lokalen Skype for Business-Benutzer in den TeamsOnly-Modus zu aktualisieren, verwenden Sie Move-CsUser im lokalen Toolset:</span><span class="sxs-lookup"><span data-stu-id="9df7a-140">To upgrade an on-premise Skype for Business user to TeamsOnly mode, use Move-CsUser in the on-premises toolset:</span></span>

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

<span data-ttu-id="9df7a-141">Führen Sie den folgenden Befehl aus, um den Modus für alle Benutzer im Mandanten zu ändern, mit Ausnahme derjenigen, die über eine explizite pro-Benutzer-Grant (die Vorrang hat) verfügen:</span><span class="sxs-lookup"><span data-stu-id="9df7a-141">To change the mode for all users in the tenant, except those who have an explicit per-user grant (which takes precedence), run the following command:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
><span data-ttu-id="9df7a-142">Wenn Sie über Benutzer mit Skype for Business-Konten lokal verfügen, können Sie den TeamsOnly-Modus auf Mandantenebene nicht zuweisen.</span><span class="sxs-lookup"><span data-stu-id="9df7a-142">If you have any users with Skype for Business accounts on-premises, you cannot assign TeamsOnly mode at the tenant level.</span></span> <span data-ttu-id="9df7a-143">Sie müssen diese Benutzer mithilfe von Move-CsUser einzeln in die Cloud verschieben.</span><span class="sxs-lookup"><span data-stu-id="9df7a-143">You must move these users individually to the cloud using Move-CsUser.</span></span>


## <a name="using-notifications-in-skype-for-business-clients"></a><span data-ttu-id="9df7a-144">Verwenden von Benachrichtigungen in Skype for Business-Clients</span><span class="sxs-lookup"><span data-stu-id="9df7a-144">Using notifications in Skype for Business clients</span></span>

<span data-ttu-id="9df7a-145">Administratoren können im Skype for Business-Clientbenachrichtigungen für Endbenutzer bereitstellen, um die Benutzer darüber zu informieren, dass Sie in Kürze auf Teams aktualisiert werden, wie in der nachstehenden Abbildung zu sehen ist.</span><span class="sxs-lookup"><span data-stu-id="9df7a-145">Administrators have the option to provide end user notifications in the Skype for Business client to inform users that they will soon be upgraded to Teams, as shown in the following diagram.</span></span> <span data-ttu-id="9df7a-146">Wenn beispielsweise eine Woche vor dem Administrator die Aktualisierung einer Gruppe von Benutzern auf den TeamsOnly-Modus plant, möchte der Administrator diese Benachrichtigungen für diese Benutzergruppe aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9df7a-146">For example, a week before the administrator plans to upgrade a group of users to TeamsOnly mode, the administrator might want to turn on these notifications for that group of users.</span></span> <span data-ttu-id="9df7a-147">Diese Benachrichtigungen werden mit einer Instanz von TeamsUpgradePolicy mit NotifySfbUsers = true aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9df7a-147">These notifications are enabled using an instance of TeamsUpgradePolicy with NotifySfbUsers=true.</span></span>  <span data-ttu-id="9df7a-148">Für alle anderen Modi als TeamsOnly gibt es tatsächlich zwei Instanzen pro Modus, die den beiden Werten von NotifySfbUsers entsprechen.</span><span class="sxs-lookup"><span data-stu-id="9df7a-148">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span>  <span data-ttu-id="9df7a-149">Für alle anderen Modi als TeamsOnly gibt es tatsächlich zwei Instanzen pro Modus, die den beiden Werten von NotifySfbUsers entsprechen.</span><span class="sxs-lookup"><span data-stu-id="9df7a-149">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span> 

![Diagramm mit Benachrichtigungen](media/teams-upgrade-sfb-with-notifications.png)

<span data-ttu-id="9df7a-151">Wenn Ihre Benutzer in Skype for Business online gehostet werden, weisen Sie einfach die Richtlinieninstanz zu, die den gleichen Modus wie der Benutzer hat, aber mit NotifySfbUsers = true.</span><span class="sxs-lookup"><span data-stu-id="9df7a-151">If your users are homed in Skype for Business Online, simply assign the policy instance that has the same mode as the user, but with NotifySfbUsers=true.</span></span> 

<span data-ttu-id="9df7a-152">Wenn Ihre Benutzer in Skype for Business Server lokal gehostet werden, müssen Sie das lokale Toolset verwenden, und Sie benötigen Skype for Business Server 2019 oder CU8 für Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9df7a-152">If your users are homed in Skype for Business Server on-premises, you’ll need to use the on-premises toolset and you’ll need Skype for Business Server 2019 or CU8 for Skype for Business Server 2015.</span></span> <span data-ttu-id="9df7a-153">Für Benutzer, die in Skype for Business Server lokal gehostet werden, wird die Mode-Eigenschaft aus der Online Instanz von TeamsUpgradePolicy berücksichtigt, die NotifySfbUsers-Eigenschaft ist jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="9df7a-153">For users homed in Skype for Business Server on-premises, the mode property from the online instance of TeamsUpgradePolicy is honored, but the NotifySfbUsers property is not.</span></span> <span data-ttu-id="9df7a-154">Wenn Benachrichtigungen erwünscht sind, müssen Sie eine lokale Instanz von TeamsUpgradePolicy erstellen, um das Clientverhalten zu steuern.</span><span class="sxs-lookup"><span data-stu-id="9df7a-154">If notifications are desired, you must create an on-premises instance of TeamsUpgradePolicy to control the client behavior.</span></span> 

<span data-ttu-id="9df7a-155">Erstellen Sie im lokalen PowerShell-Fenster eine neue Instanz von TeamsUpgradePolicy mit NotifySfbUsers = true:</span><span class="sxs-lookup"><span data-stu-id="9df7a-155">In the on-premises PowerShell window, create a new instance of TeamsUpgradePolicy with NotifySfbUsers=true:</span></span>

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

<span data-ttu-id="9df7a-156">Weisen Sie dann mithilfe desselben lokalen PowerShell-Fensters die neue Richtlinie den gewünschten Benutzern zu:</span><span class="sxs-lookup"><span data-stu-id="9df7a-156">Then, using the same on-premises PowerShell window, assign that new policy to the desired users:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a><span data-ttu-id="9df7a-157">Besprechungs Migration</span><span class="sxs-lookup"><span data-stu-id="9df7a-157">Meeting migration</span></span>

<span data-ttu-id="9df7a-158">Wenn ein Benutzer in den TeamsOnly-Modus migriert wird, werden die vorhandenen Skype for Business-Besprechungen, die Sie organisiert haben, standardmäßig in Teams konvertiert.</span><span class="sxs-lookup"><span data-stu-id="9df7a-158">When a user is migrated to TeamsOnly mode, by default their existing Skype for Business meetings that they organized will be converted to Teams.</span></span> <span data-ttu-id="9df7a-159">Sie können das Standardverhalten beim Zuweisen des TeamsOnly-Modus zu einem Benutzer optional deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9df7a-159">You can optionally disable the default behavior when assigning TeamsOnly mode to a user.</span></span> <span data-ttu-id="9df7a-160">Beim Verschieben von Benutzern aus dem lokalen Bereich müssen Besprechungen in die Cloud migriert werden, damit Sie mit dem Online Benutzerkonto funktionieren, aber wenn Sie MoveToTeams nicht angeben, werden die Besprechungen als Skype for Business-Besprechungen migriert und nicht in Teams konvertiert.</span><span class="sxs-lookup"><span data-stu-id="9df7a-160">When moving users from on-premises, meetings must be migrated to the cloud to function with the online user account, but if you do not specify -MoveToTeams, the meetings will be migrated as Skype for Business meetings, rather than converted to Teams.</span></span> 

<span data-ttu-id="9df7a-161">Wenn Sie den TeamsOnly-Modus auf Mandantenebene zuweisen, wird die Besprechungs Migration für keine Benutzer ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="9df7a-161">When assigning TeamsOnly mode at the tenant level, meeting migration is not triggered for any users.</span></span> <span data-ttu-id="9df7a-162">Wenn Sie den TeamsOnly-Modus auf Mandantenebene zuweisen und Besprechungen migrieren möchten, können Sie mithilfe von PowerShell eine Liste der Benutzer im Mandanten abrufen (beispielsweise die Verwendung von Get-CsOnlineUser mit allen benötigten Filtern) und dann jeden dieser Benutzer durchlaufen, um die Besprechungs Migration mithilfe von Start-CsExMeetingMigration zu starten.</span><span class="sxs-lookup"><span data-stu-id="9df7a-162">If you wish to assign TeamsOnly mode at the tenant level and migrate meetings, you can use PowerShell to get a list of users in the tenant (for example, using Get-CsOnlineUser with whatever filters are needed) and then loop through each of these users to trigger meeting migration using Start-CsExMeetingMigration.</span></span> <span data-ttu-id="9df7a-163">Ausführliche Informationen finden Sie unter [Verwenden des Besprechungs Migrations Diensts (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span><span class="sxs-lookup"><span data-stu-id="9df7a-163">For details, see [Using the Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>



## <a name="related-links"></a><span data-ttu-id="9df7a-164">Verwandte Links</span><span class="sxs-lookup"><span data-stu-id="9df7a-164">Related links</span></span>

[<span data-ttu-id="9df7a-165">Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden</span><span class="sxs-lookup"><span data-stu-id="9df7a-165">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="9df7a-166">Konfigurieren der Hybrid Konnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365</span><span class="sxs-lookup"><span data-stu-id="9df7a-166">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="9df7a-167">Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud</span><span class="sxs-lookup"><span data-stu-id="9df7a-167">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="9df7a-168">Festlegen Ihrer Einstellungen für Koexistenz und Upgrades</span><span class="sxs-lookup"><span data-stu-id="9df7a-168">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="9df7a-169">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="9df7a-169">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="9df7a-170">Verwenden des Besprechungs Migrations Diensts (MMS)</span><span class="sxs-lookup"><span data-stu-id="9df7a-170">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

