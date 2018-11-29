---
title: Hinzufügen eines Gasts zu einem Team
author: LaithAlShamri
ms.author: laal
manager: serdars
ms.date: 11/26/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
ms.reviewer: sbhatta
description: Hier lernen Sie die verfügbaren Tools kennen, mit denen Administratoren neue Gastbenutzer zu einer Organisation hinzufügen können. Dies schließt den Microsoft Teams-Desktop, Webclients und das Portal für Azure Active Directory B2B-Zusammenarbeit ein.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 729490af1c1e15b82d62dc35386e9ad4344d863a
ms.sourcegitcommit: 042717530bffa18ca401ad6665a652212a85bc99
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/29/2018
ms.locfileid: "26984734"
---
<a name="add-a-guest-to-a-team"></a><span data-ttu-id="f7aef-103">Hinzufügen eines Gasts zu einem Team</span><span class="sxs-lookup"><span data-stu-id="f7aef-103">Add a guest to a team</span></span>
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="f7aef-104">Jeder Benutzer mit einer Business "oder" Consumer e-Mail-Konto, wie Outlook, Google Mail oder andere, kann als Gast in Teams teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="f7aef-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span>


<span data-ttu-id="f7aef-105">Als globaler Administrator können Sie einen neuen Gastbenutzer auf unterschiedliche Weise zur Organisation hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="f7aef-105">As an admin, you can add a new guest user to the organization in a couple ways:</span></span> 
- <span data-ttu-id="f7aef-106">Globale Administratoren können mit dem Desktop- oder Webclient von Microsoft Teams einen Gast zu einem Team hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f7aef-106">Global admins who are owners of a team and owners of a team can add a guest to a team through either the Microsoft Teams desktop or the web clients.</span></span>
- <span data-ttu-id="f7aef-107">Fügen Sie Gäste über Azure Active Directory B2B-Zusammenarbeit zu Ihrer Organisation hinzu.</span><span class="sxs-lookup"><span data-stu-id="f7aef-107">Add guests to your organization through Azure Active Directory B2B collaboration.</span></span> <span data-ttu-id="f7aef-108">Azure Active Directory B2B-Zusammenarbeit ermöglicht es einem globalen Administrator, eine Reihe externer Benutzer einzuladen und zu autorisieren, indem er eine CSV-Datei (durch Trennzeichen getrennte Werte) mit nicht mehr als 2.000 Zeilen in das Portal für B2B-Zusammenarbeit hochlädt.</span><span class="sxs-lookup"><span data-stu-id="f7aef-108">Azure Active Directory B2B collaboration allows a global admin to invite and authorize a set of external users by uploading a comma-separated values (CSV) file of no more than 2,000 lines to the B2B collaboration portal.</span></span> <span data-ttu-id="f7aef-109">Ausführlichere Informationen finden Sie unter [Azure Active Directory B2B-Zusammenarbeit](https://go.microsoft.com/fwlink/p/?linkid=826383).</span><span class="sxs-lookup"><span data-stu-id="f7aef-109">For more details, check out [Azure Active Directory B2B collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).</span></span>



<span data-ttu-id="f7aef-110">Mit Azure Active Directory B2B-Zusammenarbeit können Organisationen Richtlinien für bedingten Zugriff und mehrstufige Authentifizierung für B2B-Benutzer erzwingen.</span><span class="sxs-lookup"><span data-stu-id="f7aef-110">With Azure Active Directory B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="f7aef-111">Diese Richtlinien können auf der Mandanten-, App- oder individuellen Benutzerebene genau so erzwungen werden, wie sie für Vollzeitmitarbeiter und Mitglieder der Organisation aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="f7aef-111">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="f7aef-112">Solche Richtlinien werden bei der Ressourcenorganisation erzwungen.</span><span class="sxs-lookup"><span data-stu-id="f7aef-112">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="f7aef-113">Weitere Informationen finden Sie unter [Bedingter Zugriff für Benutzer der B2B-Zusammenarbeit](https://go.microsoft.com/fwlink/?linkid=857454).</span><span class="sxs-lookup"><span data-stu-id="f7aef-113">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="f7aef-114">Einzelne Gastbenutzer können nicht blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="f7aef-114">Individual guest users can't be blocked.</span></span>



<span data-ttu-id="f7aef-115">Gast-Benutzer aus, die Sie bereits über Azure Active Directory B2B, Office 365 Gruppen oder SharePoint Online hinzugefügt haben, sind bereit.</span><span class="sxs-lookup"><span data-stu-id="f7aef-115">Guest users you have already added via Azure Active Directory B2B, Office 365 Groups, or SharePoint Online are ready to go.</span></span> <span data-ttu-id="f7aef-116">Der Office 365-Administrator oder ein Teambesitzer kann diese Gäste zu den jeweiligen Teams hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f7aef-116">The Office 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="f7aef-117">Wenn ein Team bereits zu einer Office 365-Gruppe gehört und ein Gast zur Gruppe hinzugefügt wird, erhält der Gast Zugriff auf das Team.</span><span class="sxs-lookup"><span data-stu-id="f7aef-117">If a team is already with an Office 365 group, and a guest is added to the group, the guest will get access to the team.</span></span> <span data-ttu-id="f7aef-118">Wenn ein Gast über die Office 365-Gruppe hinzugefügt wird, erhält der Gast keine Einladungs-E-Mail. Ein Mitglied des Teams sollte den Gast daher benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="f7aef-118">Adding a guest via the Office 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="f7aef-119">Gäste unterliegen den [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347)- und [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019)-Dienstbeschränkungen.</span><span class="sxs-lookup"><span data-stu-id="f7aef-119">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>



<span data-ttu-id="f7aef-120">In Azure Active Directory oder im Office 365 Security &amp; Compliance Center können Sie das Hinzufügen von Gastbenutzern nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="f7aef-120">You can track guest additions in Azure Active Directory or the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="f7aef-121">Das Hinzufügen eines Gasts in /+/Microsoft_Teams/+/ wird als Azure AD-Gruppenverwaltungsaktivität „Mitglied zur Gruppe hinzugefügt“ überwacht und protokolliert.</span><span class="sxs-lookup"><span data-stu-id="f7aef-121">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="f7aef-122">Nähere Einzelheiten finden Sie unter [Überwachung eines B2B-Zusammenarbeitsbenutzers und Berichterstellung](https://go.microsoft.com/fwlink/p/?linkid=858884) und [Durchsuchen des Überwachungsprotokolls im Office 365 Security &amp; Compliance Center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span><span class="sxs-lookup"><span data-stu-id="f7aef-122">For more details, see  [Auditing and reporting a B2B collaboration user](https://go.microsoft.com/fwlink/p/?linkid=858884) and [Search the audit log in the Office 365 Security &amp; Compliance Center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="more-information"></a><span data-ttu-id="f7aef-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f7aef-123">More information</span></span>

[<span data-ttu-id="f7aef-124">Autorisieren des Gastzugriffs in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f7aef-124">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)</br>
[<span data-ttu-id="f7aef-125">Aktivieren Sie oder Deaktivieren der Gast Access in Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="f7aef-125">Turn on or off guest access in Microsoft Teams</span></span>](set-up-guests.md)</br>
[<span data-ttu-id="f7aef-126">Verwenden von PowerShell zum Steuern des Gastzugriffs auf ein Team</span><span class="sxs-lookup"><span data-stu-id="f7aef-126">Use PowerShell to control guest access to a team</span></span>](guest-access-powershell.md)