---
title: Konfigurieren des vertraulichen Anwesenheitsmodus
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b33d57fe-b9cf-43c1-961a-edf28db738e8
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
- ms.lync.lac.OrgPresencePrivacy
description: 'Hier erfahren Sie, wie Sie den Datenschutzmodus für Ihre Benutzer einrichten, damit Sie besser steuern können, wie Personen Ihre Verfügbarkeit sehen. '
ms.openlocfilehash: a2b4ed11f1d56927a4bc7eed6ce36b5b04411509
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753440"
---
# <a name="configure-presence-privacy-mode"></a><span data-ttu-id="a99db-103">Konfigurieren des vertraulichen Anwesenheitsmodus</span><span class="sxs-lookup"><span data-stu-id="a99db-103">Configure presence privacy mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a99db-104">Das Microsoft Teams Admin Center hat das Skype for Business Admin Center (Legacy Portal) ersetzt.</span><span class="sxs-lookup"><span data-stu-id="a99db-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="a99db-105">Alle Einstellungen für die Verwaltung von Skype for Business sind jetzt im Team Admin Center.</span><span class="sxs-lookup"><span data-stu-id="a99db-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="a99db-106">Sie müssen der [Azure AD-Administratorrolle](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) des globalen Administrators oder des Skype for Business-Administrators zugewiesen sein, um Skype for Business-Funktionen im Team Admin Center verwalten zu können.</span><span class="sxs-lookup"><span data-stu-id="a99db-106">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="a99db-107">Weitere Informationen finden Sie unter [Verwalten von Skype for Business-Einstellungen im Microsoft Teams Admin Center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="a99db-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="a99db-108">Mit der Skype for Business Online-Anwesenheits Einstellung haben die Benutzer mehr Kontrolle darüber, wer sehen kann, ob Sie in einer Besprechung oder außerhalb des Büros verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a99db-108">The Skype for Business Online presence setting gives people more control over who can see whether they are available, in a meeting, or out of the office.</span></span> <span data-ttu-id="a99db-109">Details zu Skype for Business-Anwesenheits-und Datenschutzeinstellungen finden Sie unter [Konfigurieren der Anwesenheit in Skype for Business Online](configure-presence-in-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="a99db-109">For details about Skype for Business presence and privacy settings, see [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md).</span></span> 
  
## <a name="choose-the-default-online-presence-setting-for-everyone-in-your-organization"></a><span data-ttu-id="a99db-110">Auswählen der Standardeinstellung für Onlineanwesenheitsinformationen für alle Personen in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="a99db-110">Choose the default online presence setting for everyone in your organization</span></span>
<span data-ttu-id="a99db-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="a99db-111"><a name="__top"> </a></span></span>

1. <span data-ttu-id="a99db-112">Wechseln Sie zum Skype for Business Online Admin Center > **Organisation > allgemein**.</span><span class="sxs-lookup"><span data-stu-id="a99db-112">Go to the Skype for Business Online admin center > **Organization > General**.</span></span>
    
2. <span data-ttu-id="a99db-113">Wählen Sie unter **Anwesenheitsdaten Schutzmodus**die Einstellung aus, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a99db-113">Under **Presence privacy mode**, choose the setting, and then click **Save**.</span></span>
    
|<span data-ttu-id="a99db-114">**Einstellung**</span><span class="sxs-lookup"><span data-stu-id="a99db-114">**Setting**</span></span>|<span data-ttu-id="a99db-115">**Wer kann die Anwesenheit eines Benutzers anzeigen?**</span><span class="sxs-lookup"><span data-stu-id="a99db-115">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a99db-116">**Anwesenheitsinformationen automatisch anzeigen**</span><span class="sxs-lookup"><span data-stu-id="a99db-116">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="a99db-117">Jeder Skype for Business-Benutzer, der nicht zu den Vertraulichkeitsgruppen **Extern** oder **Blockiert** gehört</span><span class="sxs-lookup"><span data-stu-id="a99db-117">Any Skype for Business user who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> |
|<span data-ttu-id="a99db-118">**Anzeigen von Anwesenheitsinformationen nur für die Kontakte eines Benutzers**</span><span class="sxs-lookup"><span data-stu-id="a99db-118">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="a99db-119">Alle Personen in der Kontaktliste eines Benutzers, die nicht zu der **externen** oder **blockierten** Datenschutzgruppe gehören</span><span class="sxs-lookup"><span data-stu-id="a99db-119">Anyone in a user's contact list who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> <span data-ttu-id="a99db-120">Einzelne Benutzer können diese Einstellung im Dialogfeld **Optionen** für Skype for Business ändern.</span><span class="sxs-lookup"><span data-stu-id="a99db-120">Individual users can change this setting in the Skype for Business **Options** dialog box.</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="a99db-121">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a99db-121">Related topics</span></span>
[<span data-ttu-id="a99db-122">Einrichten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a99db-122">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="a99db-123">Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen</span><span class="sxs-lookup"><span data-stu-id="a99db-123">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
