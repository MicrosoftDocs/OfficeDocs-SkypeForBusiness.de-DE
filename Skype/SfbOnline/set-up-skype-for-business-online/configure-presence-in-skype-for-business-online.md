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
ms.openlocfilehash: b06139d3614335505c7f8682700aa3d7d6fb5df8
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739193"
---
# <a name="configure-presence-in-skype-for-business-online"></a><span data-ttu-id="c20d2-103">Konfigurieren der Anwesenheit in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c20d2-103">Configure presence in Skype for Business Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c20d2-104">Das Microsoft Teams Admin Center hat das Skype for Business Admin Center (Legacy Portal) ersetzt.</span><span class="sxs-lookup"><span data-stu-id="c20d2-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="c20d2-105">Alle Einstellungen für die Verwaltung von Skype for Business sind jetzt im Team Admin Center.</span><span class="sxs-lookup"><span data-stu-id="c20d2-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="c20d2-106">Weitere Informationen finden Sie unter [Verwalten von Skype for Business-Einstellungen im Microsoft Teams Admin Center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="c20d2-106">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="c20d2-107">Standardmäßig können alle Personen, die mit einem der Personen in Ihrer Organisation über Skype for Business kommunizieren können, auch sehen, ob diese Person online ist.</span><span class="sxs-lookup"><span data-stu-id="c20d2-107">By default, anyone who can communicate with one of the people in your organization using Skype for Business can also see whether that person is online.</span></span> <span data-ttu-id="c20d2-108">Skype for Business zeigt, ob eine Person Online, in einer Besprechung, offline oder einem anderen Indikator verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="c20d2-108">Skype for Business shows whether a person is available online, in a meeting, offline, or another indicator.</span></span>

![Ein Beispiel für den Onlinestatus einer Person in Skype for Business.](../images/f0849132-1ddb-480f-bca6-cfe9eaa0486d.png)

<span data-ttu-id="c20d2-110">Als **[Administrator](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** für alle in Ihrem Unternehmen können Sie auswählen, wer seinen Online-Status in Skype for Business sieht.</span><span class="sxs-lookup"><span data-stu-id="c20d2-110">As the **[admin](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** for everyone in your business, you can choose who sees their online presence in Skype for Business.</span></span>

<span data-ttu-id="c20d2-111">![Ein Symbol mit dem Skype for Business-Logo](../images/sfb-logo-30x30.png) **Unter Verwendung des Skype for Business Admin Centers**</span><span class="sxs-lookup"><span data-stu-id="c20d2-111">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="c20d2-112">Wechseln Sie zum Admin Center > **Admin**Center  >  **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="c20d2-112">Go to the admin center > **Admin centers** > **Skype for Business**.</span></span>

2. <span data-ttu-id="c20d2-113">Wählen Sie im **Skype for Business Admin Center**die Option **Organisation**aus.</span><span class="sxs-lookup"><span data-stu-id="c20d2-113">In the **Skype for Business admin center**, choose **organization**.</span></span>

3. <span data-ttu-id="c20d2-114">Wählen Sie unter **Anwesenheitsdaten Schutzmodus**eine der folgenden Einstellungen aus, und wählen Sie dann **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="c20d2-114">Under **presence privacy mode**, select one of the following settings, and then choose **Save**.</span></span>

|<span data-ttu-id="c20d2-115">**Einstellung**</span><span class="sxs-lookup"><span data-stu-id="c20d2-115">**Setting**</span></span>|<span data-ttu-id="c20d2-116">**Wer kann die Anwesenheit eines Benutzers anzeigen?**</span><span class="sxs-lookup"><span data-stu-id="c20d2-116">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c20d2-117">**Anwesenheitsinformationen automatisch anzeigen**</span><span class="sxs-lookup"><span data-stu-id="c20d2-117">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="c20d2-118">Alle Skype for Business-Benutzer in Ihrem Unternehmen, die keiner **externen** oder **blockierten** Liste einer Person hinzugefügt wurden, können die Onlineanwesenheit dieser Person sehen.</span><span class="sxs-lookup"><span data-stu-id="c20d2-118">Any Skype for Business user in your business who has not been added to a person's **External** or **Blocked** list will be able to see that person's online presence.</span></span> <br/> |
|<span data-ttu-id="c20d2-119">**Anzeigen von Anwesenheitsinformationen nur für die Kontakte eines Benutzers**</span><span class="sxs-lookup"><span data-stu-id="c20d2-119">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="c20d2-120">Alle Personen in der Kontaktliste einer Person, die Sie Ihrer **externen** oder **blockierten** Liste nicht hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="c20d2-120">Anyone in a person's Contacts list who they have not added to their **External** or **Blocked** list.</span></span> <br/> <span data-ttu-id="c20d2-121">Einzelpersonen können ihre Standardeinstellungen in Ihrer Skype for Business-APP außer Kraft setzen: **Einstellungen**  >  -**Tools**  >  -**Optionen**.</span><span class="sxs-lookup"><span data-stu-id="c20d2-121">Individuals can override your default settings in their Skype for Business app: **Settings** > **Tools** > **Options**.</span></span> <br/> |

<span data-ttu-id="c20d2-122">Informationen dazu, was Ihre Benutzer in Skype for Business ändern können, finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="c20d2-122">For information about what your users can change in Skype for Business, see these articles:</span></span>

- [<span data-ttu-id="c20d2-123">Steuern des Zugriffs auf ihre Anwesenheitsinformationen in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="c20d2-123">Control access to your presence information in Skype for Business</span></span>](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)

- [<span data-ttu-id="c20d2-124">Einrichten von Status Optionen in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="c20d2-124">Set Status options in Skype for Business</span></span>](https://support.office.com/article/efd25395-c8ef-4510-b9cb-6f70e2fff8a0)

## <a name="related-topics"></a><span data-ttu-id="c20d2-125">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="c20d2-125">Related topics</span></span>

[<span data-ttu-id="c20d2-126">Einrichten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c20d2-126">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="c20d2-127">Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen</span><span class="sxs-lookup"><span data-stu-id="c20d2-127">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)


