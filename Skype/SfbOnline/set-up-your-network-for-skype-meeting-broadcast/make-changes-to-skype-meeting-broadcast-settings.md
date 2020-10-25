---
title: Vornehmen von Änderungen an den Einstellungen für die Skype-Live Konferenz für Ihre Organisation
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: 8e46e857-f046-4e87-a633-0d7fb88d66d5
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
- SMB
- ms.lync.lac.BroadcastMeetings
description: Sie können Skype-Live Konferenz aktivieren und Änderungen an den Einstellungen und Richtlinien für diese Besprechungen vornehmen.
ms.openlocfilehash: 88f074838ff1d03153441beb624bc5d9b7ad157c
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753410"
---
# <a name="make-changes-to-skype-meeting-broadcast-settings-for-your-organization"></a><span data-ttu-id="c53c6-103">Vornehmen von Änderungen an den Einstellungen für die Skype-Live Konferenz für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="c53c6-103">Make changes to Skype Meeting Broadcast settings for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c53c6-104">Das Microsoft Teams Admin Center hat das Skype for Business Admin Center (Legacy Portal) ersetzt.</span><span class="sxs-lookup"><span data-stu-id="c53c6-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="c53c6-105">Alle Einstellungen für die Verwaltung von Skype for Business sind jetzt im Team Admin Center.</span><span class="sxs-lookup"><span data-stu-id="c53c6-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="c53c6-106">Sie müssen der [Azure AD-Administratorrolle](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) des globalen Administrators oder des Skype for Business-Administrators zugewiesen sein, um Skype for Business-Funktionen im Team Admin Center verwalten zu können.</span><span class="sxs-lookup"><span data-stu-id="c53c6-106">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="c53c6-107">Weitere Informationen finden Sie unter [Verwalten von Skype for Business-Einstellungen im Microsoft Teams Admin Center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="c53c6-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="c53c6-108">Sie können Skype-Live Konferenz aktivieren und Änderungen an den Einstellungen und Richtlinien für diese Besprechungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="c53c6-108">You can enable Skype Meeting Broadcast and make changes to settings and policies for those meetings.</span></span>
  
- <span data-ttu-id="c53c6-109">**Skype-Live Konferenz aktivieren** Ermöglicht Skype-Live Konferenz.</span><span class="sxs-lookup"><span data-stu-id="c53c6-109">**Enable Skype Meeting Broadcast** Enables Skype Meeting Broadcast.</span></span> <span data-ttu-id="c53c6-110">Nachdem Sie Skype-Live Konferenz aktiviert haben, müssen Sie [Ihr Netzwerk für Skype-Live Konferenz einrichten](set-up-your-network-for-skype-meeting-broadcast.md).</span><span class="sxs-lookup"><span data-stu-id="c53c6-110">After you enable Skype Meeting Broadcast, you need to [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> <span data-ttu-id="c53c6-111">Führen Sie diesen Schritt aus, wenn Sie Webinare und andere Konferenzen für Personen außerhalb Ihres Unternehmens durchführen möchten.</span><span class="sxs-lookup"><span data-stu-id="c53c6-111">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span> 
    
- <span data-ttu-id="c53c6-112">**Aktivieren der Vorschau Features für Skype-Live Konferenzen für meine Organisation** Die Skype for Business-Kundenprogramme bieten Ihnen frühen Zugriff auf neue Produkte und Funktionen.</span><span class="sxs-lookup"><span data-stu-id="c53c6-112">**Enable Skype Meeting Broadcast Preview features for my organization** The Skype for Business customer programs provide you early access to new products and features.</span></span> <span data-ttu-id="c53c6-113">Dadurch erhalten Sie von Ihrer Organisation einen kleinen Einblick in die bevorstehenden Funktionen und die Möglichkeit, die neuen Features in ihrer eigenen Umgebung zu testen und Feedback zu geben, bevor wir Produkt-Builds für die breite Öffentlichkeit freigeben.</span><span class="sxs-lookup"><span data-stu-id="c53c6-113">This gives your organization a sneak peek at what's coming and the opportunity to test the new features in your own environment and give feedback before we release product builds to the general public.</span></span><br/>[<span data-ttu-id="c53c6-114">Skype for Business-Vorschau</span><span class="sxs-lookup"><span data-stu-id="c53c6-114">Skype for Business preview</span></span>](https://www.skypepreview.com/)
    
- <span data-ttu-id="c53c6-115">**Zulassen, dass die Organisatoren anonyme Besprechungen planen** Auf diese Weise können Organisatoren Broadcast Ereignisse erstellen, mit denen Personen außerhalb Ihrer Organisation teilnehmen können, ohne dass Sie sich anmelden müssen.</span><span class="sxs-lookup"><span data-stu-id="c53c6-115">**Allow organizers to schedule anonymous meetings** This lets organizers create broadcast events that allow anyone outside their organization to join without a requirement to sign in.</span></span>
    
- <span data-ttu-id="c53c6-116">**Aufzeichnen von Broadcast Besprechungen zulassen** Dadurch können Besprechungen, die vom Referenten oder Organisator aufgezeichnet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="c53c6-116">**Allow broadcast meetings to be recorded** This enables any meetings you have to be recorded by the presenter or organizer.</span></span>
    
- <span data-ttu-id="c53c6-117">**Helpdesk-Support-URL für Teilnehmer** Geben Sie einen Link für die Teilnehmer der Besprechungs Übertragung ein, wenn Sie Hilfe beim Verbinden oder teilnehmen an einer Broadcast Besprechung benötigen.</span><span class="sxs-lookup"><span data-stu-id="c53c6-117">**Helpdesk support URL for attendees** Enter a link for meeting broadcast attendees to use if they need help connecting or attending a broadcast meeting.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="c53c6-118">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="c53c6-118">Related topics</span></span>

[<span data-ttu-id="c53c6-119">Einrichten Ihres Netzwerks für Skype Meeting Broadcast</span><span class="sxs-lookup"><span data-stu-id="c53c6-119">Set up your network for Skype Meeting Broadcast</span></span>](set-up-your-network-for-skype-meeting-broadcast.md)

  
 
