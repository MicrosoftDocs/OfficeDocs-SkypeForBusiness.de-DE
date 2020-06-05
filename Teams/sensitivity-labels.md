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
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Vertraulichkeits Beschriftungen in Microsoft Teams definieren und verwenden.
ms.openlocfilehash: 7f8eb7e0fa0d34ae21829a12011f094d8e9c9126
ms.sourcegitcommit: 2c23a8c5afc4a6b74c2c6d7487975a94fe99dc07
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "44562070"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="19939-103">Vertraulichkeits Bezeichnungen für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="19939-103">Sensitivity labels for Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="19939-104">Mit [Vertraulichkeits Beschriftungen](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) können Teams-Administratoren den Zugriff auf vertrauliche organisatorische Inhalte regulieren, die während der Zusammenarbeit in Teams erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="19939-104">[Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) allow Teams admins to regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="19939-105">Sie können Vertraulichkeits Bezeichnungen und die zugehörigen Richtlinien im [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)definieren.</span><span class="sxs-lookup"><span data-stu-id="19939-105">You can define sensitivity labels and their associated policies in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span></span> <span data-ttu-id="19939-106">Diese Bezeichnungen und Richtlinien werden automatisch auf Teams in Ihrer Organisation angewendet.</span><span class="sxs-lookup"><span data-stu-id="19939-106">These labels and policies are automatically applied to teams in your organization.</span></span>  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="19939-107">Was ist der Unterschied zwischen Vertraulichkeits Beschriftungen und Klassifikations Etiketten für Teams?</span><span class="sxs-lookup"><span data-stu-id="19939-107">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="19939-108">Vertraulichkeits Beschriftungen unterscheiden sich von Klassifizierungs Beschriftungen, die Sie mit PowerShell erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="19939-108">Sensitivity labels are different from classification labels that require you to create them using PowerShell.</span></span> <span data-ttu-id="19939-109">Klassifikations Beschriftungen sind Textzeichenfolgen, die einer Gruppe zugeordnet werden können, denen jedoch keine eigentlichen Richtlinien zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="19939-109">Classification labels are text strings that can be associated with a group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="19939-110">Sie verwenden Klassifizierungs Beschriftungen als Metadaten, um Richtlinien mithilfe interner Tools und Skripts manuell durchzusetzen.</span><span class="sxs-lookup"><span data-stu-id="19939-110">You use classification labels as metadata to manually enforce policies through internal tools and scripts.</span></span>

<span data-ttu-id="19939-111">Auf der anderen Seite werden die Vertraulichkeits Beschriftungen und ihre Richtlinien durch eine Kombination aus den Gruppen Plattform, Security & Compliance Center und Teams Services automatisch durchgesetzt.</span><span class="sxs-lookup"><span data-stu-id="19939-111">On the other hand, sensitivity labels and their policies are automatically enforced end-to-end through a combination of the Groups platform, Security & Compliance Center, and Teams services.</span></span> <span data-ttu-id="19939-112">Vertraulichkeits Beschriftungen bieten leistungsstarke Infrastrukturunterstützung zum Sichern vertraulicher Daten Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="19939-112">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data.</span></span>  

## <a name="create-manage-and-publish-sensitivity-labels-for-teams"></a><span data-ttu-id="19939-113">Erstellen, verwalten und Veröffentlichen von Vertraulichkeits Etiketten für Teams</span><span class="sxs-lookup"><span data-stu-id="19939-113">Create, manage, and publish sensitivity labels for Teams</span></span>

<span data-ttu-id="19939-114">Informationen zum Aktivieren, erstellen und Veröffentlichen von Vertraulichkeits Bezeichnungen für Teams finden Sie unter [Verwenden von Vertraulichkeits Bezeichnungen in Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="19939-114">For how to enable, create, and publish sensitivity labels for Teams, see [Use sensitivity labels with Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

>[!IMPORTANT]
><span data-ttu-id="19939-115">Das Erstellen, aktualisieren und Löschen von Vertraulichkeits Beschriftungen erfordert eine sorgfältige Sequenzierung bei der Veröffentlichung von Etiketten für Benutzer.</span><span class="sxs-lookup"><span data-stu-id="19939-115">Creating, updating and deleting sensitivity labels require careful sequencing with publishing labels to users.</span></span> <span data-ttu-id="19939-116">Jede Abweichung in der Sequenz kann zu beständigen Team Erstellungsfehlern für alle Benutzer führen.</span><span class="sxs-lookup"><span data-stu-id="19939-116">Any deviation in the sequence can result in persistent team creation errors for all users.</span></span> <span data-ttu-id="19939-117">Daher ist es wichtig, die folgenden Schritte auszuführen, wenn Sie <a href="#createpublishlabels">Etiketten erstellen und veröffentlichen</a>, <a href="#modifydeletelabels">veröffentlichte Etiketten ändern und löschen</a>sowie <a href="#manageerrors">Fehler bei der Teamerstellung verwalten</a>.</span><span class="sxs-lookup"><span data-stu-id="19939-117">Therefore, it's critical to do the following when you <a href="#createpublishlabels">create and publish labels</a>, <a href="#modifydeletelabels">modify and delete published labels</a>, and <a href="#manageerrors">manage team creation errors</a>.</span></span>

<span data-ttu-id="19939-118">**Erstellen und Veröffentlichen von Etiketten** <a name="createpublishlabels"> </a></span><span class="sxs-lookup"><span data-stu-id="19939-118">**Create and publish labels** <a name="createpublishlabels"> </a></span></span>

<span data-ttu-id="19939-119">Wenn eine Beschriftung im Security & Compliance Center erstellt und veröffentlicht wird, kann es bis zu 24 Stunden dauern, bis die Beschriftung auf der Benutzeroberfläche für die TEAMERSTELLUNG sichtbar wird.</span><span class="sxs-lookup"><span data-stu-id="19939-119">When a label is created and published in the Security & Compliance Center, it can take up to 24 hours for the label to become visible in the teams creation interface.</span></span> <span data-ttu-id="19939-120">Führen Sie die folgenden Schritte aus, um die Bezeichnung für alle Benutzer im Mandanten zu veröffentlichen:</span><span class="sxs-lookup"><span data-stu-id="19939-120">Use the following steps to publish the label for all users in the tenant:</span></span>
1. <span data-ttu-id="19939-121">Erstellen Sie die Beschriftung, und veröffentlichen Sie Sie für einige ausgewählte Benutzerkonten im Mandanten.</span><span class="sxs-lookup"><span data-stu-id="19939-121">Create the label and publish it for a few select user accounts in the tenant.</span></span>
2. <span data-ttu-id="19939-122">Wenn die Beschriftung veröffentlicht wird, warten Sie 24 Stunden.</span><span class="sxs-lookup"><span data-stu-id="19939-122">When the label is published, wait 24 hours.</span></span>
3. <span data-ttu-id="19939-123">Versuchen Sie nach 24 Stunden, ein Team mit dem Label zu erstellen, indem Sie eines der Benutzerkonten verwenden, die auf das Etikett zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="19939-123">After 24 hours, try to create a team with the label using one of the user accounts that have access to the label.</span></span>
4. <span data-ttu-id="19939-124">Wenn das Team erfolgreich in Schritt 3 erstellt wurde, veröffentlichen Sie die Beschriftung für die verbleibenden Benutzer im Mandanten.</span><span class="sxs-lookup"><span data-stu-id="19939-124">If the team successfully created in step 3, then go ahead and publish the label for the remaining users in the tenant.</span></span>

<span data-ttu-id="19939-125">**Ändern und Löschen von veröffentlichten Etiketten** <a name="modifydeletelabels"> </a></span><span class="sxs-lookup"><span data-stu-id="19939-125">**Modify and delete published labels** <a name="modifydeletelabels"> </a></span></span>

<span data-ttu-id="19939-126">Das Löschen oder Ändern der Bezeichnung, während Sie mit Vertraulichkeitsrichtlinien verknüpft ist, kann zu Team Erstellungsfehlern im gesamten Mandanten führen.</span><span class="sxs-lookup"><span data-stu-id="19939-126">Deleting or modifying the label while it's associated with sensitivity policies can result in team creation failures across the tenant.</span></span> <span data-ttu-id="19939-127">Daher müssen Sie vor dem Löschen oder Ändern einer Bezeichnung zunächst die Zuordnung der Bezeichnung von den zugehörigen Richtlinien aufheben.</span><span class="sxs-lookup"><span data-stu-id="19939-127">Therefore, before you delete or modify a label, you must first disassociate the label from its associated policies.</span></span> <span data-ttu-id="19939-128">Führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="19939-128">Use the following steps</span></span>  
<span data-ttu-id="19939-129">So löschen oder ändern Sie ein Etikett:</span><span class="sxs-lookup"><span data-stu-id="19939-129">to delete or modify a label:</span></span>
1. <span data-ttu-id="19939-130">Entfernen Sie die Beschriftung aus allen Richtlinien, die die Bezeichnung verwenden.</span><span class="sxs-lookup"><span data-stu-id="19939-130">Remove the label from all policies that use the label.</span></span> <span data-ttu-id="19939-131">Alternativ können Sie auch die Richtlinien selbst löschen.</span><span class="sxs-lookup"><span data-stu-id="19939-131">Alternatively, you can also delete the policies themselves.</span></span>
2. <span data-ttu-id="19939-132">Wenn die Beschriftung aus den Richtlinien entfernt wird oder die Richtlinien selbst gelöscht werden, warten Sie 48 Stunden, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="19939-132">When the label is removed from the policies or the policies themselves are deleted, wait 48 hours before proceeding further.</span></span>
3. <span data-ttu-id="19939-133">Starten Sie nach 48 Stunden die Team Erstellungs Schnittstelle, und stellen Sie sicher, dass die Beschriftung für keinen Benutzer im Mandanten mehr sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="19939-133">After 48 hours, launch the team creation interface and ensure that the label is no longer visible for any user in the tenant.</span></span>
4. <span data-ttu-id="19939-134">Nun können Sie die Beschriftung problemlos löschen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="19939-134">Now you can safely delete or modify the label.</span></span>

<span data-ttu-id="19939-135">**Verwalten von Team Erstellungsfehlern** <a name="manageerrors"> </a></span><span class="sxs-lookup"><span data-stu-id="19939-135">**Manage team creation errors** <a name="manageerrors"> </a></span></span>

<span data-ttu-id="19939-136">Wenn die TEAMERSTELLUNG zu einem beliebigen Zeitpunkt während der öffentlichen Vorschau fehlschlägt, haben Sie zwei Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="19939-136">If team creation begins to fail at any point during the public preview, you have two options:</span></span>
 - <span data-ttu-id="19939-137">Stellen Sie sicher, dass Vertraulichkeits Beschriftungen für Benutzer während der Teamerstellung nicht zwingend erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="19939-137">Ensure that sensitivity labels are not mandatory for any user during team creation.</span></span>
 - <span data-ttu-id="19939-138">Deaktivieren Sie die Vertraulichkeits Beschriftungen mithilfe der Skripts unter [Aktivieren dieser Vorschau](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview).</span><span class="sxs-lookup"><span data-stu-id="19939-138">Turn off sensitivity labels using the scripts in [Enable this preview](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview).</span></span>

<span data-ttu-id="19939-139">Beachten Sie, dass die EnableMIPLabels-Einstellung wie folgt auf "false" festgelegt werden muss:</span><span class="sxs-lookup"><span data-stu-id="19939-139">Note that the EnableMIPLabels setting must be set to false as follows:</span></span>

```console
$setting["EnableMIPLabels"] = "False"
```

## <a name="using-sensitivity-labels-with-teams"></a><span data-ttu-id="19939-140">Verwenden von Vertraulichkeits Beschriftungen in Teams</span><span class="sxs-lookup"><span data-stu-id="19939-140">Using sensitivity labels with Teams</span></span>

<span data-ttu-id="19939-141">Im folgenden finden Sie einige Beispielszenarien für die Verwendung von Vertraulichkeits Beschriftungen in Teams in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="19939-141">Here are some example scenarios of how you can use sensitivity labels with Teams in your organization.</span></span>

### <a name="privacy-setting-of-teams"></a><span data-ttu-id="19939-142">Datenschutzeinstellungen für Teams</span><span class="sxs-lookup"><span data-stu-id="19939-142">Privacy setting of teams</span></span>

<span data-ttu-id="19939-143">Sie können eine Vertraulichkeits Beschriftung erstellen, die den Benutzern beim Anwenden während der Teamerstellung ermöglicht, Teams mit einer bestimmten Einstellung für Privatsphäre (öffentlich oder privat) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="19939-143">You can create a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="19939-144">Beispielsweise erstellen Sie im Security & Compliance Center ein Etikett mit dem Namen "vertraulich", und Sie konfigurieren Teams so, dass jedes Team, das mit diesem Label erstellt wurde, ein privates Team sein muss.</span><span class="sxs-lookup"><span data-stu-id="19939-144">For example, you create a label named “Confidential” in the Security & Compliance Center and you configure Teams so that any team that's created with this label must be a private team.</span></span> <span data-ttu-id="19939-145">Wenn ein Benutzer ein neues Team erstellt und das **vertrauliche** Etikett auswählt, ist die einzige Datenschutzoption, die dem Benutzer zur Verfügung steht, **Privat**.</span><span class="sxs-lookup"><span data-stu-id="19939-145">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="19939-146">Andere Datenschutzoptionen wie Public und org-Wide sind für den Benutzer deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="19939-146">Other privacy options such as Public and Org-wide are disabled for the user.</span></span>

![Screenshot der vertraulichen Vertraulichkeits Kennzeichnung](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="19939-148">Auch wenn der Benutzer beim Erstellen eines neuen Teams " **Allgemein** " auswählt, kann er nur öffentliche oder organisationsweite Teams erstellen.</span><span class="sxs-lookup"><span data-stu-id="19939-148">Similarly, if the user selects **General** when they create a new team, they can only create public or org-wide teams.</span></span>

![Screenshot der allgemeinen Vertraulichkeits Beschriftung](media/sensitivity-labels-general-example.png)

<span data-ttu-id="19939-150">Wenn das Team erstellt wird, wird die Vertraulichkeits Bezeichnung in der oberen rechten Ecke der Kanäle im Team angezeigt.</span><span class="sxs-lookup"><span data-stu-id="19939-150">When the team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span>

![Screenshot der Vertraulichkeits Beschriftung im Team Kanal](media/sensitivity-labels-channel.png)

<span data-ttu-id="19939-152">Ein Teambesitzer kann die Vertraulichkeits Beschriftung und die Datenschutzeinstellung des Teams jederzeit ändern, indem er zum Team wechselt und dann auf **Team bearbeiten**klickt.</span><span class="sxs-lookup"><span data-stu-id="19939-152">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then clicking **Edit team**.</span></span>

![Screenshot der Vertraulichkeits Beschriftung im Team Kanal](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a><span data-ttu-id="19939-154">Gastzugriff auf Teams</span><span class="sxs-lookup"><span data-stu-id="19939-154">Guest access to teams</span></span>

<span data-ttu-id="19939-155">Sie können angeben, ob ein Team, das mit einer bestimmten Bezeichnung erstellt wurde, Gastzugriff ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="19939-155">You can specify whether a team created with a specific label allows guest access.</span></span> <span data-ttu-id="19939-156">Teams, die mit einer Beschriftung erstellt wurden, die keinen Gastzugriff zulässt, stehen nur Benutzern in Ihrer Organisation zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="19939-156">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="19939-157">Personen außerhalb Ihrer Organisation können dem Team nicht hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="19939-157">People outside your organization can't be added to the team.</span></span>

## <a name="known-issues"></a><span data-ttu-id="19939-158">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="19939-158">Known issues</span></span>

<span data-ttu-id="19939-159">**Unterstützung für Vertraulichkeits Beschriftungen im Microsoft Teams Admin Center**</span><span class="sxs-lookup"><span data-stu-id="19939-159">**Support for sensitivity labels in the Microsoft Teams admin center**</span></span>

<span data-ttu-id="19939-160">Derzeit werden Vertraulichkeits Beschriftungen im Microsoft Teams Admin Center nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="19939-160">Currently, sensitivity labels are not supported in the Microsoft Teams admin center.</span></span> <span data-ttu-id="19939-161">Wenn Sie Vertraulichkeits Beschriftungen verwenden, können Sie beim Erstellen oder Bearbeiten eines Teams keine Vertraulichkeits Beschriftungen einstellen.</span><span class="sxs-lookup"><span data-stu-id="19939-161">If you use sensitivity labels, you won't be able to set sensitivity labels when you create or edit a team.</span></span> <span data-ttu-id="19939-162">Vertraulichkeits Beschriftungen sind auch in den teameigenschaften nicht sichtbar und werden in der Spalte **Klassifizierung** des Microsoft Teams admin Centers nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="19939-162">Sensitivity labels are also not visible in team properties and won't be visible in the **Classification** column in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="19939-163">**Unterstützung für Vertraulichkeits Beschriftungen in Teams-Diagramm-APIs, PowerShell-Cmdlets und-Vorlagen**</span><span class="sxs-lookup"><span data-stu-id="19939-163">**Support for sensitivity labels in Teams Graph APIs, Powershell cmdlets and templates**</span></span>

<span data-ttu-id="19939-164">Derzeit können Benutzer keine Vertraulichkeits Bezeichnungen für Teams anwenden, die direkt über Diagramm-APIs, PowerShell-Cmdlets und Vorlagen erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="19939-164">Currently, users won't be able to apply sensitivity labels on teams that are created directly through Graph APIs, Powershell cmdlets, and templates.</span></span>

<span data-ttu-id="19939-165">**Unterstützung für Vertraulichkeits Beschriftungen in Teams edu-SKUs**</span><span class="sxs-lookup"><span data-stu-id="19939-165">**Support for sensitivity labels in Teams EDU SKUs**</span></span>

<span data-ttu-id="19939-166">Vertraulichkeits Beschriftungen werden derzeit für Kunden, die Team Education-SKUs verwenden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="19939-166">Sensitivity labels are currently unsupported for customers using Teams Education SKUs.</span></span>

<span data-ttu-id="19939-167">**Bearbeiten von Vertraulichkeits Beschriftungen direkt in einer SharePoint-Websitesammlung für private Kanäle**</span><span class="sxs-lookup"><span data-stu-id="19939-167">**Editing sensitivity labels directly on a SharePoint site collection for private channels**</span></span>

<span data-ttu-id="19939-168">Private Kanäle, die in einem Team erstellt werden, erben die Vertraulichkeits Bezeichnung, die in einem Team angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="19939-168">Private channels that are created in a team inherit the sensitivity label which was applied on a team.</span></span> <span data-ttu-id="19939-169">Darüber hinaus wird dieselbe Bezeichnung automatisch für die SharePoint-Websitesammlung für den privaten Kanal übernommen.</span><span class="sxs-lookup"><span data-stu-id="19939-169">Furthermore, the same label is automatically applied on the SharePoint site collection for the private channel.</span></span>

<span data-ttu-id="19939-170">Wenn ein Benutzer die Vertraulichkeits Beschriftung auf einer SharePoint-Websitesammlung für einen privaten Kanal direkt aktualisiert, wird diese Bezeichnung nicht im Team-Client aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="19939-170">If a user directly updates the sensitivity label on a SharePoint site collection for a private channel, that label isn't updated in the Teams client.</span></span> <span data-ttu-id="19939-171">In diesem Szenario wird den Benutzern weiterhin die auf ein Team angewendete Vertraulichkeits Bezeichnung in der Kopfzeile privater Kanal angezeigt.</span><span class="sxs-lookup"><span data-stu-id="19939-171">In this scenario, users will continue to see the sensitivity label applied on a team in the private channel header.</span></span>

<span data-ttu-id="19939-172">**Ausbreitungs Zeiten für Änderungen, die auf Vertraulichkeits Beschriftungen außerhalb der Teams-App angewendet werden**</span><span class="sxs-lookup"><span data-stu-id="19939-172">**Propagation times for changes applied to sensitivity labels outside the Teams app**</span></span>

<span data-ttu-id="19939-173">Änderungen an Vertraulichkeits Beschriftungen außerhalb der Teams-App können bis zu 24 Stunden dauern, bis Sie in der Teams-App wiedergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="19939-173">Changes made to sensitivity labels outside the Teams app can take up to 24 hours to reflect in the Teams app.</span></span> <span data-ttu-id="19939-174">Dies gilt für alle Änderungen, die vorgenommen wurden, um Bezeichnungen für einen Mandanten zu aktivieren oder zu deaktivieren, Änderungen an Etikettennamen, Einstellungen und Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="19939-174">This applies to any changes made to enable or disable labels for a tenant, changes to label names, settings, and policies.</span></span>

<span data-ttu-id="19939-175">Darüber hinaus kann es bis zu 24 Stunden dauern, bis Änderungen an einer Bezeichnung, die direkt an eine Gruppe oder SharePoint-Websitesammlung, die das Team zurückgibt, an die Teams-App weitergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="19939-175">Additionally, any changes to a label made directly to a group or SharePoint site collection that backs the team can take up to 24 hours to propagate to the Teams app.</span></span>
