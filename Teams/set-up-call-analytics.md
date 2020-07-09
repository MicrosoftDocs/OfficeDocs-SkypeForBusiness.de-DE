---
title: Einrichten von Anruf Analysen für Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
description: Richten Sie eine pro-Benutzer-anrufanalyse ein, um Probleme mit der Anrufqualität von Microsoft Teams zu identifizieren und zu beheben.
ms.openlocfilehash: 233d91a60ea783238e10ed1baa02334494ef6e08
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085311"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a><span data-ttu-id="e7886-103">Einrichten von Anruf Analysen für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e7886-103">Set up call analytics for Microsoft Teams</span></span>

<span data-ttu-id="e7886-104">Als Microsoft Teams-Administrator können Sie benutzerspezifische Anruf Analysen verwenden, um die Anrufqualität von Teams und Verbindungsprobleme für **einzelne Benutzer**zu beheben.</span><span class="sxs-lookup"><span data-stu-id="e7886-104">As a Microsoft Teams admin, you can use per-user call analytics to troubleshoot Teams call quality and connection problems for **individual users**.</span></span> <span data-ttu-id="e7886-105">Um die Vorteile der anrufanalyse optimal zu nutzen, müssen Sie Folgendes einrichten:</span><span class="sxs-lookup"><span data-stu-id="e7886-105">To take full advantage of call analytics, set up the following:</span></span>
  
- <span data-ttu-id="e7886-106">Weisen Sie Personen wie Helpdesk-Agents spezielle Support Rollen zu, damit Sie die anrufanalyse für Benutzer anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="e7886-106">Assign specialized support roles to people, such as helpdesk agents, to let them view call analytics for users.</span></span> <span data-ttu-id="e7886-107">Diese Support Rollen können nicht auf das restliche Team Admin Center zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e7886-107">These support roles can't access the rest of the Teams admin center.</span></span> 
    
- <span data-ttu-id="e7886-108">Fügen Sie Informationen zu Gebäude-, Website-und Mandanteninformationen für die benutzerspezifische anrufanalyse hinzu, indem Sie eine TSV-oder CSV-Datendatei hochladen.</span><span class="sxs-lookup"><span data-stu-id="e7886-108">Add building, site, and tenant information to per-user call analytics by uploading a .tsv or .csv data file.</span></span>
    
<span data-ttu-id="e7886-109">Wenn Sie bereit sind, die benutzerspezifische anrufanalyse zu verwenden, lesen Sie [Verwenden von benutzerspezifischer anrufanalyse, um eine schlechte Anrufqualität zu beheben](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span><span class="sxs-lookup"><span data-stu-id="e7886-109">When you're ready to start using per-user call analytics, read [Use per-user call analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a><span data-ttu-id="e7886-110">Erteilen der Berechtigung für Support-und Helpdesk-Mitarbeiter</span><span class="sxs-lookup"><span data-stu-id="e7886-110">Give permission to support and helpdesk staff</span></span>

<span data-ttu-id="e7886-111">Als Team-Administrator haben Sie vollständigen Zugriff auf die anrufanalyse Informationen für alle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="e7886-111">As the Teams admin, you have full access to call analytics information for all users.</span></span> <span data-ttu-id="e7886-112">Wir haben einige spezielle Azure Active Directory-Rollen erstellt, die Sie den Supportmitarbeitern und Helpdesk-Agents zuweisen können, damit Sie auch auf die benutzerspezifische anrufanalyse zugreifen können (ohne Zugriff auf das restliche Team Admin Center).</span><span class="sxs-lookup"><span data-stu-id="e7886-112">We've created some specialized Azure Active Directory roles that you can assign to support staff and helpdesk agents so they can also access per-user call analytics (without having access to the rest of the Teams admin center).</span></span> <span data-ttu-id="e7886-113">Weisen Sie die Rolle des **Teams Communications Support Specialist** für Benutzer zu, die eine begrenzte Ansicht der pro-Benutzer-anrufanalyse (Stufe 1-Unterstützung) haben sollten.</span><span class="sxs-lookup"><span data-stu-id="e7886-113">Assign the **Teams communications support specialist** role to users who should have a limited view of per-user call analytics (Tier 1 support).</span></span> <span data-ttu-id="e7886-114">Weisen Sie die Rolle **Teams Communications Support Engineer** Benutzern zu, die vollständigen Zugriff auf die pro-Benutzer-anrufanalyse benötigen (Support für Stufe 2).</span><span class="sxs-lookup"><span data-stu-id="e7886-114">Assign the **Teams communications support engineer** role to users who need full access to per-user call analytics (Tier 2 support).</span></span> <span data-ttu-id="e7886-115">Keine der Rollen hat Zugriff auf das restliche Team Admin Center.</span><span class="sxs-lookup"><span data-stu-id="e7886-115">Neither role has access to the rest of the Teams admin center.</span></span>

<span data-ttu-id="e7886-116">Wenn Sie wissen möchten, was jede dieser Rollen tut, lesen Sie [Was ist die Rolle jedes Teams unterstützen](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?</span><span class="sxs-lookup"><span data-stu-id="e7886-116">To learn what each of these roles does, read [What does each Teams Support role do](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?</span></span>

<span data-ttu-id="e7886-117">Weitere Informationen zu Teams-Administratorrollen finden Sie unter Verwenden von Teams- [Administratorrollen zum Verwalten von Teams](using-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="e7886-117">For more information about Teams admin roles, see [Use Teams admin roles to manage Teams](using-admin-roles.md).</span></span> <span data-ttu-id="e7886-118">Informationen zum Zuweisen von Administratorrollen in Azure Active Directory finden Sie unter [anzeigen und Zuweisen von Rollen in Azure Active Directory](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span><span class="sxs-lookup"><span data-stu-id="e7886-118">To learn how to assign admin roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

<span data-ttu-id="e7886-119">Informationen zum Zuweisen von Administratorrollen in Azure Active Directory finden Sie unter [anzeigen und Zuweisen von Rollen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span><span class="sxs-lookup"><span data-stu-id="e7886-119">To learn how to assign administrative roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a><span data-ttu-id="e7886-120">Hochladen einer TSV- oder CSV-'Datei, um Informationen zu Gebäuden, Standorten und Mandanten hinzuzufügen</span><span class="sxs-lookup"><span data-stu-id="e7886-120">Upload a .tsv or .csv file to add building, site, and tenant information</span></span>

<span data-ttu-id="e7886-121">Sie können der pro-Benutzer-anrufanalyse Gebäude-, Website-und Mandanteninformationen hinzufügen, indem Sie eine CSV-oder TSV-Datei hochladen.</span><span class="sxs-lookup"><span data-stu-id="e7886-121">You can add building, site, and tenant information to per-user call analytics by uploading a .csv or .tsv file.</span></span> <span data-ttu-id="e7886-122">Mit all diesen Informationen können Anruf Analysen IP-Adressen physikalischen Speicherorten zuordnen.</span><span class="sxs-lookup"><span data-stu-id="e7886-122">With all this information, call analytics can map IP addresses to physical locations.</span></span> <span data-ttu-id="e7886-123">Administratoren und Helpdesk-Agents können diese Informationen dazu verwenden, Trends bei Anruf Problemen zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="e7886-123">Admins and helpdesk agents can use this information to help spot trends in call problems.</span></span> <span data-ttu-id="e7886-124">Warum haben Benutzer im gleichen Gebäude beispielsweise ähnliche Probleme mit der Anrufqualität?</span><span class="sxs-lookup"><span data-stu-id="e7886-124">For example, why are users in the same building having similar call quality problems?</span></span> 

<span data-ttu-id="e7886-125">Wenn Sie ein Team oder ein Skype for Business-Administrator sind, können Sie eine vorhandene Mandanten-und Gebäude Datendatei aus dem Dashboard Teams oder Skype for Business-Anrufqualität (CQD) verwenden.</span><span class="sxs-lookup"><span data-stu-id="e7886-125">If you're a Teams or Skype for Business admin, you can use an existing tenant and building data file from the Teams or Skype for Business Call Quality Dashboard (CQD).</span></span> <span data-ttu-id="e7886-126">Zuerst laden Sie die Datei von CQD herunter, und laden Sie Sie dann in die anrufanalyse hoch.</span><span class="sxs-lookup"><span data-stu-id="e7886-126">First, you download the file from CQD, then upload it to call analytics.</span></span> 

- <span data-ttu-id="e7886-127">Wenn Sie eine vorhandene Datendatei herunterladen möchten, wechseln Sie jetzt zum **Microsoft Teams Admin Center**-  >  **Anruf Quality-Dashboard**  >  **hochladen**.</span><span class="sxs-lookup"><span data-stu-id="e7886-127">To download an existing data file, go to **Microsoft Teams admin center** > **Call Quality Dashboard** > **Upload now**.</span></span> <span data-ttu-id="e7886-128">Klicken Sie in der Liste **Meine Uploads** neben der gewünschten Datei auf **Herunterladen**.</span><span class="sxs-lookup"><span data-stu-id="e7886-128">In the **My uploads** list, click **Download** next to the file you want.</span></span> 

- <span data-ttu-id="e7886-129">Wenn Sie die neue Datei hochladen möchten, wechseln Sie zu den **Microsoft Teams Admin Center**-  >  **Speicherorten**, und wählen Sie dann **Standortdaten hochladen** oder **Standortdaten ersetzen**aus.</span><span class="sxs-lookup"><span data-stu-id="e7886-129">To upload the new file, go to **Microsoft Teams admin center** > **Locations**, and then select **Upload location data** or **Replace location data**.</span></span>
  
<span data-ttu-id="e7886-130">Wenn Sie die TSV-oder CSV-Datei von Grund auf neu erstellen, lesen Sie [Hochladen von Mandanten-und Gebäudedaten](CQD-upload-tenant-building-data.md).</span><span class="sxs-lookup"><span data-stu-id="e7886-130">If you're creating the .tsv or .csv file from scratch, see [Upload tenant and building data](CQD-upload-tenant-building-data.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e7886-131">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="e7886-131">Related topics</span></span>

[<span data-ttu-id="e7886-132">Verwenden von pro-Benutzer-Anruf Analysen zur Behandlung schlechter Anrufqualität</span><span class="sxs-lookup"><span data-stu-id="e7886-132">Use per-user call analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="e7886-133">Teams-Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="e7886-133">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
