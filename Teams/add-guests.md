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
description: Hier lernen Sie die verfügbaren Tools kennen, mit denen Administratoren neue Gastbenutzer zu einer Organisation hinzufügen können. Dies schließt den Microsoft Teams-Desktop, Webclients und das Portal für Azure Active Directory B2B-Zusammenarbeit ein.
appliesto:
- Microsoft Teams
ms.openlocfilehash: b68980a3c9019bbff422393e8a47f9d90bb3294a
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "30461212"
---
<a name="add-a-guest-to-a-team"></a><span data-ttu-id="6a47c-103">Hinzufügen eines Gasts zu einem Team</span><span class="sxs-lookup"><span data-stu-id="6a47c-103">Add a guest to a team</span></span>
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="6a47c-104">Jeder Benutzer mit einer Business "oder" Consumer e-Mail-Konto, wie Outlook, Google Mail oder andere, kann als Gast in Teams teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="6a47c-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span>

<span data-ttu-id="6a47c-105">Als globaler Administrator können Sie einen neuen Gastbenutzer auf unterschiedliche Weise zur Organisation hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="6a47c-105">As an admin, you can add a new guest user to the organization in a couple ways:</span></span> 
- <span data-ttu-id="6a47c-106">Globale Administratoren können mit dem Desktop- oder Webclient von Microsoft Teams einen Gast zu einem Team hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6a47c-106">Global admins who are owners of a team and owners of a team can add a guest to a team through either the Microsoft Teams desktop or the web clients.</span></span>
- <span data-ttu-id="6a47c-107">Fügen Sie Gäste über Azure Active Directory B2B-Zusammenarbeit zu Ihrer Organisation hinzu.</span><span class="sxs-lookup"><span data-stu-id="6a47c-107">Add guests to your organization through Azure Active Directory B2B collaboration.</span></span> <span data-ttu-id="6a47c-108">Azure Active Directory B2B-Zusammenarbeit ermöglicht es einem globalen Administrator, eine Reihe externer Benutzer einzuladen und zu autorisieren, indem er eine CSV-Datei (durch Trennzeichen getrennte Werte) mit nicht mehr als 2.000 Zeilen in das Portal für B2B-Zusammenarbeit hochlädt.</span><span class="sxs-lookup"><span data-stu-id="6a47c-108">Azure Active Directory B2B collaboration allows a global admin to invite and authorize a set of external users by uploading a comma-separated values (CSV) file of no more than 2,000 lines to the B2B collaboration portal.</span></span> <span data-ttu-id="6a47c-109">Ausführlichere Informationen finden Sie unter [Azure Active Directory B2B-Zusammenarbeit](https://go.microsoft.com/fwlink/p/?linkid=826383).</span><span class="sxs-lookup"><span data-stu-id="6a47c-109">For more details, check out [Azure Active Directory B2B collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).</span></span>

<span data-ttu-id="6a47c-110">Mit Azure Active Directory B2B-Zusammenarbeit können Organisationen Richtlinien für bedingten Zugriff und mehrstufige Authentifizierung für B2B-Benutzer erzwingen.</span><span class="sxs-lookup"><span data-stu-id="6a47c-110">With Azure Active Directory B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="6a47c-111">Diese Richtlinien können auf der Mandanten-, App- oder individuellen Benutzerebene genau so erzwungen werden, wie sie für Vollzeitmitarbeiter und Mitglieder der Organisation aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="6a47c-111">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="6a47c-112">Solche Richtlinien werden bei der Ressourcenorganisation erzwungen.</span><span class="sxs-lookup"><span data-stu-id="6a47c-112">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="6a47c-113">Weitere Informationen finden Sie unter [Bedingter Zugriff für Benutzer der B2B-Zusammenarbeit](https://go.microsoft.com/fwlink/?linkid=857454).</span><span class="sxs-lookup"><span data-stu-id="6a47c-113">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="6a47c-114">Einzelne Gastbenutzer können nicht blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="6a47c-114">Individual guest users can't be blocked.</span></span>

<span data-ttu-id="6a47c-115">Gast-Benutzer aus, die Sie bereits über Azure Active Directory B2B, Office 365 Gruppen oder SharePoint Online hinzugefügt haben, sind bereit.</span><span class="sxs-lookup"><span data-stu-id="6a47c-115">Guest users you have already added via Azure Active Directory B2B, Office 365 Groups, or SharePoint Online are ready to go.</span></span> <span data-ttu-id="6a47c-116">Der Office 365-Administrator oder ein Teambesitzer kann diese Gäste zu den jeweiligen Teams hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6a47c-116">The Office 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="6a47c-117">Wenn ein Team bereits zu einer Office 365-Gruppe gehört und ein Gast zur Gruppe hinzugefügt wird, erhält der Gast Zugriff auf das Team.</span><span class="sxs-lookup"><span data-stu-id="6a47c-117">If a team is already with an Office 365 group, and a guest is added to the group, the guest will get access to the team.</span></span> <span data-ttu-id="6a47c-118">Wenn ein Gast über die Office 365-Gruppe hinzugefügt wird, erhält der Gast keine Einladungs-E-Mail. Ein Mitglied des Teams sollte den Gast daher benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="6a47c-118">Adding a guest via the Office 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="6a47c-119">Gäste unterliegen den [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347)- und [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019)-Dienstbeschränkungen.</span><span class="sxs-lookup"><span data-stu-id="6a47c-119">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>

<span data-ttu-id="6a47c-120">In Azure Active Directory oder im Office 365 Security &amp; Compliance Center können Sie das Hinzufügen von Gastbenutzern nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="6a47c-120">You can track guest additions in Azure Active Directory or the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="6a47c-121">Das Hinzufügen eines Gasts in /+/Microsoft_Teams/+/ wird als Azure AD-Gruppenverwaltungsaktivität „Mitglied zur Gruppe hinzugefügt“ überwacht und protokolliert.</span><span class="sxs-lookup"><span data-stu-id="6a47c-121">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="6a47c-122">Nähere Einzelheiten finden Sie unter [Überwachung eines B2B-Zusammenarbeitsbenutzers und Berichterstellung](https://go.microsoft.com/fwlink/p/?linkid=858884) und [Durchsuchen des Überwachungsprotokolls im Office 365 Security &amp; Compliance Center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span><span class="sxs-lookup"><span data-stu-id="6a47c-122">For more details, see  [Auditing and reporting a B2B collaboration user](https://go.microsoft.com/fwlink/p/?linkid=858884) and [Search the audit log in the Office 365 Security &amp; Compliance Center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="6a47c-123">Gastzugriff im Vergleich zum externen Zugriff (Verbund)</span><span class="sxs-lookup"><span data-stu-id="6a47c-123">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="6a47c-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6a47c-124">More information</span></span>

[<span data-ttu-id="6a47c-125">Autorisieren des Gastzugriffs in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6a47c-125">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)</br>
[<span data-ttu-id="6a47c-126">Aktivieren Sie oder Deaktivieren der Gast Access in Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="6a47c-126">Turn on or off guest access in Microsoft Teams</span></span>](set-up-guests.md)</br>
[<span data-ttu-id="6a47c-127">Verwenden von PowerShell zum Steuern des Gastzugriffs auf ein Team</span><span class="sxs-lookup"><span data-stu-id="6a47c-127">Use PowerShell to control guest access to a team</span></span>](guest-access-powershell.md)