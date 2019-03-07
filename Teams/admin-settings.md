---
title: Administratoreinstellungen für Apps in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ritikag
description: Hier erfahren Sie, wie Apps in Microsoft Teams aktiviert werden. Dazu zählt auch das Querladen von externen Apps.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43d2e00e7e8608f78ef2e7ed87bd225596aec6c3
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464156"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="9d562-103">Administratoreinstellungen für Apps in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9d562-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="9d562-104">Apps werden Registerkarten, Connectors, Bots oder eine beliebige Kombination der folgenden drei, von Teams (erste Teilnehmern apps und auch bekannt als Standard-apps) oder einem Drittanbieter (auch als externe apps bezeichnet) bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="9d562-104">Apps are tabs, connectors, bots, or any combination of these three, provided by Teams (first-party apps, and also known as default apps) or by a third-party (also known as external apps).</span></span> <span data-ttu-id="9d562-105">In der Microsoft-365-Verwaltungskonsole können Sie aktivieren und Deaktivieren von Standard-apps und Konfigurieren von Einstellungen, um externe apps zu steuern.</span><span class="sxs-lookup"><span data-stu-id="9d562-105">In the Microsoft 365 admin center, you can enable and disable default apps and configure settings to control external apps.</span></span> <span data-ttu-id="9d562-106">Diese Einstellungen können Sie angeben, welche externen apps zulässig sind und nicht zulässig, neue externe app Verhalten und ob Seite laden apps zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="9d562-106">These settings let you specify which external apps are allowed and disallowed, new external app behavior, and whether side-loading apps is allowed.</span></span>

 <span data-ttu-id="9d562-107">Zum Verwalten von Einstellungen für apps in Teams Admin, wechseln Sie zur Microsoft 365 Administrationscenter, und wählen Sie **Einstellungen** > **Services &-add-ins** > **Microsoft-Teams**.</span><span class="sxs-lookup"><span data-stu-id="9d562-107">To manage admin settings for apps in Teams, go to the Microsoft 365 admin center and choose **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span> <span data-ttu-id="9d562-108">Wenn Sie als Office 365-Administrator angemeldet sind, können Sie diesen Link verwenden:</span><span class="sxs-lookup"><span data-stu-id="9d562-108">If you're signed in as an Office 365 admin, this link should take you there:</span></span>

https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns 

<span data-ttu-id="9d562-109">Weitere Informationen zu Administratoreinstellungen für Apps erhalten Sie im folgenden Video:</span><span class="sxs-lookup"><span data-stu-id="9d562-109">To learn more about admin settings for apps, see the following video:</span></span> 
 
|  |  |
|---------|---------|
| <span data-ttu-id="9d562-110">Verwalten der App-Funktionen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9d562-110">Managing the App Experience in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/CHnpw1O7EgM" frameborder="0" allowfullscreen></iframe>     | 

## <a name="allow-external-apps-in-teams"></a><span data-ttu-id="9d562-111">Zulassen von externen Apps in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9d562-111">Allow external apps in Teams</span></span>

<span data-ttu-id="9d562-112">Standardmäßig ist die Option **Allow external apps in Microsoft Teams** (Externe Apps in Microsoft Teams zulassen) aktiviert, und alle Apps sind ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="9d562-112">By default, **Allow external apps in Microsoft Teams** is turned on, with all apps selected.</span></span>  <span data-ttu-id="9d562-113">Wenn Sie diese Einstellung deaktivieren, werden alle externen Drittanbieter-apps deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="9d562-113">If you turn off this setting, all external third-party apps are disabled.</span></span> 

## <a name="enable-new-external-apps-by-default"></a><span data-ttu-id="9d562-114">Standardmäßiges Aktivieren von neuen externen Apps</span><span class="sxs-lookup"><span data-stu-id="9d562-114">Enable new external apps by default</span></span>

#### <a name="trophy-best-practice-manage-external-apps-individually"></a><span data-ttu-id="9d562-115">:trophy: Bewährte Methode: Verwalten Sie externe Apps einzeln.</span><span class="sxs-lookup"><span data-stu-id="9d562-115">:trophy: Best practice: Manage external apps individually</span></span> 
 
<span data-ttu-id="9d562-116">Um einige Apps zu aktivieren (und andere zu deaktivieren), deaktivieren Sie **Allow sideloading of external apps** (Querladen von externen Apps zulassen).</span><span class="sxs-lookup"><span data-stu-id="9d562-116">To turn on some apps (and turn off others), turn off **Allow sideloading of external apps**.</span></span> <span data-ttu-id="9d562-117">Deaktivieren Sie dann die Apps, die Ihre Benutzer nicht verwenden sollen.</span><span class="sxs-lookup"><span data-stu-id="9d562-117">Then turn off any apps you don't want your users to use.</span></span> <span data-ttu-id="9d562-118">Optional: Deaktivieren Sie **Enable new external apps by default** (Neue externe Apps standardmäßig aktivieren), wenn Sie neue Apps steuern möchten.</span><span class="sxs-lookup"><span data-stu-id="9d562-118">Optional: Turn off **Enable new external apps by default** (if you want to control new apps).</span></span> 

> [!NOTE]
> <span data-ttu-id="9d562-119">Standard-apps beispielsweise derjenigen, die von Microsoft, sind von der Einstellung der **Aktivieren von neuen externen apps standardmäßig** nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="9d562-119">Default apps, such as those built by Microsoft, are not affected by the **Enable new external apps by default** setting.</span></span> <span data-ttu-id="9d562-120">Neue apps sind bei Microsoft veröffentlicht standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9d562-120">New apps are enabled by default when released by Microsoft.</span></span>

<span data-ttu-id="9d562-121">Wenn diese Einstellung aktiviert ist, können Benutzer neue apps aktivieren, sobald zum Teams app-Katalog aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="9d562-121">When this setting is turned on, users can activate new apps as soon as they're added to the Teams app catalog.</span></span> <span data-ttu-id="9d562-122">Um den Microsoft Teams-App-Katalog zu öffnen, klicken Sie unten in Microsoft Teams auf **Store** und dann auf **Apps**.</span><span class="sxs-lookup"><span data-stu-id="9d562-122">To open the Teams app catalog, click **Store** at the bottom of Teams, then click **Apps**.</span></span> <span data-ttu-id="9d562-123">Wenn Sie möchten steuern, welche apps verfügbar sind, deaktivieren Sie diese Einstellung.</span><span class="sxs-lookup"><span data-stu-id="9d562-123">If you want to control which apps are available, turn off this setting.</span></span> <span data-ttu-id="9d562-124">Wenn Sie die Option deaktiviert haben, müssen Sie natürlich daran denken, neue Apps regelmäßig zu überprüfen, damit Ihrer Organisation keine tollen neuen Apps entgehen.</span><span class="sxs-lookup"><span data-stu-id="9d562-124">Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

<span data-ttu-id="9d562-125">Querladen ist das Verfahren zum Hinzufügen einer App in Microsoft Teams, indem Sie eine ZIP-Datei direkt in ein Team hochladen.</span><span class="sxs-lookup"><span data-stu-id="9d562-125">Sideloading is how you add an app to Teams by uploading a zip file directly to a team.</span></span> <span data-ttu-id="9d562-126">Mithilfe von Querladen können Sie Apps schon während der Entwicklung testen.</span><span class="sxs-lookup"><span data-stu-id="9d562-126">Sideloading lets you test an app as it's being developed.</span></span> <span data-ttu-id="9d562-127">Außerdem können Sie eine App nur zur internen Verwendung erstellen und für Ihr Team freigeben, ohne sie an den Microsoft Teams-App-Katalog im Office Store zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="9d562-127">It also lets you build an app for internal use only and share it with your team without submitting it to the Teams app catalog in the Office Store.</span></span> 

<span data-ttu-id="9d562-128">Nur Teambesitzer oder Mitglieder mit den entsprechenden Berechtigungen können Apps in Microsoft Teams querladen.</span><span class="sxs-lookup"><span data-stu-id="9d562-128">Only team owners, or members who are granted permissions, can sideload apps into Teams.</span></span>  

<span data-ttu-id="9d562-129">![Screenshot des Abschnitts erweiterte externe Apps.] (media/teams-tenant-wide-settings-external-apps.png "Screenshot des erweiterten externe Apps Abschnitts mit externen apps")</span><span class="sxs-lookup"><span data-stu-id="9d562-129">![Screen shot of the expanded External Apps section.](media/teams-tenant-wide-settings-external-apps.png "Screen shot of the expanded External Apps section showing external apps")</span></span>

## <a name="creating-and-uploading-app-packages"></a><span data-ttu-id="9d562-130">Erstellen und Hochladen von App-Paketen</span><span class="sxs-lookup"><span data-stu-id="9d562-130">Creating and uploading app packages</span></span> 

<span data-ttu-id="9d562-131">Weitere Informationen zu apps finden Sie unter [Entwickeln von apps für Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview).</span><span class="sxs-lookup"><span data-stu-id="9d562-131">To learn more about apps, see [Develop apps for Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview).</span></span> 



