---
title: Verwalten von Chatrooms im Server für beständigen Chat in Skype for Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: 'Zusammenfassung: Informationen Sie zum Verwalten von Chatrooms in Skype Persistent Chat Server for Business Server 2015.'
ms.openlocfilehash: fd927e3a54f1f3a8df429677f481ea224534b984
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="e2802-103">Verwalten von Chatrooms im Server für beständigen Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e2802-103">Manage chat rooms in Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e2802-104">**Zusammenfassung:** Informationen Sie zum Verwalten von Chatrooms in Skype Persistent Chat Server for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e2802-104">**Summary:** Learn how to manage Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="e2802-105">Chatrooms können mit der Verwendung der richtigen Kategorien viel einfacher erstellt und verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="e2802-105">Creating and managing chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="e2802-106">Eine Kategorie definiert, die erstellen oder die Chatrooms beitreten können.</span><span class="sxs-lookup"><span data-stu-id="e2802-106">A category defines who can create or join the chat rooms.</span></span> <span data-ttu-id="e2802-107">Bevor Sie versuchen, Chatrooms zu verwalten, müssen Sie unbedingt [Persistent Chatkategorien, Chatrooms, und Benutzerrollen in Skype für Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) und [Verwalten von Kategorien in Persistent Chat Server in Skype für Business Server 2015](categories.md)vertraut zu machen.</span><span class="sxs-lookup"><span data-stu-id="e2802-107">Before you attempt to manage chat rooms, be sure to read [Persistent chat categories, chat rooms, and user roles in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) and [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span>
  
<span data-ttu-id="e2802-108">Sie können konfigurieren und Verwalten von Chatrooms mithilfe der Windows PowerShell-Befehlszeilenschnittstelle oder mithilfe der Skype für Business-Client, wenn Sie ein Mitglied des Chatrooms sind.</span><span class="sxs-lookup"><span data-stu-id="e2802-108">You can configure and manage chat rooms by using the Windows PowerShell command-line interface, or by using the Skype for Business client if you are a member of the chat room.</span></span> <span data-ttu-id="e2802-109">In diesem Thema wird beschrieben, wie Sie Chatrooms mit der Befehlszeilenschnittstelle von Windows PowerShell verwalten.</span><span class="sxs-lookup"><span data-stu-id="e2802-109">This topic describes how to manage chat rooms by using the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="e2802-110">Zum Verwalten von Chatrooms mithilfe der Skype für Business-Client, finden Sie die Client-Hilfe.</span><span class="sxs-lookup"><span data-stu-id="e2802-110">If you want to manage chat rooms by using the Skype for Business client, see the client help.</span></span> 
  
<span data-ttu-id="e2802-111">Chatrooms kann eine der beiden folgenden Typen: Normal und Auditorium.</span><span class="sxs-lookup"><span data-stu-id="e2802-111">Chat rooms can be one of two types: Normal and Auditorium.</span></span> <span data-ttu-id="e2802-112">In einem normalen Chatroom können alle Mitglieder Nachrichten posten und lesen.</span><span class="sxs-lookup"><span data-stu-id="e2802-112">A Normal chat room allows all members to post and read messages.</span></span> <span data-ttu-id="e2802-113">Ein Auditorium ist eine Art von Chatroom, in der nur Referenten Inhalte posten, aber alle Mitglieder diese Inhalte lesen können.</span><span class="sxs-lookup"><span data-stu-id="e2802-113">An Auditorium is a type of chat room where only Presenters can post, but everyone can read.</span></span>
  
<span data-ttu-id="e2802-114">Es hängt von den jeweiligen Benutzerrollen ab, wer auf Chatrooms zugreifen und diese verwalten kann:</span><span class="sxs-lookup"><span data-stu-id="e2802-114">Who can access and manage chat rooms depends on user roles as follows:</span></span>
  
- <span data-ttu-id="e2802-115">Um Nachrichten posten und lesen zu können, müssen Benutzer Mitglied eines Chatrooms sein.</span><span class="sxs-lookup"><span data-stu-id="e2802-115">Users must be Members of a chat room to be able to post and read messages.</span></span>
    
- <span data-ttu-id="e2802-116">Referenten können Posts in Auditorium-Chatrooms veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="e2802-116">Presenters are allowed to post to Auditorium rooms.</span></span>
    
- <span data-ttu-id="e2802-117">Administratoren können frühere Inhalte aus jedem Chatroom löschen (z. B. Inhalte, die vor einem bestimmen Datum veröffentlicht wurden), um zu verhindern, dass die Datenbanken zu groß werden.</span><span class="sxs-lookup"><span data-stu-id="e2802-117">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large.</span></span> <span data-ttu-id="e2802-118">Sie können Nachrichten entfernen oder ersetzen, die für einen bestimmten Chatroom ungeeignet sind.</span><span class="sxs-lookup"><span data-stu-id="e2802-118">Administrators can also remove or replace messages that are considered inappropriate for a particular chat room.</span></span>
    
- <span data-ttu-id="e2802-119">Endbenutzer, einschließlich Autoren von Nachrichten, können keine Inhalte aus Chatrooms entfernen.</span><span class="sxs-lookup"><span data-stu-id="e2802-119">End users, including message authors, cannot delete content from any chat room.</span></span>
    
- <span data-ttu-id="e2802-120">Chatroommanager können Änderungen an allen Chatroomeigenschaften vornehmen, z. B. können sie einen Chatroom deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e2802-120">Chat room Managers can make changes to all chat room properties, including disabling rooms.</span></span> <span data-ttu-id="e2802-121">Manager können aber keine Chatrooms löschen oder die Kategorie eines Chatrooms ändern.</span><span class="sxs-lookup"><span data-stu-id="e2802-121">Managers cannot, however, delete a room, or change the category of a room.</span></span> 
    
- <span data-ttu-id="e2802-122">Nur Administratoren können Chatrooms löschen, nachdem diese erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="e2802-122">Only Administrators can delete a chat room after it has been created.</span></span>
    
<span data-ttu-id="e2802-123">Mithilfe der folgenden Windows PowerShell-Cmdlets können Sie Chatrooms konfigurieren und managen:</span><span class="sxs-lookup"><span data-stu-id="e2802-123">You can configure and manage chat rooms by using the following Windows PowerShell cmdlets:</span></span>
  

|<span data-ttu-id="e2802-124">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="e2802-124">**Cmdlet**</span></span>|<span data-ttu-id="e2802-125">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="e2802-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e2802-126">"New-cspersistentchatroom"</span><span class="sxs-lookup"><span data-stu-id="e2802-126">New-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="e2802-127">Erstellen eines neuen Chatrooms</span><span class="sxs-lookup"><span data-stu-id="e2802-127">Create a new chat room</span></span>  <br/> |
|<span data-ttu-id="e2802-128">"Set-cspersistentchatroom"</span><span class="sxs-lookup"><span data-stu-id="e2802-128">Set-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="e2802-129">Zum Konfigurieren der Einstellungen für einen vorhandenen Chatroom sowie zum Zuweisen von Benutzern und Benutzergruppen zum Chatroom</span><span class="sxs-lookup"><span data-stu-id="e2802-129">Configure settings for an existing room; assign users and user groups to the room</span></span>  <br/> |
|<span data-ttu-id="e2802-130">"Get-cspersistentchatroom"</span><span class="sxs-lookup"><span data-stu-id="e2802-130">Get-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="e2802-131">Abrufen von Informationen über Räume</span><span class="sxs-lookup"><span data-stu-id="e2802-131">Retrieve information about rooms</span></span>  <br/> |
|<span data-ttu-id="e2802-132">"Clear-cspersistentchatroom"</span><span class="sxs-lookup"><span data-stu-id="e2802-132">Clear-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="e2802-133">Löschen eines Chatrooms oder Löschen von Nachrichten in einem Chatroom</span><span class="sxs-lookup"><span data-stu-id="e2802-133">Clear a room or messages from a room</span></span>  <br/> |
|<span data-ttu-id="e2802-134">"Remove-cspersistentchatroom"</span><span class="sxs-lookup"><span data-stu-id="e2802-134">Remove-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="e2802-135">Entfernen eines Chatrooms</span><span class="sxs-lookup"><span data-stu-id="e2802-135">Remove a room</span></span>  <br/> |
|<span data-ttu-id="e2802-136">Remove-CsPersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="e2802-136">Remove-CsPersistentChatMessage</span></span>  <br/> |<span data-ttu-id="e2802-137">Entfernen von Nachrichten aus einem Chatroom</span><span class="sxs-lookup"><span data-stu-id="e2802-137">Remove messages from a room</span></span>  <br/> |
   
<span data-ttu-id="e2802-138">Mit dem Cmdlet **New-CsPersistentChatRoom** und dem Cmdlet **Set-CsPersistentChatRoom** können Sie einen vorhandenen Chatroom konfigurieren und beispielsweise Benutzer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e2802-138">You use the **New-CsPersistentChatRoom** cmdlet to create chat rooms and the **Set-CsPersistentChatRoom** cmdlet to configure an existing chat room, including adding users to the chat room.</span></span> <span data-ttu-id="e2802-139">Sie können die folgenden Parameter für Chatrooms konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="e2802-139">You can configure the following parameters for chat rooms:</span></span>
  
- <span data-ttu-id="e2802-140">Disabled: Zum Deaktivieren bzw.</span><span class="sxs-lookup"><span data-stu-id="e2802-140">Disabled.</span></span> <span data-ttu-id="e2802-141">Können Sie einen Chatroom aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e2802-141">Lets you disable or enable a chat room.</span></span> 
    
- <span data-ttu-id="e2802-142">Einladungen.</span><span class="sxs-lookup"><span data-stu-id="e2802-142">Invitations.</span></span> <span data-ttu-id="e2802-143">Können Sie aktivieren oder Deaktivieren von chatroomeinladungen, die verwendet werden, um Benutzer zu benachrichtigen, wenn sie als Chatroom-Mitglieder hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="e2802-143">Lets you enable or disable chat room invitations, which are used to notify users when they have been added as chat room members.</span></span> <span data-ttu-id="e2802-144">Die Standardeinstellung für Einladungen in erben, die verursacht den Chatroom treffen die Einstellung der Einladung auf die Kategorie, zu der es gehört konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="e2802-144">The default setting for invitations in inherit, which caused the chat room to adopt the invitation setting configured on the category it belongs to.</span></span> <span data-ttu-id="e2802-145">Konfigurieren von Einladungen ermöglicht Einstellung auf "false" auf der Ebene der Chatroom die Kategorie Einstellung außer Kraft gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="e2802-145">Configuring the invitations setting to false at the chat room level allows the category setting to be overridden.</span></span> 
    
- <span data-ttu-id="e2802-146">Datenschutz.</span><span class="sxs-lookup"><span data-stu-id="e2802-146">Privacy.</span></span> <span data-ttu-id="e2802-147">Gibt an, ob ein Chatroom öffnen, schließen oder geheimen Schlüssel ist.</span><span class="sxs-lookup"><span data-stu-id="e2802-147">Lets you specify whether a chat room is Open, Closed, or Secret.</span></span> <span data-ttu-id="e2802-148">Offene Chatrooms können durchsucht und von allen Benutzern zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="e2802-148">Open rooms can be searched and accessed by anyone.</span></span> <span data-ttu-id="e2802-149">Geschlossene Räume können von jeder Person durchsucht werden, jedoch nur von Mitgliedern zugegriffen werden können.</span><span class="sxs-lookup"><span data-stu-id="e2802-149">Closed rooms can be searched by anyone, but can be accessed only by members.</span></span> <span data-ttu-id="e2802-150">Geheimen Chatrooms können durchsucht und nur von Mitgliedern des Raums aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e2802-150">Secret rooms can be searched and accessed only by members of the room.</span></span> <span data-ttu-id="e2802-151">Standardmäßig ist jeder neuen Raums anfänglich als geschlossen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="e2802-151">By default, each new room is initially configured as Closed.</span></span>
    
- <span data-ttu-id="e2802-152">Geben Sie ein.</span><span class="sxs-lookup"><span data-stu-id="e2802-152">Type.</span></span> <span data-ttu-id="e2802-153">Gibt an, ob ein Chatroom einem normalen Raum, ist, der durch ein beliebiges Mitglied oder einem Auditorium, die nur von Referent übermittelten Nachrichten akzeptiert veröffentlichte Nachrichten akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="e2802-153">Lets you specify whether a chat room is a Normal room, which accepts messages posted by any member, or an Auditorium room, which accepts messages posted only by a Presenter.</span></span>
    
- <span data-ttu-id="e2802-154">Addin: Ermöglicht Ihnen, ein zuvor konfiguriertes Add-In mit einem Chatroom zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="e2802-154">Addin.</span></span> <span data-ttu-id="e2802-155">Auf diese Weise können Mitglieder während der Nutzung des Chatrooms URL-Inhalte anzeigen.</span><span class="sxs-lookup"><span data-stu-id="e2802-155">Lets you associate a previously configured add-in with a chat room, which allows URL content to be viewed by members while participating.</span></span>
    
<span data-ttu-id="e2802-156">Zusätzlich zu den oben genannten Parametern kann mit dem Cmdlet **"Set-cspersistentchatroom"** Zuweisen von Benutzern für den Chatroom wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e2802-156">In addition to the above parameters, the **Set-CsPersistentChatRoom** cmdlet lets you assign users to the chat room as follows:</span></span>
  
- <span data-ttu-id="e2802-157">Elemente des Objekts.</span><span class="sxs-lookup"><span data-stu-id="e2802-157">Members.</span></span> <span data-ttu-id="e2802-158">Die Mitgliedschaft für den Chatroom konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="e2802-158">Configures membership for the chat room.</span></span> <span data-ttu-id="e2802-159">Sie können hinzufügen oder Entfernen der betroffenen oder mehrere Mitglieder, die mit einem einzelnen Cmdlet durch die SIP-Adresse der Benutzer angeben.</span><span class="sxs-lookup"><span data-stu-id="e2802-159">You can add or remove either the individual or multiple members using a single cmdlet by specifying the SIP address of the users.</span></span> <span data-ttu-id="e2802-160">Damit Benutzer in einer Sammeloperation hinzugefügt werden können, können auch Active Directory-Organisationseinheiten oder Verteilergruppen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e2802-160">To allow users to be added in bulk, Active Directory organizational units or distribution groups can also be specified.</span></span>
    
- <span data-ttu-id="e2802-161">Manager.</span><span class="sxs-lookup"><span data-stu-id="e2802-161">Managers.</span></span> <span data-ttu-id="e2802-162">Hier können Sie den Chatroom Manager zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e2802-162">Lets you assign managers to the chat room.</span></span> <span data-ttu-id="e2802-163">Manager müssen die Berechtigungen, um die Mitgliedschaft eines Chatrooms zusammen mit anderen Einstellungen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="e2802-163">Managers have the permissions to define membership of a chat room along with other settings.</span></span>
    
- <span data-ttu-id="e2802-p114">Presenters: Ermöglicht Ihnen, einem Auditorium-Chatroom Referenten zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="e2802-p114">Presenters. Lets you assign presenters to an Auditorium chat room.</span></span> 
    
 <span data-ttu-id="e2802-166">Ausführliche Informationen zur Syntax, einschließlich aller Parameter finden Sie unter [Skype für Business Server 2015-Verwaltungsshell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="e2802-166">For details about syntax, including all parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  
## <a name="create-a-new-room"></a><span data-ttu-id="e2802-167">Einen neuen Chatroom erstellen</span><span class="sxs-lookup"><span data-stu-id="e2802-167">Create a new room</span></span>

<span data-ttu-id="e2802-168">Mit dem Cmdlet **New-CsPersistentChatRoom** können Sie einen neuen Chatroom erstellen.</span><span class="sxs-lookup"><span data-stu-id="e2802-168">You can create a new room by using the **New-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="e2802-169">Der folgende Befehl wird beispielsweise einen neuen Chatroom mit dem Namen "itchatroom" auf den Pool Atl-Cs-001.contoso.com erstellt. In diesem Beispiel wird die IT-Kategorie den Chatroom hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="e2802-169">For example, the following command creates a new chat room named ITChatRoom on the pool atl-cs-001.contoso.com. In this example, the chat room is added to the IT category:</span></span>
  
```
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

<span data-ttu-id="e2802-170">**Hinweis:** PersistentChatPoolFqdn ist nicht erforderlich, wenn eine der folgenden Bedingungen erfüllt ist:</span><span class="sxs-lookup"><span data-stu-id="e2802-170">**Note:** PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
  
- <span data-ttu-id="e2802-171">Nur ein Persistent Chat Server-Pool ist vorhanden.</span><span class="sxs-lookup"><span data-stu-id="e2802-171">There is only one Persistent Chat Server pool.</span></span>
    
- <span data-ttu-id="e2802-172">Sie stellen für die Kategorie einen Pool-FQDN bereit.</span><span class="sxs-lookup"><span data-stu-id="e2802-172">You provide a pool FQDN to the category.</span></span>
    
- <span data-ttu-id="e2802-173">Sie stellen einen Pool-FQDN zum Hinzufügen des Chatrooms bereit.</span><span class="sxs-lookup"><span data-stu-id="e2802-173">You provide a pool FQDN to adding the room.</span></span>
    
## <a name="configure-an-existing-room"></a><span data-ttu-id="e2802-174">Konfigurieren eines vorhandenen Chatrooms</span><span class="sxs-lookup"><span data-stu-id="e2802-174">Configure an existing room</span></span>

<span data-ttu-id="e2802-175">Sie können eine vorhandene Raum konfigurieren, mit dem Cmdlet **"Set-cspersistentchatroom"** .</span><span class="sxs-lookup"><span data-stu-id="e2802-175">You can configure an existing room by using the **Set-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="e2802-176">Dem folgenden Befehl wird beispielsweise user1 als Member und Referent und user2 als Manager, der die TestCat Auditorium-Chatrooms:</span><span class="sxs-lookup"><span data-stu-id="e2802-176">For example, the following command assigns user1 as a Member and Presenter, and user2 as a Manager, of the testCat Auditorium room:</span></span>
  
```
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 <span data-ttu-id="e2802-177">Mit dem folgenden Befehl werden beispielsweise alle Benutzer in der Organisationseinheit „NorthAmericaUsers“ in Active Directory zum Chatroom „NorthAmerica“ hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="e2802-177">The next example adds all the users from the NorthAmericaUsers OU in active Directory to the NorthAmerica chat room:</span></span>
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

<span data-ttu-id="e2802-178">Mit dem folgenden Befehl werden alle Mitglieder der Finanzdistributionsgruppe zum selben Chatroom hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="e2802-178">The next example adds all the members from the Finance distribution group to the same chat room:</span></span>
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a><span data-ttu-id="e2802-179">Deaktivieren oder Aktivieren eines Chatrooms</span><span class="sxs-lookup"><span data-stu-id="e2802-179">Disable or enable a room</span></span>

<span data-ttu-id="e2802-180">Wenn das Thema eines beständigen Chatrooms nicht mehr relevant ist, können Sie den Chatroom Benutzern zur Verfügung durch deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e2802-180">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="e2802-181">Wenn ein Chatroom deaktiviert wird, werden alle Mitglieder vom Chatroom getrennt.</span><span class="sxs-lookup"><span data-stu-id="e2802-181">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="e2802-182">Nach der Deaktivierung eines Chatrooms können Benutzer dem Chatroom nicht wieder beitreten und er wird auch nicht bei der Suche nach Chatrooms gefunden.</span><span class="sxs-lookup"><span data-stu-id="e2802-182">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>
  
<span data-ttu-id="e2802-183">Wenn Sie den Chatroom Verlauf weiterhin auftritt, wird der Inhalt beibehalten, wenn Chatrooms deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e2802-183">If the chat room's history persists, the content is preserved when the chat room is disabled.</span></span> <span data-ttu-id="e2802-184">Allerdings werden diese Inhalte in Suchvorgängen nicht angezeigt, solange der Chatroom deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e2802-184">However, that content will not appear in searches during the time that the chat room remains in a disabled state.</span></span> <span data-ttu-id="e2802-185">Wenn Sie den Chatroom später wieder aktivieren, können Benutzer nach Nachrichten suchen, die vor der Deaktivierung des Chatrooms bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="e2802-185">If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span> <span data-ttu-id="e2802-186">Informationen zum Konfigurieren von chatroomverlauf finden Sie unter [Verwalten von Kategorien in Persistent Chat Server in Skype für Business Server 2015](categories.md).</span><span class="sxs-lookup"><span data-stu-id="e2802-186">For information about configuring chat room history, see [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span> 
  
<span data-ttu-id="e2802-187">Wenn ein Chatroom deaktiviert wurde, bleiben die zugehörigen Mitgliederlisten und sonstigen Einstellungen erhalten.</span><span class="sxs-lookup"><span data-stu-id="e2802-187">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="e2802-188">Sie als Administrator können einen deaktivierten Chatroom wieder aktivieren und brauchen die Einstellungen dabei nicht manuell wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="e2802-188">As an administrator, you can enable a room that has been disabled, and you do not need to manually re-create the settings.</span></span>
  
<span data-ttu-id="e2802-189">Sie können einen Chatroom deaktivieren, indem Sie mithilfe des Cmdlets **"Set-cspersistentchatroom"** und den Parameter deaktiviert auf True festlegen:</span><span class="sxs-lookup"><span data-stu-id="e2802-189">You can disable a room by using the **Set-CsPersistentChatRoom** cmdlet and setting the Disabled parameter to True:</span></span>
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

<span data-ttu-id="e2802-190">Zum Aktivieren eines Chatrooms legen Sie den Parameter „Disabled“ auf „False“ fest:</span><span class="sxs-lookup"><span data-stu-id="e2802-190">To enable a chat room, set the Disabled parameter to False:</span></span>
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False

```

## <a name="get-information-about-rooms"></a><span data-ttu-id="e2802-191">Abrufen von Informationen über Räume</span><span class="sxs-lookup"><span data-stu-id="e2802-191">Get information about rooms</span></span>

<span data-ttu-id="e2802-192">Mithilfe des Cmdlets **Get-CsPersistentChatRoom** können Sie Informationen für die in Ihrer Organisation konfigurierten und verwendeten Chatrooms abrufen.</span><span class="sxs-lookup"><span data-stu-id="e2802-192">To get information about the rooms configured for use in your organization, you can use the **Get-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="e2802-193">Der folgende Befehl gibt Informationen zu allen Chatrooms zurück, die für die Verwendung in Ihrer Organisation konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="e2802-193">The following command returns information about all the chat rooms configured for use in the organization:</span></span>
  
```
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a><span data-ttu-id="e2802-194">Entfernen aller Inhalte aus einem Chatroom</span><span class="sxs-lookup"><span data-stu-id="e2802-194">Remove all content from a room</span></span>

<span data-ttu-id="e2802-p120">Mit dem Cmdlet **Clear-CsPersistentChatRoom** können Sie Inhalte aus einem Chatroom entfernen. Der folgende Befehl entfernt beispielsweise alle Inhalte aus dem Chatroom für beständigen Chat „ITChatRoom“, die dem Chatroom am oder vor dem 1. März 2015 hinzugefügt wurden:</span><span class="sxs-lookup"><span data-stu-id="e2802-p120">You can remove content from a room by using the **Clear-CsPersistentChatRoom** cmdlet. For example, the following command removes all the content from the Persistent Chat room ITChatRoom that was added to the room on or before March 1, 2015:</span></span>
  
```
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a><span data-ttu-id="e2802-197">Entfernen einer Nachricht aus einem Chatroom</span><span class="sxs-lookup"><span data-stu-id="e2802-197">Remove a message from a room</span></span>

<span data-ttu-id="e2802-p121">Mit dem Cmdlet **Remove-CsPersistentChatMessage** können Sie eine oder mehrere Nachrichten aus der Datenbank des beständigen Chats entfernen und optional durch eine Standardnachricht oder eine durch den Administrator bereitgestellte Nachricht ersetzen. Der folgende Befehl entfernt beispielsweise alle Nachrichten aus dem Chatroom „ITChatRoom“, die vom Benutzer „kenmyer@contoso.com“ gepostet wurden:</span><span class="sxs-lookup"><span data-stu-id="e2802-p121">You can remove one or more messages in the Persistent Chat database, and optionally replace the message with a default message or with an administrator-provided message, by using the **Remove-CsPersistentChatMessage** cmdlet. For example, the following command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@contoso.com:</span></span>
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="e2802-200">Mit diesem Beispiel werden alle entfernten Nachrichten durch den Hinweis ersetzt, dass die Nachricht nicht mehr verfügbar ist:</span><span class="sxs-lookup"><span data-stu-id="e2802-200">The next example replaces any removed messages with the note that the message is no longer available:</span></span>
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a><span data-ttu-id="e2802-201">Entfernen eines Chatrooms</span><span class="sxs-lookup"><span data-stu-id="e2802-201">Remove a room</span></span>

<span data-ttu-id="e2802-202">Mit dem Cmdlet **Remove-CsPersistentChatRoom** können Sie einen Chatroom entfernen.</span><span class="sxs-lookup"><span data-stu-id="e2802-202">You can remove a room by using the **Remove-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="e2802-203">Mit dem folgenden Befehl wird beispielsweise der Chatroom „RedmondChatRoom“ entfernt:</span><span class="sxs-lookup"><span data-stu-id="e2802-203">For example, the following command removes the chat room RedmondChatRoom:</span></span>
  
```
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a><span data-ttu-id="e2802-204">Verschieben eines Chatrooms von einer Kategorie in eine andere</span><span class="sxs-lookup"><span data-stu-id="e2802-204">Move a room from one category to another</span></span>

<span data-ttu-id="e2802-p122">Wenn ein Chatroommanager **Ersteller**-Berechtigungen in einer anderen Kategorie hat, kann er den Chatroom von einer Kategorie in eine andere verschieben. Der Chatroom wird dabei nicht gelöscht und neu erstellt, sondern die Verknüpfung mit der Datenbank wird geändert.</span><span class="sxs-lookup"><span data-stu-id="e2802-p122">If a chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another. The room is not deleted and recreated. It is a change of association within the database.</span></span>
  
<span data-ttu-id="e2802-p123">Chatroomkategorien sollten eher selten und nur mit Vorsicht geändert werden. Eine Kategorie legt die erlaubte Mitgliedschaft für einen Chatroom fest. Wenn also der Chatroom in eine andere Kategorie verschoben wird, werden alle Systemzugriffssteuerungslisten (SACLs) gelöscht, die von der neuen Kategorie nicht unterstützt werden. Wenn beispielsweise ein Benutzer Mitglied eines Chatrooms war und nun kein zugelassenes Mitglied der neuen Kategorie mehr ist, wird die Mitgliedschaft für den Chatroom geändert und der Benutzer aus diesem entfernt.</span><span class="sxs-lookup"><span data-stu-id="e2802-p123">Changing a chat room category should be done rarely and with caution. A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged. For example, if a user was a member of the room and is no longer an allowed member in the new category, the room membership will be modified and the user will be removed from the room.</span></span>
  

