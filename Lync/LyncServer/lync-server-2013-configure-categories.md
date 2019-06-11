---
title: 'Lync Server 2013: Konfigurieren von Kategorien'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure categories
ms:assetid: 4547f514-f0c0-404d-890f-092ddeeac852
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204859(v=OCS.15)
ms:contentKeyID: 48184033
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 310d0b2e32c8a21f00e20593a408df260eb80e32
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-categories-in-lync-server-2013"></a><span data-ttu-id="94987-102">Konfigurieren von Kategorien in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94987-102">Configure categories in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94987-103">_**Letztes Änderungsdatum des Themas:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="94987-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="94987-104">In der lync Server 2013-Systemsteuerung können Sie auf der Seite "beständiger **Chat** " den Abschnitt " **Kategorie** " verwenden, um Kategorien zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="94987-104">In Lync Server 2013 Control Panel, you can use the **Category** section of the **Persistent Chat** page to configure categories.</span></span> <span data-ttu-id="94987-105">Eine beständige Chatroom-Kategorie ist eine logische Struktur zum Organisieren von Chatrooms.</span><span class="sxs-lookup"><span data-stu-id="94987-105">A Persistent Chat room category is a logical structure for organizing chat rooms.</span></span> <span data-ttu-id="94987-106">In einer Kategorie ist eine Standardgruppe von Zugriffssteuerungslisten (Access Control Lists, ACLs) zum Steuern der Benutzer und Benutzergruppen definiert, die zum Erstellen von oder zum Beitreten zu Chatrooms berechtigt sind.</span><span class="sxs-lookup"><span data-stu-id="94987-106">A category defines a default set of access control lists (ACLs) for controlling the users and user groups who may create or join the chat rooms.</span></span> <span data-ttu-id="94987-107">Sie können Kategorien verwenden, um „Chinesische Mauern“ zwischen verschiedenen Unterabteilungen der Organisationen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="94987-107">You can use categories enforce ethical walls between different subdivisions within their organizations.</span></span>

<span data-ttu-id="94987-108">Chatroomkategorien können Chatrooms enthalten, jedoch keine anderen Kategorien.</span><span class="sxs-lookup"><span data-stu-id="94987-108">Chat room categories may contain chat rooms, but not other categories.</span></span> <span data-ttu-id="94987-109">Jede Kategorie beschreibt ihren Inhalt mithilfe von Metadaten wie „Name“ und „Beschreibung“.</span><span class="sxs-lookup"><span data-stu-id="94987-109">Each category describes its contents with metadata, such as Name and Description.</span></span> <span data-ttu-id="94987-110">Zusätzlich verfügt die Kategorie über Eigenschaften, die festgelegt werden können, um das Verhalten der zur Kategorie gehörenden Chatrooms zu steuern, beispielsweise ob die Chatrooms Invitations oder File Uploads zulassen oder einen Chat History enthalten.</span><span class="sxs-lookup"><span data-stu-id="94987-110">In addition, the category has properties which can be set to control the behavior of the chat rooms belonging to it, such as if the chat rooms allow Invitations or File Uploads, or contain Chat History.</span></span>

<div>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="94987-111">So konfigurieren Sie Kategorien für Chatrooms</span><span class="sxs-lookup"><span data-stu-id="94987-111">To configure categories for chat rooms</span></span>

1.  <span data-ttu-id="94987-112">Melden Sie sich mit einem Benutzerkonto, das über die Rolle „CsPersistentChatAdministrator“ oder „CsAdministrator“ verfügt, bei einem Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="94987-112">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="94987-113">Wählen Sie im **Startmenü** die lync Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein.</span><span class="sxs-lookup"><span data-stu-id="94987-113">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="94987-114">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="94987-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="94987-115">Sie können auch Windows PowerShell-Cmdlets verwenden.</span><span class="sxs-lookup"><span data-stu-id="94987-115">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="94987-116">Ausführliche Informationen finden Sie unter Konfigurieren des beständigen <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Chat Servers mithilfe von Windows PowerShell</A> -Cmdlets in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="94987-116">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="94987-117">Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Kategorie**.</span><span class="sxs-lookup"><span data-stu-id="94987-117">In the left navigation bar, click **Persistent Chat**, and then click **Category**.</span></span>
    
    <span data-ttu-id="94987-118">Wählen Sie für die Bereitstellung mehrerer beständiger Chat Server Pools den entsprechenden Pool in der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="94987-118">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4.  <span data-ttu-id="94987-119">Klicken Sie auf der Seite **Kategorie** auf **Neu** oder auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="94987-119">On the **Category** page, click **New** or **Edit**.</span></span>

5.  <span data-ttu-id="94987-120">Wählen Sie in **Dienst auswählen**den Dienst aus, der dem Server Pool für beständigen Chat entspricht, auf dem die Kategorie erstellt werden muss.</span><span class="sxs-lookup"><span data-stu-id="94987-120">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool on which the category needs to be created.</span></span> <span data-ttu-id="94987-121">Bei dem Dienst handelt es sich um den Server Pool für beständigen Chat, den der beständige Chat (Client) verwendet, um zu ermitteln, zu welchem Pool die Kategorie gehört.</span><span class="sxs-lookup"><span data-stu-id="94987-121">The service is the Persistent Chat Server pool that the Persistent Chat (client) uses to identify which pool the category belongs to.</span></span> <span data-ttu-id="94987-122">Eine Kategorie kann nur einem beständigen Chat Server Pool angehören und kann nicht in eine andere Gruppe verschoben oder für einen anderen Pool freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="94987-122">A category can belong to only one Persistent Chat Server pool, and cannot be moved to another one, or shared with another pool.</span></span>

6.  <span data-ttu-id="94987-123">Führen Sie unter **Neue Kategorie** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="94987-123">In **New Category**, do the following:</span></span>
    
    1.  <span data-ttu-id="94987-124">Geben Sie unter **Name** einen Namen für die neue Raumkategorie an.</span><span class="sxs-lookup"><span data-stu-id="94987-124">In **Name**, specify a name for the new room category.</span></span>
    
    2.  <span data-ttu-id="94987-125">Geben Sie unter **Beschreibung** Einzelheiten über die Raumkategorie an (z. B. eine Raumkategorie für Contoso).</span><span class="sxs-lookup"><span data-stu-id="94987-125">In **Description**, provide a detailed description for the room category (for example, a room category for Contoso).</span></span>
    
    3.  <span data-ttu-id="94987-126">Wenn Sie steuern möchten, ob Einladungen für Chatrooms, die zu dieser Kategorie gehören, aktiviert werden können, aktivieren oder deaktivieren Sie das Kontrollkästchen **Einladungen aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="94987-126">To control whether invitations can be enabled for chat rooms that belong to this category, select or clear the **Enable invitations** check box.</span></span> <span data-ttu-id="94987-127">Wenn diese Option ausgewählt ist, können Chatrooms in dieser Kategorie möglicherweise Einladungen aktivieren oder deaktivieren. Wenn diese Option deaktiviert ist, dürfen die Räume in dieser Kategorie keine Einladungen haben.</span><span class="sxs-lookup"><span data-stu-id="94987-127">If selected, rooms in this category may have invitations on or off; if cleared, the rooms in this category are not allowed to have invitations.</span></span> <span data-ttu-id="94987-128">Wenn ein Raum Einladungen enthält, wenn ein neues Mitglied zu einem Raum hinzugefügt wird, erhält er eine Benachrichtigung über den neuen Chatroom in seinem beständigen Chat-Client.</span><span class="sxs-lookup"><span data-stu-id="94987-128">If a room has invitations on, when a new member is added to a room, he or she gets a notification of the new room in their Persistent Chat client.</span></span>
    
    4.  <span data-ttu-id="94987-p107">Um Dateiuploads in Chatrooms in dieser Kategorie zu kontrollieren, aktivieren oder deaktivieren Sie das Kontrollkästchen **Dateiupload aktivieren**. Wenn diese Option ausgewählt ist, können Sie für Räume in dieser Kategorie Dateiuploads aktivieren oder deaktivieren. Wenn sie nicht ausgewählt ist, sind für Räume in dieser Kategorie keine Dateiuploads zulässig.</span><span class="sxs-lookup"><span data-stu-id="94987-p107">To control file uploads in chat rooms belonging to this category, select or clear the **Enable file upload** check box. If selected, the rooms of this category can enable or disable file uploads; if cleared, the rooms of this category are not allowed to have file uploads.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="94987-131">Diese Einstellung wird auf dem Server erzwungen, da benutzerdefinierte Anwendungen oder vorherige Gruppen-Chat-Clients, die den Office Communications&nbsp;Server 2007 R2-Gruppen-Chat Server oder lync Server 2010 verwenden, Gruppen-Chat Dateien in einem Raum bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="94987-131">This setting is enforced on the server because custom applications or previous Group Chat clients that use Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="94987-132">Wenn Sie über eine reine lync 2013-Bereitstellung oder einen lync 2013-Client verfügen, ist der lync 2013-Client nicht in der Lage, Dateien in einem beständigen Chat Server-Chatroom zu Posten.</span><span class="sxs-lookup"><span data-stu-id="94987-132">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="94987-133">Aktivieren oder deaktivieren Sie das Kontrollkästchen Chat- **Protokoll aktivieren** , um das Chat-Protokoll zu kontrollieren.</span><span class="sxs-lookup"><span data-stu-id="94987-133">To control chat history, select or clear the **Enable chat history** check box.</span></span> <span data-ttu-id="94987-134">Wenn diese Option ausgewählt ist, werden Chatroom-Chats persistent; Andernfalls bleiben Chatnachrichten nicht erhalten.</span><span class="sxs-lookup"><span data-stu-id="94987-134">If selected, room chats become persistent; otherwise, chat messages are not persisted.</span></span> <span data-ttu-id="94987-135">Wenn Compliance aktiviert ist, werden Chatroom-Chats unter Compliance gespeichert, aber die Benutzer können nicht auf ältere Nachrichten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="94987-135">If compliance is enabled, room chats will be saved in compliance, but users will not be able to access older messages.</span></span> <span data-ttu-id="94987-136">Diese Option kann für Chatrooms verwendet werden, die für die Ad-hoc-Zusammenarbeit in Echtzeit vorgesehen sind und keine Beibehaltung des Chat-Verlaufs erforderlich machen.</span><span class="sxs-lookup"><span data-stu-id="94987-136">This option can be used for rooms designated for real-time, ad hoc collaborations that don’t need chat history to be persisted.</span></span>

7.  <span data-ttu-id="94987-137">Führen Sie unter **Kategorie bearbeiten** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="94987-137">In **Edit Category**, do the following:</span></span>
    
      - <span data-ttu-id="94987-138">Fügen Sie unter **Mitgliedschaft**im Abschnitt **zulässige Mitglieder** Benutzer und andere Active Directory-Domänendienst Prinzipale (Benutzer, Verteilergruppen, Organisationseinheiten usw.) hinzu, die als Mitglieder von Chatrooms hinzugefügt werden dürfen. gehören zur Kategorie.</span><span class="sxs-lookup"><span data-stu-id="94987-138">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="94987-139">Prinzipale, die in einer Kategorie zugelassen sind, können nach den Räumen in der Kategorie suchen (es sei denn, der Raum ist ausgeblendet; in diesem Fall können nur Mitglieder des Raums im Verzeichnis danach suchen).</span><span class="sxs-lookup"><span data-stu-id="94987-139">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>
    
      - <span data-ttu-id="94987-140">Fügen Sie in der **Mitgliedschaft**im Abschnitt **Abgelehnte Mitglieder** Benutzer und andere Active Directory-Prinzipale hinzu, die Mitgliedern zugeordnet sind, die aus dem Chatroom verweigert werden.</span><span class="sxs-lookup"><span data-stu-id="94987-140">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>
    
      - <span data-ttu-id="94987-141">Fügen Sie unter **Mitgliedschaft**im \*\*\*\* Abschnitt Creators Benutzer und andere Active Directory-Prinzipale hinzu, die den Erstellern für die Kategorie zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="94987-141">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="94987-142">Ein Ersteller ist ein Benutzer, der Berechtigungen zum Erstellen von Chatrooms und zum Zuweisen von Chatroom-Managern und -mitgliedern besitzt.</span><span class="sxs-lookup"><span data-stu-id="94987-142">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>

8.  <span data-ttu-id="94987-143">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="94987-143">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

