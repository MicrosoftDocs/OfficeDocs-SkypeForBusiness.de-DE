---
title: Vertraulichkeits Bezeichnungen für Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: abgupta
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Vertraulichkeits Beschriftungen in Microsoft Teams definieren und verwenden.
ms.openlocfilehash: 3a0c40a51653a525587a0662949a3fdd4e63faf4
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2019
ms.locfileid: "38653581"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="daffd-103">Vertraulichkeits Bezeichnungen für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="daffd-103">Sensitivity labels for Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="daffd-104">Mit [Vertraulichkeits Beschriftungen](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) können Teams-Administratoren den Zugriff auf vertrauliche organisatorische Inhalte regulieren, die während der Zusammenarbeit in Teams erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="daffd-104">[Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) allow Teams admins to regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="daffd-105">Sie können Vertraulichkeits Bezeichnungen und die zugehörigen Richtlinien im [Security #a0 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)definieren.</span><span class="sxs-lookup"><span data-stu-id="daffd-105">You can define sensitivity labels and their associated policies in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span></span> <span data-ttu-id="daffd-106">Diese Bezeichnungen und Richtlinien werden automatisch auf Teams in Ihrer Organisation angewendet.</span><span class="sxs-lookup"><span data-stu-id="daffd-106">These labels and policies are automatically applied to teams in your organization.</span></span>  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="daffd-107">Was ist der Unterschied zwischen Vertraulichkeits Beschriftungen und Klassifikations Etiketten für Teams?</span><span class="sxs-lookup"><span data-stu-id="daffd-107">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="daffd-108">Vertraulichkeits Beschriftungen unterscheiden sich von Klassifizierungs Beschriftungen, die Sie mit PowerShell erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="daffd-108">Sensitivity labels are different from classification labels that require you to create them using PowerShell.</span></span> <span data-ttu-id="daffd-109">Klassifikations Beschriftungen sind Textzeichenfolgen, die einer Gruppe zugeordnet werden können, denen jedoch keine eigentlichen Richtlinien zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="daffd-109">Classification labels are text strings that can be associated with a group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="daffd-110">Sie verwenden Klassifizierungs Beschriftungen als Metadaten, um Richtlinien mithilfe interner Tools und Skripts manuell durchzusetzen.</span><span class="sxs-lookup"><span data-stu-id="daffd-110">You use classification labels as metadata to manually enforce policies through internal tools and scripts.</span></span>

<span data-ttu-id="daffd-111">Auf der anderen Seite werden die Vertraulichkeits Beschriftungen und ihre Richtlinien durch eine Kombination aus den Gruppen Plattform, Security #a0 Compliance Center und Teams Services automatisch durchgesetzt.</span><span class="sxs-lookup"><span data-stu-id="daffd-111">On the other hand, sensitivity labels and their policies are automatically enforced end-to-end through a combination of the Groups platform, Security & Compliance Center, and Teams services.</span></span> <span data-ttu-id="daffd-112">Vertraulichkeits Beschriftungen bieten leistungsstarke Infrastrukturunterstützung zum Sichern vertraulicher Daten Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="daffd-112">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data.</span></span>  

## <a name="create-and-publish-sensitivity-labels-for-teams"></a><span data-ttu-id="daffd-113">Erstellen und Veröffentlichen von Vertraulichkeits Beschriftungen für Teams</span><span class="sxs-lookup"><span data-stu-id="daffd-113">Create and publish sensitivity labels for Teams</span></span>

<span data-ttu-id="daffd-114">Informationen zum Aktivieren, erstellen und Veröffentlichen von Vertraulichkeits Bezeichnungen für Teams finden Sie unter [Verwenden von Vertraulichkeits Bezeichnungen in Microsoft Teams, Office 365-Gruppen und SharePoint-Websites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="daffd-114">For how to enable, create, and publish sensitivity labels for Teams, see [Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

## <a name="using-sensitivity-labels-with-teams"></a><span data-ttu-id="daffd-115">Verwenden von Vertraulichkeits Beschriftungen in Teams</span><span class="sxs-lookup"><span data-stu-id="daffd-115">Using sensitivity labels with Teams</span></span>

<span data-ttu-id="daffd-116">Im folgenden finden Sie einige Beispielszenarien für die Verwendung von Vertraulichkeits Beschriftungen in Teams in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="daffd-116">Here are some example scenarios of how you can use sensitivity labels with Teams in your organization.</span></span>

### <a name="privacy-setting-of-teams"></a><span data-ttu-id="daffd-117">Datenschutzeinstellungen für Teams</span><span class="sxs-lookup"><span data-stu-id="daffd-117">Privacy setting of teams</span></span>

<span data-ttu-id="daffd-118">Sie können eine Vertraulichkeits Beschriftung erstellen, die den Benutzern beim Anwenden während der Teamerstellung ermöglicht, Teams mit einer bestimmten Einstellung für Privatsphäre (öffentlich oder privat) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="daffd-118">You can create a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="daffd-119">Beispielsweise erstellen Sie im Security #a0 Compliance Center ein Etikett mit dem Namen "vertraulich", und Sie konfigurieren Teams so, dass jedes Team, das mit diesem Label erstellt wurde, ein privates Team sein muss.</span><span class="sxs-lookup"><span data-stu-id="daffd-119">For example, you create a label named “Confidential” in the Security & Compliance Center and you configure Teams so that any team that's created with this label must be a private team.</span></span> <span data-ttu-id="daffd-120">Wenn ein Benutzer ein neues Team erstellt und das **vertrauliche** Etikett auswählt, ist die einzige Datenschutzoption, die dem Benutzer zur Verfügung steht, **Privat**.</span><span class="sxs-lookup"><span data-stu-id="daffd-120">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="daffd-121">Andere Datenschutzoptionen wie Public und org-Wide sind für den Benutzer deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="daffd-121">Other privacy options such as Public and Org-wide are disabled for the user.</span></span>

![Screenshot der vertraulichen Vertraulichkeits Kennzeichnung](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="daffd-123">Auch wenn der Benutzer beim Erstellen eines neuen Teams " **Allgemein** " auswählt, kann er nur öffentliche oder organisationsweite Teams erstellen.</span><span class="sxs-lookup"><span data-stu-id="daffd-123">Similarly, if the user selects **General** when they create a new team, they can only create public or org-wide teams.</span></span>

![Screenshot der allgemeinen Vertraulichkeits Beschriftung](media/sensitivity-labels-general-example.png)

<span data-ttu-id="daffd-125">Wenn das Team erstellt wird, wird die Vertraulichkeits Bezeichnung in der oberen rechten Ecke der Kanäle im Team angezeigt.</span><span class="sxs-lookup"><span data-stu-id="daffd-125">When the team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span>

![Screenshot der Vertraulichkeits Beschriftung im Team Kanal](media/sensitivity-labels-channel.png)

<span data-ttu-id="daffd-127">Ein Teambesitzer kann die Vertraulichkeits Beschriftung und die Datenschutzeinstellung des Teams jederzeit ändern, indem er zum Team wechselt und dann auf **Team bearbeiten**klickt.</span><span class="sxs-lookup"><span data-stu-id="daffd-127">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then clicking **Edit team**.</span></span>

![Screenshot der Vertraulichkeits Beschriftung im Team Kanal](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a><span data-ttu-id="daffd-129">Gastzugriff auf Teams</span><span class="sxs-lookup"><span data-stu-id="daffd-129">Guest access to teams</span></span>

<span data-ttu-id="daffd-130">Sie können angeben, ob ein Team, das mit einer bestimmten Bezeichnung erstellt wurde, Gastzugriff ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="daffd-130">You can specify whether a team created with a specific label allows guest access.</span></span> <span data-ttu-id="daffd-131">Teams, die mit einer Beschriftung erstellt wurden, die keinen Gastzugriff zulässt, stehen nur Benutzern in Ihrer Organisation zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="daffd-131">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="daffd-132">Personen außerhalb Ihrer Organisation können dem Team nicht hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="daffd-132">People outside your organization can't be added to the team.</span></span>

## <a name="known-issues"></a><span data-ttu-id="daffd-133">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="daffd-133">Known issues</span></span>

<span data-ttu-id="daffd-134">**Unterstützung für Vertraulichkeits Beschriftungen im Microsoft Teams Admin Center**</span><span class="sxs-lookup"><span data-stu-id="daffd-134">**Support for sensitivity labels in the Microsoft Teams admin center**</span></span>

<span data-ttu-id="daffd-135">Derzeit werden Vertraulichkeits Beschriftungen im Microsoft Teams Admin Center nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="daffd-135">Currently, sensitivity labels are not supported in the Microsoft Teams admin center.</span></span> <span data-ttu-id="daffd-136">Wenn Sie Vertraulichkeits Beschriftungen verwenden, können Sie beim Erstellen oder Bearbeiten eines Teams keine Vertraulichkeits Beschriftungen einstellen.</span><span class="sxs-lookup"><span data-stu-id="daffd-136">If you use sensitivity labels, you won't be able to set sensitivity labels when you create or edit a team.</span></span> <span data-ttu-id="daffd-137">Vertraulichkeits Beschriftungen sind auch in den teameigenschaften nicht sichtbar und werden in der Spalte **Klassifizierung** des Microsoft Teams admin Centers nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="daffd-137">Sensitivity labels are also not visible in team properties and won't be visible in the **Classification** column in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="daffd-138">**Unterstützung für Vertraulichkeits Beschriftungen in Teams-Diagramm-APIs, PowerShell-Cmdlets und-Vorlagen**</span><span class="sxs-lookup"><span data-stu-id="daffd-138">**Support for sensitivity labels in Teams Graph APIs, Powershell cmdlets and templates**</span></span>

<span data-ttu-id="daffd-139">Derzeit können Benutzer keine Vertraulichkeits Bezeichnungen für Teams anwenden, die direkt über Diagramm-APIs, PowerShell-Cmdlets und Vorlagen erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="daffd-139">Currently, users won't be able to apply sensitivity labels on teams that are created directly through Graph APIs, Powershell cmdlets, and templates.</span></span>

<span data-ttu-id="daffd-140">**Bearbeiten von Vertraulichkeits Beschriftungen direkt in einer SharePoint-Websitesammlung für private Kanäle**</span><span class="sxs-lookup"><span data-stu-id="daffd-140">**Editing sensitivity labels directly on a SharePoint site collection for private channels**</span></span>

<span data-ttu-id="daffd-141">Private Kanäle, die in einem Team erstellt werden, erben die Vertraulichkeits Bezeichnung, die in einem Team angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="daffd-141">Private channels that are created in a team inherit the sensitivity label which was applied on a team.</span></span> <span data-ttu-id="daffd-142">Darüber hinaus wird dieselbe Bezeichnung automatisch für die SharePoint-Websitesammlung für den privaten Kanal übernommen.</span><span class="sxs-lookup"><span data-stu-id="daffd-142">Furthermore, the same label is automatically applied on the SharePoint site collection for the private channel.</span></span>

<span data-ttu-id="daffd-143">Wenn ein Benutzer die Vertraulichkeits Beschriftung auf einer SharePoint-Websitesammlung für einen privaten Kanal direkt aktualisiert, wird diese Bezeichnung nicht im Team-Client aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="daffd-143">If a user directly updates the sensitivity label on a SharePoint site collection for a private channel, that label isn't updated in the Teams client.</span></span> <span data-ttu-id="daffd-144">In diesem Szenario wird den Benutzern weiterhin die auf ein Team angewendete Vertraulichkeits Bezeichnung in der Kopfzeile privater Kanal angezeigt.</span><span class="sxs-lookup"><span data-stu-id="daffd-144">In this scenario, users will continue to see the sensitivity label applied on a team in the private channel header.</span></span>

<span data-ttu-id="daffd-145">**Ausbreitungs Zeiten für Änderungen, die auf Vertraulichkeits Beschriftungen außerhalb der Teams-App angewendet werden**</span><span class="sxs-lookup"><span data-stu-id="daffd-145">**Propagation times for changes applied to sensitivity labels outside the Teams app**</span></span>

<span data-ttu-id="daffd-146">Änderungen an Vertraulichkeits Beschriftungen außerhalb der Teams-App können bis zu 24 Stunden dauern, bis Sie in der Teams-App wiedergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="daffd-146">Changes made to sensitivity labels outside the Teams app can take up to 24 hours to reflect in the Teams app.</span></span> <span data-ttu-id="daffd-147">Dies gilt für alle Änderungen, die vorgenommen wurden, um Bezeichnungen für einen Mandanten zu aktivieren oder zu deaktivieren, Änderungen an Etikettennamen, Einstellungen und Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="daffd-147">This applies to any changes made to enable or disable labels for a tenant, changes to label names, settings, and policies.</span></span>

<span data-ttu-id="daffd-148">Darüber hinaus kann es bis zu 24 Stunden dauern, bis Änderungen an einer Bezeichnung, die direkt an eine Gruppe oder SharePoint-Websitesammlung, die das Team zurückgibt, an die Teams-App weitergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="daffd-148">Additionally, any changes to a label made directly to a group or SharePoint site collection that backs the team can take up to 24 hours to propagate to the Teams app.</span></span>