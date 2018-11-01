---
title: Microsoft-Teams, Verwendung bezogenen Verzeichnissuche
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/09/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Microsoft-Teams, bereichsbasierte Verzeichnissuche verwenden, um benutzerdefinierte Ansichten des Verzeichnisses bereitzustellen.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c8173445fff6acaa3a5381199220a376401076c
ms.sourcegitcommit: 6d30cfdd8c8b8908d4e4f278c39fd22062f4a888
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2018
ms.locfileid: "25890697"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="06390-103">Microsoft-Teams, Verwendung bezogenen Verzeichnissuche</span><span class="sxs-lookup"><span data-stu-id="06390-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="06390-104">Microsoft-Teams, bereichsbasierte Verzeichnissuche finden kann Organisationen virtuelle Grenzen erstellen, die steuern, wie Benutzer suchen und mit anderen Benutzern in ihrer Organisation kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="06390-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="06390-105">Microsoft-Teams können Organisationen benutzerdefinierte Ansichten des Verzeichnisses für ihre Benutzer bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="06390-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="06390-106">Microsoft-Teams, verwendet [Exchange adressbuchrichtlinien](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/address-book-policies?view=exchserver-2019) , um diese benutzerdefinierten Ansichten unterstützen.</span><span class="sxs-lookup"><span data-stu-id="06390-106">Microsoft Teams uses [Exchange address book policies](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/address-book-policies?view=exchserver-2019) to support these custom views.</span></span> <span data-ttu-id="06390-107">Nachdem die Richtlinien aktiviert sind, werden von der Suche für andere Benutzer (beispielsweise um einen Chat zu initiieren oder ein Team Mitglieder hinzu) zurückgegebenen Ergebnisse gemäß den konfigurierten Richtlinien zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="06390-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="06390-108">Benutzer werden nicht zu suchen oder Teams bei der bereichsbezogenen Suche wirksam ist ermitteln können.</span><span class="sxs-lookup"><span data-stu-id="06390-108">Users will not be able to search or discover teams when scoped search is in effect.</span></span> 

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="06390-109">Wann sollten Sie bereichsbezogenen Verzeichnissuchen werden verwendet?</span><span class="sxs-lookup"><span data-stu-id="06390-109">When should you use scoped directory searches?</span></span>

<span data-ttu-id="06390-110">Szenarien, die von bereichsbezogenen Verzeichnissuchen profitieren ähneln Address Book Policy Szenarien.</span><span class="sxs-lookup"><span data-stu-id="06390-110">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="06390-111">Sie möchten beispielsweise bereichsbezogenen Verzeichnissuche in den folgenden Situationen verwenden:</span><span class="sxs-lookup"><span data-stu-id="06390-111">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="06390-112">Ihre Organisation verfügt über mehrere Mandanten innerhalb dessen Mandanten, die Sie trennen möchten.</span><span class="sxs-lookup"><span data-stu-id="06390-112">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="06390-113">Ihre Schule möchte Chats zwischen Fakultät und Schüler zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="06390-113">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="06390-114">Weitere Informationen finden Sie Informationen zu wie adressbuchrichtlinien verwendet werden können [hier](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/abp-scenarios?view=exchserver-2019).</span><span class="sxs-lookup"><span data-stu-id="06390-114">You can learn more about how address book policies can be used [here](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/abp-scenarios?view=exchserver-2019).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="06390-115">Adressbuchrichtlinien enthalten nur eine virtuelle Trennung von Benutzern aus der Perspektive Directory.</span><span class="sxs-lookup"><span data-stu-id="06390-115">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="06390-116">Benutzer können weiterhin initiieren Kommunikation mit anderen Personen vollständige e-Mail-Adressen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="06390-116">Users can still initiate communications with others by providing complete email addresses.</span></span> 

## <a name="enable-scoped-directory-search"></a><span data-ttu-id="06390-117">Aktivieren Sie bereichsbezogenen Verzeichnissuche</span><span class="sxs-lookup"><span data-stu-id="06390-117">Enable scoped directory search</span></span>

1.  <span data-ttu-id="06390-118">Verwenden Sie adressbuchrichtlinien, um Ihre Organisation in virtuellen Untergruppen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="06390-118">Use address book policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="06390-119">Weitere Informationen finden Sie unter [Prozeduren für adressbuchrichtlinien](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/abp-procedures?view=exchserver-2019).</span><span class="sxs-lookup"><span data-stu-id="06390-119">For more information, see [Procedures for address book policies](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/abp-procedures?view=exchserver-2019).</span></span>

2.  <span data-ttu-id="06390-120">Melden Sie sich bei Microsoft 365 Administrationscenter, wählen Sie **Admin centers**und wählen Sie dann **Teams & Skype**.</span><span class="sxs-lookup"><span data-stu-id="06390-120">Sign in to the Microsoft 365 admin center, select **Admin centers**, and then select **Teams & Skype**.</span></span>
 
3.  <span data-ttu-id="06390-121">Wählen Sie in der Microsoft-Teams & Skype für Business Administrationscenter **Org geltende Einstellungen** > **Teams Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="06390-121">In the Microsoft Teams & Skype for Business admin center, select **Org-wide settings** > **Teams settings**.</span></span>

4.  <span data-ttu-id="06390-122">Aktivieren Sie unter **Search**neben- **Bereich der Verzeichnissuche in eine adressbuchrichtlinie (APB) für das Exchange-Teams**die Umschaltfläche **auf**.</span><span class="sxs-lookup"><span data-stu-id="06390-122">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (APB)**, turn the toggle **On**.</span></span> 

    ![Bereich der Verzeichnissuche in Teams & Skype für Business-Verwaltungskonsole](media/teams-scoped-directory-search-image1.png)

> [!NOTE]
> <span data-ttu-id="06390-124">Hybridkonfigurationen (mit lokale Exchange-Teams) unterstützt bereichsbezogenen Search-Modus nicht.</span><span class="sxs-lookup"><span data-stu-id="06390-124">Hybrid configurations (Teams with Exchange on-premises) do not support scoped search mode.</span></span> 

