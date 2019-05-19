---
title: Hinzufügen eines Gasts zu einem Team
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 01/31/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: sbhatta
localization_priority: Priority
description: Hier lernen Sie die verfügbaren Tools kennen, mit denen Administratoren neue Gastbenutzer zu einer Organisation hinzufügen können. Dies schließt den Microsoft Teams-Desktop, Webclients und das Portal für Azure Active Directory B2B-Zusammenarbeit ein.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1c68d6c88fded1933a30f10bfd1bfea57d88c4dc
ms.sourcegitcommit: d7c8d03883d4ae4e37af88625dd74ab037eac914
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2019
ms.locfileid: "34159148"
---
<a name="add-a-guest-to-a-team"></a><span data-ttu-id="bfed6-103">Hinzufügen eines Gasts zu einem Team</span><span class="sxs-lookup"><span data-stu-id="bfed6-103">Add a guest to a team</span></span>
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="bfed6-104">Alle Benutzer, die über ein E-Mail-Konto für Geschäftsbenutzer oder Heimanwender (z. B. Outlook, Gmail usw.) verfügen, können als Gäste in Microsoft Teams teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="bfed6-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span>

<span data-ttu-id="bfed6-105">Als globaler Administrator können Sie einen neuen Gastbenutzer auf unterschiedliche Weise zur Organisation hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="bfed6-105">As an admin, you can add a new guest user to the organization in a couple ways:</span></span> 
- <span data-ttu-id="bfed6-106">Globale Administratoren können mit dem Desktop- oder Webclient von Microsoft Teams einen Gast zu einem Team hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="bfed6-106">Global admins who are owners of a team and owners of a team can add a guest to a team through either the Microsoft Teams desktop or the web clients.</span></span> <span data-ttu-id="bfed6-107">Weitere Informationen finden Sie unter [Hinzufügen von Gästen zu einem Team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)</span><span class="sxs-lookup"><span data-stu-id="bfed6-107">For more details, check out [Add guests to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)</span></span>
- <span data-ttu-id="bfed6-108">Fügen Sie Gäste über Azure Active Directory B2B-Zusammenarbeit zu Ihrer Organisation hinzu.</span><span class="sxs-lookup"><span data-stu-id="bfed6-108">Add guests to your organization through Azure Active Directory B2B collaboration.</span></span> <span data-ttu-id="bfed6-109">Azure Active Directory B2B-Zusammenarbeit ermöglicht es einem globalen Administrator, eine Reihe externer Benutzer einzuladen und zu autorisieren, indem er eine CSV-Datei (durch Trennzeichen getrennte Werte) mit nicht mehr als 2.000 Zeilen in das Portal für B2B-Zusammenarbeit hochlädt.</span><span class="sxs-lookup"><span data-stu-id="bfed6-109">Azure Active Directory B2B collaboration allows a global admin to invite and authorize a set of external users by uploading a comma-separated values (CSV) file of no more than 2,000 lines to the B2B collaboration portal.</span></span> <span data-ttu-id="bfed6-110">Ausführlichere Informationen finden Sie unter [Azure Active Directory B2B-Zusammenarbeit](https://go.microsoft.com/fwlink/p/?linkid=826383).</span><span class="sxs-lookup"><span data-stu-id="bfed6-110">For more details, check out [Azure Active Directory B2B collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).</span></span>

<span data-ttu-id="bfed6-111">Mit Azure Active Directory B2B-Zusammenarbeit können Organisationen Richtlinien für bedingten Zugriff und mehrstufige Authentifizierung für B2B-Benutzer erzwingen.</span><span class="sxs-lookup"><span data-stu-id="bfed6-111">With Azure Active Directory B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="bfed6-112">Diese Richtlinien können auf Mandantenebene, App-Ebene oder der Ebene einzelner Benutzer auf die gleiche Weise erzwungen werden, wie sie für Vollzeitmitarbeiter und Mitglieder der Organisation aktiviert werden können.</span><span class="sxs-lookup"><span data-stu-id="bfed6-112">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="bfed6-113">Solche Richtlinien werden bei der Ressourcenorganisation erzwungen.</span><span class="sxs-lookup"><span data-stu-id="bfed6-113">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="bfed6-114">Weitere Informationen finden Sie unter [Bedingter Zugriff für Benutzer der B2B-Zusammenarbeit](https://go.microsoft.com/fwlink/?linkid=857454).</span><span class="sxs-lookup"><span data-stu-id="bfed6-114">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="bfed6-115">Einzelne Gastbenutzer können nicht blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="bfed6-115">Individual guest users can't be blocked.</span></span>

<span data-ttu-id="bfed6-116">Für die von Ihnen bereits über Azure Active Directory B2B, Office 365-Gruppen oder SharePoint Online hinzugefügten Gastbenutzer kann es losgehen.</span><span class="sxs-lookup"><span data-stu-id="bfed6-116">Guest users you have already added via Azure Active Directory B2B, Office 365 Groups or SharePoint Online are ready to go.</span></span> <span data-ttu-id="bfed6-117">Der Office 365-Administrator oder ein Teambesitzer kann diese Gäste zu den jeweiligen Teams hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="bfed6-117">The Office 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="bfed6-118">Wenn ein Team bereits zu einer Office 365-Gruppe gehört und ein Gast zur Gruppe hinzugefügt wird, erhält der Gast Zugriff auf das Team.</span><span class="sxs-lookup"><span data-stu-id="bfed6-118">If a team is already with an Office 365 group, and a guest is added to the group, the guest will get access to the team.</span></span> <span data-ttu-id="bfed6-119">Wenn ein Gast über die Office 365-Gruppe hinzugefügt wird, erhält der Gast keine Einladungs-E-Mail. Ein Mitglied des Teams sollte den Gast daher benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="bfed6-119">Adding a guest via the Office 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="bfed6-120">Gäste unterliegen den [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347)- und [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019)-Dienstbeschränkungen.</span><span class="sxs-lookup"><span data-stu-id="bfed6-120">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>

<span data-ttu-id="bfed6-121">In Azure Active Directory oder im Office 365 Security &amp; Compliance Center können Sie das Hinzufügen von Gastbenutzern nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="bfed6-121">You can track guest additions in Azure Active Directory or the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="bfed6-122">Das Hinzufügen eines Gasts in /+/Microsoft_Teams/+/ wird als Azure AD-Gruppenverwaltungsaktivität „Mitglied zur Gruppe hinzugefügt“ überwacht und protokolliert.</span><span class="sxs-lookup"><span data-stu-id="bfed6-122">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="bfed6-123">Nähere Einzelheiten finden Sie unter [Überwachung eines B2B-Zusammenarbeitsbenutzers und Berichterstellung](https://go.microsoft.com/fwlink/p/?linkid=858884) und [Durchsuchen des Überwachungsprotokolls im Office 365 Security &amp; Compliance Center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span><span class="sxs-lookup"><span data-stu-id="bfed6-123">For more details, see  [Auditing and reporting a B2B collaboration user](https://go.microsoft.com/fwlink/p/?linkid=858884) and [Search the audit log in the Office 365 Security &amp; Compliance Center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="bfed6-124">Gastzugriff und externer Zugriff (Partnerverbund) im Vergleich</span><span class="sxs-lookup"><span data-stu-id="bfed6-124">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="bfed6-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bfed6-125">More information</span></span>

[<span data-ttu-id="bfed6-126">Autorisieren des Gastzugriffs in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bfed6-126">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)</br>
[<span data-ttu-id="bfed6-127">Aktivieren oder Deaktivieren des Gastzugriffs in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bfed6-127">Turn on or off guest access to Teams</span></span>](set-up-guests.md)</br>
[<span data-ttu-id="bfed6-128">Verwenden von PowerShell zum Steuern des Gastzugriffs auf ein Team</span><span class="sxs-lookup"><span data-stu-id="bfed6-128">Use PowerShell to control guest access to a team</span></span>](guest-access-powershell.md)
