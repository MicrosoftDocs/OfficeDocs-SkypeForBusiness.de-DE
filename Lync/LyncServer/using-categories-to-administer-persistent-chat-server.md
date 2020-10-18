---
title: Verwenden von Kategorien zum Verwalten des Servers für beständigen Chat
description: Verwenden von Kategorien zum Verwalten des Servers für beständigen Chat.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Using categories to administer Persistent Chat Server
ms:assetid: dfcb3ad1-da90-467e-b08c-f4e68673b7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398988(v=OCS.15)
ms:contentKeyID: 48185628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 181ecba944a042e3598b2964ad233590cf63349e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579541"
---
# <a name="using-categories-to-administer-persistent-chat-server"></a><span data-ttu-id="108af-103">Verwenden von Kategorien zum Verwalten des Servers für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="108af-103">Using categories to administer Persistent Chat Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="108af-104">_**Letztes Änderungsstand des Themas:** 2013-10-01_</span><span class="sxs-lookup"><span data-stu-id="108af-104">_**Topic Last Modified:** 2013-10-01_</span></span>

<span data-ttu-id="108af-105">Die Server Bereitstellung für beständigen Chat kann viele gleichzeitige beständige Chatrooms hosten.</span><span class="sxs-lookup"><span data-stu-id="108af-105">Your Persistent Chat Server deployment can host many concurrent Persistent Chat rooms.</span></span> <span data-ttu-id="108af-106">Chatrooms können in Kategoriegruppen auf dem Server angeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="108af-106">Chat rooms can be organized into a set of categories on the server.</span></span> <span data-ttu-id="108af-107">Jeder Chatroom gehört einer Kategorie an und erbt Einstellungen von dieser Kategorie.</span><span class="sxs-lookup"><span data-stu-id="108af-107">Each chat room belongs to one category, and inherits some settings from that category.</span></span> <span data-ttu-id="108af-108">Diese Anordnung ergibt eine hilfreiche Struktur zum Identifizieren von Konversationen basierend auf ihrem geschäftlichen Anlass und ermöglicht die delegierte Administration und eine einfachere Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="108af-108">This organization creates a useful structure for identifying conversations, based on their business purpose, and facilitates delegated administration and simplified management.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="108af-109">Obwohl viele Verwaltungsfeatures von Chatrooms in Computern mit persistent Chat (lync-Client) für den Benutzer verfügbar sind, müssen Administratoren für beständigen Chat (in der <STRONG>"cspersistentchatadministrator"</STRONG> -Rolle) die lync Server-Systemsteuerung-oder Windows PowerShell-Cmdlets verwenden, um Kategorien zu erstellen oder zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="108af-109">Although many of the management features of chat rooms are available in computers running Persistent Chat (Lync client) for the user, Persistent Chat Administrators (in the <STRONG>cspersistentchatadministrator</STRONG> role) must use the Lync Server Control Panel or Windows PowerShell cmdlets to create or manage categories.</span></span>



</div>

<span data-ttu-id="108af-110">Administratoren für beständigen Chat verwenden lync Server-Systemsteuerung-oder Windows PowerShell-Cmdlets zum Erstellen und Verwalten von Kategorien und zum Entwerfen des Zugriffs für Chatrooms für die Benutzer in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="108af-110">Persistent Chat administrators use Lync Server Control Panel or Windows PowerShell cmdlets to create and manage categories, and to design access for chat rooms for the users in their organization.</span></span>

<span data-ttu-id="108af-111">Manager für beständigen Chatrooms, die die Möglichkeit haben, einen oder mehrere Chatrooms zu verwalten, können den lync-Client verwenden, um eine Raum Verwaltungsdienst-Webanwendung zum Erstellen und Verwalten von Räumen zu starten (oder Kunden können benutzerdefinierte Lösungen und Workflows erstellen, die aufgerufen werden).</span><span class="sxs-lookup"><span data-stu-id="108af-111">Persistent Chat room managers, who have the ability to manage one or more chat rooms, can use the Lync client to launch a room management Web application to create and manage rooms (or customers can create custom solutions and workflows to be invoked).</span></span> <span data-ttu-id="108af-112">Administratoren für beständigen Chat können auch lync Server-Systemsteuerung-oder Windows PowerShell-Cmdlets zum Erstellen und Verwalten von Räumen verwenden.</span><span class="sxs-lookup"><span data-stu-id="108af-112">Persistent Chat administrators can also use Lync Server Control Panel or Windows PowerShell cmdlets to create and manage rooms.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="108af-113">Ein beständiger Chatroom kann nicht den gleichen Namen wie eine Kategorie für beständigen Chat haben.</span><span class="sxs-lookup"><span data-stu-id="108af-113">A Persistent Chat room cannot have the same name as a Persistent Chat category.</span></span>



</div>

<span data-ttu-id="108af-p103">Chatroommanager können Änderungen an allen Chatroomeigenschaften vornehmen. Die Kategorie des Chatrooms können Sie jedoch nicht ändern. Sie können nicht am Ausführen der folgenden Aktionen gehindert werden:</span><span class="sxs-lookup"><span data-stu-id="108af-p103">Chat room managers can make changes to all chat room properties, except for changing the category of the room. They cannot be restricted from performing the following actions:</span></span>

  - <span data-ttu-id="108af-116">Deaktivieren eines Chatrooms</span><span class="sxs-lookup"><span data-stu-id="108af-116">Disabling a chat room</span></span>

  - <span data-ttu-id="108af-117">Ändern des Namens eines Chatrooms</span><span class="sxs-lookup"><span data-stu-id="108af-117">Changing a chat room name</span></span>

  - <span data-ttu-id="108af-118">Ändern der Beschreibung eines Chatrooms</span><span class="sxs-lookup"><span data-stu-id="108af-118">Changing a chat room description</span></span>

  - <span data-ttu-id="108af-119">Ändern des Chatroomtyps ("Auditorium" bzw. "Normal")</span><span class="sxs-lookup"><span data-stu-id="108af-119">Changing a chat room type (Auditorium versus Normal)</span></span>

  - <span data-ttu-id="108af-120">Ändern des Datenschutzes eines Chatrooms (offen, geschlossen bzw. geheim)</span><span class="sxs-lookup"><span data-stu-id="108af-120">Changing the privacy of a room (open versus closed versus secret)</span></span>

  - <span data-ttu-id="108af-121">Hinzufügen oder Entfernen von Mitgliedern</span><span class="sxs-lookup"><span data-stu-id="108af-121">Adding or removing members</span></span>

  - <span data-ttu-id="108af-122">Hinzufügen oder Entfernen von Chatroommanagern</span><span class="sxs-lookup"><span data-stu-id="108af-122">Adding or removing chat room managers</span></span>

  - <span data-ttu-id="108af-123">Hinzufügen oder Entfernen eines Add-Ins</span><span class="sxs-lookup"><span data-stu-id="108af-123">Adding or removing an add-in</span></span>

  - <span data-ttu-id="108af-124">Ändern von Einstellungen wie z. B. Einladungen (je nachdem, was durch die Kategorie zulässig ist)</span><span class="sxs-lookup"><span data-stu-id="108af-124">Changing settings such as invitations (according to what’s permitted by the category)</span></span>

<div>

## <a name="delegated-administration"></a><span data-ttu-id="108af-125">Delegierte Administration</span><span class="sxs-lookup"><span data-stu-id="108af-125">Delegated Administration</span></span>

<span data-ttu-id="108af-126">Das Erstellen und Verwalten von beständigen Chatrooms ist mit der korrekten Verwendung von Kategorien wesentlich einfacher.</span><span class="sxs-lookup"><span data-stu-id="108af-126">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="108af-127">Ein Administrator für beständigen Chat kann **AllowedMembers** und **Ersteller** für jede Kategorie definieren und kann auch die Standardeinstellungen und-Verhaltensweisen für Chatrooms definieren, die auf alle Chatrooms angewendet werden, die in der Kategorie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="108af-127">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="108af-128">Administratoren für beständigen Chat erstellen und Verwalten von Kategorien mithilfe von lync Server-Systemsteuerung-oder Windows PowerShell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="108af-128">Persistent Chat administrators create and manage categories by using Lync Server Control Panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="108af-129">Benutzer, Organisationseinheiten (Organizational Units, OUs) und Benutzergruppen, die als Ersteller der Kategorie identifiziert werden, sind die einzigen Personen und Gruppen, die Räume in der Kategorie erstellen dürfen.</span><span class="sxs-lookup"><span data-stu-id="108af-129">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="108af-130">Nachdem die Kategorie erstellt wurde, können Sie Benutzer, OUs und Benutzergruppen aus der **AllowedMembers** -Liste der Kategorie als Chatroommanager und Mitglieder zur Verwaltung und Teilnahme am Chatroom auswählen.</span><span class="sxs-lookup"><span data-stu-id="108af-130">After the category is created, they can choose users, OUs, and user groups from the category’s **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

<span data-ttu-id="108af-131">Chatrooms, die in einer Kategorie erstellt werden, erfüllen die von der Kategorie erzwungenen Richtlinien und Einstellungen (z. B. wer Mitglied beim Chatroom sein kann, wer den Chatroom verwalten kann, ob Dateiuploads zulässig sind, ob Einladungen versendet werden usw.).</span><span class="sxs-lookup"><span data-stu-id="108af-131">Chat rooms that are created in a category adhere to the policies and settings enforced by the category (such as who can be in the room’s membership, who can manage the room, whether file uploads are allowed, whether invitations are sent, and so on).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

