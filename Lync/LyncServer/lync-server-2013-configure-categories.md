---
title: 'Lync Server 2013: Konfigurieren von Kategorien'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure categories
ms:assetid: 4547f514-f0c0-404d-890f-092ddeeac852
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204859(v=OCS.15)
ms:contentKeyID: 48184033
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b808fff7a6356e437490a3f80a6f4f30b9a66801
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146488"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-categories-in-lync-server-2013"></a><span data-ttu-id="64c0e-102">Konfigurieren von Kategorien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64c0e-102">Configure categories in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64c0e-103">_**Letztes Änderungsstand des Themas:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="64c0e-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="64c0e-104">In lync Server 2013 Systemsteuerung können Sie den Abschnitt **Kategorie** der Seite für **beständigen Chat** verwenden, um Kategorien zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="64c0e-104">In Lync Server 2013 Control Panel, you can use the **Category** section of the **Persistent Chat** page to configure categories.</span></span> <span data-ttu-id="64c0e-105">Eine Kategorie für beständigen Chatroom ist eine logische Struktur zum Organisieren von Chatrooms.</span><span class="sxs-lookup"><span data-stu-id="64c0e-105">A Persistent Chat room category is a logical structure for organizing chat rooms.</span></span> <span data-ttu-id="64c0e-106">In einer Kategorie ist eine Standardgruppe von Zugriffssteuerungslisten (Access Control Lists, ACLs) zum Steuern der Benutzer und Benutzergruppen definiert, die zum Erstellen oder zum Beitreten zu Chatrooms berechtigt sind.</span><span class="sxs-lookup"><span data-stu-id="64c0e-106">A category defines a default set of access control lists (ACLs) for controlling the users and user groups who may create or join the chat rooms.</span></span> <span data-ttu-id="64c0e-107">Sie können Kategorien verwenden, um "Chinesische Mauern" zwischen verschiedenen Unterabteilungen der Organisationen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="64c0e-107">You can use categories enforce ethical walls between different subdivisions within their organizations.</span></span>

<span data-ttu-id="64c0e-108">Chatroomkategorien können Chatrooms enthalten, jedoch keine anderen Kategorien.</span><span class="sxs-lookup"><span data-stu-id="64c0e-108">Chat room categories may contain chat rooms, but not other categories.</span></span> <span data-ttu-id="64c0e-109">In jeder Kategorie wird der Inhalt mithilfe von Metadaten beschrieben, z. B. Name und Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="64c0e-109">Each category describes its contents with metadata, such as Name and Description.</span></span> <span data-ttu-id="64c0e-110">Zusätzlich verfügt die Kategorie über Eigenschaften, die festgelegt werden können, um das Verhalten der zur Kategorie gehörenden Chatrooms zu steuern, beispielsweise ob die Chatrooms Einladungen oder Dateiuploads zulassen oder einen Chatverlauf enthalten.</span><span class="sxs-lookup"><span data-stu-id="64c0e-110">In addition, the category has properties which can be set to control the behavior of the chat rooms belonging to it, such as if the chat rooms allow Invitations or File Uploads, or contain Chat History.</span></span>

<div>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="64c0e-111">So konfigurieren Sie Kategorien für Chatrooms</span><span class="sxs-lookup"><span data-stu-id="64c0e-111">To configure categories for chat rooms</span></span>

1.  <span data-ttu-id="64c0e-112">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsPersistentChatAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="64c0e-112">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="64c0e-113">Wählen Sie im **Startmenü** die lync Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die admin-URL ein.</span><span class="sxs-lookup"><span data-stu-id="64c0e-113">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="64c0e-114">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="64c0e-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="64c0e-115">Sie können auch Windows PowerShell-Cmdlets verwenden.</span><span class="sxs-lookup"><span data-stu-id="64c0e-115">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="64c0e-116">Ausführliche Informationen finden Sie unter <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Konfigurieren des Servers für beständigen Chat mit Windows PowerShell-Cmdlets</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="64c0e-116">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="64c0e-117">Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Kategorie**.</span><span class="sxs-lookup"><span data-stu-id="64c0e-117">In the left navigation bar, click **Persistent Chat**, and then click **Category**.</span></span>
    
    <span data-ttu-id="64c0e-118">Wählen Sie für mehrere Server Pool Bereitstellungen für beständigen Chat den entsprechenden Pool aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="64c0e-118">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4.  <span data-ttu-id="64c0e-119">Klicken Sie auf der Seite **Kategorie** auf **Neu** oder **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="64c0e-119">On the **Category** page, click **New** or **Edit**.</span></span>

5.  <span data-ttu-id="64c0e-120">Wählen Sie unter **Dienst auswählen**den Dienst aus, der dem Server Pool für beständigen Chat entspricht, in dem die Kategorie erstellt werden muss.</span><span class="sxs-lookup"><span data-stu-id="64c0e-120">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool on which the category needs to be created.</span></span> <span data-ttu-id="64c0e-121">Der Dienst ist der Server Pool für beständigen Chat, den der beständige Chat (Client) verwendet, um zu identifizieren, zu welchem Pool die Kategorie gehört.</span><span class="sxs-lookup"><span data-stu-id="64c0e-121">The service is the Persistent Chat Server pool that the Persistent Chat (client) uses to identify which pool the category belongs to.</span></span> <span data-ttu-id="64c0e-122">Eine Kategorie kann nur zu einem Server Pool für beständigen Chat gehören und kann nicht in einen anderen Pool verschoben oder in einen anderen Pool freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="64c0e-122">A category can belong to only one Persistent Chat Server pool, and cannot be moved to another one, or shared with another pool.</span></span>

6.  <span data-ttu-id="64c0e-123">Führen Sie unter **Neue Kategorie** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="64c0e-123">In **New Category**, do the following:</span></span>
    
    1.  <span data-ttu-id="64c0e-124">Geben Sie unter **Name** einen Namen für die neue Chatroomkategorie an.</span><span class="sxs-lookup"><span data-stu-id="64c0e-124">In **Name**, specify a name for the new room category.</span></span>
    
    2.  <span data-ttu-id="64c0e-125">Geben Sie unter **Beschreibung** eine ausführliche Beschreibung der Chatroomkategorie an (z. B. eine Chatroomkategorie für Contoso).</span><span class="sxs-lookup"><span data-stu-id="64c0e-125">In **Description**, provide a detailed description for the room category (for example, a room category for Contoso).</span></span>
    
    3.  <span data-ttu-id="64c0e-126">Aktivieren oder deaktivieren Sie das Kontrollkästchen **Einladungen aktivieren** , um zu steuern, ob Einladungen für Chatrooms, die zu dieser Kategorie gehören, aktiviert werden können.</span><span class="sxs-lookup"><span data-stu-id="64c0e-126">To control whether invitations can be enabled for chat rooms that belong to this category, select or clear the **Enable invitations** check box.</span></span> <span data-ttu-id="64c0e-127">Wenn diese Option aktiviert ist, können die Räume in dieser Kategorie Einladungen ein-oder ausschalten; Wenn diese Option deaktiviert ist, sind die Räume in dieser Kategorie nicht berechtigt, Einladungen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="64c0e-127">If selected, rooms in this category may have invitations on or off; if cleared, the rooms in this category are not allowed to have invitations.</span></span> <span data-ttu-id="64c0e-128">Wenn ein Raum Einladungen hat, wenn ein neues Mitglied einem Raum hinzugefügt wird, erhält er eine Benachrichtigung über den neuen Chatroom in seinem Client für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="64c0e-128">If a room has invitations on, when a new member is added to a room, he or she gets a notification of the new room in their Persistent Chat client.</span></span>
    
    4.  <span data-ttu-id="64c0e-p107">Um Dateiuploads in Chatrooms dieser Kategorie zu steuern, aktivieren bzw. deaktivieren Sie das Kontrollkästchen **Dateiupload aktivieren**. Ist diese Option aktiviert, können für die Chatrooms dieser Kategorie Dateiuploads aktiviert und deaktiviert werden. Ist die Option deaktiviert, sind Dateiuploads für die Chatrooms dieser Kategorie nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="64c0e-p107">To control file uploads in chat rooms belonging to this category, select or clear the **Enable file upload** check box. If selected, the rooms of this category can enable or disable file uploads; if cleared, the rooms of this category are not allowed to have file uploads.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="64c0e-131">Diese Einstellung wird auf dem Server erzwungen, da benutzerdefinierte Anwendungen oder frühere Gruppenchatclients, die Office Communications Server 2007 R2&nbsp;Gruppenchatserver oder lync Server 2010 verwenden, Gruppenchat Dateien in einem Chatroom bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="64c0e-131">This setting is enforced on the server because custom applications or previous Group Chat clients that use Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="64c0e-132">Der lync 2013-Client hat keine Dateiupload/Download-Funktion, wenn Sie also über eine reine lync 2013-Bereitstellung oder lync 2013-Client verfügen, ist es nicht möglich, Dateien in einem Chatroom für beständigen Chat Server bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="64c0e-132">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="64c0e-133">Aktivieren oder deaktivieren Sie das Kontrollkästchen **Chatverlauf aktivieren** , um Chatverlauf zu steuern.</span><span class="sxs-lookup"><span data-stu-id="64c0e-133">To control chat history, select or clear the **Enable chat history** check box.</span></span> <span data-ttu-id="64c0e-134">Wenn diese Option ausgewählt ist, werden Chatroom-Chats persistent; Andernfalls werden Chatnachrichten nicht dauerhaft gespeichert.</span><span class="sxs-lookup"><span data-stu-id="64c0e-134">If selected, room chats become persistent; otherwise, chat messages are not persisted.</span></span> <span data-ttu-id="64c0e-135">Wenn die Kompatibilität aktiviert ist, werden Chatrooms in Übereinstimmung gespeichert, aber die Benutzer können nicht auf ältere Nachrichten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="64c0e-135">If compliance is enabled, room chats will be saved in compliance, but users will not be able to access older messages.</span></span> <span data-ttu-id="64c0e-136">Diese Option kann für Räume verwendet werden, die für die Ad-hoc-Zusammenarbeit in Echtzeit vorgesehen sind und in denen kein Chatverlauf gespeichert werden muss.</span><span class="sxs-lookup"><span data-stu-id="64c0e-136">This option can be used for rooms designated for real-time, ad hoc collaborations that don’t need chat history to be persisted.</span></span>

7.  <span data-ttu-id="64c0e-137">Führen Sie unter **Kategorie bearbeiten** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="64c0e-137">In **Edit Category**, do the following:</span></span>
    
      - <span data-ttu-id="64c0e-138">Unter **Mitgliedschaft**können Sie im Abschnitt **zugelassene Mitglieder** Benutzer und andere Active Directory-Domänendienste Prinzipale (Benutzer, Verteilergruppen, Organisationseinheiten usw.) hinzufügen oder entfernen, die als Mitglieder von Chatrooms hinzugefügt werden dürfen, die zur Kategorie gehören.</span><span class="sxs-lookup"><span data-stu-id="64c0e-138">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="64c0e-139">Prinzipale, die in einer Kategorie zugelassen sind, können nach den Räumen in der Kategorie suchen (es sei denn, der Raum ist ausgeblendet, in diesem Fall können nur Mitglieder des Raums im Verzeichnis danach suchen).</span><span class="sxs-lookup"><span data-stu-id="64c0e-139">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>
    
      - <span data-ttu-id="64c0e-140">Fügen Sie unter **Mitgliedschaft**im Abschnitt **Abgelehnte Mitglieder** Benutzer und andere Active Directory Prinzipale hinzu, die Mitgliedern verweigert werden, die aus dem Chatroom abgelehnt werden.</span><span class="sxs-lookup"><span data-stu-id="64c0e-140">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>
    
      - <span data-ttu-id="64c0e-141">Fügen Sie unter **Mitgliedschaft**im Abschnitt **Ersteller** Benutzer und andere Active Directory Prinzipale hinzu, die Erstellern für die Kategorie zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="64c0e-141">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="64c0e-142">Ein Ersteller ist ein Benutzer, der Berechtigungen zum Erstellen von Chatrooms und zum Zuweisen von Chatroom-Managern und -mitgliedern besitzt.</span><span class="sxs-lookup"><span data-stu-id="64c0e-142">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>

8.  <span data-ttu-id="64c0e-143">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="64c0e-143">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

