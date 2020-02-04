---
title: Auswählen abgelehnter Mitglieder
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.SelectDeniedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c626b6b4-15f3-4a59-bb1d-55dc8c60f5cb
description: Ein beständiger Chat-Administrator kann Chatroom-Kategorien erstellen und verwalten. Im Rahmen des Erstellens und Verwaltens von Chatroom-Kategorien kann ein beständiger Chat-Administrator Prinzipale (Active Directory-Domänendienste-Gruppen/Container/Benutzer) konfigurieren, die Zugriff auf Mitglieder/Ersteller von Chatrooms einer bestimmten Kategorie haben. Ein beständiger Chat-Administrator kann auch DeniedMembers zu einer Kategorie hinzufügen, und diese werden explizite Ausschlüsse auf die Liste der zulässigen Listen. DeniedMembers außer Kraft setzen, was in AllowedMembers.
ms.openlocfilehash: c8b357abe49d794283b7165d9c5decdffaece275
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685881"
---
# <a name="select-denied-members"></a><span data-ttu-id="6b464-106">Auswählen abgelehnter Mitglieder</span><span class="sxs-lookup"><span data-stu-id="6b464-106">Select Denied Members</span></span>

<span data-ttu-id="6b464-107">Ein beständiger Chat-Administrator kann Chatroom-Kategorien erstellen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="6b464-107">A Persistent Chat Administrator can create and manage chat room categories.</span></span> <span data-ttu-id="6b464-108">Im Rahmen des Erstellens und Verwaltens von Chatroom-Kategorien kann ein beständiger Chat-Administrator Prinzipale (Active Directory-Domänendienste-Gruppen/Container/Benutzer) konfigurieren, die Zugriff auf Mitglieder/Ersteller von Chatrooms einer bestimmten Kategorie haben.</span><span class="sxs-lookup"><span data-stu-id="6b464-108">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory Domain Services groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="6b464-109">Ein beständiger Chat-Administrator kann auch DeniedMembers zu einer Kategorie hinzufügen, und diese werden explizite Ausschlüsse auf die Liste der zulässigen Listen.</span><span class="sxs-lookup"><span data-stu-id="6b464-109">A Persistent Chat Administrator can also add DeniedMembers to a category and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="6b464-110">DeniedMembers außer Kraft setzen, was in AllowedMembers.</span><span class="sxs-lookup"><span data-stu-id="6b464-110">DeniedMembers override what's in AllowedMembers.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="6b464-111">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="6b464-111">Tasks that you can perform</span></span>

<span data-ttu-id="6b464-112">Auf der Seite **Abgelehnte Mitglieder auswählen** können Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="6b464-112">You can perform the following tasks on the **Select Denied Members** page:</span></span>

- [<span data-ttu-id="6b464-113">Configure Categories</span><span class="sxs-lookup"><span data-stu-id="6b464-113">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="6b464-114">New Persistent Chat Server Features</span><span class="sxs-lookup"><span data-stu-id="6b464-114">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="6b464-115">Details zu den verschiedenen Verfahren, die Sie mit der Skype for Business Server-Systemsteuerung ausführen können, finden Sie unter [Verwalten von Skype for Business Server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="6b464-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="6b464-116">So konfigurieren Sie Kategorien für Chatrooms</span><span class="sxs-lookup"><span data-stu-id="6b464-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="6b464-117">Fügen Sie in der **Mitgliedschaft**im Abschnitt **Abgelehnte Mitglieder** Benutzer und andere Active Directory-Prinzipale hinzu, die Mitgliedern zugeordnet sind, die aus dem Chatroom verweigert werden.</span><span class="sxs-lookup"><span data-stu-id="6b464-117">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>


<span data-ttu-id="6b464-118">Ausführliche Informationen zu den Features und Funktionen des beständigen Chat Servers finden Sie unter Übersicht über den [Server für beständigen Chat](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="6b464-118">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="6b464-119">Details zum Arbeiten mit beständigen Chat Serverkonfigurationen finden Sie unter [Konfigurieren des beständigen Chat Servers](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in der Bereitstellungsdokumentation und [Verwalten von lync Server 2013, beständiger Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="6b464-119">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b464-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b464-120">See also</span></span>

[<span data-ttu-id="6b464-121">Understanding Persistent Chat Membership</span><span class="sxs-lookup"><span data-stu-id="6b464-121">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
