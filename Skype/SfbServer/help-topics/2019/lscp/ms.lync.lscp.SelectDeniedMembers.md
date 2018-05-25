---
title: Auswählen abgelehnter Mitglieder
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.SelectDeniedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c626b6b4-15f3-4a59-bb1d-55dc8c60f5cb
description: A Persistent Chat Administrator können erstellen und Verwalten von Kategorien für Chatrooms. Als Teil des erstellen und Verwalten von Kategorien für Chatrooms kann ein Persistent Chat Administrator Prinzipale (Active Directory Domain Services Gruppen/Container/Benutzer) zu konfigurieren, die Zugriff auf Member/Ersteller von einer bestimmten Kategorie Chatrooms sein. A Persistent Chat Administrator können auch DeniedMembers zu einer Kategorie hinzufügen, und diese werden zur Liste zugelassenen explizite Ausschlüsse. DeniedMembers außer Kraft setzen, was in AllowedMembers ist.
ms.openlocfilehash: f8fc7179df8facb98408e4506cf681cbefb97c62
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2018
---
# <a name="select-denied-members"></a><span data-ttu-id="9b721-106">Auswählen abgelehnter Mitglieder</span><span class="sxs-lookup"><span data-stu-id="9b721-106">Select Denied Members</span></span>
 
<span data-ttu-id="9b721-107">A Persistent Chat Administrator können erstellen und Verwalten von Kategorien für Chatrooms.</span><span class="sxs-lookup"><span data-stu-id="9b721-107">A Persistent Chat Administrator can create and manage chat room categories.</span></span> <span data-ttu-id="9b721-108">Als Teil des erstellen und Verwalten von Kategorien für Chatrooms kann ein Persistent Chat Administrator Prinzipale (Active Directory Domain Services Gruppen/Container/Benutzer) zu konfigurieren, die Zugriff auf Member/Ersteller von einer bestimmten Kategorie Chatrooms sein.</span><span class="sxs-lookup"><span data-stu-id="9b721-108">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory Domain Services groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="9b721-109">A Persistent Chat Administrator können auch DeniedMembers zu einer Kategorie hinzufügen, und diese werden zur Liste zugelassenen explizite Ausschlüsse.</span><span class="sxs-lookup"><span data-stu-id="9b721-109">A Persistent Chat Administrator can also add DeniedMembers to a category and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="9b721-110">DeniedMembers außer Kraft setzen, was in AllowedMembers ist.</span><span class="sxs-lookup"><span data-stu-id="9b721-110">DeniedMembers override what's in AllowedMembers.</span></span>
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="9b721-111">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="9b721-111">Tasks that you can perform</span></span>

<span data-ttu-id="9b721-112">Auf der Seite **Abgelehnte Mitglieder auswählen** können Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="9b721-112">You can perform the following tasks on the **Select Denied Members** page:</span></span>
  
- [<span data-ttu-id="9b721-113">Konfigurieren von Kategorien</span><span class="sxs-lookup"><span data-stu-id="9b721-113">Configure Categories</span></span>](http://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)
    
- [<span data-ttu-id="9b721-114">Neue Features für Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="9b721-114">New Persistent Chat Server Features</span></span>](http://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)
    
<span data-ttu-id="9b721-115">Ausführliche Informationen zu den verschiedenen Verfahren, die Sie mithilfe der Skype für Business Server-Systemsteuerung ausführen können, finden Sie unter [Verwalten von Skype für Business Server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="9b721-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>
  
## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="9b721-116">So konfigurieren Sie Kategorien für Chatrooms</span><span class="sxs-lookup"><span data-stu-id="9b721-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="9b721-117">**Die Mitgliedschaft**in den Abschnitt **abgelehnten Mitglieder** hinzufügen oder Entfernen von Benutzern und anderen Active Directory-Prinzipale wird diesen Raum Mitgliedern zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="9b721-117">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>
  
### 

<span data-ttu-id="9b721-118">Ausführliche Informationen zur Persistent Chat Server-Features und Funktionen finden Sie unter [Overview of Persistent Chat Server](http://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="9b721-118">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](http://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="9b721-119">Ausführliche Informationen zur Verwendung von Persistent Chat Server-Konfigurationen finden Sie unter [Configuring Persistent Chat Server](http://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in der Dokumentation zur Bereitstellung und [Verwaltung von Lync Server 2013, Persistent Chat Server](http://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="9b721-119">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](http://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](http://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9b721-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b721-120">See also</span></span>

#### 

[<span data-ttu-id="9b721-121">Grundlegendes zur Persistent Chat-Mitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="9b721-121">Understanding Persistent Chat Membership</span></span>](http://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)

