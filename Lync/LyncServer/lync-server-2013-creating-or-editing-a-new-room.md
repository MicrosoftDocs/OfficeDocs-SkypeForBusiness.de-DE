---
title: 'Lync Server 2013: Erstellen oder Bearbeiten eines neuen Raums'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or editing a new room
ms:assetid: aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215880(v=OCS.15)
ms:contentKeyID: 48706008
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 564db7b9d1bfaab00e51628377f330da05af17e8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-or-editing-a-new-room-in-lync-server-2013"></a><span data-ttu-id="5708d-102">Erstellen oder Bearbeiten eines neuen Raums in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5708d-102">Creating or editing a new room in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5708d-103">_**Letztes Änderungsstand des Themas:** 2015-03-19_</span><span class="sxs-lookup"><span data-stu-id="5708d-103">_**Topic Last Modified:** 2015-03-19_</span></span>

<span data-ttu-id="5708d-104">Das Konfigurieren von beständigen Chatrooms wird häufig von Benutzern verarbeitet. ein Administrator für beständigen Chat konfiguriert oder verwaltet Chatrooms in der Regel nicht.</span><span class="sxs-lookup"><span data-stu-id="5708d-104">Configuring Persistent Chat rooms is commonly handled by users; a Persistent Chat administrator typically does not configure or manage chat rooms.</span></span> <span data-ttu-id="5708d-105">Windows PowerShell-Cmdlets zum Verwalten von Räumen stehen nur **"cspersistentchatadministrator"** -Administratoren zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="5708d-105">Windows PowerShell cmdlets to manage rooms are available only to **CsPersistentChatAdministrator** Administrators.</span></span>

<span data-ttu-id="5708d-106">Benutzer, die **Ersteller** in einer bestimmten Kategorie sind, können den lync-Client zum Erstellen und Verwalten von Räumen verwenden.</span><span class="sxs-lookup"><span data-stu-id="5708d-106">Users who are **Creators** in any given category can use the Lync client to create and manage rooms.</span></span> <span data-ttu-id="5708d-107">Benutzer, die für einen bestimmten Chatroom als Manager bestimmt wurden, können den Chatroom auch fortlaufend verwalten, indem sie beispielsweise dessen Eigenschaften oder Mitgliedschaften bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="5708d-107">Users who have been designated as managers for a specific chat room can also perform ongoing management of the room, such as editing the room properties or membership.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="5708d-108">Administratoren für beständigen Chat können auch Ersteller sein, und Sie unterliegen nicht den Einschränkungen, die den Erstellern auferlegt werden.</span><span class="sxs-lookup"><span data-stu-id="5708d-108">Persistent Chat administrators can also be Creators, and they are not subject to the restrictions placed on Creators.</span></span>



</div>

<span data-ttu-id="5708d-109">Optional können Sie als Administrator für beständigen Chat eine Benutzeroberfläche verwenden, um Chatrooms zu erstellen und zu verwalten, anstatt Windows PowerShell-Cmdlets zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="5708d-109">Optionally, if you are a Persistent Chat administrator, you can employ a user interface to create and manage chat rooms instead of using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="5708d-110">Aktivieren Sie dazu einen Administrator für den Server für beständigen Chat, und verwenden Sie dann den lync-Client zum Erstellen und Verwalten von Chatrooms.</span><span class="sxs-lookup"><span data-stu-id="5708d-110">To do this, SIP-enable an administrator for Persistent Chat Server, and then use the Lync client to create and manage chat rooms.</span></span>

<span data-ttu-id="5708d-111">Wenn Sie einen benutzerdefinierten Raum Verwaltungs Workflow für Ihre Benutzer erstellen möchten, können Sie die **RoomManagementUrl** -Eigenschaft für die Server Konfiguration für beständigen Chat festlegen, um Benutzer zu Ihrer benutzerdefinierten Lösung vom lync-Client umzuleiten.</span><span class="sxs-lookup"><span data-stu-id="5708d-111">If you want to create a custom room management workflow for your users, you can set the **RoomManagementUrl** property on your Persistent Chat Server configuration to redirect users to your custom solution from the Lync client.</span></span>

<span data-ttu-id="5708d-112">Ausführliche Informationen zum Konfigurieren von Chatrooms mithilfe der Befehlszeilenschnittstelle Windows PowerShell finden Sie unter "Raumverwaltung" im Thema [Konfigurieren des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="5708d-112">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="5708d-113">Ausführliche Informationen zum Konfigurieren von Chatrooms finden Sie unter [configure Rooms in lync Server 2013](lync-server-2013-configure-rooms.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="5708d-113">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5708d-114">Mit dem Server für beständigen Chat können Benutzer Chatrooms für eine bestimmte Website erstellen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="5708d-114">Persistent Chat Server lets users create and manage chat room for a specific site.</span></span> <span data-ttu-id="5708d-115">Benutzer können Chatrooms jedoch nicht an anderen Standorten innerhalb derselben Topologie erstellen oder verwalten.</span><span class="sxs-lookup"><span data-stu-id="5708d-115">Users cannot, however, create or manage chat rooms on other sites within the same topology.</span></span> <span data-ttu-id="5708d-116">Achten Sie darauf, die Ersteller und Manager für Chatrooms für alle Websites in Ihrer Organisation anzugeben.</span><span class="sxs-lookup"><span data-stu-id="5708d-116">Be sure to specify chat room Creators and Managers for all the sites in your organization.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="5708d-117">Benutzer, die in einer lync Server Survivable Branch Appliance verwaltet werden, können keine neuen Chatrooms erstellen oder die raumkarte für vorhandene Räume anzeigen.</span><span class="sxs-lookup"><span data-stu-id="5708d-117">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

