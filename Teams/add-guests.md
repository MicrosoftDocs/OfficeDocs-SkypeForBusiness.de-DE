---
title: Hinzufügen eines Gasts zu einem Team
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
search.appverid: MET150
ms.reviewer: sbhatta
f1.keywords:
- NOCSH
localization_priority: Priority
description: Administratoren lernen, wie sie neue Gastbenutzer zu einer Organisation im Microsoft Teams-Desktop, in Webclients und im Portal für Azure Active Directory B2B-Zusammenarbeit hinzufügen können.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 60538383021028d043cb47197dd41ee89f8a4d37
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "43139364"
---
<a name="add-a-guest-to-a-team"></a><span data-ttu-id="9a887-103">Hinzufügen eines Gasts zu einem Team</span><span class="sxs-lookup"><span data-stu-id="9a887-103">Add a guest to a team</span></span>
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="9a887-104">Alle Benutzer, die über ein E-Mail-Konto für Geschäftsbenutzer oder Heimanwender (z. B. Outlook, Gmail usw.) verfügen, können als Gäste in Microsoft Teams teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="9a887-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span>

<span data-ttu-id="9a887-105">Als globaler Administrator können Sie einen neuen Gastbenutzer auf unterschiedliche Weise zur Organisation hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="9a887-105">As an admin, you can add a new guest user to the organization in a couple of ways:</span></span>
- <span data-ttu-id="9a887-106">Globale Administratoren oder Teams Administratoren und Teambesitzer fügen einen Gast zu einem Team in den Teams Clients oder im Team Admin Center hinzu.</span><span class="sxs-lookup"><span data-stu-id="9a887-106">Global admins or Teams admins and team owners add a guest to a team in the Teams clients or in the Teams admin center.</span></span> <span data-ttu-id="9a887-107">Weitere Informationen dazu finden Sie unter [Hinzufügen von Gästen zu einem Team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span><span class="sxs-lookup"><span data-stu-id="9a887-107">To learn more, read [Add guests to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span> <span data-ttu-id="9a887-108">Wenn Sie noch keinen Gastzugriff eingerichtet haben, führen Sie die Schritte in der [Prüfliste für den Gastzugriff](guest-access-checklist.md)durch.</span><span class="sxs-lookup"><span data-stu-id="9a887-108">If you haven't set up guest access yet, go through the steps in the [Guest access checklist](guest-access-checklist.md).</span></span>

> [!NOTE] 
> <span data-ttu-id="9a887-109">Dies gilt nicht, wenn **Administratoren und Benutzer mit der Rolle "Gasteinladender" können einladen** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9a887-109">This does not apply when **Admins and users in the guest inviter role can invite** is enabled.</span></span> <span data-ttu-id="9a887-110">Der Grund dafür ist, dass die Rolle "Gasteinladender" in Teams nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="9a887-110">This is because the guest inviter role isn't supported in Teams.</span></span>

- <span data-ttu-id="9a887-111">Fügen Sie Gäste über Azure Active Directory (Azure AD) B2B-Zusammenarbeit zu Ihrer Organisation hinzu.</span><span class="sxs-lookup"><span data-stu-id="9a887-111">Add guests to your organization through Azure Active Directory (Azure AD) B2B collaboration.</span></span> <span data-ttu-id="9a887-112">Azure AD B2B-Zusammenarbeit ermöglicht es einem globalen Administrator, eine Reihe externer Benutzer einzuladen und zu autorisieren, indem er eine CSV-Datei (durch Trennzeichen getrennte Werte) mit nicht mehr als 2.000 Zeilen in das Portal für B2B-Zusammenarbeit hochlädt.</span><span class="sxs-lookup"><span data-stu-id="9a887-112">Azure AD B2B collaboration allows a global admin to invite and authorize a set of external users by uploading a comma-separated values (CSV) file of no more than 2,000 lines to the B2B collaboration portal.</span></span> <span data-ttu-id="9a887-113">Ausführlichere Informationen finden Sie unter [Azure Active Directory B2B-Zusammenarbeit](https://go.microsoft.com/fwlink/p/?linkid=826383).</span><span class="sxs-lookup"><span data-stu-id="9a887-113">For more details, check out [Azure Active Directory B2B collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).</span></span>

<span data-ttu-id="9a887-114">Mit Azure AD B2B-Zusammenarbeit können Organisationen Richtlinien für bedingten Zugriff und mehrstufige Authentifizierung für B2B-Benutzer erzwingen.</span><span class="sxs-lookup"><span data-stu-id="9a887-114">With Azure AD B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="9a887-115">Diese Richtlinien können auf Mandantenebene, App-Ebene oder der Ebene einzelner Benutzer auf die gleiche Weise erzwungen werden, wie sie für Vollzeitmitarbeiter und Mitglieder der Organisation aktiviert werden können.</span><span class="sxs-lookup"><span data-stu-id="9a887-115">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="9a887-116">Solche Richtlinien werden bei der Ressourcenorganisation erzwungen.</span><span class="sxs-lookup"><span data-stu-id="9a887-116">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="9a887-117">Weitere Informationen finden Sie unter [Bedingter Zugriff für Benutzer der B2B-Zusammenarbeit](https://go.microsoft.com/fwlink/?linkid=857454).</span><span class="sxs-lookup"><span data-stu-id="9a887-117">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="9a887-118">Einzelne Gastbenutzer können nicht blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="9a887-118">Individual guest users can't be blocked.</span></span>

<span data-ttu-id="9a887-119">Für die von Ihnen bereits über Azure AD B2B, Office 365-Gruppen oder SharePoint Online hinzugefügten Gastbenutzer kann es losgehen.</span><span class="sxs-lookup"><span data-stu-id="9a887-119">Guest users you have already added via Azure AD B2B, Office 365 Groups, or SharePoint Online are ready to go.</span></span> <span data-ttu-id="9a887-120">Der Office 365-Administrator oder ein Teambesitzer kann diese Gäste zu den jeweiligen Teams hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9a887-120">The Office 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="9a887-121">Wenn ein Team bereits zu einer Office 365-Gruppe gehört und ein Gast zur Gruppe hinzugefügt wird, erhält der Gast Zugriff auf das Team.</span><span class="sxs-lookup"><span data-stu-id="9a887-121">If a team is already with an Office 365 group, and a guest is added to the group, the guest will get access to the team.</span></span> <span data-ttu-id="9a887-122">Wenn ein Gast über die Office 365-Gruppe hinzugefügt wird, erhält der Gast keine Einladungs-E-Mail. Ein Mitglied des Teams sollte den Gast daher benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="9a887-122">Adding a guest via the Office 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="9a887-123">Gäste unterliegen den [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347)- und [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019)-Dienstbeschränkungen.</span><span class="sxs-lookup"><span data-stu-id="9a887-123">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>

<span data-ttu-id="9a887-124">In Azure AD oder im Office 365 Security &amp; Compliance Center können Sie das Hinzufügen von Gastbenutzern nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="9a887-124">You can track guest additions in Azure AD or the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="9a887-125">Das Hinzufügen eines Gasts in /+/Microsoft_Teams/+/ wird als Azure AD-Gruppenverwaltungsaktivität „Mitglied zur Gruppe hinzugefügt“ überwacht und protokolliert.</span><span class="sxs-lookup"><span data-stu-id="9a887-125">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="9a887-126">Nähere Einzelheiten finden Sie unter [Überwachung eines B2B-Zusammenarbeitsbenutzers und Berichterstellung](https://go.microsoft.com/fwlink/p/?linkid=858884) und [Durchsuchen des Überwachungsprotokolls im Office 365 Security &amp; Compliance Center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span><span class="sxs-lookup"><span data-stu-id="9a887-126">For more details, see  [Auditing and reporting a B2B collaboration user](https://go.microsoft.com/fwlink/p/?linkid=858884) and [Search the audit log in the Office 365 Security &amp; Compliance Center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>


## <a name="more-information"></a><span data-ttu-id="9a887-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9a887-127">More information</span></span>

[<span data-ttu-id="9a887-128">Autorisieren des Gastzugriffs in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9a887-128">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)</br>
[<span data-ttu-id="9a887-129">Aktivieren oder Deaktivieren des Gastzugriffs in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9a887-129">Turn on or off guest access in Microsoft Teams</span></span>](set-up-guests.md)</br>
[<span data-ttu-id="9a887-130">Verwenden von PowerShell zum Steuern des Gastzugriffs auf ein Team</span><span class="sxs-lookup"><span data-stu-id="9a887-130">Use PowerShell to control guest access to a team</span></span>](guest-access-powershell.md)
