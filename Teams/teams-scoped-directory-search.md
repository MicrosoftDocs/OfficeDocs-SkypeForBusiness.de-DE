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
- Teams_ITAdmin_Help
description: Hier erfahren Sie, wie Sie die Verzeichnissuche in Microsoft Teams verwenden, um angepasste Ansichten des Verzeichnisses bereitzustellen.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: bf65cec72c21e34e0aab8338d20ae36549497846
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221731"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="17600-103">Verwenden der Verzeichnissuche in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="17600-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="17600-104">Mithilfe der Verzeichnissuche in Microsoft Teams können Organisationen virtuelle Grenzen erstellen, die Steuern, wie Benutzer andere Benutzer in Ihrer Organisation finden und mit Ihnen kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="17600-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="17600-105">In Microsoft Teams können Organisationen ihren Benutzern benutzerdefinierte Ansichten des Verzeichnisses zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="17600-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="17600-106">Microsoft Teams verwendet [Exchange-adressbuchrichtlinien](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) , um diese benutzerdefinierten Ansichten zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="17600-106">Microsoft Teams uses [Exchange address book policies](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) to support these custom views.</span></span> <span data-ttu-id="17600-107">Sobald die Richtlinien aktiviert sind, werden die Ergebnisse, die von Suchvorgängen nach anderen Benutzern zurückgegeben wurden (beispielsweise zum Initiieren eines Chats oder zum Hinzufügen von Mitgliedern zu einem Team), entsprechend den konfigurierten Richtlinien zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="17600-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="17600-108">Benutzer können keine Teams durchsuchen oder entdecken, wenn die Bereichssuche aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="17600-108">Users will not be able to search or discover teams when scoped search is in effect.</span></span> 

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="17600-109">Wann sollten Sie Bereichs Verzeichnis suchen verwenden?</span><span class="sxs-lookup"><span data-stu-id="17600-109">When should you use scoped directory searches?</span></span>

<span data-ttu-id="17600-110">Szenarien, die von umfangreicheren Verzeichnis suchen profitieren, ähneln den Szenarien für adressbuchrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="17600-110">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="17600-111">So können Sie beispielsweise die bereichsbezogene Verzeichnissuche in den folgenden Situationen verwenden:</span><span class="sxs-lookup"><span data-stu-id="17600-111">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="17600-112">Der Mandant Ihrer Organisation enthält mehrere Unternehmen, die voneinander getrennt sein sollen.</span><span class="sxs-lookup"><span data-stu-id="17600-112">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="17600-113">Ihre Bildungseinrichtung möchte Chats zwischen dem Lehrpersonal und den Kursteilnehmern begrenzen.</span><span class="sxs-lookup"><span data-stu-id="17600-113">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="17600-114">Informationen zum Verwenden von adressbuchrichtlinien finden Sie [unter adressbuchrichtlinien in Exchange Online](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span><span class="sxs-lookup"><span data-stu-id="17600-114">To learn how to use address book policies, read [Address book policies in Exchange Online](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="17600-115">Adressbuchrichtlinien bieten nur eine virtuelle Trennung von Benutzern aus der Verzeichnis Perspektive.</span><span class="sxs-lookup"><span data-stu-id="17600-115">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="17600-116">Benutzer können die Kommunikation mit anderen Personen weiterhin initiieren, indem Sie vollständige e-Mail-Adressen angeben.</span><span class="sxs-lookup"><span data-stu-id="17600-116">Users can still initiate communications with others by providing complete email addresses.</span></span> <span data-ttu-id="17600-117">Beachten Sie auch, dass alle Benutzerdaten, die bereits vor der Erzwingung neuer oder aktualisierter adressbuchrichtlinien zwischengespeichert wurden, für Benutzer bis zu 30 Tage verfügbar bleiben können.</span><span class="sxs-lookup"><span data-stu-id="17600-117">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="turn-on-scoped-directory-search"></a><span data-ttu-id="17600-118">Aktivieren der Bereich-Verzeichnissuche</span><span class="sxs-lookup"><span data-stu-id="17600-118">Turn on scoped directory search</span></span>

1. <span data-ttu-id="17600-119">Verwenden Sie adressbuchrichtlinien, um Ihre Organisation in virtuellen Untergruppen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="17600-119">Use address book policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="17600-120">Weitere Informationen finden Sie unter [Verfahren für adressbuchrichtlinien](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span><span class="sxs-lookup"><span data-stu-id="17600-120">For more information, see [Procedures for address book policies](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span></span>

2. <span data-ttu-id="17600-121">Wählen Sie im Microsoft Teams Admin Center die Option **organisationsweite Einstellungen** > **Teams Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="17600-121">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

3. <span data-ttu-id="17600-122">Aktivieren Sie unter **Suchen**neben **Bereichs Verzeichnissuche in Teams mithilfe einer Exchange-adressbuchrichtlinie (Fahndung)** die Umschaltfläche \*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="17600-122">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (APB)**, turn the toggle **On**.</span></span>

    ![Verzeichnissuche im Bereich "Bereich" im Microsoft Teams Admin Center](media/teams-scoped-directory-search-image1.png)

> [!NOTE]
> <span data-ttu-id="17600-124">Hybrid Konfigurationen (Teams mit Exchange lokal) unterstützen den Bereich Such Modus nicht.</span><span class="sxs-lookup"><span data-stu-id="17600-124">Hybrid configurations (Teams with Exchange on-premises) do not support scoped search mode.</span></span> 

