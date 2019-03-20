---
title: Veröffentlichen von Apps im App-Katalog eines Microsoft Teams-Mandanten
author: lolaj
ms.author: lolaj
manager: serdars
ms.date: 03/15/2019
ms.topic: article
ms.service: msteams
ms.reviewer: prem
description: Anleitung zum Veröffentlichen von apps im Microsoft-Teams Mandanten Apps Katalog.
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.apppolicies.publishtenantapps
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 909ed249ea4e408cbddcd52824a7cb0047504613
ms.sourcegitcommit: 28dd9b8ca3de35a73e4d6923eff5546925435b8b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2019
ms.locfileid: "30684072"
---
<a name="publish-apps-to-the-microsoft-teams-tenant-apps-catalog"></a><span data-ttu-id="47e38-103">Veröffentlichen von Apps im App-Katalog eines Microsoft Teams-Mandanten</span><span class="sxs-lookup"><span data-stu-id="47e38-103">Publish apps to the Microsoft Teams Tenant Apps Catalog</span></span>
=======================================================

<span data-ttu-id="47e38-104">Der Katalog von Microsoft-Teams Mandanten Apps können zum Testen und Verteilen von Line-of-Business Applications für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="47e38-104">You can use the Microsoft Teams Tenant Apps Catalog to test and distribute line-of-business applications to your organization.</span></span> 

<span data-ttu-id="47e38-105">Führen Sie kritischen geschäftlichen Funktionen für die Benutzer, Teams Mandanten App-Katalog können Sie Ihre LOB Anwendung verteilen, die speziell für Ihre Organisation erstellt wurden und dass Sie sich verlassen.</span><span class="sxs-lookup"><span data-stu-id="47e38-105">The Teams Tenant Apps Catalog lets you distribute your line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions to your users.</span></span> 
 
<span data-ttu-id="47e38-106">Melden Sie sich an Ihren Teams Client mit Ihren Anmeldeinformationen globaler Administrator und Veröffentlichen von apps für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="47e38-106">Sign in to your Teams client using your global admin credentials and publish apps for your organization.</span></span> 

## <a name="publish-an-app-to-the-tenant-apps-catalog-from-the-teams-client"></a><span data-ttu-id="47e38-107">Veröffentlichen einer app mit dem Mandanten Apps Katalog vom Client Teams</span><span class="sxs-lookup"><span data-stu-id="47e38-107">Publish an app to the Tenant Apps Catalog from the Teams client</span></span>

<span data-ttu-id="47e38-108">Hinweis: Sie müssen bei der Microsoft-Teams, Client mit Ihren globaler Administrator-Anmeldeinformationen zum Veröffentlichen von apps für Ihre Organisation angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="47e38-108">NOTE: You need to be signed in to the Microsoft Teams client using your global admin credentials to publish apps for your organization.</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="47e38-109">Abrufen eines Teams app-Pakets</span><span class="sxs-lookup"><span data-stu-id="47e38-109">Get a Teams app package</span></span>

<span data-ttu-id="47e38-110">Eine app-Paket Teams wird mithilfe von [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)erstellt.</span><span class="sxs-lookup"><span data-stu-id="47e38-110">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="47e38-111">Nachdem Sie das app-Paket haben, können Sie Enterprise-app-Katalog hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="47e38-111">Once you have the app package, you can add it to enterprise app catalog.</span></span> <span data-ttu-id="47e38-112">Während alle Benutzer in den Mandanten kann Ansicht der app-Katalog derzeit nur globale-Admins haben die Möglichkeit, veröffentlichen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="47e38-112">While all users in the tenant can view the app catalog, currently only global admins have the ability to publish and manage it.</span></span> <span data-ttu-id="47e38-113">(Schließlich Teams-Admins kann auch dazu werden.)</span><span class="sxs-lookup"><span data-stu-id="47e38-113">(Eventually, Teams admins will be able to do this as well.)</span></span>

### <a name="go-to-the-tenant-apps-catalog"></a><span data-ttu-id="47e38-114">Wechseln Sie zu dem Mandanten Apps Katalog</span><span class="sxs-lookup"><span data-stu-id="47e38-114">Go to the Tenant Apps Catalog</span></span>

<span data-ttu-id="47e38-115">Starten Sie den Client für Microsoft-Teams, und melden Sie sich mit Ihren Anmeldeinformationen globaler Administrator.</span><span class="sxs-lookup"><span data-stu-id="47e38-115">Launch the Microsoft Teams client and sign-in using your global admin credentials.</span></span> <span data-ttu-id="47e38-116">Wählen Sie aus dem Microsoft-Teams Store den neuen Abschnitt mit dem Namen für Ihre Organisation bestimmte (in diesem Beispiel wird "Contoso").</span><span class="sxs-lookup"><span data-stu-id="47e38-116">From the Microsoft Teams Store, select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="47e38-117">Benutzer in Ihrer Organisation können apps im Katalog anzeigen und installieren Sie diese Teams, denen sie Mitglied sind.</span><span class="sxs-lookup"><span data-stu-id="47e38-117">Users in your organization can view apps in the catalog and install them to teams of which they are a member.</span></span> 

![Screenshot, der von den Teams App Store zeigt den app-Katalog.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a><span data-ttu-id="47e38-119">Hinzufügen einer app mit dem Mandanten Apps-Katalog</span><span class="sxs-lookup"><span data-stu-id="47e38-119">Add an app to the Tenant Apps Catalog</span></span>

<span data-ttu-id="47e38-120">Wählen Sie aus dem Speicher, **eine benutzerdefinierte Anwendung hochladen** > **für Contoso hochladen**.</span><span class="sxs-lookup"><span data-stu-id="47e38-120">From the Store, select **Upload a custom app** > **Upload for Contoso**.</span></span>

![Screenshot, der von den Teams App Store zeigt den app-Katalog.](media/private-app-store-teams-image02.png)

<span data-ttu-id="47e38-122">(Sie können auch **für ich oder Meine Teams hochladen**, die Sideloading, aufgerufen wird, die die app nur für den oder die ausgewählten Teams verfügbar macht auswählen.)</span><span class="sxs-lookup"><span data-stu-id="47e38-122">(You can also choose **Upload for me or my teams**, which is called sideloading, that makes the app available only to your or your selected teams.)</span></span> 

<span data-ttu-id="47e38-123">Navigieren Sie zu dem app-Paket, und wählen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="47e38-123">Navigate to the app package and select it.</span></span>

![Screenshot, der von den Teams App Store zeigt den app-Katalog.](media/private-app-store-teams-image03.png)

<span data-ttu-id="47e38-125">Wenn Sie zu Ihrem Mandanten Apps Katalog zurückzukehren, wird die neue Enterprise-app vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="47e38-125">When you go back to your Tenant Apps Catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="47e38-126">Beachten Sie, dass nur Sie und Mitglieder Ihrer Organisation haben Zugriff auf diese app-Katalog.</span><span class="sxs-lookup"><span data-stu-id="47e38-126">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-apps-catalog"></a><span data-ttu-id="47e38-127">Aktualisieren einer app in den Mandanten App-Katalog</span><span class="sxs-lookup"><span data-stu-id="47e38-127">Update an app in the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="47e38-128">Wählen Sie aus Ihrem Mandanten Apps Katalog "**...**"</span><span class="sxs-lookup"><span data-stu-id="47e38-128">From your Tenant Apps Catalog, select “**…**”</span></span> <span data-ttu-id="47e38-129">Klicken Sie auf oben rechts von der app, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="47e38-129">on top right of the app you want to update.</span></span>
2. <span data-ttu-id="47e38-130">Navigieren Sie zu dem aktualisierten app-Paket, und wählen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="47e38-130">Navigate to the updated app package and select it.</span></span>

![Screenshot, der von den Teams App Store zeigt den app-Katalog.](media/private-app-store-teams-image04.png)

<span data-ttu-id="47e38-132">Die app wird auf Version 2.0 überarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="47e38-132">The app will be revised to version 2.0.</span></span> <span data-ttu-id="47e38-133">Sie werden auch die app für das gesamte Unternehmen aus diesem Menü löschen.</span><span class="sxs-lookup"><span data-stu-id="47e38-133">You also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a><span data-ttu-id="47e38-134">Mit dem Mandanten-App-Katalog verwalten der Office 365-Verwaltungsportals</span><span class="sxs-lookup"><span data-stu-id="47e38-134">Use the Office 365 admin portal to manage the Tenant Apps Catalog</span></span>

<span data-ttu-id="47e38-135">Wenn Sie apps verfügen, Fehlerbehebungen erforderlich sind, Sie können vorübergehend apps über das Office 365-Admin-Portal deaktivieren, wählen Sie **Einstellungen** > **Services &-add-ins** > **Microsoft-Teams**.</span><span class="sxs-lookup"><span data-stu-id="47e38-135">If you have apps that need bug fixes, you can temporarily disable apps through the Office 365 admin portal, select **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span> <span data-ttu-id="47e38-136">Zusätzlich zur vorherigen Einstellungen ist vorhanden jetzt ein Abschnitt für Ihr Unternehmen apps.</span><span class="sxs-lookup"><span data-stu-id="47e38-136">In addition to previous settings, there is now a section dedicated to your company's apps.</span></span> <span data-ttu-id="47e38-137">Sie können auswählen, welche apps Sie aktivieren oder deaktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="47e38-137">You can choose which apps you want to enable or disable.</span></span>

![Screenshot, der von den Teams App Store zeigt den app-Katalog.](media/private-app-store-teams-image05.png)

<span data-ttu-id="47e38-139">Dies hindert die Benutzer am Interaktion mit der app, ohne dass die app vollständig gelöscht.</span><span class="sxs-lookup"><span data-stu-id="47e38-139">This blocks users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="47e38-140">Diese Steuerelemente bieten Administratoren zusätzliche Flexibilität und bestimmen, wann die Steuerung von apps im Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="47e38-140">These controls give admins additional flexibility and control when governance of apps in your enterprise.</span></span> 


