---
title: 'Lync Server 2013: Benutzerrollen auf dem Server für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User roles in Persistent Chat Server
ms:assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ676774(v=OCS.15)
ms:contentKeyID: 49361095
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c91fcb656d936d0fb469cdec4b01824d3fa97d1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518852"
---
# <a name="user-roles-in-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="ab991-102">Benutzerrollen auf dem Server für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab991-102">User roles in Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab991-103">_**Letztes Änderungsstand des Themas:** 2015-03-19_</span><span class="sxs-lookup"><span data-stu-id="ab991-103">_**Topic Last Modified:** 2015-03-19_</span></span>

<span data-ttu-id="ab991-104">Der Server für beständigen Chat stellt das Konzept der zulässigen/abgelehnten Mitglieder bereit, das auf Kategorien für beständigen Chat angewendet wird, und steuert, wer auf Räume in einer bestimmten Kategorie zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="ab991-104">Persistent Chat Server provides the concept of Allowed/Denied members, which applies to Persistent Chat categories and controls who can access rooms in a particular category.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ab991-105">Zugelassene/abgelehnte Mitglieder in einer Kategorie sind nicht identisch mit einer <STRONG>Mitglieder Rolle,</STRONG> die für einen beständigen Chatroom gilt.</span><span class="sxs-lookup"><span data-stu-id="ab991-105">Allowed/Denied members in a Category is not the same as a <STRONG>Member</STRONG> role, which applies to a Persistent Chat room.</span></span><BR><span data-ttu-id="ab991-p101">Bei Suchen werden alle geöffneten und geschlossenen Chatrooms angezeigt, für die sich der Benutzer, der die Suche durchführt, in der Liste der zulässigen/abgelehnten Mitglieder befindet. Geheime Chatrooms werden nur angezeigt, wenn der Benutzer, der die Suche durchführt, Mitglied des geheimen Chatrooms ist. Der Benutzer kann nur nach Chatrooms suchen, bei denen er bereits Mitglied ist oder für die er eine Mitgliedschaft anfordern kann.</span><span class="sxs-lookup"><span data-stu-id="ab991-p101">Searches display all open and closed chat rooms for which the user performing the search is in the Allowed/Denied member list. Secret rooms are not displayed unless the user who performs the search is a member of the secret room. The user can search only for rooms that he or she is already a member of, or those for which they can request membership.</span></span>



</div>

<span data-ttu-id="ab991-p102">Das primäre Grundprinzip für das Konzept der zulässigen/abgelehnten Mitglieder sind so genannte Chinesische Mauern. Beispielsweise ist es bei Banken und Finanzinstitutionen üblich, dass beim Implementieren von Richtlinien und Konventionen ethische Grenzen definiert werden, die verhindern, dass Händler und Analysten Mitteilungen und Informationen austauschen. Um dieser Anforderung nachzukommen, kann ein Administrator Kategorien erstellen, sodass in einer Kategorie Chatrooms von Händlern und in einer anderen Kategorie Chatrooms von Analysten erstellt und verwendet werden können. Wenn diese Einschränkung im System definiert ist, kann einem Chatroom kein Benutzer hinzugefügt werden, wenn die übergeordnete Kategorie dies verhindert.</span><span class="sxs-lookup"><span data-stu-id="ab991-p102">The primary rationale for the concept of Allowed/Denied Members is ethical walls. For example, it is common in banking and financial institutions to have ethical boundaries that prevent traders and analysts from sharing communications while implementing policies and conventions. To address this requirement, an administrator can create categories so that one category allows rooms to be created and used by traders, and another category allows rooms to be created and used by analysts. With this constraint is designed into the system prohibits adding a user as a member of the room if the parent category prevents it.</span></span>

<span data-ttu-id="ab991-113">Im folgenden sind die vier Benutzerrollen für beständigen Chat Server:</span><span class="sxs-lookup"><span data-stu-id="ab991-113">Following are the four user roles Persistent Chat Server:</span></span>

  - <span data-ttu-id="ab991-114">**Creator:** Benutzer mit Berechtigungen zum Erstellen von Chatrooms.</span><span class="sxs-lookup"><span data-stu-id="ab991-114">**Creator:** Users who have permissions to create chat rooms.</span></span> <span data-ttu-id="ab991-115">Diese Benutzer befinden sich in der Liste der Ersteller bestimmter Kategorien: Sie können Chatrooms in dieser Kategorie erstellen, und Sie können auch eine Mitgliedschaft entsprechend der Kategorie zuweisen und Managern die Verwaltung des Chatrooms zuweisen.</span><span class="sxs-lookup"><span data-stu-id="ab991-115">These users are in the Creators list of certain categories: they can create chat rooms in that category, and they can also assign membership according to the category, and assign managers to manage the chat room.</span></span> <span data-ttu-id="ab991-116">Der Benutzer, der einen Chatroom erstellt, wird automatisch als Manager des Chatrooms hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ab991-116">The user who creates a chat room is automatically added as a manager of the room.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ab991-p104">Als Ersteller besitzt ein Benutzer lediglich die Rechte zum Erstellen von Chatrooms. Durch die automatische Heraufstufung zum Manager erhält der Ersteller die Berechtigung, Mitgliedschaften, Manager usw. für die erstellten Chatdienste zu verfeinern.</span><span class="sxs-lookup"><span data-stu-id="ab991-p104">Being a Creator simply provides rights for creating chat rooms. It is the automatic promotion to Manager that enables the Creator to further refine memberships, managers, and so on, on the created chat services.</span></span>

    
    </div>
    
    <span data-ttu-id="ab991-119">Mit dieser Rolle können Sie steuern, wer die Chatrooms in Ihrer Organisation erstellt. Dies ist insbesondere praktisch, wenn Sie das Erstellen von Chatrooms zentral verwalten möchten, um Richtlinien und Konventionen zu erzwingen, und anschließend die Chatroomverwaltung an andere Benutzer in der Organisation delegieren möchten.</span><span class="sxs-lookup"><span data-stu-id="ab991-119">This role exists to give you the option of controlling who creates chat rooms in your organization, particularly if you want to centrally manage creating chat rooms to enforce policies and conventions, and subsequently delegate the chat room management to other users in the organization.</span></span>

  - <span data-ttu-id="ab991-120">**Manager:** Benutzer, die die Eigenschaften eines Chatrooms verwalten.</span><span class="sxs-lookup"><span data-stu-id="ab991-120">**Manager:** Users who manage properties of a chat room.</span></span> <span data-ttu-id="ab991-121">Chatroommanager können die Mitgliederliste ändern (Mitglieder hinzufügen und entfernen) und die Chatroommanager-Liste ändern (Manager hinzufügen und entfernen).</span><span class="sxs-lookup"><span data-stu-id="ab991-121">Chat room managers can modify the member list (add and remove members), and modify the chat room managers list (add and remove managers).</span></span> <span data-ttu-id="ab991-122">Chatroommanager können sich selbst der Mitglieder- oder Referentenliste (für ein Auditorium) hinzufügen, damit sie am Chatroom teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="ab991-122">Chat room managers can add themselves to the members or presenters list (for auditorium rooms) so they can participate in the chat room.</span></span> <span data-ttu-id="ab991-123">Chatroommanager können Chatrooms auch deaktivieren (Administratoren können deaktivierte Chatrooms abfragen und dauerhaft löschen).</span><span class="sxs-lookup"><span data-stu-id="ab991-123">Chat room managers can also disable chat rooms (administrators can query for disabled chat rooms and can permanently delete them).</span></span> <span data-ttu-id="ab991-124">Manager können bis auf die Chatroomkategorie alle Eigenschaften eines Chatrooms ändern.</span><span class="sxs-lookup"><span data-stu-id="ab991-124">Managers can change all the properties of a chat room, except the category of the chat room.</span></span> <span data-ttu-id="ab991-125">Nur der Administrator für beständigen Chat kann die Kategorie ändern, nachdem der Chatroom erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="ab991-125">Only the Persistent Chat Administrator can change the category after the chat room has been created.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ab991-126">Wenn der Manager in einer anderen Kategorie auch der Ersteller ist, kann der Manager die Kategorie in eine Kategorie ändern, für die eine Berechtigung zum Erstellen von Chatrooms besitzt.</span><span class="sxs-lookup"><span data-stu-id="ab991-126">If the manager is also a Creator in another category, he or she can change the category to one where they are authorized to create rooms.</span></span>

    
    </div>

  - <span data-ttu-id="ab991-127">**Mitglied:** Benutzer, die Mitglied eines Chatrooms sind.</span><span class="sxs-lookup"><span data-stu-id="ab991-127">**Member:** Users who are members of a chat room.</span></span> <span data-ttu-id="ab991-128">Diese Benutzer können die Chatrooms im Verzeichnis sehen (auch wenn der Chatroom geheim ist) sowie den Chatroom abonnieren (einschließlich der Metadaten-Optionen wie ungelesene Nachrichten, Ego-Filter und Stichwortfilter) und am Chatroom teilnehmen (kann Beitrag, es sei denn, der Raum ist ein hörsaalraum, in dem nur Referenten Beiträge veröffentlichen, Inhalte abrufen und suchen können).</span><span class="sxs-lookup"><span data-stu-id="ab991-128">These users can see the chat rooms in the directory (even if the chat room is secret), as well as subscribe to the chat room (including metadata options such as unread messages, ego filters, and keyword filters), and participate in the chat room (can post, unless the room is an auditorium room where only presenters can post, get content, and search).</span></span> <span data-ttu-id="ab991-129">Benutzer, die nicht Mitglied des Chatrooms sind, können nach dem Chatroom suchen, wenn Sie sich in der Liste zugelassene Mitglieder der Kategorie befinden, müssen jedoch den Zugriff auf diese Chatrooms anfordern, um auf Inhalte zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="ab991-129">Users who aren’t members of the chat room can search for the chat room if they are in the Allowed Members list of the category, but need to request access to join these chat rooms to access content.</span></span> <span data-ttu-id="ab991-130">(Es gibt keinen Anforderungs Zugriff oder keine Genehmigungen, die in das System integriert sind; diese werden extern per e-Mail, Telefon oder anderen Kontaktformen ausgeführt.)</span><span class="sxs-lookup"><span data-stu-id="ab991-130">(There is no request access or approvals built into the system; these are done externally by email, phone, or other forms of contact.)</span></span>

  - <span data-ttu-id="ab991-131">**Referent:** Benutzer, die in einem Auditorium-Raum Posten können.</span><span class="sxs-lookup"><span data-stu-id="ab991-131">**Presenter:** Users who can post to an auditorium room.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ab991-132">Mit dem Server für beständigen Chat können Benutzer Chatrooms für eine bestimmte Website erstellen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="ab991-132">Persistent Chat Server lets users create and manage chat room for a specific site.</span></span> <span data-ttu-id="ab991-133">Benutzer können Chatrooms jedoch nicht an anderen Standorten innerhalb derselben Topologie erstellen oder verwalten.</span><span class="sxs-lookup"><span data-stu-id="ab991-133">Users cannot, however, create or manage chat rooms on other sites within the same topology.</span></span> <span data-ttu-id="ab991-134">Achten Sie darauf, die Ersteller und Manager für Chatrooms für alle Websites in Ihrer Organisation anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ab991-134">Be sure to specify chat room Creators and Managers for all the sites in your organization.</span></span>



</div>

<span data-ttu-id="ab991-135">Die folgenden Rollen sind Administratorrollen für den Server für beständigen Chat:</span><span class="sxs-lookup"><span data-stu-id="ab991-135">The following roles are administrator roles for Persistent Chat Server:</span></span>

  - <span data-ttu-id="ab991-136">**Administrator für beständigen Chat ("cspersistentchatadministrator"):** Dies ist eine neue Rolle für die Role-Based Zugriffssteuerung, um den Server für beständigen Chat zu verwalten und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="ab991-136">**Persistent Chat Administrator (CsPersistentChatAdministrator):** This is a new Role-Based Access Control (RBAC) role to administer and manage Persistent Chat Server.</span></span> <span data-ttu-id="ab991-137">Benutzer oder Sicherheitsgruppen, die als "cspersistentchatadministrator" festgelegt sind, können den Server für beständigen Chat verwalten, indem Sie Windows PowerShell-Cmdlets Remote verwenden (also von einem anderen Computer als dem Server für beständigen Chat).</span><span class="sxs-lookup"><span data-stu-id="ab991-137">Users or security groups designated as CsPersistentChatAdministrator are able administer Persistent Chat Server by using Windows PowerShell cmdlets remotely (that is, from a computer other than the Persistent Chat Server).</span></span> <span data-ttu-id="ab991-138">Der Server für beständigen Chat überprüft, ob der Administrator für beständigen Chat Mitglied der lokalen Gruppe RTC Local Administrator auf dem Server für beständigen Chat ist Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="ab991-138">Persistent Chat Server checks that the Persistent Chat Administrator is member of the RTC Local administrator local group on the Persistent Chat Server Front End Server.</span></span>
    
    <span data-ttu-id="ab991-139">Die "cspersistentchatadministrator"-Rolle kann Chatrooms verwalten (alle Eigenschaften einschließlich Mitgliedschaft, Manager, Kategorien, Kennzeichen von Räumen als deaktiviert) sowie Chatroom-Kategorien erstellen und verwalten, die definieren, wer Chatrooms erstellen und auf Sie zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="ab991-139">The CsPersistentChatAdministrator role can manage chat rooms (modify all properties including membership, managers, categories, mark rooms as disabled), as well as create and manage chat room categories that define who can create and access chat rooms.</span></span> <span data-ttu-id="ab991-140">Administratoren können Chatrooms auch als deaktiviert kennzeichnen und Chatrooms bereinigen, die nicht mehr aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="ab991-140">Administrators can also mark chat rooms as disabled and clean up chat rooms that are no longer active.</span></span> <span data-ttu-id="ab991-141">Administratoren unterliegen nicht den Einschränkungen der Ersteller oder zugelassenen Mitglieder.</span><span class="sxs-lookup"><span data-stu-id="ab991-141">Administrators are not subject to the Creators or Allowed Members restrictions.</span></span> <span data-ttu-id="ab991-142">Administratoren können alle Arten von Chatrooms erstellen und sich selbst als Mitglied in Chatrooms hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ab991-142">Administrators can create any kind of chat room and add themselves as a member to any chat room.</span></span> <span data-ttu-id="ab991-143">Administratoren können auch die Konfiguration beständiger Chats ändern und verwalten (Pooleigenschaften, globale Einstellungen und Kompatibilitäts Konfiguration), und Sie können auch die Migration von einer älteren Gruppen Chat Server-Bereitstellung zu beständiger Chat von lync Server 2013 Server planen und implementieren.</span><span class="sxs-lookup"><span data-stu-id="ab991-143">Administrators can also modify and manage Persistent Chat configuration (pool properties, global settings, and compliance configuration) and can also plan and implement migration from an older Group Chat Server deployment to Lync Server 2013 Persistent Chat Server.</span></span>

  - <span data-ttu-id="ab991-144">**Lync-Administrator:** Gesamtunternehmens Administrator für lync Server 2013, die für die Bereitstellung zuständig sind.</span><span class="sxs-lookup"><span data-stu-id="ab991-144">**Lync Administrator:** Overall enterprise administrator for Lync Server 2013 responsible for deployment.</span></span>

  - <span data-ttu-id="ab991-145">**Operations Manager:** Benutzer, der für die Verwaltung von alltäglichen Vorgängen verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="ab991-145">**Operations Manager:** User responsible for managing day-to-day operations.</span></span>

  - <span data-ttu-id="ab991-146">**Drittanbieter-Entwickler und-Partner:** Drittanbieter erweitern das System, insbesondere die Bereitstellung einer ethischen Wandlösung für Gruppenunterhaltungen, Compliance-Support und-Tools, Web/Mobile-Clients und ein Framework für bot-Entwicklung.</span><span class="sxs-lookup"><span data-stu-id="ab991-146">**Third-party developers and partners:** Third-party developers extend the system, in particular providing an ethical wall solution for group conversations, compliance support and tools, web/mobile clients, and a framework for Bot development.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

