---
title: Veröffentlichen von apps im Microsoft Teams-Mandanten-App-Katalog
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: prem
audience: admin
description: Leitfaden zum Veröffentlichen von apps im Microsoft Teams-App-Katalog für Mandanten.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.publishtenantapps
- ms.teamsadmincenter.apppolicies.publishtenantapps
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f3d4f5937c766c1c4f6f54a6a38872e793a3825
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "42161614"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-app-catalog"></a><span data-ttu-id="9e2b6-103">Veröffentlichen von apps im Microsoft Teams-Mandanten-App-Katalog</span><span class="sxs-lookup"><span data-stu-id="9e2b6-103">Publish apps in the Microsoft Teams tenant app catalog</span></span>
=======================================================

<span data-ttu-id="9e2b6-104">Sie können den Microsoft Teams-Mandanten-App-Katalog verwenden, um Branchenanwendungen zu testen und an Ihre Organisation zu verteilen.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-104">You can use the Microsoft Teams tenant app catalog to test and distribute line-of-business applications to your organization.</span></span>

<span data-ttu-id="9e2b6-105">Mit dem App-Katalog für Team Mandanten können Sie branchenspezifische Anwendungen verteilen, die speziell für Ihre Organisation entwickelt wurden und auf die Sie sich verlassen, um wichtige Geschäftsfunktionen abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-105">The Teams tenant app catalog lets you distribute line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions.</span></span>

<span data-ttu-id="9e2b6-106">Wenn Sie Apps für Ihre Organisation veröffentlichen möchten, müssen Sie sich mit einem Konto mit der Rolle globaler Administrator oder Team Dienstadministrator beim Team-Client anmelden und dann die folgenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-106">To publish apps for your organization, sign in to the Teams client using an account with either the global admin or teams service admin role and then follow the steps below.</span></span>

## <a name="publish-an-app-in-the-tenant-app-catalog-from-the-teams-client"></a><span data-ttu-id="9e2b6-107">Veröffentlichen einer APP im Mandanten-App-Katalog vom Team-Client</span><span class="sxs-lookup"><span data-stu-id="9e2b6-107">Publish an app in the tenant app catalog from the Teams client</span></span>

> [!NOTE]
> <span data-ttu-id="9e2b6-108">In diesen Schritten wird beschrieben, wie Sie eine App mithilfe des Teams-Clients veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-108">These steps describe how to publish an app by using the Teams client.</span></span> <span data-ttu-id="9e2b6-109">Sie können eine APP auch auf der Seite " **apps verwalten** " im Microsoft Teams Admin Center veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-109">You can also publish an app on the **Manage apps** page in the Microsoft Teams admin center.</span></span> <span data-ttu-id="9e2b6-110">Weitere Informationen finden Sie unter [Verwalten von apps in Teams](manage-apps.md).</span><span class="sxs-lookup"><span data-stu-id="9e2b6-110">To learn more, see [Manage apps in Teams](manage-apps.md).</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="9e2b6-111">Abrufen eines Teams-App-Pakets</span><span class="sxs-lookup"><span data-stu-id="9e2b6-111">Get a Teams app package</span></span>

<span data-ttu-id="9e2b6-112">Ein Team-App-Paket wird mithilfe von [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)erstellt.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-112">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="9e2b6-113">Nachdem Sie das App-Paket installiert haben, können Sie es dem Mandanten-App-Katalog hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-113">Once you have the app package, you can add it to the tenant app catalog.</span></span> <span data-ttu-id="9e2b6-114">Während alle Benutzer in Ihrer Organisation den App-Katalog anzeigen können, haben nur globale Administratoren und Teams-Dienstadministratoren die Möglichkeit, diese zu veröffentlichen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-114">While all users in your organization can view the app catalog, only global admins and teams service admins have the ability to publish and manage it.</span></span>

### <a name="go-to-the-tenant-app-catalog"></a><span data-ttu-id="9e2b6-115">Wechseln zum Mandanten-App-Katalog</span><span class="sxs-lookup"><span data-stu-id="9e2b6-115">Go to the tenant app catalog</span></span>

<span data-ttu-id="9e2b6-116">Starten Sie Teams, und melden Sie sich mit ihren globalen oder Teams-Dienstadministrator Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-116">Start Teams and sign in using your global or teams service admin credentials.</span></span> <span data-ttu-id="9e2b6-117">Wählen Sie auf der linken Seite der APP **apps** aus, und wählen Sie dann den neuen Abschnitt aus, der für Ihre spezifische Organisation benannt ist (in diesem Beispiel Contoso).</span><span class="sxs-lookup"><span data-stu-id="9e2b6-117">Select **Apps** on the left side of the app, and then select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="9e2b6-118">Benutzer in Ihrer Organisation können apps im Katalog anzeigen und für Teams installieren, deren Mitglied Sie sind.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-118">Users in your organization can view apps in the catalog and install them for teams of which they are a member.</span></span>

![Screenshot des Teams-APP-Speichers mit dem App-Katalog](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-app-catalog"></a><span data-ttu-id="9e2b6-120">Hinzufügen einer App zum Mandanten-App-Katalog</span><span class="sxs-lookup"><span data-stu-id="9e2b6-120">Add an app to the tenant app catalog</span></span>

1. <span data-ttu-id="9e2b6-121">Wählen Sie auf der Seite **apps** die Option **Hochladen eines benutzerdefinierten App** > -**Uploads für Contoso**aus.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-121">On the **Apps** page, select **Upload a custom app** > **Upload for Contoso**.</span></span>

    ![Screenshot des Teams-APP-Speichers mit dem App-Katalog](media/private-app-store-teams-image02.png)

    <span data-ttu-id="9e2b6-123">(Sie können auch **für mich oder meine Teams hochladen**wählen, die als *Sideloading*bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-123">(You can also choose **Upload for me or my teams**, which is called *sideloading*.</span></span> <span data-ttu-id="9e2b6-124">Sideloading stellt die app nur für Ihre Teams oder für die von Ihnen ausgewählten Teams zur Verfügung.)</span><span class="sxs-lookup"><span data-stu-id="9e2b6-124">Sideloading makes the app available only to your teams or to teams you select.)</span></span>

2. <span data-ttu-id="9e2b6-125">Navigieren Sie zum App-Paket, und wählen Sie es aus, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-125">Navigate to the app package and select it, and then click **Open**.</span></span>

    ![Screenshot des Teams-APP-Speichers mit dem App-Katalog](media/private-app-store-teams-image03.png)

<span data-ttu-id="9e2b6-127">Wenn Sie zu Ihrem Mandanten-App-Katalog zurückkehren, wird die neue Enterprise-app vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-127">When you go back to your tenant app catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="9e2b6-128">Beachten Sie, dass nur Sie und Mitglieder Ihrer Organisation auf diesen app-Katalog zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-128">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-app-catalog"></a><span data-ttu-id="9e2b6-129">Aktualisieren einer APP im Mandanten-App-Katalog</span><span class="sxs-lookup"><span data-stu-id="9e2b6-129">Update an app in the tenant app catalog</span></span>

1. <span data-ttu-id="9e2b6-130">Wählen Sie in Ihrem Mandanten-App-Katalog "**...**" aus.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-130">From your tenant app catalog, select “**…**”</span></span> <span data-ttu-id="9e2b6-131">Klicken Sie oben rechts in der APP, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-131">on the top right of the app you want to update.</span></span>

2. <span data-ttu-id="9e2b6-132">Navigieren Sie zum aktualisierten App-Paket, und wählen Sie es aus, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-132">Navigate to the updated app package and select it, and then click **Open**.</span></span>

    ![Screenshot des Teams-APP-Speichers mit dem App-Katalog](media/private-app-store-teams-image04.png)

<span data-ttu-id="9e2b6-134">Die APP wird auf Version 2,0 überarbeitet.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-134">The app will be revised to version 2.0.</span></span> <span data-ttu-id="9e2b6-135">In diesem Menü können Sie auch die APP für Ihr gesamtes Unternehmen löschen.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-135">You can also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-manage-the-tenant-app-catalog"></a><span data-ttu-id="9e2b6-136">Verwenden des Microsoft Teams admin Centers zum Verwalten des Mandanten-App-Katalogs</span><span class="sxs-lookup"><span data-stu-id="9e2b6-136">Use the Microsoft Teams admin center to manage the tenant app catalog</span></span>

<span data-ttu-id="9e2b6-137">Wenn Sie apps haben, die Fehlerbehebungen benötigen, können Sie Apps für Benutzer vorübergehend in einer APP-Berechtigungsrichtlinie deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-137">If you have apps that need bug fixes, you can temporarily disable apps for users in an app permission policy.</span></span>

1. <span data-ttu-id="9e2b6-138">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams-apps** > -**Berechtigungsrichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-138">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="9e2b6-139">Wählen Sie die APP-Berechtigungsrichtlinie aus, die Sie bearbeiten möchten, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-139">Select the app permission policy that you want to edit, and then click **Edit**.</span></span>
3. <span data-ttu-id="9e2b6-140">Wählen Sie unter **Mandanten-apps**die Option **bestimmte apps blockieren und alle anderen zulassen**aus, und fügen Sie dann die apps hinzu, die Sie blockieren möchten.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-140">Under **Tenant apps**, select **Block specific apps and allow all others**, and then add the apps that you want to block.</span></span>

<span data-ttu-id="9e2b6-141">Durch das Deaktivieren einer APP wird verhindert, dass Benutzer mit der APP interagieren, ohne die APP vollständig zu löschen.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-141">Disabling an app blocks users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="9e2b6-142">Diese Steuerelemente bieten zusätzliche Flexibilität und Steuern beim Verwalten von apps in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-142">These controls give you additional flexibility and control when managing apps in your organization.</span></span>

<span data-ttu-id="9e2b6-143">Weitere Informationen finden Sie unter [Verwalten von App-Berechtigungsrichtlinien in Teams](teams-app-permission-policies.md).</span><span class="sxs-lookup"><span data-stu-id="9e2b6-143">To learn more, see [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>