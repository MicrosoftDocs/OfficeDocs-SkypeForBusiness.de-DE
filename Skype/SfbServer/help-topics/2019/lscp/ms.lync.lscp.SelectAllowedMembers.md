---
title: Auswählen zugelassener Mitglieder
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: Erstellen und Verwalten von Chatrooms für beständigen Chat ist wesentlich einfacher mit die richtige Verwendung von Kategorien. A Persistent Chat Administrator können das Definieren von AllowedMembers und Creators für jede Kategorie, und Sie können auch definieren, die Standardeinstellungen für die Chatroom und Verhaltensweisen, die auf alle in der Kategorie erstellten Chatrooms angewendet werden. Administratoren für den beständigen Chat erstellen und Verwalten von Kategorien mithilfe der Systemsteuerung oder Windows PowerShell-Cmdlets.
ms.openlocfilehash: f83ff99905a9c2ada133c6a21d235a8385261545
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/20/2018
ms.locfileid: "19974670"
---
# <a name="select-allowed-members"></a><span data-ttu-id="6191b-105">Auswählen zugelassener Mitglieder</span><span class="sxs-lookup"><span data-stu-id="6191b-105">Select Allowed Members</span></span>
 
<span data-ttu-id="6191b-106">Erstellen und Verwalten von Chatrooms für beständigen Chat ist wesentlich einfacher mit die richtige Verwendung von Kategorien.</span><span class="sxs-lookup"><span data-stu-id="6191b-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="6191b-107">A Persistent Chat Administrator können das Definieren von **AllowedMembers** und **Creators** für jede Kategorie, und Sie können auch definieren, die Standardeinstellungen für die Chatroom und Verhaltensweisen, die auf alle in der Kategorie erstellten Chatrooms angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="6191b-107">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="6191b-108">Administratoren für den beständigen Chat erstellen und Verwalten von Kategorien mithilfe der Systemsteuerung oder Windows PowerShell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="6191b-108">Persistent Chat Administrators create and manage categories by using the control panel or Windows PowerShell cmdlets.</span></span>
  
<span data-ttu-id="6191b-109">Benutzer, Organisationseinheiten (Organizational Units, OUs) und Benutzergruppen, die als Ersteller einer Kategorie definiert werden, sind die einzigen Personen und Benutzergruppen, die Chatrooms in dieser Kategorie erstellen dürfen.</span><span class="sxs-lookup"><span data-stu-id="6191b-109">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="6191b-110">Nachdem die Kategorie erstellt wurde, können sie auswählen OUs, Benutzer und Benutzergruppen aus der Kategorie **AllowedMembers** Liste als chatroommanager und Member zum Verwalten von und teilnehmen an den Chatroom.</span><span class="sxs-lookup"><span data-stu-id="6191b-110">After the category is created, they can choose users, OUs, and user groups from the category's **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="6191b-111">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="6191b-111">Tasks that you can perform</span></span>

<span data-ttu-id="6191b-112">Auf der Seite **Zugelassene Mitglieder auswählen** können Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="6191b-112">You can perform the following tasks on the **Select Allowed Members** page:</span></span>
  
- [<span data-ttu-id="6191b-113">Konfigurieren von Kategorien</span><span class="sxs-lookup"><span data-stu-id="6191b-113">Configure Categories</span></span>](http://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)
    
- [<span data-ttu-id="6191b-114">Neue Features für Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="6191b-114">New Persistent Chat Server Features</span></span>](http://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)
    
<span data-ttu-id="6191b-115">Ausführliche Informationen zu den verschiedenen Verfahren, die Sie mithilfe der Skype für Business Server-Systemsteuerung ausführen können, finden Sie unter [Verwalten von Skype für Business Server 2015](../../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="6191b-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../../manage/manage.md).</span></span>
  
## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="6191b-116">So konfigurieren Sie Kategorien für Chatrooms</span><span class="sxs-lookup"><span data-stu-id="6191b-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="6191b-117">Unter **Mitgliedschaft**im Abschnitt **Zugelassene Mitglieder** hinzufügen oder Entfernen von Benutzern und anderen Active Directory-Domänendienste Prinzipale (Benutzer, Verteilergruppen, Organisationseinheiten usw.), die als Mitglieder des Chatrooms hinzugefügt werden dürfen für die Kategorie gehören.</span><span class="sxs-lookup"><span data-stu-id="6191b-117">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="6191b-118">Prinzipale, die in einer Kategorie zugelassen sind, können nach den Räumen in der Kategorie suchen (es sei denn, der Raum ist ausgeblendet; in diesem Fall können nur Mitglieder des Raums im Verzeichnis danach suchen).</span><span class="sxs-lookup"><span data-stu-id="6191b-118">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>
  
### 

<span data-ttu-id="6191b-119">Ausführliche Informationen zur Persistent Chat Server-Features und Funktionen finden Sie unter [Overview of Persistent Chat Server](http://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="6191b-119">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](http://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="6191b-120">Ausführliche Informationen zur Verwendung von Persistent Chat Server-Konfigurationen finden Sie unter [Configuring Persistent Chat Server](http://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in der Dokumentation zur Bereitstellung und [Verwaltung von Lync Server 2013, Persistent Chat Server](http://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="6191b-120">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](http://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](http://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6191b-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6191b-121">See also</span></span>

[<span data-ttu-id="6191b-122">Grundlegendes zur Persistent Chat-Mitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="6191b-122">Understanding Persistent Chat Membership</span></span>](http://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)