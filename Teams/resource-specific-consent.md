---
title: Ressourcenspezifische Zustimmung in Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: nkramer
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informieren Sie sich über die Einstellungen, die Sie konfigurieren müssen, um zu steuern, ob die Teambesitzer in Ihrer Organisation apps zustimmen können.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1ed13f1f85b0c7eccead3737c4549931f016284c
ms.sourcegitcommit: 682566e51a9e5f0fc65540535c7dcdcbd38e04c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "45429377"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a><span data-ttu-id="52d5c-103">Ressourcenspezifische Zustimmung in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="52d5c-103">Resource-specific consent in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="52d5c-104">Die ressourcenspezifische Zustimmung in Microsoft Teams ermöglicht es den Teambesitzern, Apps für den Zugriff auf Team Daten zu genehmigen.</span><span class="sxs-lookup"><span data-stu-id="52d5c-104">Resource-specific consent in Microsoft Teams lets team owners give consent to apps to access team data.</span></span> <span data-ttu-id="52d5c-105">Beispiele für diesen Zugriff sind die Möglichkeit, Kanal Nachrichten zu lesen, Kanäle zu erstellen und zu löschen sowie Kanal Registerkarten zu erstellen und zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="52d5c-105">Examples of such access include the ability to read channel messages, create and delete channels, and create and remove channel tabs.</span></span>

<span data-ttu-id="52d5c-106">Als Administrator steuern Sie, ob die Teambesitzer in Ihrer Organisation mithilfe des Azure Active Directory (Azure AD) PowerShell-Moduls oder des Azure-Portals und des Microsoft Teams admin Centers die Zustimmung über Einstellungen erteilen können, die Sie konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="52d5c-106">As an admin, you control whether team owners in your organization can give consent through settings that you configure by using the Azure Active Directory (Azure AD) PowerShell module or the Azure portal and the Microsoft Teams admin center.</span></span>  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a><span data-ttu-id="52d5c-107">Festlegen, ob Teambesitzer die Zustimmung zu apps erteilen können</span><span class="sxs-lookup"><span data-stu-id="52d5c-107">Set whether team owners can give consent to apps</span></span>

<span data-ttu-id="52d5c-108">Hier sind die Einstellungen, die Sie festlegen müssen, um zu steuern, ob Teambesitzer die Zustimmung zu Apps geben können.</span><span class="sxs-lookup"><span data-stu-id="52d5c-108">Here are the settings that you must set to control whether team owners can give consent to apps.</span></span> <span data-ttu-id="52d5c-109">Achten Sie darauf, alle folgenden Einstellungen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="52d5c-109">Be sure to review all the following settings.</span></span>

### <a name="settings-in-azure-ad"></a><span data-ttu-id="52d5c-110">Einstellungen in Azure AD</span><span class="sxs-lookup"><span data-stu-id="52d5c-110">Settings in Azure AD</span></span>

<span data-ttu-id="52d5c-111">Die beiden folgenden Einstellungen bestimmen, ob Teambesitzer die Zustimmung zu Apps geben können.</span><span class="sxs-lookup"><span data-stu-id="52d5c-111">The following two settings determine whether team owners can give consent to apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="52d5c-112">Das Ändern dieser Einstellungen hat keinen Einfluss auf den Datenzugriff für apps, denen bereits eine Genehmigung erteilt wurde.</span><span class="sxs-lookup"><span data-stu-id="52d5c-112">Changing any of these settings doesn't affect data access for apps that were already granted consent.</span></span> <span data-ttu-id="52d5c-113">Wenn Sie beispielsweise diese Einstellungen so konfigurieren, dass die Zustimmung der Teambesitzer verhindert wird, entfernen diese Änderungen nicht den bereits gewährten Datenzugriff.</span><span class="sxs-lookup"><span data-stu-id="52d5c-113">For example, if you configure these settings to prevent team owners from giving consent, these changes don't remove data access that's already been granted.</span></span>

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a><span data-ttu-id="52d5c-114">"Benutzer können den apps zustimmen, die in Ihrem Auftrag auf Unternehmensdaten zugreifen"</span><span class="sxs-lookup"><span data-stu-id="52d5c-114">The "Users can consent to apps accessing company data on their behalf" setting</span></span>

<span data-ttu-id="52d5c-115">Mit dieser Einstellung wird gesteuert, ob Benutzer in Ihrer Organisation apps in Ihrem Auftrag zustimmen können.</span><span class="sxs-lookup"><span data-stu-id="52d5c-115">This setting controls whether users in your organization can consent to apps on their behalf.</span></span> <span data-ttu-id="52d5c-116">Damit Teambesitzer die Zustimmung erteilen können, muss diese Einstellung auf **Ja**festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="52d5c-116">To enable team owners to give consent, this setting must be set to **Yes**.</span></span> <span data-ttu-id="52d5c-117">Gehen Sie wie folgt vor, um diese Einstellung zu verwalten:</span><span class="sxs-lookup"><span data-stu-id="52d5c-117">To manage this setting, do the following:</span></span>

1. <span data-ttu-id="52d5c-118">Wechseln Sie im Azure-Portal zu Benutzereinstellungen für **Enterprise-Anwendungen**  >  **User settings**.</span><span class="sxs-lookup"><span data-stu-id="52d5c-118">In the Azure portal, go to **Enterprise applications** > **User settings**.</span></span>
2. <span data-ttu-id="52d5c-119">Unter **Unternehmensanwendungen**können Benutzer festzulegen, **dass apps den Zugriff auf Unternehmensdaten in Ihrem Namen** auf **Nein** oder **Ja**genehmigen.</span><span class="sxs-lookup"><span data-stu-id="52d5c-119">Under **Enterprise applications**, set **Users can consent to apps accessing company data on their behalf** to **No** or **Yes**.</span></span>

<span data-ttu-id="52d5c-120">Sie können diese Einstellung auch mithilfe von PowerShell verwalten.</span><span class="sxs-lookup"><span data-stu-id="52d5c-120">You can also manage this setting using PowerShell.</span></span> <span data-ttu-id="52d5c-121">Weitere Informationen finden Sie unter [Konfigurieren von Benutzerinhalten für Anwendungen](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications).</span><span class="sxs-lookup"><span data-stu-id="52d5c-121">To learn more, see [Configure user content to applications](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications).</span></span>

#### <a name="the-enablegroupspecificconsent-setting"></a><span data-ttu-id="52d5c-122">Die Einstellung "EnableGroupSpecificConsent"</span><span class="sxs-lookup"><span data-stu-id="52d5c-122">The "EnableGroupSpecificConsent" setting</span></span>

<span data-ttu-id="52d5c-123">Mit dieser Einstellung wird gesteuert, ob die Benutzer in Ihrer Organisation den apps den Zugriff auf Unternehmensdaten für Ihre eigenen Gruppen zustimmen können.</span><span class="sxs-lookup"><span data-stu-id="52d5c-123">This setting controls whether users in your organization can consent to apps accessing company data for the groups that they own.</span></span> <span data-ttu-id="52d5c-124">Diese Einstellung muss aktiviert sein, damit die Teambesitzer die Zustimmung erteilen können.</span><span class="sxs-lookup"><span data-stu-id="52d5c-124">This setting must be enabled for team owners to give consent.</span></span> <span data-ttu-id="52d5c-125">Eine schrittweise Anleitung zum Verwalten dieser Einstellung mithilfe von PowerShell finden Sie unter [Konfigurieren der Zustimmung des Gruppen Besitzers zu apps, die auf Gruppendaten zugreifen](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data).</span><span class="sxs-lookup"><span data-stu-id="52d5c-125">For steps on how to manage this setting by using PowerShell, see [Configure group owner consent to apps accessing group data](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data).</span></span>

### <a name="settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="52d5c-126">Einstellungen im Microsoft Teams Admin Center</span><span class="sxs-lookup"><span data-stu-id="52d5c-126">Settings in the Microsoft Teams admin center</span></span>

<span data-ttu-id="52d5c-127">Zusätzlich zu den Einstellungen in Azure AD [-, org-Wide-App-Einstellungen](manage-apps.md#manage-org-wide-app-settings) auf der Seite " [apps verwalten](manage-apps.md) ", unabhängig davon, ob eine APP auf der Seite " [apps verwalten](manage-apps.md#allow-and-block-apps) " blockiert oder zulässig ist, und die dem Teambesitzer zugewiesene [App-Berechtigungsrichtlinie](teams-app-permission-policies.md) bestimmt, ob ein Teambesitzer die Zustimmung erteilen kann.</span><span class="sxs-lookup"><span data-stu-id="52d5c-127">In addition to settings in Azure AD, [org-wide app settings](manage-apps.md#manage-org-wide-app-settings) on the [Manage apps](manage-apps.md) page, whether an app is blocked or allowed on the [Manage apps](manage-apps.md#allow-and-block-apps) page, and the [app permission policy](teams-app-permission-policies.md) assigned to the team owner determine whether a team owner can give consent.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="52d5c-128">Das Ändern dieser Einstellungen hat keinen Einfluss auf den Datenzugriff für apps, denen bereits eine Genehmigung erteilt wurde.</span><span class="sxs-lookup"><span data-stu-id="52d5c-128">Changing any of these settings doesn't affect data access for apps that were already granted consent.</span></span> <span data-ttu-id="52d5c-129">Wenn Sie beispielsweise apps von Drittanbietern in der gesamten Organisation deaktivieren oder bestimmte apps blockieren, um zu verhindern, dass Teambesitzer Ihre Zustimmung erteilen, entfernen diese Änderungen den bereits gewährten Datenzugriff nicht.</span><span class="sxs-lookup"><span data-stu-id="52d5c-129">For example, if you disable third-party apps org-wide or if you block specific apps to prevent team owners from giving consent, these changes don't remove data access that's already been granted.</span></span>  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a><span data-ttu-id="52d5c-130">Die Einstellung "Drittanbieter-apps zulassen" in den organisationsweiten App-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="52d5c-130">The "Allow third party apps" setting in org-wide app settings</span></span>

<span data-ttu-id="52d5c-131">Diese organisationsweite app-Einstellung steuert, ob Benutzer in Ihrer Organisation Drittanbieter-Apps verwenden können.</span><span class="sxs-lookup"><span data-stu-id="52d5c-131">This org-wide app setting controls whether users in your organization can use third-party apps.</span></span> <span data-ttu-id="52d5c-132">Diese Einstellung muss aktiviert sein, damit die Teambesitzer die Zustimmung erteilen können.</span><span class="sxs-lookup"><span data-stu-id="52d5c-132">This setting must be on to enable team owners to give consent.</span></span> <span data-ttu-id="52d5c-133">Gehen Sie wie folgt vor, um diese Einstellung zu verwalten:</span><span class="sxs-lookup"><span data-stu-id="52d5c-133">To manage this setting, do the following:</span></span>

1. <span data-ttu-id="52d5c-134">Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams apps**  >  **Verwalten von apps**, und klicken Sie dann auf **organisationsweite App-Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="52d5c-134">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**, and then click **Org-wide app settings**.</span></span>
2. <span data-ttu-id="52d5c-135">Deaktivieren oder aktivieren Sie unter **apps von Drittanbietern**das **Zulassen von Drittanbieter-apps**.</span><span class="sxs-lookup"><span data-stu-id="52d5c-135">Under **Third party apps**, turn off or turn on **Allow third party apps**.</span></span>

    ![Screenshot der Einstellung "Drittanbieter-apps in Teams zulassen"](media/resource-specific-consent-org-wide-setting.png)

<span data-ttu-id="52d5c-137">Sie müssen ggf. bis zu 24 Stunden warten, bis Ihre Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="52d5c-137">You may have to wait up to 24 hours for your changes to take effect.</span></span>

#### <a name="allow-or-block-the-app-at-the-org-level"></a><span data-ttu-id="52d5c-138">Zulassen oder Blockieren der APP auf Organisationsebene</span><span class="sxs-lookup"><span data-stu-id="52d5c-138">Allow or block the app at the org level</span></span>

<span data-ttu-id="52d5c-139">Wenn Sie eine APP auf der Seite " [apps verwalten](manage-apps.md#allow-and-block-apps) " blockieren oder zulassen, wird diese APP für alle Benutzer in Ihrer Organisation blockiert oder zugelassen.</span><span class="sxs-lookup"><span data-stu-id="52d5c-139">When you block or allow an app on the [Manage apps](manage-apps.md#allow-and-block-apps) page, that app is blocked or allowed for all users in your organization.</span></span> <span data-ttu-id="52d5c-140">Team Besitzer können einer APP nur zustimmen, wenn die APP zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="52d5c-140">Team owners can only give consent to an app if the app is allowed.</span></span> <span data-ttu-id="52d5c-141">Gehen Sie wie folgt vor, um eine APP auf Organisationsebene zuzulassen oder zu blockieren:</span><span class="sxs-lookup"><span data-stu-id="52d5c-141">To allow or block an app at the org level, do the following:</span></span>

1. <span data-ttu-id="52d5c-142">Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams apps**  >  **Verwalten von apps**.</span><span class="sxs-lookup"><span data-stu-id="52d5c-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="52d5c-143">Wählen Sie auf der Seite apps verwalten die APP aus, und klicken Sie dann auf **blockieren** , um Sie zu blockieren, oder auf **zulassen** , um Sie zu erlauben.</span><span class="sxs-lookup"><span data-stu-id="52d5c-143">On the Manage apps page, select the app, and then click **Block** to block it or click **Allow** to allow it.</span></span>

    ![Screenshot der blockierten apps in organisationsweiten Einstellungen](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a><span data-ttu-id="52d5c-145">Dem Teambesitzer zugewiesene App-Berechtigungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="52d5c-145">App permission policy assigned to the team owner</span></span>

<span data-ttu-id="52d5c-146">Team Besitzer können Apps nur zustimmen, wenn Sie von der APP-Berechtigungsrichtlinie ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="52d5c-146">Team owners can only give consent to apps that their app permission policy allows them to run.</span></span> <span data-ttu-id="52d5c-147">Gehen Sie wie folgt vor, um die APP-Berechtigungsrichtlinie anzuzeigen und zu verwalten, die einem Teambesitzer zugewiesen ist:</span><span class="sxs-lookup"><span data-stu-id="52d5c-147">To view and manage the app permission policy that's assigned to a team owner, do the following:</span></span>

1. <span data-ttu-id="52d5c-148">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="52d5c-148">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="52d5c-149">Doppelklicken Sie auf den Anzeigenamen des Team Besitzers, und klicken Sie dann auf **Richtlinien**.</span><span class="sxs-lookup"><span data-stu-id="52d5c-149">Double-click the display name of the team owner, and then click **Policies**.</span></span>
3. <span data-ttu-id="52d5c-150">Die dem Teambesitzer zugewiesene Richtlinie wird unter **App-Berechtigungsrichtlinie**aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="52d5c-150">The policy assigned to the team owner is listed under **App permission policy**.</span></span>
    - <span data-ttu-id="52d5c-151">Wenn Sie eine andere Richtlinie zuweisen möchten, klicken Sie auf **Bearbeiten**, und wählen Sie dann die Richtlinie aus, die Sie zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="52d5c-151">To assign a different policy, click **Edit**, and then select the policy that you want to assign.</span></span>
    - <span data-ttu-id="52d5c-152">Wenn Sie die Einstellungen der Richtlinie bearbeiten möchten, die dem Teambesitzer zugewiesen ist, klicken Sie auf den Richtliniennamen, und nehmen Sie dann die gewünschten Änderungen vor.</span><span class="sxs-lookup"><span data-stu-id="52d5c-152">To edit the settings of the policy that's assigned to the team owner, click the policy name, and then make the changes that you want.</span></span>  

## <a name="uploading-custom-apps"></a><span data-ttu-id="52d5c-153">Hochladen benutzerdefinierter apps</span><span class="sxs-lookup"><span data-stu-id="52d5c-153">Uploading custom apps</span></span>

<span data-ttu-id="52d5c-154">Wenn Sie eine benutzerdefinierte app (auch bekannt Sideloading) hochladen, die eine ressourcenspezifische Zustimmung verwendet, muss die APP von dem Mandanten stammen, in dem Sie installiert ist.</span><span class="sxs-lookup"><span data-stu-id="52d5c-154">When uploading a custom app (also known sideloading) that uses resource-specific consent, the app must come from the tenant that it's being installed to.</span></span> <span data-ttu-id="52d5c-155">Anders ausgedrückt, muss die Azure AD-App-Registrierung von diesem Mandanten sein.</span><span class="sxs-lookup"><span data-stu-id="52d5c-155">In other words, the Azure AD app registration must be from this tenant.</span></span> <span data-ttu-id="52d5c-156">Globale Administratoren sind von dieser Einschränkung ausgenommen und können benutzerdefinierte apps von einem beliebigen Mandanten hochladen, entweder direkt in ein Team (Sideloading) oder in den Mandanten-App-Katalog.</span><span class="sxs-lookup"><span data-stu-id="52d5c-156">Global admins are exempted from this restriction, and can upload custom apps from any tenant, either directly to a team (sideloading) or to the tenant app catalog.</span></span>

## <a name="related-topics"></a><span data-ttu-id="52d5c-157">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="52d5c-157">Related topics</span></span>

- [<span data-ttu-id="52d5c-158">Verfügbare RSC-Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="52d5c-158">Available RSC permissions</span></span>](https://aka.ms/teams-rsc)
- [<span data-ttu-id="52d5c-159">Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="52d5c-159">Microsoft Graph</span></span>](https://developer.microsoft.com/graph)
- [<span data-ttu-id="52d5c-160">Verwalten Ihrer Apps im Microsoft Teams Admin Center</span><span class="sxs-lookup"><span data-stu-id="52d5c-160">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="52d5c-161">Verwalten von Richtlinien für App-Berechtigungen in Teams</span><span class="sxs-lookup"><span data-stu-id="52d5c-161">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
