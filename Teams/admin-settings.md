---
title: "Administratoreinstellungen für Apps in Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Hier erfahren Sie, wie Apps in Microsoft Teams aktiviert werden. Dazu zählt auch das Querladen von externen Apps."
ms.openlocfilehash: 4265866bb346da1aa773d337d02fc1c11149f579
ms.sourcegitcommit: ee1c79b6d6d73e5fc702fe55b9e5aee8a7aae793
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/10/2018
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="4a7d8-103">Administratoreinstellungen für Apps in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4a7d8-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================

<span data-ttu-id="4a7d8-p101">Apps sind Registerkarten, Connectors und Bots bzw. eine beliebige Kombination dieser drei Elemente, die von einem Drittanbieterdienst bereitgestellt werden. Im Office 365 Admin Center können Administratorrichtlinien konfiguriert werden, um zu steuern, welche externen Drittanbieter-Apps zulässig sind. Mit diesen Richtlinien können Sie festlegen, welche Apps zulässig bzw. nicht zulässig sind, das Verhalten neuer externer Apps definieren und angeben, ob das Querladen von Apps zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="4a7d8-p101">In this section, we refer to tabs, connectors, and bots, or any combination of these capabilities, provided by a single third-party service as Apps. There are Admin policies that can be configured in the Office 365 Admin Portal to control which external third-party apps are allowed. These policies let you specify which apps are allowed and disallowed, new external App behavior, as well as whether side-loading apps is allowed.</span></span>

> [!NOTE]
> <span data-ttu-id="4a7d8-107">Um die Administratoreinstellungen für Apps in Microsoft Teams zu verwalten, wechseln Sie zum Office 365 Admin Center. Öffnen Sie **Einstellungen** > **Dienste und Add-Ins**, und wählen Sie dann **Microsoft Teams** aus.</span><span class="sxs-lookup"><span data-stu-id="4a7d8-107">To manage admin settings for apps in Teams, go to the Office 365 admin center and open **Settings** > **Services & add-ins**, then choose **Microsoft Teams**.</span></span> <span data-ttu-id="4a7d8-108">Wenn Sie als Office 365-Administrator angemeldet sind, können Sie diesen Link verwenden:</span><span class="sxs-lookup"><span data-stu-id="4a7d8-108">If you're signed in as an Office 365 admin, this link should take you there:</span></span>
> 
> <span data-ttu-id="4a7d8-109">https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns</span><span class="sxs-lookup"><span data-stu-id="4a7d8-109">https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns</span></span> 

<span data-ttu-id="4a7d8-110">**Externe Apps in Microsoft Teams zulassen**</span><span class="sxs-lookup"><span data-stu-id="4a7d8-110">**Allow external apps in Microsoft Teams**</span></span>

<span data-ttu-id="4a7d8-p103">In Microsoft Teams ist die Option „Externe Apps zulassen“ bei Auswahl aller Apps aktiviert. Wenn Sie für diese Richtlinie **„Aus“** wählen, werden alle Drittanbieter-Apps deaktiviert. Bei der Aktivierung externer Apps können Sie ein präziseres Steuerungsverhalten erzielen, indem Sie nur bestimmte Apps auf individueller Basis deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4a7d8-p103">By default, allow external apps in Microsoft Teams is enabled with all apps selected. When turning this policy to **“Off”**, then all external third-party apps are disabled. You can get more granular and allow external apps to be enabled and uncheck specific apps that you want to disable on an individual basis.</span></span>

<span data-ttu-id="4a7d8-114">**Neue externe Apps standardmäßig aktivieren**</span><span class="sxs-lookup"><span data-stu-id="4a7d8-114">**Enable new external apps by default**</span></span>

<span data-ttu-id="4a7d8-p104">Immer, wenn neue Apps zum App-Katalog von Teams hinzugefügt werden, wird geprüft, ob diese für Benutzer in diesem Mandanten verfügbar sind. Standardmäßig ist für diese Richtlinie **„Ein“** festgelegt, wodurch Benutzer Zugriff auf die Apps haben, sobald diese zum App-Katalog von Teams hinzugefügt wurden. Wenn Sie die Apps überprüfen möchten, bevor sie in Teams verwendet werden können, legen Sie für diese Richtlinie **„Aus“** fest. Denken Sie einfach daran, dass Sie bei Auswahl von **„Aus“** neu hinzugefügte Apps regelmäßig überprüfen sollten, um sicherzustellen, das Benutzer von den neuesten Innovationen und Erweiterungen der Apps profitieren.</span><span class="sxs-lookup"><span data-stu-id="4a7d8-p104">Whenever new apps are submitted to the Teams App Catalog, this switch controls whether they are available for users in this tenant. By default, this policy is set to **“On”** which allows users to have access to apps as soon as they are added to the Team’s app catalog. If you would prefer to validate apps before allowing them to be utilized in Teams, then set this policy to **Off.** Just remember, if you set this to **"Off",** you should evaluate newly added apps on a regular basis to make sure your users benefit from the latest innovations and additions of apps.</span></span>

<span data-ttu-id="4a7d8-119">**Querladen von externen Apps zulassen**</span><span class="sxs-lookup"><span data-stu-id="4a7d8-119">**Allow side-loading of external apps**</span></span>

<span data-ttu-id="4a7d8-p105">Nur Teambesitzer oder Mitglieder mit den entsprechenden Berechtigungen können das Querladen von Apps in Microsoft Teams durchführen. Einige Vorteile des Querladens von Apps in Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="4a7d8-p105">Only Team owners or members who are granted permissions, can side-load apps into Microsoft Teams. Some benefits of side-loading apps into Microsoft Teams are:</span></span>

-   <span data-ttu-id="4a7d8-122">Testen der Apps vor dem Übermitteln an Microsoft</span><span class="sxs-lookup"><span data-stu-id="4a7d8-122">Ability to test apps prior to submitting to Microsoft</span></span>

-   <span data-ttu-id="4a7d8-123">Direkte Bereitstellung der Apps für Benutzer innerhalb der Organisation, ohne Umweg über den Office Store.</span><span class="sxs-lookup"><span data-stu-id="4a7d8-123">Provide apps directly to users within your organization without having to submit to the Office Store.</span></span>

<span data-ttu-id="4a7d8-124">Weitere Informationen zum Querladen von Apps in Microsoft Teams finden Sie unter: [Querladen Ihrer App in ein Team](https://go.microsoft.com/fwlink/?linkid=854631).</span><span class="sxs-lookup"><span data-stu-id="4a7d8-124">To learn more about side loading apps into Microsoft Teams, visit: [Side loading your app in a team](https://go.microsoft.com/fwlink/?linkid=854631).</span></span>

![Screenshot des Abschnitts „Apps“ in den Microsoft Teams-Einstellungen](media/Admin_settings_for_apps_in_Microsoft_Teams_image1.png)
