---
title: Veröffentlichen von apps mit dem Microsoft-Teams Mandanten Apps-Katalog
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/02/2018
ms.topic: article
ms.service: msteams
ms.reviewer: prem
description: Anleitung zum Veröffentlichen von apps im Microsoft-Teams Mandanten Apps Katalog.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 655a9da3670a7894e581cd2e6adebd02ef22706b
ms.sourcegitcommit: d619e44d685e2109b995ffd67ff4b98e5647c8ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "21762935"
---
<a name="publish-apps-to-the-microsoft-teams-tenant-apps-catalog"></a><span data-ttu-id="80cb9-103">Veröffentlichen von apps mit dem Microsoft-Teams Mandanten Apps-Katalog</span><span class="sxs-lookup"><span data-stu-id="80cb9-103">Publish apps to the Microsoft Teams Tenant Apps Catalog</span></span>
=======================================================

<span data-ttu-id="80cb9-104">Der Katalog von Microsoft-Teams Mandanten Apps können zum Testen und Verteilen von Line-of-Business Applications für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="80cb9-104">You can use the Microsoft Teams Tenant Apps Catalog to test and distribute line-of-business applications to your organization.</span></span> 

<span data-ttu-id="80cb9-105">Führen Sie kritischen geschäftlichen Funktionen für die Benutzer, Teams Mandanten App-Katalog können Sie Ihre LOB Anwendung verteilen, die speziell für Ihre Organisation erstellt wurden und dass Sie sich verlassen.</span><span class="sxs-lookup"><span data-stu-id="80cb9-105">The Teams Tenant Apps Catalog lets you distribute your line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions to your users.</span></span> 
 
<span data-ttu-id="80cb9-106">Sie können die Teams Mandanten App-Katalog direkt vom Client Teams apps veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="80cb9-106">You can publish apps to the Teams Tenant Apps Catalog directly from the Teams client.</span></span>

## <a name="publish-an-app-to-the-tenant-apps-catalog-from-the-teams-client"></a><span data-ttu-id="80cb9-107">Veröffentlichen einer app mit dem Mandanten Apps Katalog vom Client Teams</span><span class="sxs-lookup"><span data-stu-id="80cb9-107">Publish an app to the Tenant Apps Catalog from the Teams client</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="80cb9-108">Abrufen eines Teams app-Pakets</span><span class="sxs-lookup"><span data-stu-id="80cb9-108">Get a Teams app package</span></span>

<span data-ttu-id="80cb9-109">Eine app-Paket Teams wird mithilfe von [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)erstellt.</span><span class="sxs-lookup"><span data-stu-id="80cb9-109">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="80cb9-110">Nachdem Sie das app-Paket haben, können Sie Enterprise-app-Katalog hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="80cb9-110">Once you have the app package, you can add it to enterprise app catalog.</span></span> <span data-ttu-id="80cb9-111">Während alle Benutzer in den Mandanten kann Ansicht der app-Katalog derzeit nur globale-Admins haben die Möglichkeit, veröffentlichen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="80cb9-111">While all users in the tenant can view the app catalog, currently only global admins have the ability to publish and manage it.</span></span> <span data-ttu-id="80cb9-112">(Schließlich Teams-Admins kann auch dazu werden.)</span><span class="sxs-lookup"><span data-stu-id="80cb9-112">(Eventually, Teams admins will be able to do this as well.)</span></span>

### <a name="go-to-the-tenant-apps-catalog"></a><span data-ttu-id="80cb9-113">Wechseln Sie zu dem Mandanten Apps Katalog</span><span class="sxs-lookup"><span data-stu-id="80cb9-113">Go to the Tenant Apps Catalog</span></span>

<span data-ttu-id="80cb9-114">Wählen Sie aus dem Microsoft-Teams Store den neuen Abschnitt mit dem Namen für Ihre Organisation bestimmte (in diesem Beispiel wird "Contoso").</span><span class="sxs-lookup"><span data-stu-id="80cb9-114">From the Microsoft Teams Store, select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="80cb9-115">Benutzer in Ihrer Organisation können apps im Katalog anzeigen und installieren Sie diese Teams, denen sie Mitglied sind.</span><span class="sxs-lookup"><span data-stu-id="80cb9-115">Users in your organization can view apps in the catalog and install them to teams of which they are a member.</span></span> 

![Screenshot, der von den Teams App Store zeigt den app-Katalog.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a><span data-ttu-id="80cb9-117">Hinzufügen einer app mit dem Mandanten Apps-Katalog</span><span class="sxs-lookup"><span data-stu-id="80cb9-117">Add an app to the Tenant Apps Catalog</span></span>

<span data-ttu-id="80cb9-118">Wählen Sie aus dem Speicher, **eine benutzerdefinierte Anwendung hochladen** > **für Contoso hochladen**.</span><span class="sxs-lookup"><span data-stu-id="80cb9-118">From the Store, select **Upload a custom app** > **Upload for Contoso**.</span></span>

![Screenshot, der von den Teams App Store zeigt den app-Katalog.](media/private-app-store-teams-image02.png)

<span data-ttu-id="80cb9-120">(Sie können auch **für ich oder Meine Teams hochladen**, die Sideloading, aufgerufen wird, die die app nur für den oder die ausgewählten Teams verfügbar macht auswählen.)</span><span class="sxs-lookup"><span data-stu-id="80cb9-120">(You can also choose **Upload for me or my teams**, which is called sideloading, that makes the app available only to your or your selected teams.)</span></span> 

<span data-ttu-id="80cb9-121">Navigieren Sie zu dem app-Paket, und wählen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="80cb9-121">Navigate to the app package and select it.</span></span>

![Screenshot, der von den Teams App Store zeigt den app-Katalog.](media/private-app-store-teams-image03.png)

<span data-ttu-id="80cb9-123">Wenn Sie zu Ihrem Mandanten Apps Katalog zurückzukehren, wird die neue Enterprise-app vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="80cb9-123">When you go back to your Tenant Apps Catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="80cb9-124">Beachten Sie, dass nur Sie und Mitglieder Ihrer Organisation haben Zugriff auf diese app-Katalog.</span><span class="sxs-lookup"><span data-stu-id="80cb9-124">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-apps-catalog"></a><span data-ttu-id="80cb9-125">Aktualisieren einer app in den Mandanten App-Katalog</span><span class="sxs-lookup"><span data-stu-id="80cb9-125">Update an app in the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="80cb9-126">Wählen Sie aus Ihrem Mandanten Apps Katalog "**...**"</span><span class="sxs-lookup"><span data-stu-id="80cb9-126">From your Tenant Apps Catalog, select “**…**”</span></span> <span data-ttu-id="80cb9-127">Klicken Sie auf oben rechts von der app, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="80cb9-127">on top right of the app you want to update.</span></span>
2. <span data-ttu-id="80cb9-128">Navigieren Sie zu dem aktualisierten app-Paket, und wählen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="80cb9-128">Navigate to the updated app package and select it.</span></span>

![Screenshot, der von den Teams App Store zeigt den app-Katalog.](media/private-app-store-teams-image04.png)

<span data-ttu-id="80cb9-130">Die app wird auf Version 2.0 überarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="80cb9-130">The app will be revised to version 2.0.</span></span> <span data-ttu-id="80cb9-131">Sie werden auch die app für das gesamte Unternehmen aus diesem Menü löschen.</span><span class="sxs-lookup"><span data-stu-id="80cb9-131">You also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a><span data-ttu-id="80cb9-132">Mit dem Mandanten-App-Katalog verwalten der Office 365-Verwaltungsportals</span><span class="sxs-lookup"><span data-stu-id="80cb9-132">Use the Office 365 admin portal to manage the Tenant Apps Catalog</span></span>

<span data-ttu-id="80cb9-133">Wenn Sie apps verfügen, die Fehlerbehebungen erforderlich sind, können Sie vorübergehend apps über das Office 365-Admin-Portal deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="80cb9-133">If you have apps that need bug fixes, you can temporarily disable apps through the Office 365 admin portal.</span></span> <span data-ttu-id="80cb9-134">Zusätzlich zur vorherigen Einstellungen ist vorhanden jetzt ein Abschnitt für Ihr Unternehmen apps.</span><span class="sxs-lookup"><span data-stu-id="80cb9-134">In addition to previous settings, there is now a section dedicated to your company's apps.</span></span> <span data-ttu-id="80cb9-135">Sie können auswählen, welche apps Sie aktivieren oder deaktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="80cb9-135">You can choose which apps you want to enable or disable.</span></span>

![Screenshot, der von den Teams App Store zeigt den app-Katalog.](media/private-app-store-teams-image05.png)

<span data-ttu-id="80cb9-137">Dies hindert die Benutzer am Interaktion mit der app, ohne dass die app vollständig gelöscht.</span><span class="sxs-lookup"><span data-stu-id="80cb9-137">This blocks users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="80cb9-138">Diese Steuerelemente bieten Administratoren zusätzliche Flexibilität und bestimmen, wann die Steuerung von apps im Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="80cb9-138">These controls give admins additional flexibility and control when governance of apps in your enterprise.</span></span> 


