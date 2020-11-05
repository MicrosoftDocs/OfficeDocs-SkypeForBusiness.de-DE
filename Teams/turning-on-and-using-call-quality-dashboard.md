---
title: Einrichten des Dashboards für die Anrufqualität (CQD)
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Hier erfahren Sie, wie Sie das Dashboard für die Anrufqualität aktivieren und verwenden und zusammenfassende Berichte über die Qualität von Anrufen erhalten.
ms.openlocfilehash: 9a864b0ad0f48e3a0bd8665b8dfeb917e67f4062
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2020
ms.locfileid: "48918650"
---
# <a name="set-up-call-quality-dashboard-cqd"></a><span data-ttu-id="a0edf-103">Einrichten des Dashboards für die Anrufqualität (CQD)</span><span class="sxs-lookup"><span data-stu-id="a0edf-103">Set up Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="a0edf-104">Öffnen Sie das Microsoft Call Quality-Dashboard (CQD) unter [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (melden Sie sich mit Ihren Administratoranmeldeinformationen an).</span><span class="sxs-lookup"><span data-stu-id="a0edf-104">Open the Microsoft Call Quality Dashboard (CQD) at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (sign in with your admin credentials).</span></span> <span data-ttu-id="a0edf-105">Oder wechseln Sie zum Team Admin Center, und wählen Sie **Anruf Qualitäts Dashboard** aus.</span><span class="sxs-lookup"><span data-stu-id="a0edf-105">Or go to the Teams admin center and select **Call Quality Dashboard**.</span></span> 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Screenshot der Schaltfläche "Anrufqualität" im Team Admin Center":::

<span data-ttu-id="a0edf-107">Klicken Sie auf der Seite, die geöffnet wird, auf **Anmelden** , und geben Sie Ihr globales Administrator Konto oder Microsoft Teams-Dienstadministratorkonto Informationen ein.</span><span class="sxs-lookup"><span data-stu-id="a0edf-107">On the page that opens, click **Sign in** and enter your Global Administrator account or Microsoft Teams Service Admin account information.</span></span> <span data-ttu-id="a0edf-108">Nachdem Sie sich das erste Mal angemeldet haben, wird CQD mit dem sammeln und Verarbeiten von Daten beginnen.</span><span class="sxs-lookup"><span data-stu-id="a0edf-108">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="a0edf-109">Beachten Sie, dass es möglicherweise eine oder mehrere Stunden dauert, bis genügend Daten verarbeitet werden, um aussagekräftige Ergebnisse in den Berichten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a0edf-109">Keep in mind that it may take one or more hours to process enough data to display meaningful results in the reports.</span></span>

<span data-ttu-id="a0edf-110">CQD zeigt Anruf-und Besprechungs Qualität auf organisationsweiter Ebene für Microsoft Teams, Skype for Business Online und Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a0edf-110">CQD shows call and meeting quality, at an org-wide level, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="a0edf-111">Wenn Sie CQD mit Skype for Business Server 2019 verwenden möchten, müssen Sie den [Anrufdaten-Konnektor konfigurieren](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector).</span><span class="sxs-lookup"><span data-stu-id="a0edf-111">To use CQD with Skype for Business Server 2019, you'll have to [Configure Call Data Connector](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector).</span></span> <span data-ttu-id="a0edf-112">Weitere Informationen finden Sie unter [Planen von Anrufdaten-Konnektoren](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) vor dem Start.</span><span class="sxs-lookup"><span data-stu-id="a0edf-112">See [Plan Call Data Connector](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) before you start.</span></span>


## <a name="assign-admin-roles-for-access-to-cqd"></a><span data-ttu-id="a0edf-113">Zuweisen von Administratorrollen für den Zugriff auf CQD</span><span class="sxs-lookup"><span data-stu-id="a0edf-113">Assign admin roles for access to CQD</span></span>

<span data-ttu-id="a0edf-114">Zuweisen von [Rollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) für den Zugriff auf CQD für Personen, die Sie verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="a0edf-114">Assign [roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) for accessing CQD to the people who need to use it.</span></span>

<span data-ttu-id="a0edf-115">Wenn Sie möchten, dass Benutzer, die keine Administratoren sind (beispielsweise Support Engineers und Helpdesk-Agents), das Dashboard für die Anrufqualität verwenden, können Sie diesen Benutzern eine der folgenden Rollen zuweisen, die Zugriff auf CQD gewährt.</span><span class="sxs-lookup"><span data-stu-id="a0edf-115">If you want non-admin users (such as support engineers and helpdesk agents) to use Call Quality Dashboard, you can assign those users one of the following roles, which gives access to CQD.</span></span> 


|  |<span data-ttu-id="a0edf-116">Berichte anzeigen</span><span class="sxs-lookup"><span data-stu-id="a0edf-116">View reports</span></span>  |<span data-ttu-id="a0edf-117">EUII-Felder anzeigen</span><span class="sxs-lookup"><span data-stu-id="a0edf-117">View EUII fields</span></span>  |<span data-ttu-id="a0edf-118">Berichte erstellen</span><span class="sxs-lookup"><span data-stu-id="a0edf-118">Create reports</span></span>  |<span data-ttu-id="a0edf-119">Gebäudedaten hochladen</span><span class="sxs-lookup"><span data-stu-id="a0edf-119">Upload building data</span></span>  |
|---------|:-------:|:-------:|:-------:|:-------:|
|<span data-ttu-id="a0edf-120">Globaler Office 365-Administrator</span><span class="sxs-lookup"><span data-stu-id="a0edf-120">Office 365 Global Administrator</span></span>     |<span data-ttu-id="a0edf-121">Ja</span><span class="sxs-lookup"><span data-stu-id="a0edf-121">Yes</span></span>         |<span data-ttu-id="a0edf-122">Ja</span><span class="sxs-lookup"><span data-stu-id="a0edf-122">Yes</span></span>         |<span data-ttu-id="a0edf-123">Ja</span><span class="sxs-lookup"><span data-stu-id="a0edf-123">Yes</span></span>         |<span data-ttu-id="a0edf-124">Ja</span><span class="sxs-lookup"><span data-stu-id="a0edf-124">Yes</span></span>         |
|<span data-ttu-id="a0edf-125">Teams-Dienstadministrator</span><span class="sxs-lookup"><span data-stu-id="a0edf-125">Teams Service Administrator</span></span>     |<span data-ttu-id="a0edf-126">Ja</span><span class="sxs-lookup"><span data-stu-id="a0edf-126">Yes</span></span>         |<span data-ttu-id="a0edf-127">Ja</span><span class="sxs-lookup"><span data-stu-id="a0edf-127">Yes</span></span>         |<span data-ttu-id="a0edf-128">Ja</span><span class="sxs-lookup"><span data-stu-id="a0edf-128">Yes</span></span>         |<span data-ttu-id="a0edf-129">Ja</span><span class="sxs-lookup"><span data-stu-id="a0edf-129">Yes</span></span>         |
|<span data-ttu-id="a0edf-130">Teams-Kommunikationsadministrator</span><span class="sxs-lookup"><span data-stu-id="a0edf-130">Teams Communications Administrator</span></span>     |<span data-ttu-id="a0edf-131">Ja</span><span class="sxs-lookup"><span data-stu-id="a0edf-131">Yes</span></span>         |<span data-ttu-id="a0edf-132">Ja</span><span class="sxs-lookup"><span data-stu-id="a0edf-132">Yes</span></span>         |<span data-ttu-id="a0edf-133">Ja</span><span class="sxs-lookup"><span data-stu-id="a0edf-133">Yes</span></span>         |<span data-ttu-id="a0edf-134">Ja</span><span class="sxs-lookup"><span data-stu-id="a0edf-134">Yes</span></span>         |
|<span data-ttu-id="a0edf-135">Teams-Kommunikationssupporttechniker</span><span class="sxs-lookup"><span data-stu-id="a0edf-135">Teams Communications Support Engineer</span></span>     |<span data-ttu-id="a0edf-136">Ja</span><span class="sxs-lookup"><span data-stu-id="a0edf-136">Yes</span></span>         |<span data-ttu-id="a0edf-137">Ja</span><span class="sxs-lookup"><span data-stu-id="a0edf-137">Yes</span></span>         |<span data-ttu-id="a0edf-138">Ja</span><span class="sxs-lookup"><span data-stu-id="a0edf-138">Yes</span></span>         |<span data-ttu-id="a0edf-139">Nein</span><span class="sxs-lookup"><span data-stu-id="a0edf-139">No</span></span>         |
|<span data-ttu-id="a0edf-140">Supportfachmann für die Teams-Kommunikation</span><span class="sxs-lookup"><span data-stu-id="a0edf-140">Teams Communications Support Specialist</span></span>     |<span data-ttu-id="a0edf-141">Ja</span><span class="sxs-lookup"><span data-stu-id="a0edf-141">Yes</span></span>         |<span data-ttu-id="a0edf-142">Nein</span><span class="sxs-lookup"><span data-stu-id="a0edf-142">No</span></span>         |<span data-ttu-id="a0edf-143">Ja</span><span class="sxs-lookup"><span data-stu-id="a0edf-143">Yes</span></span>         |<span data-ttu-id="a0edf-144">Nein</span><span class="sxs-lookup"><span data-stu-id="a0edf-144">No</span></span>         |
|<span data-ttu-id="a0edf-145">Skype for Business-Administrator</span><span class="sxs-lookup"><span data-stu-id="a0edf-145">Skype for Business Administrator</span></span>     |<span data-ttu-id="a0edf-146">Ja</span><span class="sxs-lookup"><span data-stu-id="a0edf-146">Yes</span></span>         |<span data-ttu-id="a0edf-147">Ja</span><span class="sxs-lookup"><span data-stu-id="a0edf-147">Yes</span></span>         |<span data-ttu-id="a0edf-148">Ja</span><span class="sxs-lookup"><span data-stu-id="a0edf-148">Yes</span></span>         |<span data-ttu-id="a0edf-149">Ja</span><span class="sxs-lookup"><span data-stu-id="a0edf-149">Yes</span></span>         |
|<span data-ttu-id="a0edf-150">Azure AD globaler Leseberechtigter</span><span class="sxs-lookup"><span data-stu-id="a0edf-150">Azure AD Global Reader</span></span> |<span data-ttu-id="a0edf-151">Ja</span><span class="sxs-lookup"><span data-stu-id="a0edf-151">Yes</span></span>         |<span data-ttu-id="a0edf-152">Ja</span><span class="sxs-lookup"><span data-stu-id="a0edf-152">Yes</span></span>         |<span data-ttu-id="a0edf-153">Ja</span><span class="sxs-lookup"><span data-stu-id="a0edf-153">Yes</span></span>         |<span data-ttu-id="a0edf-154">Nein</span><span class="sxs-lookup"><span data-stu-id="a0edf-154">No</span></span>         |
|<span data-ttu-id="a0edf-155">Office 365-Berichtleseberechtigter<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a0edf-155">Office 365 Reports Reader<sup>1</sup></span></span>     |<span data-ttu-id="a0edf-156">Ja</span><span class="sxs-lookup"><span data-stu-id="a0edf-156">Yes</span></span>         |<span data-ttu-id="a0edf-157">Nein</span><span class="sxs-lookup"><span data-stu-id="a0edf-157">No</span></span>         |<span data-ttu-id="a0edf-158">Ja</span><span class="sxs-lookup"><span data-stu-id="a0edf-158">Yes</span></span>         |<span data-ttu-id="a0edf-159">Nein</span><span class="sxs-lookup"><span data-stu-id="a0edf-159">No</span></span>         |

<span data-ttu-id="a0edf-160"><sup>1</sup> Zusätzlich zum Lesen von CQD-Berichten kann der Office 365-Berichtleseberechtigter alle [Aktivitätsberichte](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) im Admin Center sowie alle Berichte aus dem [Inhaltspaket zur Microsoft 365-Einführung](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f) anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a0edf-160"><sup>1</sup> In addition to reading CQD reports, the Office 365 Reports Reader can view all the [activity reports](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) in the admin center and any reports from the [Microsoft 365 Adoption content pack](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).</span></span>

> [!NOTE]
> <span data-ttu-id="a0edf-161">Wenn Sie [EUII (Endbenutzer-identifizierbare Informationen)](CQD-data-and-reports.md#euii-data) nicht sehen und über eine der Rollen verfügen, die diese Informationen anzeigen dürfen, denken Sie daran, dass CQD nur 28 Tage lang EUII.</span><span class="sxs-lookup"><span data-stu-id="a0edf-161">If you're not seeing [EUII (end-user identifiable information)](CQD-data-and-reports.md#euii-data) and you have one of the roles that's permitted to see this information, keep in mind that CQD only keeps EUII for 28 days.</span></span> <span data-ttu-id="a0edf-162">Alles, was älter als 28 Tage ist, wird gelöscht.</span><span class="sxs-lookup"><span data-stu-id="a0edf-162">Anything older than 28 days is deleted.</span></span>

<span data-ttu-id="a0edf-163">Weitere Informationen zu diesen Rollen finden Sie unter [Informationen zu Office 365-Administratorrollen](/office365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="a0edf-163">For more information about these roles, see [About Office 365 admin roles](/office365/admin/add-users/about-admin-roles).</span></span>


<span data-ttu-id="a0edf-164">Nachdem Sie sich das erste Mal angemeldet haben, wird CQD mit dem sammeln und Verarbeiten von Daten beginnen.</span><span class="sxs-lookup"><span data-stu-id="a0edf-164">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="a0edf-165">Ab Dezember 2019 können Sie weiterhin auf die ältere Version von CQD (CQD.lync.com) zugreifen, obwohl das Legacy Portal Ihnen einen Link zu dem neuesten CQD (CQD.Teams.Microsoft.com) bietet.</span><span class="sxs-lookup"><span data-stu-id="a0edf-165">As of December 2019, you can still access the older version of CQD (cqd.lync.com), although the legacy portal gives you a link to the latest CQD (cqd.teams.microsoft.com).</span></span> <span data-ttu-id="a0edf-166">Schließlich wird die ältere Version von CQD außer Betrieb genommen.</span><span class="sxs-lookup"><span data-stu-id="a0edf-166">Eventually, the older version of CQD will be decommissioned.</span></span> <span data-ttu-id="a0edf-167">Ab dem 1. Juli 2020 greift die ältere Version von CQD auf Daten aus dem neuesten CQD zu.</span><span class="sxs-lookup"><span data-stu-id="a0edf-167">As of July 1, 2020, the older version of CQD accesses data from the latest CQD.</span></span>


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a><span data-ttu-id="a0edf-168">Migrieren von Gebäudedaten und Berichten aus einer früheren Version von CQD</span><span class="sxs-lookup"><span data-stu-id="a0edf-168">Migrate building data and reports from previous version of CQD</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a0edf-169">Ab dem 1. Juli 2020 können Sie keine Gebäudedaten und Berichte mehr aus dem alten CQD ( https://CQD.lync.com) .</span><span class="sxs-lookup"><span data-stu-id="a0edf-169">As of July 1, 2020, you can no longer migrate building data and reports from the old CQD (https://CQD.lync.com).</span></span> 



## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="a0edf-170">Verwenden von Power BI zum Analysieren von CQD-Daten</span><span class="sxs-lookup"><span data-stu-id="a0edf-170">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="a0edf-171">Neu im Januar 2020: [Power BI-Abfragevorlagen für CQD herunterladen](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="a0edf-171">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="a0edf-172">Anpassbare Power BI-Vorlagen, mit deren Hilfe Sie Ihre CQD-Daten analysieren und berichten können.</span><span class="sxs-lookup"><span data-stu-id="a0edf-172">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="a0edf-173">Lesen [verwenden Sie Power BI zum Analysieren von CQD-Daten](CQD-Power-BI-query-templates.md) , um weitere Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a0edf-173">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>


## <a name="related-topics"></a><span data-ttu-id="a0edf-174">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a0edf-174">Related topics</span></span>

[<span data-ttu-id="a0edf-175">Verbessern und Überwachen der Anrufqualität für Teams</span><span class="sxs-lookup"><span data-stu-id="a0edf-175">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="a0edf-176">Was ist CQD?</span><span class="sxs-lookup"><span data-stu-id="a0edf-176">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="a0edf-177">Hochladen von Mandanten-und Gebäudedaten</span><span class="sxs-lookup"><span data-stu-id="a0edf-177">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="a0edf-178">CQD-Daten und-Berichte</span><span class="sxs-lookup"><span data-stu-id="a0edf-178">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="a0edf-179">Verwenden von CQD zum Verwalten von Anruf-und Besprechungs Qualität</span><span class="sxs-lookup"><span data-stu-id="a0edf-179">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="a0edf-180">In CQD verfügbare Dimensionen und Measures</span><span class="sxs-lookup"><span data-stu-id="a0edf-180">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="a0edf-181">Datenstrom Klassifizierung in CQD</span><span class="sxs-lookup"><span data-stu-id="a0edf-181">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="a0edf-182">Verwenden von Power BI zum Analysieren von CQD-Daten</span><span class="sxs-lookup"><span data-stu-id="a0edf-182">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)
