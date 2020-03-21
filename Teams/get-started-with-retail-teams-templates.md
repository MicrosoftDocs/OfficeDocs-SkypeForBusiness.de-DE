---
title: Erste Schritte mit Microsoft Teams-Vorlagen im Einzelhandel
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie mithilfe von Teams-Vorlagen Teamstrukturen erstellen, die für den Einzelhandel entwickelt wurden.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: ec16f919bad5ed696741664836aa3d7127837c5a
ms.sourcegitcommit: 92a278c0145798266ecbe052e645b2259bcbd62d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42892365"
---
# <a name="get-started-with-teams-templates-in-retail"></a><span data-ttu-id="497b3-103">Erste Schritte mit Microsoft Teams-Vorlagen im Einzelhandel</span><span class="sxs-lookup"><span data-stu-id="497b3-103">Get started with Teams templates in retail</span></span> 

<span data-ttu-id="497b3-104">Mithilfe von Vorlagen für Teams können Sie Teams schnell und einfach erstellen, indem Sie eine vordefinierte Vorlage mit Einstellungen, Kanälen und vorinstallierten apps bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="497b3-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="497b3-105">In den Teams-Vorlagen gibt es vorgefertigte Definitionen von Teamstrukturen, die für die Anforderungen des Einzelhändlers entwickelt wurden.</span><span class="sxs-lookup"><span data-stu-id="497b3-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="497b3-106">Mithilfe von Teams-Vorlagen können Sie schnell die Typen von Teams erstellen, die für Einzelhändler gut geeignet sind, und Sie in Ihrer Organisation bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="497b3-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="497b3-107">Sie können die Teams-Vorlagen auch erweitern, um Teams zu erstellen, die auf Ihre spezifischen organisatorischen Anforderungen zugeschnitten sind.</span><span class="sxs-lookup"><span data-stu-id="497b3-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="497b3-108">In diesem Artikel werden die einzelnen Teams-Vorlagen vorgestellt, und es wird empfohlen, diese zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="497b3-108">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="497b3-109">Dieser Artikel ist für Sie zuständig, wenn Sie für die Planung, Bereitstellung und Verwaltung mehrerer Teams in ihrer Einzelhandelsorganisation verantwortlich sind.</span><span class="sxs-lookup"><span data-stu-id="497b3-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="497b3-110">Wir gehen davon aus, dass Sie bereits einen Team Dienst in Ihrer Organisation bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="497b3-110">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="497b3-111">Wenn Sie noch keine Teams ausgearbeitet haben, lesen Sie zunächst die [Anleitung zum Rollout von Microsoft Teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="497b3-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="497b3-112">Weitere Informationen zu Teamvorlagen im Allgemeinen finden Sie unter [Erste Schritte mit Microsoft Teams-Vorlagen](get-started-with-teams-templates.md).</span><span class="sxs-lookup"><span data-stu-id="497b3-112">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="store-template"></a><span data-ttu-id="497b3-113">Store-Vorlage</span><span class="sxs-lookup"><span data-stu-id="497b3-113">Store template</span></span>

<span data-ttu-id="497b3-114">Die Store-Vorlage eignet sich hervorragend zum Erstellen eines Teams zur Darstellung eines einzelnen Einzelhandels Standorts.</span><span class="sxs-lookup"><span data-stu-id="497b3-114">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="497b3-115">Mithilfe der Store-Vorlage können Sie ein Team für jeden Einzelhändler Standort in Ihrer Organisation erstellen.</span><span class="sxs-lookup"><span data-stu-id="497b3-115">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="497b3-116">Basis Vorlagentyp</span><span class="sxs-lookup"><span data-stu-id="497b3-116">Base template type</span></span> | <span data-ttu-id="497b3-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="497b3-117">baseTemplateId</span></span> | <span data-ttu-id="497b3-118">Eigenschaften, die mit dieser Basisvorlage geliefert werden</span><span class="sxs-lookup"><span data-stu-id="497b3-118">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="497b3-119">Retail</span><span class="sxs-lookup"><span data-stu-id="497b3-119">Retail -</span></span> <br><span data-ttu-id="497b3-120">Store</span><span class="sxs-lookup"><span data-stu-id="497b3-120">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="497b3-121">Kanäle</span><span class="sxs-lookup"><span data-stu-id="497b3-121">Channels</span></span> <ul><li><span data-ttu-id="497b3-122">Verschiebt die Übergabe\*</span><span class="sxs-lookup"><span data-stu-id="497b3-122">Shifts handoff\*</span></span></li><li><span data-ttu-id="497b3-123">Lerntools\*</span><span class="sxs-lookup"><span data-stu-id="497b3-123">Learning\*</span></span></li></ul><span data-ttu-id="497b3-124">\*Automatisch bevorzugte Kanäle</span><span class="sxs-lookup"><span data-stu-id="497b3-124">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="497b3-125">Team Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="497b3-125">Team properties</span></span> <ul><li><span data-ttu-id="497b3-126">Team Sichtbarkeit auf "öffentlich" eingestellt</span><span class="sxs-lookup"><span data-stu-id="497b3-126">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="497b3-127">Mitglieder Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="497b3-127">Member permissions</span></span> <ul><li><span data-ttu-id="497b3-128">Kanäle können nicht erstellt/aktualisiert/gelöscht werden</span><span class="sxs-lookup"><span data-stu-id="497b3-128">Cannot create/update/delete channels</span></span> </li><li><span data-ttu-id="497b3-129">Apps können nicht hinzugefügt/entfernt werden</span><span class="sxs-lookup"><span data-stu-id="497b3-129">Cannot add/remove apps</span></span> </li><li><span data-ttu-id="497b3-130">Registerkarten können nicht erstellt/aktualisiert/entfernt werden</span><span class="sxs-lookup"><span data-stu-id="497b3-130">Cannot create/update/remove tabs</span></span></li><li><span data-ttu-id="497b3-131">Connectors können nicht erstellt/aktualisiert/entfernt werden</span><span class="sxs-lookup"><span data-stu-id="497b3-131">Cannot create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="497b3-132">Empfohlene Vorgehensweisen zum Anpassen der Store-Vorlage für Ihre Organisation:</span><span class="sxs-lookup"><span data-stu-id="497b3-132">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="497b3-133">Wenn Ihre Organisation über Abteilungen innerhalb der einzelnen Stores verfügt, fügen Sie für jede Abteilung einen Kanal hinzu.</span><span class="sxs-lookup"><span data-stu-id="497b3-133">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="497b3-134">Dadurch wird die Kommunikation und Zusammenarbeit innerhalb der Abteilung vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="497b3-134">This will facilitate communication and collaboration within the department.</span></span>

- <span data-ttu-id="497b3-135">Wenn Ihre Organisation über interne Websites verfügt (beispielsweise eine SharePoint-Website), sollten Sie Sie als Registerkarten im entsprechenden Teamkanal anheften.</span><span class="sxs-lookup"><span data-stu-id="497b3-135">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="497b3-136">Anweisungen hierzu finden Sie unter [Erste Schritte mit Microsoft Teams-Vorlagen](get-started-with-teams-templates.md) .</span><span class="sxs-lookup"><span data-stu-id="497b3-136">Refer to [Get started with Teams templates](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="manager-collaboration-template"></a><span data-ttu-id="497b3-137">Manager-Zusammenarbeits Vorlage</span><span class="sxs-lookup"><span data-stu-id="497b3-137">Manager Collaboration template</span></span>

<span data-ttu-id="497b3-138">Die Vorlage "Manager-Zusammenarbeit" ist eine weitere der Teamvorlagen, die für Einzelhändler benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="497b3-138">The Manager Collaboration template is another one of the Teams templates designed around retailer needs.</span></span> <span data-ttu-id="497b3-139">Die Vorlage "Manager-Zusammenarbeit" eignet sich hervorragend zum Erstellen eines Teams für eine Gruppe von Managern für die Zusammenarbeit in verschiedenen Geschäften/Regionen usw. Wenn Ihre Organisation beispielsweise Regionen hat, können Sie ein Manager-Zusammenarbeits Team für die Region Kalifornien erstellen und alle Filialmanager in dieser Region sowie den regionalen Manager für diese Region einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="497b3-139">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="497b3-140">Basis Vorlagentyp</span><span class="sxs-lookup"><span data-stu-id="497b3-140">Base template type</span></span> | <span data-ttu-id="497b3-141">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="497b3-141">baseTemplateId</span></span> | <span data-ttu-id="497b3-142">Eigenschaften, die mit dieser Basisvorlage geliefert werden</span><span class="sxs-lookup"><span data-stu-id="497b3-142">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="497b3-143">Retail</span><span class="sxs-lookup"><span data-stu-id="497b3-143">Retail -</span></span> <br><span data-ttu-id="497b3-144">Store</span><span class="sxs-lookup"><span data-stu-id="497b3-144">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="497b3-145">Kanäle</span><span class="sxs-lookup"><span data-stu-id="497b3-145">Channels</span></span> <ul><li><span data-ttu-id="497b3-146">Vorgänge\*</span><span class="sxs-lookup"><span data-stu-id="497b3-146">Operations\*</span></span></li><li><span data-ttu-id="497b3-147">Lerntools\*</span><span class="sxs-lookup"><span data-stu-id="497b3-147">Learning\*</span></span></li></ul><span data-ttu-id="497b3-148">\*Automatisch bevorzugte Kanäle</span><span class="sxs-lookup"><span data-stu-id="497b3-148">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="497b3-149">Team Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="497b3-149">Team properties</span></span> <ul><li><span data-ttu-id="497b3-150">Team Sichtbarkeit auf "Privat" gesetzt</span><span class="sxs-lookup"><span data-stu-id="497b3-150">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="497b3-151">Mitglieder Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="497b3-151">Member permissions</span></span> <ul><li><span data-ttu-id="497b3-152">Kann Kanäle erstellen/aktualisieren/löschen</span><span class="sxs-lookup"><span data-stu-id="497b3-152">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="497b3-153">Kann apps hinzufügen/entfernen</span><span class="sxs-lookup"><span data-stu-id="497b3-153">Can add/remove apps</span></span> </li><li><span data-ttu-id="497b3-154">Kann Registerkarten erstellen/aktualisieren/entfernen</span><span class="sxs-lookup"><span data-stu-id="497b3-154">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="497b3-155">Kann Connectors erstellen/aktualisieren/entfernen</span><span class="sxs-lookup"><span data-stu-id="497b3-155">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="497b3-156">Empfohlene Vorgehensweisen zum Anpassen der Vorlage für die Manager-Zusammenarbeit für Ihre Organisation:</span><span class="sxs-lookup"><span data-stu-id="497b3-156">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="497b3-157">Wenn Ihre Organisation über interne Websites (beispielsweise eine SharePoint-Website) verfügt, die für Manager relevant sind, sollten Sie Sie als Registerkarten in einem relevanten Teamkanal fixieren ( [hier](get-started-with-teams-templates.md) finden Sie Anweisungen dazu unter Dokumentation).</span><span class="sxs-lookup"><span data-stu-id="497b3-157">If your organization has any internal websites (for example, a SharePoint site) that are relevant for managers, consider pinning them as tabs in a relevant team channel (refer to documentation [here](get-started-with-teams-templates.md) for instructions).</span></span>

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="497b3-158">Verwenden von Vorlagen für Erstanbieter</span><span class="sxs-lookup"><span data-stu-id="497b3-158">How to use first party templates</span></span>

<span data-ttu-id="497b3-159">Wenn Sie diese Vorlagen verwenden möchten, ändern Sie einfach die Eigenschaft "Template@odata. Bind" im Anforderungstext von "Standard" in das obige TemplateIDs.</span><span class="sxs-lookup"><span data-stu-id="497b3-159">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="497b3-160">Weitere Informationen zum Bereitstellen von Teams-Vorlagen finden Sie im Microsoft Graph-Artikel zum [Erstellen eines Teams](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="497b3-160">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="497b3-161">Die Kanäle in der Vorlage werden auf der RegisterkarteAllgemein automatisch erstellt.</span><span class="sxs-lookup"><span data-stu-id="497b3-161">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-store-template-extension-script"></a><span data-ttu-id="497b3-162">Beispiel: Vorlagen Erweiterungs Skript speichern</span><span class="sxs-lookup"><span data-stu-id="497b3-162">Example: Store template extension script</span></span>

``` PowerShell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('retailStore')",
  "DisplayName": "Contoso Store",
  "Description": "Team for all staff in Contoso Store",
  "Channels": [
    {
      "displayName": "Additional store channel",
      "IsFavoriteByDefault": false
    }
  ]
}
```
