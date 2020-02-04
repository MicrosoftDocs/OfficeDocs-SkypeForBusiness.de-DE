---
title: Auswählen zugelassener Mitglieder
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: Das Erstellen und verwalten beständiger Chatrooms ist mit der korrekten Verwendung von Kategorien viel einfacher. Ein beständiger Chat-Administrator kann AllowedMembers und Creators für jede Kategorie definieren und auch die Standardeinstellungen und-Verhaltensweisen für Chatrooms definieren, die auf alle Chatrooms angewendet werden, die in der Kategorie erstellt wurden. Beständige Chat Administratoren erstellen und verwalten Kategorien mithilfe der Systemsteuerung oder Windows PowerShell-Cmdlets.
ms.openlocfilehash: 916077fe25e1616888dd58dc40f0ef0f14c61e7a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41699700"
---
# <a name="select-allowed-members"></a><span data-ttu-id="fcfae-105">Auswählen zugelassener Mitglieder</span><span class="sxs-lookup"><span data-stu-id="fcfae-105">Select Allowed Members</span></span>

<span data-ttu-id="fcfae-106">Das Erstellen und verwalten beständiger Chatrooms ist mit der korrekten Verwendung von Kategorien viel einfacher.</span><span class="sxs-lookup"><span data-stu-id="fcfae-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="fcfae-107">Ein beständiger Chat-Administrator kann **AllowedMembers** und **Creators** für jede Kategorie definieren und auch die Standardeinstellungen und-Verhaltensweisen für Chatrooms definieren, die auf alle Chatrooms angewendet werden, die in der Kategorie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="fcfae-107">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="fcfae-108">Beständige Chat Administratoren erstellen und verwalten Kategorien mithilfe der Systemsteuerung oder Windows PowerShell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="fcfae-108">Persistent Chat Administrators create and manage categories by using the control panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="fcfae-109">Benutzer, Organisationseinheiten (Organizational Units, OUs) und Benutzergruppen, die als Ersteller einer Kategorie definiert werden, sind die einzigen Personen und Benutzergruppen, die Chatrooms in dieser Kategorie erstellen dürfen.</span><span class="sxs-lookup"><span data-stu-id="fcfae-109">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="fcfae-110">Nachdem die Kategorie erstellt wurde, können Sie Benutzer, OUs und Benutzergruppen aus der **AllowedMembers** -Liste der Kategorie als Chatroom-Manager und Mitglieder auswählen, um den Chatroom zu verwalten und daran teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="fcfae-110">After the category is created, they can choose users, OUs, and user groups from the category's **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="fcfae-111">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="fcfae-111">Tasks that you can perform</span></span>

<span data-ttu-id="fcfae-112">Auf der Seite **Zugelassene Mitglieder auswählen** können Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="fcfae-112">You can perform the following tasks on the **Select Allowed Members** page:</span></span>

- [<span data-ttu-id="fcfae-113">Configure Categories</span><span class="sxs-lookup"><span data-stu-id="fcfae-113">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="fcfae-114">New Persistent Chat Server Features</span><span class="sxs-lookup"><span data-stu-id="fcfae-114">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="fcfae-115">Details zu den verschiedenen Verfahren, die Sie mit der Skype for Business Server-Systemsteuerung ausführen können, finden Sie unter [Verwalten von Skype for Business Server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="fcfae-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="fcfae-116">So konfigurieren Sie Kategorien für Chatrooms</span><span class="sxs-lookup"><span data-stu-id="fcfae-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="fcfae-117">Fügen Sie unter **Mitgliedschaft**im Abschnitt **zulässige Mitglieder** Benutzer und andere Active Directory-Domänendienst Prinzipale (Benutzer, Verteilergruppen, Organisationseinheiten usw.) hinzu, die als Mitglieder von Chatrooms, die der Kategorie angehören, hinzugefügt werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="fcfae-117">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="fcfae-118">Prinzipale, die in einer Kategorie zugelassen sind, können nach den Räumen in der Kategorie suchen (es sei denn, der Raum ist ausgeblendet; in diesem Fall können nur Mitglieder des Raums im Verzeichnis danach suchen).</span><span class="sxs-lookup"><span data-stu-id="fcfae-118">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>


<span data-ttu-id="fcfae-119">Ausführliche Informationen zu den Features und Funktionen des beständigen Chat Servers finden Sie unter Übersicht über den [Server für beständigen Chat](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="fcfae-119">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="fcfae-120">Details zum Arbeiten mit beständigen Chat Serverkonfigurationen finden Sie unter [Konfigurieren des beständigen Chat Servers](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in der Bereitstellungsdokumentation und [Verwalten von lync Server 2013, beständiger Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="fcfae-120">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="fcfae-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fcfae-121">See also</span></span>

[<span data-ttu-id="fcfae-122">Understanding Persistent Chat Membership</span><span class="sxs-lookup"><span data-stu-id="fcfae-122">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
