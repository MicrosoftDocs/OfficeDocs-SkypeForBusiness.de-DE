---
title: Grundlegendes zur Mitgliedschaft beim beständigen Chat
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Understanding Persistent Chat membership
ms:assetid: 900392d6-6e9f-4dae-93d6-39d7474409ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398730(v=OCS.15)
ms:contentKeyID: 48184781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2b4eb5fbe4342c1bd6bcb3bbb842e076e5863ad
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741945"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-persistent-chat-membership"></a><span data-ttu-id="cf830-102">Grundlegendes zur Mitgliedschaft beim beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="cf830-102">Understanding Persistent Chat membership</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf830-103">_**Letztes Änderungsdatum des Themas:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="cf830-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="cf830-104">Der Benutzer Zugriff auf beständige Chatrooms wird von der Mitgliedschaft verwaltet. Benutzer müssen Mitglieder eines Chatrooms sein, um Nachrichten Posten und lesen zu können.</span><span class="sxs-lookup"><span data-stu-id="cf830-104">User access to Persistent Chat rooms is managed by membership; users must be members of a chat room to be able to post and read messages.</span></span> <span data-ttu-id="cf830-105">Nur **Referenten** , die über eine bestimmte Zugehörigkeit zu Chatrooms verfügen, dürfen **Beiträge in Auditorium**-Chatrooms verwenden.</span><span class="sxs-lookup"><span data-stu-id="cf830-105">Only **Presenters** who have a designated affiliation with chat rooms are allowed to use **Posting to Auditorium rooms**.</span></span> <span data-ttu-id="cf830-106">Bei einem Auditorium handelt es sich um eine Art Chatroom (der andere ist **Normal**), in dem nur Referenten Beiträge Posten können und jeder lesen kann.</span><span class="sxs-lookup"><span data-stu-id="cf830-106">An auditorium is a type of chat room (the other is **Normal**), where only Presenters can post and everyone can read.</span></span>

<span data-ttu-id="cf830-107">Darüber hinaus arbeiten beständige Chatrooms unter den Regeln einer Kategorie.</span><span class="sxs-lookup"><span data-stu-id="cf830-107">In addition, Persistent Chat rooms operate under the rules of a category.</span></span> <span data-ttu-id="cf830-108">Ausführliche Informationen zu Kategorien finden Sie unter [Verwalten von Kategorien, Räumen und Add-Ins in lync Server 2013 sowie in](lync-server-2013-managing-categories-rooms-and-add-ins.md)den Abschnitten "Funktionsweise der Kategorie" und "raumkategorie-Strategien" weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="cf830-108">For details about categories, see [Managing categories, rooms, and add-ins in Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md), and also the sections "How Category Scoping Works" and "Room Category Strategies" later in this topic.</span></span>

<span data-ttu-id="cf830-109">Ein beständiger Chat-Administrator kann Chatroom-Kategorien erstellen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="cf830-109">A Persistent Chat administrator can create and manage chat room categories.</span></span> <span data-ttu-id="cf830-110">Im Rahmen des Erstellens und Verwaltens von Chatroom-Kategorien kann der Administrator für beständigen Chat Prinzipale (Active Directory-Domänendienste, Gruppen, Container und Benutzer) konfigurieren, die Zugriff auf Mitglieder oder Ersteller von Chatrooms einer bestimmten Kategorie haben.</span><span class="sxs-lookup"><span data-stu-id="cf830-110">As part of creating and managing chat room categories, the Persistent Chat administrator can configure principals (Active Directory Domain Services groups, containers, and users) that have access to be members or creators of chat rooms of a particular category.</span></span>

<div>

## <a name="active-directory-domain-services-and-persistent-chat"></a><span data-ttu-id="cf830-111">Active Directory-Domänendienste und beständiger Chat</span><span class="sxs-lookup"><span data-stu-id="cf830-111">Active Directory Domain Services and Persistent Chat</span></span>

<span data-ttu-id="cf830-112">Der Server für beständigen Chat basiert auf Active Directory für den Pool interner beständiger Chat-Benutzer.</span><span class="sxs-lookup"><span data-stu-id="cf830-112">Persistent Chat Server relies on Active Directory for the pool of internal Persistent Chat users.</span></span> <span data-ttu-id="cf830-113">Nach der Installation des beständigen Chats (Client) können Sie der Kategorie Raum Domänen von Benutzern und Benutzergruppen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="cf830-113">After you install Persistent Chat (client), you can add domains of users and user groups to the room category.</span></span> <span data-ttu-id="cf830-114">Sie können diese Benutzer und Gruppen dann zur Mitgliedschaft in ihren Raumkategorien hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="cf830-114">You can then add these users and groups to the membership of your room categories.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cf830-115">Sie müssen sicherstellen, dass keine doppelten Namen für Benutzer vorhanden sind, die Änderungen an Ihren beständigen Chatrooms vornehmen möchten.</span><span class="sxs-lookup"><span data-stu-id="cf830-115">You must ensure that there are no duplicate names for users who want to make changes to their Persistent Chat room(s).</span></span> <span data-ttu-id="cf830-116">Wenn doppelte Benutzernamen vorhanden sind, ändern Sie Sie in verschiedene Namen, damit die Benutzer diese Änderungen nicht mehr vornehmen können.</span><span class="sxs-lookup"><span data-stu-id="cf830-116">If duplicate user names exist, change them to different names to unblock users from making those changes.</span></span> <span data-ttu-id="cf830-117">Wenn ein Benutzer in Active Directory doppelte Namen hat und versucht, Änderungen in seinen Räumen vorzunehmen, wird eine Fehlermeldung angezeigt, in der der Benutzer aufgefordert wird, den Administrator zur Lösung zu kontaktieren.</span><span class="sxs-lookup"><span data-stu-id="cf830-117">If a user has duplicate names in Active Directory and tries to make changes in their room(s), an error message appears prompting the user to contact the administrator for resolution.</span></span>



</div>

</div>

<div>

## <a name="how-category-scoping-works"></a><span data-ttu-id="cf830-118">Funktionsweise von Kategorie-Scoping</span><span class="sxs-lookup"><span data-stu-id="cf830-118">How Category Scoping Works</span></span>

<span data-ttu-id="cf830-119">Eine Kategorie gibt alle Benutzer und Gruppen an, die auf der Grundlage ihrer **AllowedMembers** -Eigenschaft Mitglieder in einer Mitgliederliste eines beständigen Chatrooms in dieser Kategorie sein können.</span><span class="sxs-lookup"><span data-stu-id="cf830-119">A category specifies all the users and groups that can be members in a membership list of a Persistent Chat room in that category, based on its **AllowedMembers** property.</span></span> <span data-ttu-id="cf830-120">Wenn Sie beispielsweise die **AllowedMembers** der Kategorie auf contoso.com festzulegen, können Sie eine beliebige Gruppe oder einen Benutzer bei *contoso* als Mitglied zu Chatrooms in dieser Kategorie hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="cf830-120">For example, if you set the category’s **AllowedMembers** to contoso.com, you can add any group or user at *Contoso* as a member to chat rooms in that category.</span></span> <span data-ttu-id="cf830-121">Wenn Sie das **AllowedMembers** für eine Kategorie auf *Sales*festzulegen, können nur Gruppen und Benutzer in dieser Verteilerliste als Mitglieder zu Chatrooms in dieser Kategorie hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="cf830-121">If you set the **AllowedMembers** on a category to *Sales*, only groups and users in this distribution list can be added as members to chat rooms in that category.</span></span> <span data-ttu-id="cf830-122">Auf ähnliche Weise können Sie mit der **Creators** -Eigenschaft steuern, wer Chatrooms in dieser Kategorie erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="cf830-122">Similarly, the **Creators** property enables you to control who can create chat rooms in that category.</span></span> <span data-ttu-id="cf830-123">Nach dem Erstellen des Chatrooms kann jeder aus der **AllowedMembers** -Gruppe als **Manager** für laufende Verwaltungsvorgänge in den Räumen (beispielsweise Mitgliedschaftsänderungen und Genehmigungen) festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="cf830-123">After the chat room is created, anyone from the **AllowedMembers** group can be designated as a **Manager** for ongoing management operations on the rooms (for example, membership changes and approvals).</span></span>

<span data-ttu-id="cf830-124">Das Definieren von **AllowedMembers** und **Erstellern** für eine Kategorie bietet die folgenden Vorteile:</span><span class="sxs-lookup"><span data-stu-id="cf830-124">Defining **AllowedMembers** and **Creators** for a category has the following benefits:</span></span>

  - <span data-ttu-id="cf830-125">Alle in dieser Kategorie enthaltenen Chatrooms unterliegen den auf Kategorieebene festgelegten Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="cf830-125">All chat rooms in this category are bound by the restrictions set at the category level.</span></span> <span data-ttu-id="cf830-126">Hierdurch können Sie Chatrooms auf der Grundlage von Unternehmensanforderungen und Zugangsrichtlinien isolieren.</span><span class="sxs-lookup"><span data-stu-id="cf830-126">You can use this to segregate chat rooms based on business need and access policies.</span></span>

  - <span data-ttu-id="cf830-127">Ein Benutzer, der sich in der Liste der **Ersteller** befindet, kann neue Chatrooms in dieser Kategorie erstellen.</span><span class="sxs-lookup"><span data-stu-id="cf830-127">A user who is in the **Creators** list can create new chat rooms in that category.</span></span> <span data-ttu-id="cf830-128">Wenn Sie ein System implementieren möchten, bei dem eine begrenzte Anzahl von Mitarbeitern in der Organisation Chatrooms erstellen kann, kann dieses Steuerelement verwendet werden, um diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="cf830-128">If you want to implement a system where a restricted number of personnel in the organization can create chat rooms, this control can be used to meet that requirement.</span></span>

</div>

<div>

## <a name="room-category-strategies"></a><span data-ttu-id="cf830-129">Strategien für Raumkategorien</span><span class="sxs-lookup"><span data-stu-id="cf830-129">Room Category Strategies</span></span>

<span data-ttu-id="cf830-130">Die **AllowedMembers** einer Kategorie müssen alle Benutzer umfassen, die in dieser Kategorie einen beliebigen beständigen Chatroom verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="cf830-130">A category’s **AllowedMembers** must include all users who will use any Persistent Chat room in this category.</span></span> <span data-ttu-id="cf830-131">Je nach Ihren Anforderungen, um Geschäftsdaten zu schützen und die angemessene Zugriffsebene zu gewährleisten, möchten Sie möglicherweise eine oder mehrere Kategorien definieren, um anzugeben, wer in Räumen suchen und daran teilnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="cf830-131">Depending on your requirements to protect business data and ensure the appropriate level of access, you may want to define one or more categories to specify who can search and participate in rooms.</span></span> <span data-ttu-id="cf830-132">Wenn Sie nur einer bestimmten Gruppe von Benutzern (einem zentralen Helpdesk oder nur Vollzeit-Mitarbeitern) das Erstellen von Räumen gestatten möchten, können Sie die **Ersteller** einer Kategorie so einrichten, dass diese Anforderung erfüllt wird.</span><span class="sxs-lookup"><span data-stu-id="cf830-132">If you want to allow only a particular set of users (a central helpdesk, or only full-time employees) to create rooms, you can scope the **Creators** of a category to satisfy that requirement.</span></span>

<span data-ttu-id="cf830-133">Kategorien können auch verwendet werden, um ethische Wände zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cf830-133">Categories can also be used to create ethical walls.</span></span> <span data-ttu-id="cf830-134">Ethische Mauern verhindern einen Interessenkonflikt in einer Organisation.</span><span class="sxs-lookup"><span data-stu-id="cf830-134">Ethical walls prevent any conflict of interest in an organization.</span></span> <span data-ttu-id="cf830-135">Beispielsweise kann ein Administrator Chatrooms in einer Kategorie nur für Händler erstellen, während Chatrooms in einer anderen Kategorie nur von Analysten verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="cf830-135">For example, an administrator can create chat rooms in a category for traders only, whereas chat rooms in another category can be used by analysts only.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cf830-136">In lync Server 2013, beständiger Chat Server, wird der Zugriff auf Verbundbenutzer nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cf830-136">In Lync Server 2013, Persistent Chat Server, we do not support access to federated users.</span></span> <span data-ttu-id="cf830-137">Wenn in früheren Versionen des beständigen Chat Servers Chats von Verbundbenutzern vorhanden sind, werden Sie migriert.</span><span class="sxs-lookup"><span data-stu-id="cf830-137">If there are chats from federated users in previous versions of Persistent Chat Server, they will be migrated.</span></span> <span data-ttu-id="cf830-138">Die Verbundbenutzer werden als deaktivierte Prinzipale hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="cf830-138">The federated users are added as disabled principals.</span></span>



</div>

</div>

<div>

## <a name="narrowing-the-members-to-user-groups"></a><span data-ttu-id="cf830-139">Einschränken der Mitglieder auf Benutzergruppen</span><span class="sxs-lookup"><span data-stu-id="cf830-139">Narrowing the Members to User Groups</span></span>

<span data-ttu-id="cf830-140">Wenn Sie einer Kategorie eine Domäne hinzufügen, stehen die Benutzergruppen, deren Gruppenobjekte in dieser Domäne enthalten sind, für Sie zur Verfügung, damit Sie Sie als Mitglieder von Räumen in dieser Kategorie angeben können.</span><span class="sxs-lookup"><span data-stu-id="cf830-140">When you add a domain to a category, the user groups whose group objects are contained in that domain are available to you so that you can specify them as members of rooms in that category.</span></span>

<span data-ttu-id="cf830-141">Wir empfehlen, dass Sie in der Regel Active Directory-Container wie Domänen und Organisationseinheiten verwenden, um **AllowedMembers** und **Creators**einer Kategorie zu definieren.</span><span class="sxs-lookup"><span data-stu-id="cf830-141">We recommend, as a general rule, that you use Active Directory containers, such as domains and organizational units, for defining a category’s **AllowedMembers** and **Creators**.</span></span> <span data-ttu-id="cf830-142">Sie können Objekte aus einer beliebigen Domäne zu einer **AllowedMembers** -oder **Creators** -Liste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="cf830-142">You can add objects from any domain to an **AllowedMembers** or **Creators** list.</span></span> <span data-ttu-id="cf830-143">Den Räumen unter dieser Kategorie können nur Objekte in der **AllowedMembers** -oder **Creators** -Liste hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="cf830-143">Only objects within the **AllowedMembers** or **Creators** list can be added to rooms under that category.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

