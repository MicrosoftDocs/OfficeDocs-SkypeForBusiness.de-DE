---
title: Verwenden der Verzeichnissuche in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
description: Erfahren Sie, wie Microsoft-Teams, bereichsbasierte Verzeichnissuche verwenden, um benutzerdefinierte Ansichten des Verzeichnisses bereitzustellen.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3b51b56b8cc8a1f08d756cdab245915a2ac6824
ms.sourcegitcommit: 7ca70e8a2108462afd505258b455169ead30f33f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "31041942"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="1afc6-103">Verwenden der Verzeichnissuche in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1afc6-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="1afc6-104">Microsoft-Teams, bereichsbasierte Verzeichnissuche finden kann Organisationen virtuelle Grenzen erstellen, die steuern, wie Benutzer suchen und mit anderen Benutzern in ihrer Organisation kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="1afc6-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="1afc6-105">Microsoft-Teams können Organisationen benutzerdefinierte Ansichten des Verzeichnisses für ihre Benutzer bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1afc6-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="1afc6-106">Microsoft-Teams, verwendet [Exchange adressbuchrichtlinien](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) , um diese benutzerdefinierten Ansichten unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1afc6-106">Microsoft Teams uses [Exchange address book policies](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) to support these custom views.</span></span> <span data-ttu-id="1afc6-107">Nachdem die Richtlinien aktiviert sind, werden von der Suche für andere Benutzer (beispielsweise um einen Chat zu initiieren oder ein Team Mitglieder hinzu) zurückgegebenen Ergebnisse gemäß den konfigurierten Richtlinien zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="1afc6-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="1afc6-108">Benutzer werden nicht zu suchen oder Teams bei der bereichsbezogenen Suche wirksam ist ermitteln können.</span><span class="sxs-lookup"><span data-stu-id="1afc6-108">Users will not be able to search or discover teams when scoped search is in effect.</span></span> 

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="1afc6-109">Wann sollten Sie bereichsbezogenen Verzeichnissuchen werden verwendet?</span><span class="sxs-lookup"><span data-stu-id="1afc6-109">When should you use scoped directory searches?</span></span>

<span data-ttu-id="1afc6-110">Szenarien, die von bereichsbezogenen Verzeichnissuchen profitieren ähneln Address Book Policy Szenarien.</span><span class="sxs-lookup"><span data-stu-id="1afc6-110">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="1afc6-111">Sie möchten beispielsweise bereichsbezogenen Verzeichnissuche in den folgenden Situationen verwenden:</span><span class="sxs-lookup"><span data-stu-id="1afc6-111">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="1afc6-112">Der Mandant Ihrer Organisation enthält mehrere Unternehmen, die voneinander getrennt sein sollen.</span><span class="sxs-lookup"><span data-stu-id="1afc6-112">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="1afc6-113">Ihre Bildungseinrichtung möchte Chats zwischen dem Lehrpersonal und den Kursteilnehmern begrenzen.</span><span class="sxs-lookup"><span data-stu-id="1afc6-113">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="1afc6-114">Gewusst wie: Verwenden von adressbuchrichtlinien finden Sie unter [Adressbuch Richtlinien im Exchange Online](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span><span class="sxs-lookup"><span data-stu-id="1afc6-114">To learn how to use address book policies, read [Address book policies in Exchange Online](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1afc6-115">Adressbuchrichtlinien enthalten nur eine virtuelle Trennung von Benutzern aus der Perspektive Directory.</span><span class="sxs-lookup"><span data-stu-id="1afc6-115">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="1afc6-116">Benutzer können weiterhin initiieren Kommunikation mit anderen Personen vollständige e-Mail-Adressen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="1afc6-116">Users can still initiate communications with others by providing complete email addresses.</span></span> <span data-ttu-id="1afc6-117">Es ist außerdem zu beachten, dass alle Benutzerdaten, die bereits, bevor Sie die Erzwingung von neuen oder aktualisierten adressbuchrichtlinien zwischengespeicherten hatte bis zu 30 Tage für Benutzer verfügbar bleiben.</span><span class="sxs-lookup"><span data-stu-id="1afc6-117">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="enable-scoped-directory-search"></a><span data-ttu-id="1afc6-118">Aktivieren Sie bereichsbezogenen Verzeichnissuche</span><span class="sxs-lookup"><span data-stu-id="1afc6-118">Enable scoped directory search</span></span>

1.  <span data-ttu-id="1afc6-119">Verwenden Sie adressbuchrichtlinien, um Ihre Organisation in virtuellen Untergruppen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1afc6-119">Use address book policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="1afc6-120">Weitere Informationen finden Sie unter [Prozeduren für adressbuchrichtlinien](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span><span class="sxs-lookup"><span data-stu-id="1afc6-120">For more information, see [Procedures for address book policies](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span></span>

2.  <span data-ttu-id="1afc6-121">Melden Sie sich bei Microsoft 365 Administrationscenter, wählen Sie **Admin zentriert**, und wählen Sie dann **Teams & Skype**.</span><span class="sxs-lookup"><span data-stu-id="1afc6-121">Sign in to the Microsoft 365 admin center, select **Admin centers**, and then select **Teams & Skype**.</span></span>
 
3.  <span data-ttu-id="1afc6-122">Wählen Sie in der Verwaltungskonsole von Microsoft-Teams, **Org geltende Einstellungen** > **Teams Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="1afc6-122">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

4.  <span data-ttu-id="1afc6-123">Aktivieren Sie unter **Search**neben- **Bereich der Verzeichnissuche in eine adressbuchrichtlinie (APB) für das Exchange-Teams**die Umschaltfläche **auf**.</span><span class="sxs-lookup"><span data-stu-id="1afc6-123">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (APB)**, turn the toggle **On**.</span></span> 

    ![Bereich der Verzeichnissuche im Microsoft-Teams, Administrationscenter](media/teams-scoped-directory-search-image1.png)

> [!NOTE]
> <span data-ttu-id="1afc6-125">Hybridkonfigurationen (mit lokale Exchange-Teams) unterstützt bereichsbezogenen Search-Modus nicht.</span><span class="sxs-lookup"><span data-stu-id="1afc6-125">Hybrid configurations (Teams with Exchange on-premises) do not support scoped search mode.</span></span> 

