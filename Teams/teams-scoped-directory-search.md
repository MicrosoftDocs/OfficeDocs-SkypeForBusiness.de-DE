---
title: Verwenden der Verzeichnissuche in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Hier erfahren Sie, wie Sie die Verzeichnissuche in Microsoft Teams verwenden, um angepasste Ansichten des Verzeichnisses bereitzustellen.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6b06e675e93dd022847fc7af202045c3ecdebe63
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341769"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="d069e-103">Verwenden der Verzeichnissuche in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d069e-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="d069e-104">Mithilfe der Verzeichnissuche in Microsoft Teams können Organisationen virtuelle Grenzen erstellen, die Steuern, wie Benutzer andere Benutzer in Ihrer Organisation finden und mit Ihnen kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="d069e-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="d069e-105">In Microsoft Teams können Organisationen ihren Benutzern benutzerdefinierte Ansichten des Verzeichnisses zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="d069e-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="d069e-106">Microsoft Teams verwendet [Richtlinien für Informationsbarrieren](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) , um diese benutzerdefinierten Ansichten zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="d069e-106">Microsoft Teams uses [Information Barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) to support these custom views.</span></span> <span data-ttu-id="d069e-107">Sobald die Richtlinien aktiviert sind, werden die Ergebnisse, die von Suchvorgängen nach anderen Benutzern zurückgegeben wurden (beispielsweise zum Initiieren eines Chats oder zum Hinzufügen von Mitgliedern zu einem Team), entsprechend den konfigurierten Richtlinien zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d069e-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="d069e-108">Benutzer können keine Teams durchsuchen oder entdecken, wenn die Bereichssuche aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d069e-108">Users will not be able to search or discover teams when scoped search is in effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="d069e-109">In Exchange-Hybrid Umgebungen funktioniert dieses Feature nur mit Exchange Online-Postfächern und nicht mit lokalen Postfächern.</span><span class="sxs-lookup"><span data-stu-id="d069e-109">In Exchange hybrid environments, this feature only works with Exchange Online mailboxes, and not with on-premises mailboxes.</span></span>

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="d069e-110">Wann sollten Sie Bereichs Verzeichnis suchen verwenden?</span><span class="sxs-lookup"><span data-stu-id="d069e-110">When should you use scoped directory searches?</span></span>

<span data-ttu-id="d069e-111">Szenarien, die von umfangreicheren Verzeichnis suchen profitieren, ähneln den Szenarien für adressbuchrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="d069e-111">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="d069e-112">So können Sie beispielsweise die bereichsbezogene Verzeichnissuche in den folgenden Situationen verwenden:</span><span class="sxs-lookup"><span data-stu-id="d069e-112">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="d069e-113">Der Mandant Ihrer Organisation enthält mehrere Unternehmen, die voneinander getrennt sein sollen.</span><span class="sxs-lookup"><span data-stu-id="d069e-113">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="d069e-114">Ihre Bildungseinrichtung möchte Chats zwischen dem Lehrpersonal und den Kursteilnehmern begrenzen.</span><span class="sxs-lookup"><span data-stu-id="d069e-114">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="d069e-115">Informationen zum Verwenden von adressbuchrichtlinien finden Sie [unter Richtlinien für Informationsbarrieren in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/information-barriers).</span><span class="sxs-lookup"><span data-stu-id="d069e-115">To learn how to use address book policies, read [Information Barrier policies in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/information-barriers).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d069e-116">Adressbuchrichtlinien bieten nur eine virtuelle Trennung von Benutzern aus der Verzeichnis Perspektive.</span><span class="sxs-lookup"><span data-stu-id="d069e-116">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="d069e-117">Benutzer können die Kommunikation mit anderen Personen weiterhin initiieren, indem Sie vollständige e-Mail-Adressen angeben.</span><span class="sxs-lookup"><span data-stu-id="d069e-117">Users can still initiate communications with others by providing complete email addresses.</span></span> <span data-ttu-id="d069e-118">Beachten Sie auch, dass alle Benutzerdaten, die bereits vor der Erzwingung neuer oder aktualisierter adressbuchrichtlinien zwischengespeichert wurden, für Benutzer bis zu 30 Tage verfügbar bleiben können.</span><span class="sxs-lookup"><span data-stu-id="d069e-118">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="turn-on-scoped-directory-search"></a><span data-ttu-id="d069e-119">Aktivieren der Bereich-Verzeichnissuche</span><span class="sxs-lookup"><span data-stu-id="d069e-119">Turn on scoped directory search</span></span>

1. <span data-ttu-id="d069e-120">Verwenden Sie Richtlinien für Informationsbarrieren, um Ihre Organisation in virtuellen Untergruppen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d069e-120">Use Information Barrier policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="d069e-121">Weitere Informationen finden Sie unter [Definieren von Richtlinien für Informationsbarrieren](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies).</span><span class="sxs-lookup"><span data-stu-id="d069e-121">For more information, see [Define Information Barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies).</span></span>

2. <span data-ttu-id="d069e-122">Wählen Sie im Microsoft Teams Admin Center die Option **organisationsweite Einstellungen** > **Teams Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="d069e-122">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

3. <span data-ttu-id="d069e-123">Aktivieren Sie unter **Suchen**neben **Bereichs Verzeichnissuche in Teams, die eine Exchange-adressbuchrichtlinie (ABP) verwenden**, **die Umschaltfläche**.</span><span class="sxs-lookup"><span data-stu-id="d069e-123">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (ABP)**, turn the toggle **On**.</span></span>

    ![Verzeichnissuche im Bereich "Bereich" im Microsoft Teams Admin Center](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> <span data-ttu-id="d069e-125">Diese Änderung kann bis zu 24 Stunden dauern, bis Sie repliziert wurde.</span><span class="sxs-lookup"><span data-stu-id="d069e-125">This change can take up to 24 hours to replicate.</span></span>
