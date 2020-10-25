---
title: Konfigurieren der Anwesenheit in Skype for Business Online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: ce59ac0b-8115-4c6b-8174-e3aef982d3cb
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- O365P_OnlinePresenceDesc
description: 'Hier erfahren Sie, wie Sie Skype for Business einrichten, damit Sie die Verfügbarkeit Ihrer Kollegen sehen können. '
ms.openlocfilehash: f2b149a2b6277d356fe4478ee6de12ec6b078f48
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753450"
---
# <a name="configure-presence-in-skype-for-business-online"></a><span data-ttu-id="a33fb-103">Konfigurieren der Anwesenheit in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a33fb-103">Configure presence in Skype for Business Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a33fb-104">Das Microsoft Teams Admin Center hat das Skype for Business Admin Center (Legacy Portal) ersetzt.</span><span class="sxs-lookup"><span data-stu-id="a33fb-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="a33fb-105">Alle Einstellungen für die Verwaltung von Skype for Business sind jetzt im Team Admin Center.</span><span class="sxs-lookup"><span data-stu-id="a33fb-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="a33fb-106">Sie müssen der [Azure AD-Administratorrolle](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) des globalen Administrators oder des Skype for Business-Administrators zugewiesen sein, um Skype for Business-Funktionen im Team Admin Center verwalten zu können.</span><span class="sxs-lookup"><span data-stu-id="a33fb-106">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="a33fb-107">Weitere Informationen finden Sie unter [Verwalten von Skype for Business-Einstellungen im Microsoft Teams Admin Center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="a33fb-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="a33fb-108">Standardmäßig können alle Personen, die mit einem der Personen in Ihrer Organisation über Skype for Business kommunizieren können, auch sehen, ob diese Person online ist.</span><span class="sxs-lookup"><span data-stu-id="a33fb-108">By default, anyone who can communicate with one of the people in your organization using Skype for Business can also see whether that person is online.</span></span> <span data-ttu-id="a33fb-109">Skype for Business zeigt, ob eine Person Online, in einer Besprechung, offline oder einem anderen Indikator verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="a33fb-109">Skype for Business shows whether a person is available online, in a meeting, offline, or another indicator.</span></span>

![Ein Beispiel für den Onlinestatus einer Person in Skype for Business.](../images/f0849132-1ddb-480f-bca6-cfe9eaa0486d.png)

<span data-ttu-id="a33fb-111">Als **[Administrator](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** für alle in Ihrem Unternehmen können Sie auswählen, wer seinen Online-Status in Skype for Business sieht.</span><span class="sxs-lookup"><span data-stu-id="a33fb-111">As the **[admin](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** for everyone in your business, you can choose who sees their online presence in Skype for Business.</span></span>

<span data-ttu-id="a33fb-112">![Ein Symbol mit dem Skype for Business-Logo](../images/sfb-logo-30x30.png) **Unter Verwendung des Skype for Business Admin Centers**</span><span class="sxs-lookup"><span data-stu-id="a33fb-112">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="a33fb-113">Wechseln Sie zum Admin Center > **Admin**Center  >  **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="a33fb-113">Go to the admin center > **Admin centers** > **Skype for Business**.</span></span>

2. <span data-ttu-id="a33fb-114">Wählen Sie im **Skype for Business Admin Center**die Option **Organisation**aus.</span><span class="sxs-lookup"><span data-stu-id="a33fb-114">In the **Skype for Business admin center**, choose **organization**.</span></span>

3. <span data-ttu-id="a33fb-115">Wählen Sie unter **Anwesenheitsdaten Schutzmodus**eine der folgenden Einstellungen aus, und wählen Sie dann **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="a33fb-115">Under **presence privacy mode**, select one of the following settings, and then choose **Save**.</span></span>

|<span data-ttu-id="a33fb-116">**Einstellung**</span><span class="sxs-lookup"><span data-stu-id="a33fb-116">**Setting**</span></span>|<span data-ttu-id="a33fb-117">**Wer kann die Anwesenheit eines Benutzers anzeigen?**</span><span class="sxs-lookup"><span data-stu-id="a33fb-117">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a33fb-118">**Anwesenheitsinformationen automatisch anzeigen**</span><span class="sxs-lookup"><span data-stu-id="a33fb-118">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="a33fb-119">Alle Skype for Business-Benutzer in Ihrem Unternehmen, die keiner **externen** oder **blockierten** Liste einer Person hinzugefügt wurden, können die Onlineanwesenheit dieser Person sehen.</span><span class="sxs-lookup"><span data-stu-id="a33fb-119">Any Skype for Business user in your business who has not been added to a person's **External** or **Blocked** list will be able to see that person's online presence.</span></span> <br/> |
|<span data-ttu-id="a33fb-120">**Anzeigen von Anwesenheitsinformationen nur für die Kontakte eines Benutzers**</span><span class="sxs-lookup"><span data-stu-id="a33fb-120">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="a33fb-121">Alle Personen in der Kontaktliste einer Person, die Sie Ihrer **externen** oder **blockierten** Liste nicht hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="a33fb-121">Anyone in a person's Contacts list who they have not added to their **External** or **Blocked** list.</span></span> <br/> <span data-ttu-id="a33fb-122">Einzelpersonen können ihre Standardeinstellungen in Ihrer Skype for Business-APP außer Kraft setzen: **Einstellungen**  >  -**Tools**  >  -**Optionen**.</span><span class="sxs-lookup"><span data-stu-id="a33fb-122">Individuals can override your default settings in their Skype for Business app: **Settings** > **Tools** > **Options**.</span></span> <br/> |

<span data-ttu-id="a33fb-123">Informationen dazu, was Ihre Benutzer in Skype for Business ändern können, finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="a33fb-123">For information about what your users can change in Skype for Business, see these articles:</span></span>

- [<span data-ttu-id="a33fb-124">Steuern des Zugriffs auf ihre Anwesenheitsinformationen in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="a33fb-124">Control access to your presence information in Skype for Business</span></span>](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)

- [<span data-ttu-id="a33fb-125">Einrichten von Status Optionen in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="a33fb-125">Set Status options in Skype for Business</span></span>](https://support.office.com/article/efd25395-c8ef-4510-b9cb-6f70e2fff8a0)

## <a name="related-topics"></a><span data-ttu-id="a33fb-126">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a33fb-126">Related topics</span></span>

[<span data-ttu-id="a33fb-127">Einrichten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a33fb-127">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="a33fb-128">Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen</span><span class="sxs-lookup"><span data-stu-id="a33fb-128">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)


