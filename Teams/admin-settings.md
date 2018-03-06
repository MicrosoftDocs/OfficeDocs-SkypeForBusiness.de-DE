---
title: "Administratoreinstellungen für Apps in Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/29/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: "Hier erfahren Sie, wie Apps in Microsoft Teams aktiviert werden. Dazu zählt auch das Querladen von externen Apps."
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0fb8d7680338ebda68624a765068d4c386ea46b3
ms.sourcegitcommit: 2e8fa3084db7e741c6120fa4c0db7cd3a335e92d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="00afb-103">Administratoreinstellungen für Apps in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="00afb-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================

<span data-ttu-id="00afb-p101">Apps sind Registerkarten, Connectors und Bots bzw. eine beliebige Kombination dieser drei Elemente, die von einem Drittanbieterdienst bereitgestellt werden. Im Office 365 Admin Center können Microsoft Teams-Administratorrichtlinien konfiguriert werden, um zu steuern, welche externen Drittanbieter-Apps zulässig sind. Mit diesen Richtlinien können Sie festlegen, welche Apps zulässig bzw. nicht zulässig sind, das Verhalten neuer externer Apps definieren und angeben, ob das Querladen von Apps zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="00afb-p101">Apps are tabs, connectors, bots, or any combination of these three, provided by a third-party service. There are Admin policies that can be configured in the Office 365 admin center to control which external third-party apps are allowed. These policies let you specify which apps are allowed and disallowed, new external App behavior, and whether side-loading apps is allowed.</span></span>

> [!NOTE]
> <span data-ttu-id="00afb-107">Um die Administratoreinstellungen für Apps in Microsoft Teams zu verwalten, wechseln Sie zum Office 365 Admin Center. Öffnen Sie **Einstellungen** > **Dienste und Add-Ins**, und wählen Sie dann **Microsoft Teams** aus.</span><span class="sxs-lookup"><span data-stu-id="00afb-107">To manage admin settings for apps in Teams, go to the Office 365 admin center and open **Settings** > **Services & add-ins**, then choose **Microsoft Teams**.</span></span> <span data-ttu-id="00afb-108">Wenn Sie als Office 365-Administrator angemeldet sind, können Sie diesen Link verwenden:</span><span class="sxs-lookup"><span data-stu-id="00afb-108">If you're signed in as an Office 365 admin, this link should take you there:</span></span>
> 
> <span data-ttu-id="00afb-109">https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns</span><span class="sxs-lookup"><span data-stu-id="00afb-109">https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns</span></span> 

<span data-ttu-id="00afb-110">Weitere Informationen zu Administratoreinstellungen für Apps erhalten Sie im folgenden Video:</span><span class="sxs-lookup"><span data-stu-id="00afb-110">To learn more about admin settings for apps, see the following video:</span></span> 
 
|  |  |
|---------|---------|
| <span data-ttu-id="00afb-111">Verwalten der App-Funktionen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="00afb-111">Managing the App Experience in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/CHnpw1O7EgM" frameborder="0" allowfullscreen></iframe>     | 

## <a name="allow-external-apps-in-teams"></a><span data-ttu-id="00afb-112">Zulassen von externen Apps in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="00afb-112">Allow external apps in Microsoft Teams</span></span>

<span data-ttu-id="00afb-113">Standardmäßig ist die Option **Allow external apps in Microsoft Teams** (Externe Apps in Microsoft Teams zulassen) aktiviert, und alle Apps sind ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="00afb-113">By default, **Allow external apps in Microsoft Teams** is turned on, with all apps selected.</span></span>  <span data-ttu-id="00afb-114">Wenn Sie diese Option deaktivieren, sind alle externen Drittanbieter-Apps deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="00afb-114">If you turn off this switch, all external third-party apps are disabled.</span></span> 

## <a name="enable-new-external-apps-by-default"></a><span data-ttu-id="00afb-115">Standardmäßiges Aktivieren von neuen externen Apps</span><span class="sxs-lookup"><span data-stu-id="00afb-115">Enable new external apps by default</span></span>

#### <a name="trophy-best-practice-manage-external-apps-individually"></a><span data-ttu-id="00afb-116">:trophy: Bewährte Methode: Verwalten Sie externe Apps einzeln.</span><span class="sxs-lookup"><span data-stu-id="00afb-116">:trophy: Best practice: Manage external apps individually</span></span> 
 
<span data-ttu-id="00afb-117">Um einige Apps zu aktivieren (und andere zu deaktivieren), deaktivieren Sie **Allow sideloading of external apps** (Querladen von externen Apps zulassen).</span><span class="sxs-lookup"><span data-stu-id="00afb-117">To turn on some apps (and turn off others), turn off **Allow sideloading of external apps**.</span></span> <span data-ttu-id="00afb-118">Deaktivieren Sie dann die Apps, die Ihre Benutzer nicht verwenden sollen.</span><span class="sxs-lookup"><span data-stu-id="00afb-118">Then turn off any apps you don't want your users to use.</span></span> <span data-ttu-id="00afb-119">Optional: Deaktivieren Sie **Enable new external apps by default** (Neue externe Apps standardmäßig aktivieren), wenn Sie neue Apps steuern möchten.</span><span class="sxs-lookup"><span data-stu-id="00afb-119">Optional: Turn off **Enable new external apps by default** (if you want to control new apps).</span></span> 

<span data-ttu-id="00afb-120">Wenn diese Option aktiviert ist, können Benutzer neue Apps aktivieren, sobald diese zum Microsoft Teams-App-Katalog hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="00afb-120">When this switch is turned on, users can activate new apps as soon as they're added to the Teams app catalog.</span></span> <span data-ttu-id="00afb-121">Um den Microsoft Teams-App-Katalog zu öffnen, klicken Sie unten in Microsoft Teams auf **Store** und dann auf **Apps**.</span><span class="sxs-lookup"><span data-stu-id="00afb-121">To open the Teams app catalog, click **Store** at the bottom of Teams, then click **Apps**.</span></span> <span data-ttu-id="00afb-122">Wenn Sie die Verfügbarkeit von Apps steuern möchten, deaktivieren Sie diese Option.</span><span class="sxs-lookup"><span data-stu-id="00afb-122">If you want to control which apps are available, turn this switch off.</span></span> <span data-ttu-id="00afb-123">Wenn Sie die Option deaktiviert haben, müssen Sie natürlich daran denken, neue Apps regelmäßig zu überprüfen, damit Ihrer Organisation keine tollen neuen Apps entgehen.</span><span class="sxs-lookup"><span data-stu-id="00afb-123">Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

<span data-ttu-id="00afb-124">Querladen ist das Verfahren zum Hinzufügen einer App in Microsoft Teams, indem Sie eine ZIP-Datei direkt in ein Team hochladen.</span><span class="sxs-lookup"><span data-stu-id="00afb-124">Sideloading is how you add an app to Teams by uploading a zip file directly to a team.</span></span> <span data-ttu-id="00afb-125">Mithilfe von Querladen können Sie Apps schon während der Entwicklung testen.</span><span class="sxs-lookup"><span data-stu-id="00afb-125">Sideloading lets you test an app as it's being developed.</span></span> <span data-ttu-id="00afb-126">Außerdem können Sie eine App nur zur internen Verwendung erstellen und für Ihr Team freigeben, ohne sie an den Microsoft Teams-App-Katalog im Office Store zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="00afb-126">It also lets you build an app for internal use only and share it with your team without submitting it to the Teams app catalog in the Office Store.</span></span> 

<span data-ttu-id="00afb-127">Nur Teambesitzer oder Mitglieder mit den entsprechenden Berechtigungen können Apps in Microsoft Teams querladen.</span><span class="sxs-lookup"><span data-stu-id="00afb-127">Only team owners, or members who are granted permissions, can sideload apps into Teams.</span></span>  

![Screenshot des Abschnitts „Apps“ in den Microsoft Teams-Einstellungen](media/Admin_settings_for_apps_in_Microsoft_Teams_image1.png) 

## <a name="creating-and-uploading-app-packages"></a><span data-ttu-id="00afb-129">Erstellen und Hochladen von App-Paketen</span><span class="sxs-lookup"><span data-stu-id="00afb-129">Creating and uploading app packages</span></span> 

<span data-ttu-id="00afb-130">Weitere Informationen zu Apps finden Sie unter [Apps für Microsoft Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview).</span><span class="sxs-lookup"><span data-stu-id="00afb-130">To learn more about apps, read [Develop apps for Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview).</span></span> 



