---
title: Veröffentlichen von apps im Microsoft Teams-Mandanten-apps-Katalog
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/20/2019
ms.topic: article
ms.service: msteams
ms.reviewer: prem
audience: admin
description: Leitfaden zum Veröffentlichen von apps im Microsoft Teams-Mandanten-apps-Katalog.
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.apppermspolicies.publishtenantapps
- ms.teamsadmincenter.apppolicies.publishtenantapps
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 42fd9820f6f8ce11b245412a5ae99ed7b43dbc1e
ms.sourcegitcommit: 0f6321d51b40f06855679c18f7313febfedd419a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "38793531"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-apps-catalog"></a><span data-ttu-id="3c968-103">Veröffentlichen von apps im Microsoft Teams-Mandanten-apps-Katalog</span><span class="sxs-lookup"><span data-stu-id="3c968-103">Publish apps in the Microsoft Teams Tenant Apps Catalog</span></span>
=======================================================

<span data-ttu-id="3c968-104">Sie können den Microsoft Teams-Mandanten-apps-Katalog verwenden, um Branchenanwendungen zu testen und an Ihre Organisation zu verteilen.</span><span class="sxs-lookup"><span data-stu-id="3c968-104">You can use the Microsoft Teams Tenant Apps Catalog to test and distribute line-of-business applications to your organization.</span></span>

<span data-ttu-id="3c968-105">Der Katalog "Teams-Mandanten-Apps" ermöglicht es Ihnen, branchenspezifische Anwendungen zu verteilen, die speziell für Ihre Organisation entwickelt wurden und auf die Sie sich verlassen, um wichtige Geschäftsfunktionen abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="3c968-105">The Teams Tenant Apps Catalog lets you distribute line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions.</span></span>

<span data-ttu-id="3c968-106">Wenn Sie Apps für Ihre Organisation veröffentlichen möchten, müssen Sie sich mit einem Konto mit den Rollen des globalen Administrators oder des Teams für Dienstadministratoren bei Ihrem Team-Client anmelden, und folgen Sie dann den nachstehenden Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="3c968-106">To publish apps for your organization, sign in to your Teams client using an account with the global admin or teams service admin roles and then follow the instructions below.</span></span>

## <a name="publish-an-app-in-the-tenant-apps-catalog-from-the-teams-client"></a><span data-ttu-id="3c968-107">Veröffentlichen einer APP im Mandanten-apps-Katalog des Teams-Clients</span><span class="sxs-lookup"><span data-stu-id="3c968-107">Publish an app in the Tenant Apps Catalog from the Teams client</span></span>

> [!NOTE]
> <span data-ttu-id="3c968-108">Sie müssen beim Microsoft Teams-Client mit einem Konto angemeldet sein, das über die Rolle "globaler Administrator" oder "Team Dienstadministrator" verfügt, um Apps für Ihre Organisation zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="3c968-108">You need to be signed in to the Microsoft Teams client with an account that has either the global admin or teams service admin role enabled to publish apps for your organization.</span></span> <span data-ttu-id="3c968-109">Weitere Informationen finden Sie [unter Verwenden von Administratorrollen zum Verwalten von Teams](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="3c968-109">Learn more about [using administrator roles to manage Teams](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles).</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="3c968-110">Abrufen eines Teams-App-Pakets</span><span class="sxs-lookup"><span data-stu-id="3c968-110">Get a Teams app package</span></span>

<span data-ttu-id="3c968-111">Ein Team-App-Paket wird mithilfe von [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)erstellt.</span><span class="sxs-lookup"><span data-stu-id="3c968-111">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="3c968-112">Nachdem Sie das App-Paket installiert haben, können Sie es dem Enterprise-App-Katalog hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3c968-112">Once you have the app package, you can add it to the enterprise app catalog.</span></span> <span data-ttu-id="3c968-113">Während alle Benutzer im Mandanten den App-Katalog anzeigen können, haben nur globale Administratoren und Teams-Dienstadministratoren die Möglichkeit, diese zu veröffentlichen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="3c968-113">While all users in the tenant can view the app catalog, only global admins and teams service admins have the ability to publish and manage it.</span></span>

### <a name="go-to-the-tenant-apps-catalog"></a><span data-ttu-id="3c968-114">Wechseln zum Mandanten-apps-Katalog</span><span class="sxs-lookup"><span data-stu-id="3c968-114">Go to the Tenant Apps Catalog</span></span>

<span data-ttu-id="3c968-115">Starten Sie den Microsoft Teams-Client, und melden Sie sich mit Ihren Dienstadministrator Anmeldeinformationen für Global oder Teams an.</span><span class="sxs-lookup"><span data-stu-id="3c968-115">Start the Microsoft Teams client and sign in using your global or teams service admin credentials.</span></span> <span data-ttu-id="3c968-116">Wählen Sie auf der linken Seite der APP **apps** aus, und wählen Sie dann den neuen Abschnitt aus, der für Ihre spezifische Organisation benannt ist (in diesem Beispiel Contoso).</span><span class="sxs-lookup"><span data-stu-id="3c968-116">Select **Apps** on the left side of the app, and then select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="3c968-117">Benutzer in Ihrer Organisation können apps im Katalog anzeigen und für Teams installieren, deren Mitglied Sie sind.</span><span class="sxs-lookup"><span data-stu-id="3c968-117">Users in your organization can view apps in the catalog and install them for teams of which they are a member.</span></span>

![Screenshot des Teams-APP-Speichers mit dem App-Katalog](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a><span data-ttu-id="3c968-119">Hinzufügen einer App zum Mandanten-apps-Katalog</span><span class="sxs-lookup"><span data-stu-id="3c968-119">Add an app to the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="3c968-120">Wählen Sie auf der Seite **apps** die Option **Hochladen eines benutzerdefinierten App** > -**Uploads für Contoso**aus.</span><span class="sxs-lookup"><span data-stu-id="3c968-120">On the **Apps** page, select **Upload a custom app** > **Upload for Contoso**.</span></span>

    ![Screenshot des Teams-APP-Speichers mit dem App-Katalog](media/private-app-store-teams-image02.png)

    <span data-ttu-id="3c968-122">(Sie können auch **für mich oder meine Teams hochladen**wählen, die als *Sideloading*bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="3c968-122">(You can also choose **Upload for me or my teams**, which is called *sideloading*.</span></span> <span data-ttu-id="3c968-123">Sideloading stellt die app nur für Ihre Teams oder für die von Ihnen ausgewählten Teams zur Verfügung.)</span><span class="sxs-lookup"><span data-stu-id="3c968-123">Sideloading makes the app available only to your teams or to teams you select.)</span></span>

2. <span data-ttu-id="3c968-124">Navigieren Sie zum App-Paket, und wählen Sie es aus, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="3c968-124">Navigate to the app package and select it, and then click **Open**.</span></span>

    ![Screenshot des Teams-APP-Speichers mit dem App-Katalog](media/private-app-store-teams-image03.png)

<span data-ttu-id="3c968-126">Wenn Sie zu Ihrem Mandanten-apps-Katalog zurückkehren, wird die neue Enterprise-app vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="3c968-126">When you go back to your Tenant Apps Catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="3c968-127">Beachten Sie, dass nur Sie und Mitglieder Ihrer Organisation auf diesen app-Katalog zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="3c968-127">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-apps-catalog"></a><span data-ttu-id="3c968-128">Aktualisieren einer APP im Mandanten-apps-Katalog</span><span class="sxs-lookup"><span data-stu-id="3c968-128">Update an app in the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="3c968-129">Wählen Sie in Ihrem Mandanten-apps-Katalog "**...**" aus.</span><span class="sxs-lookup"><span data-stu-id="3c968-129">From your Tenant Apps Catalog, select “**…**”</span></span> <span data-ttu-id="3c968-130">Klicken Sie oben rechts in der APP, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="3c968-130">on the top right of the app you want to update.</span></span>

2. <span data-ttu-id="3c968-131">Navigieren Sie zum aktualisierten App-Paket, und wählen Sie es aus, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="3c968-131">Navigate to the updated app package and select it, and then click **Open**.</span></span>

    ![Screenshot des Teams-APP-Speichers mit dem App-Katalog](media/private-app-store-teams-image04.png)

<span data-ttu-id="3c968-133">Die APP wird auf Version 2,0 überarbeitet.</span><span class="sxs-lookup"><span data-stu-id="3c968-133">The app will be revised to version 2.0.</span></span> <span data-ttu-id="3c968-134">In diesem Menü können Sie auch die APP für Ihr gesamtes Unternehmen löschen.</span><span class="sxs-lookup"><span data-stu-id="3c968-134">You can also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a><span data-ttu-id="3c968-135">Verwenden des Office 365-Administrator Portals zum Verwalten des Mandanten-apps-Katalogs</span><span class="sxs-lookup"><span data-stu-id="3c968-135">Use the Office 365 admin portal to manage the Tenant Apps Catalog</span></span>

<span data-ttu-id="3c968-136">Wenn Sie apps haben, die Fehlerbehebungen benötigen, können Sie apps vorübergehend über die Microsoft 365 Admin Center-#a0 **Teams Admin Center** > **Teams apps** > -**Berechtigungsrichtlinien** > <Richtliniennamen deaktivieren, beispielsweise "Global (org-Wide Standard)" #a3 **Mandanten-apps** > bestimmte apps blockieren und alle anderen Personen und Ihre APP zur Liste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3c968-136">If you have apps that need bug fixes, you can temporarily disable apps through the Microsoft 365 admin center > **Teams admin center** > **Teams apps** > **Permission Policies** > <policy name, e.g. "Global (Org-wide default)"> **Tenant apps** > Block specific apps and allow all others and add your app to the list.</span></span>

![Screenshot des Teams-APP-Speichers mit dem App-Katalog](media/private-app-store-teams-image05.png)

<span data-ttu-id="3c968-138">Durch das Deaktivieren einer APP wird verhindert, dass Benutzer mit der APP interagieren, ohne die APP vollständig zu löschen.</span><span class="sxs-lookup"><span data-stu-id="3c968-138">Disabling an app will block users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="3c968-139">Diese Steuerelemente bieten Ihnen zusätzliche Flexibilität und Kontrolle beim Verwalten von apps in Ihrem Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="3c968-139">These controls give you additional flexibility and control when managing apps in your enterprise.</span></span>
