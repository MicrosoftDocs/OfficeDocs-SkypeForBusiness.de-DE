---
title: Grundlegendes zur Mitgliedschaft im beständigen Chat
description: Grundlegendes zur Mitgliedschaft in beständigen Chat.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Understanding Persistent Chat membership
ms:assetid: 900392d6-6e9f-4dae-93d6-39d7474409ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398730(v=OCS.15)
ms:contentKeyID: 48184781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63e0d26ea56552d8906ab9a5cf216a7026868017
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579601"
---
# <a name="understanding-persistent-chat-membership"></a><span data-ttu-id="4395f-103">Grundlegendes zur Mitgliedschaft im beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="4395f-103">Understanding Persistent Chat membership</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4395f-104">_**Letztes Änderungsstand des Themas:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="4395f-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="4395f-105">Der Benutzer Zugriff auf beständige Chatrooms wird durch die Mitgliedschaft verwaltet. Benutzer müssen Mitglied eines Chatrooms sein, um Nachrichten Posten und lesen zu können.</span><span class="sxs-lookup"><span data-stu-id="4395f-105">User access to Persistent Chat rooms is managed by membership; users must be members of a chat room to be able to post and read messages.</span></span> <span data-ttu-id="4395f-106">Nur **Referenten** , die über eine bestimmte Zugehörigkeit mit Chatrooms verfügen, können das **Posting in Auditorium**-Chatrooms verwenden.</span><span class="sxs-lookup"><span data-stu-id="4395f-106">Only **Presenters** who have a designated affiliation with chat rooms are allowed to use **Posting to Auditorium rooms**.</span></span> <span data-ttu-id="4395f-107">Ein Auditorium ist eine Art Chatroom (der andere ist **Normal**), wo nur Referenten Posten können und jeder lesen kann.</span><span class="sxs-lookup"><span data-stu-id="4395f-107">An auditorium is a type of chat room (the other is **Normal**), where only Presenters can post and everyone can read.</span></span>

<span data-ttu-id="4395f-108">Darüber hinaus werden die Räume für beständigen Chatrooms unter den Regeln einer Kategorie ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4395f-108">In addition, Persistent Chat rooms operate under the rules of a category.</span></span> <span data-ttu-id="4395f-109">Ausführliche Informationen zu Kategorien finden Sie unter [Verwalten von Kategorien, Räumen und Add-Ins in lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md)sowie in den Abschnitten "How Category Scoping Works" und "Room category Strategies" weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="4395f-109">For details about categories, see [Managing categories, rooms, and add-ins in Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md), and also the sections "How Category Scoping Works" and "Room Category Strategies" later in this topic.</span></span>

<span data-ttu-id="4395f-110">Ein Administrator für beständigen Chat kann Chat Raumkategorien erstellen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="4395f-110">A Persistent Chat administrator can create and manage chat room categories.</span></span> <span data-ttu-id="4395f-111">Im Rahmen der Erstellung und Verwaltung von Chatroom-Kategorien kann der Administrator für beständigen Chat Prinzipale (Active Directory-Domänendienste Gruppen, Container und Benutzer) konfigurieren, die Zugriff auf Mitglieder oder Ersteller von Chatrooms einer bestimmten Kategorie haben.</span><span class="sxs-lookup"><span data-stu-id="4395f-111">As part of creating and managing chat room categories, the Persistent Chat administrator can configure principals (Active Directory Domain Services groups, containers, and users) that have access to be members or creators of chat rooms of a particular category.</span></span>

<div>

## <a name="active-directory-domain-services-and-persistent-chat"></a><span data-ttu-id="4395f-112">Active Directory-Domänendienste und beständiger Chat</span><span class="sxs-lookup"><span data-stu-id="4395f-112">Active Directory Domain Services and Persistent Chat</span></span>

<span data-ttu-id="4395f-113">Der Server für beständigen Chat basiert auf Active Directory für den Pool interner persistent Chat-Benutzer.</span><span class="sxs-lookup"><span data-stu-id="4395f-113">Persistent Chat Server relies on Active Directory for the pool of internal Persistent Chat users.</span></span> <span data-ttu-id="4395f-114">Nachdem Sie den beständigen Chat (Client) installiert haben, können Sie der raumkategorie Domänen von Benutzern und Benutzergruppen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="4395f-114">After you install Persistent Chat (client), you can add domains of users and user groups to the room category.</span></span> <span data-ttu-id="4395f-115">Sie können dann die Benutzer und Gruppen zur Mitgliedschaft Ihrer Chatroomkategorien hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="4395f-115">You can then add these users and groups to the membership of your room categories.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4395f-116">Sie müssen sicherstellen, dass für Benutzer, die Änderungen an Ihren beständigen Chatrooms vornehmen möchten, keine doppelten Namen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="4395f-116">You must ensure that there are no duplicate names for users who want to make changes to their Persistent Chat room(s).</span></span> <span data-ttu-id="4395f-117">Falls doppelte Benutzernamen vorhanden sind, ändern Sie diese in andere Namen, um die Sperrung der Änderungen durch diese Benutzer aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="4395f-117">If duplicate user names exist, change them to different names to unblock users from making those changes.</span></span> <span data-ttu-id="4395f-118">Wenn ein Benutzer in Active Directory doppelte Namen aufweist und versucht, Änderungen in den/den-Räumen vorzunehmen, wird eine Fehlermeldung angezeigt, in der der Benutzer aufgefordert wird, den Administrator zur Lösung zu kontaktieren.</span><span class="sxs-lookup"><span data-stu-id="4395f-118">If a user has duplicate names in Active Directory and tries to make changes in their room(s), an error message appears prompting the user to contact the administrator for resolution.</span></span>



</div>

</div>

<div>

## <a name="how-category-scoping-works"></a><span data-ttu-id="4395f-119">Funktionsweise von Bereichen in Kategorien</span><span class="sxs-lookup"><span data-stu-id="4395f-119">How Category Scoping Works</span></span>

<span data-ttu-id="4395f-120">Eine Kategorie gibt alle Benutzer und Gruppen an, die in einer Mitgliedschaftsliste eines beständigen Chatrooms in dieser Kategorie basierend auf der **AllowedMembers** -Eigenschaft Mitglieder sein können.</span><span class="sxs-lookup"><span data-stu-id="4395f-120">A category specifies all the users and groups that can be members in a membership list of a Persistent Chat room in that category, based on its **AllowedMembers** property.</span></span> <span data-ttu-id="4395f-121">Wenn Sie beispielsweise die **AllowedMembers** der Kategorie auf contoso.com festlegen, können Sie eine beliebige Gruppe oder einen Benutzer bei *contoso* als Mitglied zu Chatrooms in dieser Kategorie hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="4395f-121">For example, if you set the category’s **AllowedMembers** to contoso.com, you can add any group or user at *Contoso* as a member to chat rooms in that category.</span></span> <span data-ttu-id="4395f-122">Wenn Sie für die Eigenschaft **AllowedMembers** einer Kategorie *Sales* festlegen, können nur Gruppen und Benutzer dieser Verteilerliste als Mitglieder von Chatrooms in dieser Kategorie festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="4395f-122">If you set the **AllowedMembers** on a category to *Sales*, only groups and users in this distribution list can be added as members to chat rooms in that category.</span></span> <span data-ttu-id="4395f-123">Ähnlich können Sie mit der Eigenschaft **Creators** steuern, wer Chatrooms in der Kategorie erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="4395f-123">Similarly, the **Creators** property enables you to control who can create chat rooms in that category.</span></span> <span data-ttu-id="4395f-124">Nachdem der Chatroom erstellt wurde, können alle Mitglieder der Gruppe **AllowedMembers** als **Manager** für laufende Verwaltungsvorgänge für die Chatrooms festgelegt werden (z. B. Änderungen der Mitgliedschaft und Genehmigungen).</span><span class="sxs-lookup"><span data-stu-id="4395f-124">After the chat room is created, anyone from the **AllowedMembers** group can be designated as a **Manager** for ongoing management operations on the rooms (for example, membership changes and approvals).</span></span>

<span data-ttu-id="4395f-125">Das Definieren von **AllowedMembers** und **Creators** für eine Kategorie hat folgende Vorteile:</span><span class="sxs-lookup"><span data-stu-id="4395f-125">Defining **AllowedMembers** and **Creators** for a category has the following benefits:</span></span>

  - <span data-ttu-id="4395f-p107">Alle in dieser Kategorie enthaltenen Chatrooms unterliegen den auf Kategorieebene festgelegten Einschränkungen. Hierdurch können Sie Chatrooms auf der Grundlage von Unternehmensanforderungen und Zugangsrichtlinien isolieren.</span><span class="sxs-lookup"><span data-stu-id="4395f-p107">All chat rooms in this category are bound by the restrictions set at the category level. You can use this to segregate chat rooms based on business need and access policies.</span></span>

  - <span data-ttu-id="4395f-p108">Ein Benutzer, der in der Liste **Creators** vorhanden ist, kann in der Kategorie neue Chatrooms erstellen. Falls Sie ein System implementieren möchten, in dem nur eine beschränkt Anzahl Mitarbeiter der Organisation Chatrooms erstellen kann, können Sie dies nach diesem Verfahren realisieren.</span><span class="sxs-lookup"><span data-stu-id="4395f-p108">A user who is in the **Creators** list can create new chat rooms in that category. If you want to implement a system where a restricted number of personnel in the organization can create chat rooms, this control can be used to meet that requirement.</span></span>

</div>

<div>

## <a name="room-category-strategies"></a><span data-ttu-id="4395f-130">Strategien für Chatroomkategorien</span><span class="sxs-lookup"><span data-stu-id="4395f-130">Room Category Strategies</span></span>

<span data-ttu-id="4395f-131">Das **AllowedMembers** einer Kategorie muss alle Benutzer einschließen, die in dieser Kategorie einen beliebigen beständigen Chatroom verwenden sollen.</span><span class="sxs-lookup"><span data-stu-id="4395f-131">A category’s **AllowedMembers** must include all users who will use any Persistent Chat room in this category.</span></span> <span data-ttu-id="4395f-132">Abhängig von Ihren Anforderungen im Hinblick auf den Schutz von Geschäftsdaten und zur Sicherstellung der passenden Zugriffsebene können Sie eine oder mehrere Kategorien definieren, um festzulegen, wer in Chatrooms suchen und sich beteiligen kann.</span><span class="sxs-lookup"><span data-stu-id="4395f-132">Depending on your requirements to protect business data and ensure the appropriate level of access, you may want to define one or more categories to specify who can search and participate in rooms.</span></span> <span data-ttu-id="4395f-133">Wenn Sie nur einer bestimmten Gruppe von Benutzern (zentraler Helpdesk oder ausschließlich Vollzeitkräfte) erlauben möchten, Chatrooms zu erstellen, können Sie die **Creators** einer Kategorie entsprechend festlegen.</span><span class="sxs-lookup"><span data-stu-id="4395f-133">If you want to allow only a particular set of users (a central helpdesk, or only full-time employees) to create rooms, you can scope the **Creators** of a category to satisfy that requirement.</span></span>

<span data-ttu-id="4395f-p110">Kategorien können auch eingesetzt werden, um chinesische Mauern zu errichten. Chinesische Mauern verhindern das Auftreten von Interessenkonflikten in einer Organisation. Ein Administrator kann z. B. Chatrooms in einer Kategorie erstellen, die nur für Händler vorgesehen ist, während die Chatrooms in einer anderen Kategorie ausschließlich durch Analysten genutzt werden können.</span><span class="sxs-lookup"><span data-stu-id="4395f-p110">Categories can also be used to create ethical walls. Ethical walls prevent any conflict of interest in an organization. For example, an administrator can create chat rooms in a category for traders only, whereas chat rooms in another category can be used by analysts only.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4395f-137">In lync Server 2013 Server für beständigen Chat wird der Zugriff auf Partnerverbund Benutzer nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4395f-137">In Lync Server 2013, Persistent Chat Server, we do not support access to federated users.</span></span> <span data-ttu-id="4395f-138">Wenn in früheren Versionen des Servers für beständigen Chat Chats von Verbundbenutzern vorhanden sind, werden diese migriert.</span><span class="sxs-lookup"><span data-stu-id="4395f-138">If there are chats from federated users in previous versions of Persistent Chat Server, they will be migrated.</span></span> <span data-ttu-id="4395f-139">Die Partnerbenutzer werden als deaktivierte Prinzipale hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4395f-139">The federated users are added as disabled principals.</span></span>



</div>

</div>

<div>

## <a name="narrowing-the-members-to-user-groups"></a><span data-ttu-id="4395f-140">Beschränken der Mitglieder  auf Benutzergruppen</span><span class="sxs-lookup"><span data-stu-id="4395f-140">Narrowing the Members to User Groups</span></span>

<span data-ttu-id="4395f-141">Wenn Sie eine Domäne zu einer Kategorie hinzufügen, können Sie die Benutzergruppen, deren Gruppenobjekte in dieser Domäne enthalten sind, als Mitglieder von Chatrooms in der Kategorie festlegen.</span><span class="sxs-lookup"><span data-stu-id="4395f-141">When you add a domain to a category, the user groups whose group objects are contained in that domain are available to you so that you can specify them as members of rooms in that category.</span></span>

<span data-ttu-id="4395f-142">In der Regel wird empfohlen, Active Directory Container wie Domänen und Organisationseinheiten zum Definieren der **AllowedMembers** und **Ersteller**einer Kategorie zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4395f-142">We recommend, as a general rule, that you use Active Directory containers, such as domains and organizational units, for defining a category’s **AllowedMembers** and **Creators**.</span></span> <span data-ttu-id="4395f-143">Zur Liste der **AllowedMembers** oder der **Creators** können Objekte aus beliebigen Domänen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="4395f-143">You can add objects from any domain to an **AllowedMembers** or **Creators** list.</span></span> <span data-ttu-id="4395f-144">Ausschließlich Objekte, die in der Liste **AllowedMembers** oder **Creators** enthalten sind, können zu Chatrooms der entsprechenden Kategorie hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="4395f-144">Only objects within the **AllowedMembers** or **Creators** list can be added to rooms under that category.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

