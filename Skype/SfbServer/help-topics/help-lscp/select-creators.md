---
title: Auswählen von Erstellern
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.SelectCreators
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f8d9ed6f-22ba-470e-b0b4-0da3cea5e961
description: Erstellen und Verwalten von Chatrooms für beständigen Chat ist wesentlich einfacher mit die richtige Verwendung von Kategorien. Ein Persistent Chat Administrator kann das Definieren von AllowedMembers und Creators für jede Kategorie, und kann auch definieren, die Standardeinstellungen für die Chatroom und Verhaltensweisen, die auf alle in der Kategorie erstellten Chatrooms angewendet werden. Persistente Chat-Administratoren erstellen und Verwalten von Kategorien mithilfe von Skype für Business Server-Systemsteuerung oder Windows PowerShell-Cmdlets.
ms.openlocfilehash: 9a814a5a6408e80fc1b51679fad80ef8c44f6b49
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21005584"
---
# <a name="select-creators"></a><span data-ttu-id="9bfa6-105">Auswählen von Erstellern</span><span class="sxs-lookup"><span data-stu-id="9bfa6-105">Select Creators</span></span>
 
<span data-ttu-id="9bfa6-106">Erstellen und Verwalten von Chatrooms für beständigen Chat ist wesentlich einfacher mit die richtige Verwendung von Kategorien.</span><span class="sxs-lookup"><span data-stu-id="9bfa6-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="9bfa6-107">Ein Persistent Chat Administrator kann das Definieren von **AllowedMembers** und **Creators** für jede Kategorie, und kann auch definieren, die Standardeinstellungen für die Chatroom und Verhaltensweisen, die auf alle in der Kategorie erstellten Chatrooms angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="9bfa6-107">A Persistent Chat administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="9bfa6-108">Persistente Chat-Administratoren erstellen und Verwalten von Kategorien mithilfe von Skype für Business Server-Systemsteuerung oder Windows PowerShell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="9bfa6-108">Persistent Chat administrators create and manage categories by using Skype for Business Server Control Panel or Windows PowerShell cmdlets.</span></span>
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="9bfa6-109">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="9bfa6-109">Tasks that you can perform</span></span>

<span data-ttu-id="9bfa6-110">Auf der Seite **Ersteller auswählen** können Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="9bfa6-110">You can perform the following tasks on the **Select Creators** page:</span></span>
  
- [<span data-ttu-id="9bfa6-111">Konfigurieren von Kategorien</span><span class="sxs-lookup"><span data-stu-id="9bfa6-111">Configure Categories</span></span>](http://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)
    
- [<span data-ttu-id="9bfa6-112">Neue Features für Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="9bfa6-112">New Persistent Chat Server Features</span></span>](http://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)
    
<span data-ttu-id="9bfa6-113">Ausführliche Informationen zu den verschiedenen Verfahren, die Sie mithilfe der Skype für Business Server-Systemsteuerung ausführen können, finden Sie unter [Verwalten von Skype für Business Server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="9bfa6-113">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>
  
## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="9bfa6-114">So konfigurieren Sie Kategorien für Chatrooms</span><span class="sxs-lookup"><span data-stu-id="9bfa6-114">To configure categories for chat rooms</span></span>

<span data-ttu-id="9bfa6-115">**Die Mitgliedschaft**in den Abschnitt **Ersteller** hinzufügen oder Entfernen von Benutzern und anderen Active Directory-Prinzipale Ersteller für die Kategorie zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="9bfa6-115">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="9bfa6-116">Ein Ersteller ist ein Benutzer, der Berechtigungen zum Erstellen von Chatrooms und zum Zuweisen von Chatroom-Managern und -mitgliedern besitzt.</span><span class="sxs-lookup"><span data-stu-id="9bfa6-116">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>
  


<span data-ttu-id="9bfa6-117">Ausführliche Informationen zur Persistent Chat Server-Features und Funktionen finden Sie unter [Overview of Persistent Chat Server](http://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="9bfa6-117">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](http://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="9bfa6-118">Ausführliche Informationen zur Verwendung von Persistent Chat Server-Konfigurationen finden Sie unter [Configuring Persistent Chat Server](http://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in der Dokumentation zur Bereitstellung und [Verwaltung von Lync Server 2013, Persistent Chat Server](http://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="9bfa6-118">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](http://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](http://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9bfa6-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9bfa6-119">See also</span></span>

[<span data-ttu-id="9bfa6-120">Grundlegendes zur Persistent Chat-Mitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="9bfa6-120">Understanding Persistent Chat Membership</span></span>](http://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
  
[<span data-ttu-id="9bfa6-121">Verwenden von Kategorien zur Verwaltung von Persistent Chatserver</span><span class="sxs-lookup"><span data-stu-id="9bfa6-121">Using Categories to Administer Persistent Chat Server</span></span>](http://technet.microsoft.com/library/dfcb3ad1-da90-467e-b08c-f4e68673b7b5.aspx)
  
[<span data-ttu-id="9bfa6-122">Verschieben eines Chatrooms aus einer Kategorie in eine andere</span><span class="sxs-lookup"><span data-stu-id="9bfa6-122">Moving a Chat Room from One Category to Another</span></span>](http://technet.microsoft.com/library/7e93b8f6-5a18-4476-a432-3918e01bcfa6.aspx)
  
[<span data-ttu-id="9bfa6-123">Erstellen oder Bearbeiten eines neuen Raums</span><span class="sxs-lookup"><span data-stu-id="9bfa6-123">Creating or Editing a New Room</span></span>](http://technet.microsoft.com/library/aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4.aspx)