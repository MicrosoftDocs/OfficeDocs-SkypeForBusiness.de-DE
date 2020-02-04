---
title: Auswählen von Erstellern
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.SelectCreators
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f8d9ed6f-22ba-470e-b0b4-0da3cea5e961
description: Das Erstellen und verwalten beständiger Chatrooms ist mit der korrekten Verwendung von Kategorien viel einfacher. Ein beständiger Chat-Administrator kann AllowedMembers und Creators für jede Kategorie definieren und auch die Standardeinstellungen und-Verhaltensweisen für Chatrooms definieren, die auf alle Chatrooms angewendet werden, die in der Kategorie erstellt wurden. Beständige Chat-Administratoren erstellen und verwalten Kategorien mithilfe von Skype for Business Server Control Panel oder Windows PowerShell-Cmdlets.
ms.openlocfilehash: cfaa7531f4f2a401dd90dc9473409d301a2fbfa6
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41699640"
---
# <a name="select-creators"></a><span data-ttu-id="114e5-105">Auswählen von Erstellern</span><span class="sxs-lookup"><span data-stu-id="114e5-105">Select Creators</span></span>

<span data-ttu-id="114e5-106">Das Erstellen und verwalten beständiger Chatrooms ist mit der korrekten Verwendung von Kategorien viel einfacher.</span><span class="sxs-lookup"><span data-stu-id="114e5-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="114e5-107">Ein beständiger Chat-Administrator kann **AllowedMembers** und **Creators** für jede Kategorie definieren und auch die Standardeinstellungen und-Verhaltensweisen für Chatrooms definieren, die auf alle Chatrooms angewendet werden, die in der Kategorie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="114e5-107">A Persistent Chat administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="114e5-108">Beständige Chat-Administratoren erstellen und verwalten Kategorien mithilfe von Skype for Business Server Control Panel oder Windows PowerShell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="114e5-108">Persistent Chat administrators create and manage categories by using Skype for Business Server Control Panel or Windows PowerShell cmdlets.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="114e5-109">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="114e5-109">Tasks that you can perform</span></span>

<span data-ttu-id="114e5-110">Auf der Seite **Ersteller auswählen** können Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="114e5-110">You can perform the following tasks on the **Select Creators** page:</span></span>

- [<span data-ttu-id="114e5-111">Configure Categories</span><span class="sxs-lookup"><span data-stu-id="114e5-111">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="114e5-112">New Persistent Chat Server Features</span><span class="sxs-lookup"><span data-stu-id="114e5-112">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="114e5-113">Details zu den verschiedenen Verfahren, die Sie mit der Skype for Business Server-Systemsteuerung ausführen können, finden Sie unter [Verwalten von Skype for Business Server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="114e5-113">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="114e5-114">So konfigurieren Sie Kategorien für Chatrooms</span><span class="sxs-lookup"><span data-stu-id="114e5-114">To configure categories for chat rooms</span></span>

<span data-ttu-id="114e5-115">Fügen Sie unter **Mitgliedschaft**im Abschnitt **Creators** Benutzer und andere Active Directory-Prinzipale hinzu, die den Erstellern für die Kategorie zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="114e5-115">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="114e5-116">Ein Ersteller ist ein Benutzer, der Berechtigungen zum Erstellen von Chatrooms und zum Zuweisen von Chatroom-Managern und -mitgliedern besitzt.</span><span class="sxs-lookup"><span data-stu-id="114e5-116">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>



<span data-ttu-id="114e5-117">Ausführliche Informationen zu den Features und Funktionen des beständigen Chat Servers finden Sie unter Übersicht über den [Server für beständigen Chat](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="114e5-117">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="114e5-118">Details zum Arbeiten mit beständigen Chat Serverkonfigurationen finden Sie unter [Konfigurieren des beständigen Chat Servers](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in der Bereitstellungsdokumentation und [Verwalten von lync Server 2013, beständiger Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="114e5-118">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="114e5-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="114e5-119">See also</span></span>

[<span data-ttu-id="114e5-120">Understanding Persistent Chat Membership</span><span class="sxs-lookup"><span data-stu-id="114e5-120">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)

[<span data-ttu-id="114e5-121">Verwenden von Kategorien zum Verwalten des beständigen Chat Servers</span><span class="sxs-lookup"><span data-stu-id="114e5-121">Using Categories to Administer Persistent Chat Server</span></span>](https://technet.microsoft.com/library/dfcb3ad1-da90-467e-b08c-f4e68673b7b5.aspx)

[<span data-ttu-id="114e5-122">Verschieben eines Chatrooms von einer Kategorie in eine andere</span><span class="sxs-lookup"><span data-stu-id="114e5-122">Moving a Chat Room from One Category to Another</span></span>](https://technet.microsoft.com/library/7e93b8f6-5a18-4476-a432-3918e01bcfa6.aspx)

[<span data-ttu-id="114e5-123">Erstellen oder Bearbeiten eines neuen Chatrooms</span><span class="sxs-lookup"><span data-stu-id="114e5-123">Creating or Editing a New Room</span></span>](https://technet.microsoft.com/library/aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4.aspx)
