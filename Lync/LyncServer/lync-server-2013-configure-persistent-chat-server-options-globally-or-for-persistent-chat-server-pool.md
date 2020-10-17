---
title: 'Lync Server 2013: Konfigurieren von Optionen für den Server für beständigen Chat Global oder für den Serverpool für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Persistent Chat Server options globally or for Persistent Chat Server pool
ms:assetid: 1e8d5245-cd58-4aad-9a1c-35b24189bc40
ms:mtpsurl: https://technet.microsoft.com/library/JJ204731(v=OCS.15)
ms:contentKeyID: 48183581
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a9cadd23099dbcaee5c577705ca1c2e4bdf6c00
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520462"
---
# <a name="configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool-in-lync-server-2013"></a><span data-ttu-id="e7d55-102">Konfigurieren von Optionen für den Server für beständigen Chat Global oder für den Serverpool für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7d55-102">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7d55-103">_**Letztes Änderungsstand des Themas:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="e7d55-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="e7d55-104">In lync Server 2013 Systemsteuerung können Sie den Abschnitt **Konfiguration** für beständigen Chat auf der Seite **beständiger Chat** verwenden, um Einstellungen für beständigen Chat Global zu konfigurieren, auf denen Sie für alle Server Pools für beständigen Chat oder für einen bestimmten Serverpool für beständigen Chat gilt.</span><span class="sxs-lookup"><span data-stu-id="e7d55-104">In Lync Server 2013 Control Panel, you can use the **Persistent Chat Configuration** section of the **Persistent Chat** page to configure Persistent Chat settings globally where it applies to all Persistent Chat Server pools, or for a specific Persistent Chat Server pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e7d55-105">Um den Server für beständigen Chat zu konfigurieren und zu verwenden, müssen Sie zuerst den Topologie-Generator verwenden, um die Unterstützung für beständigen Chat Server zur Topologie hinzuzufügen und die Topologie dann zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="e7d55-105">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="e7d55-106">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Hinzufügen von beständigen Chat Servern zur Bereitstellung in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e7d55-106">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-persistent-chat-options-globally"></a><span data-ttu-id="e7d55-107">So konfigurieren Sie Optionen für beständigen Chat Global</span><span class="sxs-lookup"><span data-stu-id="e7d55-107">To configure Persistent Chat options globally</span></span>

1.  <span data-ttu-id="e7d55-108">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsPersistentChatAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="e7d55-108">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e7d55-109">Wählen Sie im **Startmenü** die lync Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die admin-URL ein.</span><span class="sxs-lookup"><span data-stu-id="e7d55-109">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="e7d55-110">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e7d55-110">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e7d55-111">Sie können auch Windows PowerShell-Cmdlets verwenden.</span><span class="sxs-lookup"><span data-stu-id="e7d55-111">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="e7d55-112">Ausführliche Informationen finden Sie unter <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Konfigurieren des Servers für beständigen Chat mit Windows PowerShell-Cmdlets</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e7d55-112">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="e7d55-113">Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Konfiguration für beständigen Chat**.</span><span class="sxs-lookup"><span data-stu-id="e7d55-113">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="e7d55-114">Klicken Sie auf der Seite **Konfiguration für beständigen Chat** auf **neu,** und klicken Sie dann auf **Websitekonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="e7d55-114">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e7d55-115">Wählen Sie diese Option aus, wenn die Konfiguration auf alle in der Website bereitgestellten Server Pools für beständigen Chat angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e7d55-115">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="e7d55-116">Klicken Sie auf <STRONG>Pool Konfiguration</STRONG> , wenn die Konfiguration auf einen bestimmten Server Pool für beständigen Chat angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e7d55-116">Click <STRONG>Pool Configuration</STRONG> if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>

    
    </div>

5.  <span data-ttu-id="e7d55-117">Wählen Sie unter **Standort auswählen**den Standort aus, der für die Server Standortkonfiguration für beständigen Chat konfiguriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="e7d55-117">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>

6.  <span data-ttu-id="e7d55-118">Führen Sie unter **Neue Konfiguration für beständigen Chat** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="e7d55-118">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="e7d55-p105">Geben Sie unter **Name** einen Namen für die neuen Konfigurationseinstellungen an. Standardmäßig ist der Standortname bereits vorhanden.</span><span class="sxs-lookup"><span data-stu-id="e7d55-p105">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
      - <span data-ttu-id="e7d55-p106">Definieren Sie unter **Standardchatverlauf** die Anzahl von Chatnachrichten, die für jeden Chatroom bei der ersten Anforderung verarbeitet werden. Der Standardwert lautet 30. Dies ist der globale Standardwert, und Administratoren können den Chatverlauf pro Kategorie deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e7d55-p106">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="e7d55-124">Der Server für beständigen Chat speichert diese Nachrichten im Arbeitsspeicher, wenn Sie also diese Anzahl erweitern, werden weitere Nachrichten zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="e7d55-124">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="e7d55-125">Sie können jederzeit auf Verlaufs Inhalte zugreifen, indem Sie die Suche durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="e7d55-125">You can always access historical content by search.</span></span> <span data-ttu-id="e7d55-126">Die Standardnummer bestimmt einfach die maximale Anzahl von Nachrichten, die Sie beim Herstellen einer Verbindung mit einem Chatroom anfänglich sehen.</span><span class="sxs-lookup"><span data-stu-id="e7d55-126">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="e7d55-p108">Wählen Sie unter **Maximale Dateigröße (KB)** die maximale Dateigröße für jeden Chatverlauf aus. Der Standardwert lautet 20 MB (20.000 KB). Dies ist die maximale Größe einer Datei, die in einen Chatroom des Systems hochgeladen werden kann (Dateiuploads werden jeweils über die Einstellung **Kategorie** aktiviert).</span><span class="sxs-lookup"><span data-stu-id="e7d55-p108">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="e7d55-130">Diese Einstellung wird auf dem Server erzwungen, da benutzerdefinierte Anwendungen oder frühere Gruppenchatclients, die Office Communications Server 2007 R2 &nbsp; Gruppenchatserver oder lync Server 2010 verwenden, Gruppenchat Dateien in einem Chatroom bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="e7d55-130">This setting is enforced on the server because custom applications or previous Group Chat clients using Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="e7d55-131">Der lync 2013-Client hat keine Dateiupload/Download-Funktion, wenn Sie also über eine reine lync 2013-Bereitstellung oder lync 2013-Client verfügen, ist es nicht möglich, Dateien in einem Chatroom für beständigen Chat Server bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="e7d55-131">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="e7d55-132">Wählen Sie unter **Grenzwert für Teilnehmer Aktualisierung**den Grenzwert für Teilnehmer Aktualisierungen aus.</span><span class="sxs-lookup"><span data-stu-id="e7d55-132">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="e7d55-133">Der Server für beständigen Chat sendet Dienstplan Informationen (die mit einem Chatroom verbunden sind) an alle Teilnehmer, bis die Anzahl der verbundenen Benutzer diese Nummer erreicht.</span><span class="sxs-lookup"><span data-stu-id="e7d55-133">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="e7d55-134">Standardmäßig lautet die Zahl 75.</span><span class="sxs-lookup"><span data-stu-id="e7d55-134">By default, the number is 75.</span></span> <span data-ttu-id="e7d55-135">Dieser Grenzwert gibt die maximale Anzahl von Teilnehmern in einem bestimmten Raum an, über die der Server für beständigen Chat hinaus aufhört, die Dienstplan Aktualisierungen an verbundene Clients zu senden, die sich im Chatroom befinden.</span><span class="sxs-lookup"><span data-stu-id="e7d55-135">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="e7d55-p111">(Optional) Wählen Sie unter **Raumverwaltungs-URL** die Raumverwaltungs-URL aus. Dies ist die URL für die webbasierte benutzerdefinierte Raumverwaltung. Wenn Sie die Raumverwaltung nicht anpassen müssen und lediglich die Standardeinstellung verwenden möchten, können Sie diese Option leer lassen. Nach dem Festlegen der URL wird diese sowohl als interne als auch als externe Raumverwaltungs-URL angewendet.</span><span class="sxs-lookup"><span data-stu-id="e7d55-p111">(Optional.) In **Room management URL**, select the room management URL. This is the URL for a web-based custom room management. If you don’t need to customize room management, and you simply use the default setting, leave this option blank. After the URL is set, it is applied as both the internal and external room management URL.</span></span>
        
        <span data-ttu-id="e7d55-140">Wenn Sie Ihre Raum Erstellungs Erfahrung anpassen und ihren spezifischen geschäftsworkflow einbeziehen möchten, können Sie eine benutzerdefinierte Raum Verwaltungslösung erstellen, indem Sie den Server für beständigen Chat Server Software Development Kit (SDK) verwenden, ihn irgendwo hosten und die URL hier einfügen.</span><span class="sxs-lookup"><span data-stu-id="e7d55-140">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="e7d55-141">Diese URL wird an den Client gesendet, sodass ein Benutzer, der versucht, einen Chatroom anzuzeigen oder zu erstellen, an die benutzerdefinierte Raum Verwaltungslösung weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="e7d55-141">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="e7d55-142">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e7d55-142">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="e7d55-143">So konfigurieren Sie Optionen für beständigen Chat für einen bestimmten Server Pool für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="e7d55-143">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

1.  <span data-ttu-id="e7d55-144">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsPersistentChatAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="e7d55-144">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e7d55-145">Wählen Sie im **Startmenü** die lync Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die admin-URL ein.</span><span class="sxs-lookup"><span data-stu-id="e7d55-145">From the **Start** menu, select the Lync Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="e7d55-146">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e7d55-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e7d55-147">Sie können auch Windows PowerShell-Cmdlets verwenden.</span><span class="sxs-lookup"><span data-stu-id="e7d55-147">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="e7d55-148">Ausführliche Informationen finden Sie unter <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Konfigurieren des Servers für beständigen Chat mit Windows PowerShell-Cmdlets</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e7d55-148">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="e7d55-149">Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Konfiguration für beständigen Chat**.</span><span class="sxs-lookup"><span data-stu-id="e7d55-149">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="e7d55-150">Klicken Sie auf der Seite **Konfiguration für beständigen Chat** auf **Neu** und dann auf **Poolkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="e7d55-150">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>

5.  <span data-ttu-id="e7d55-151">Wählen Sie unter **Dienst auswählen**den Dienst aus, der dem Server Pool für beständigen Chat zugeordnet ist, der konfiguriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="e7d55-151">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>

6.  <span data-ttu-id="e7d55-152">Führen Sie unter **Neue Konfiguration für beständigen Chat** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="e7d55-152">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="e7d55-p115">Geben Sie unter **Name** einen Namen für die neuen Konfigurationseinstellungen an. Standardmäßig ist der Standortpoolname bereits vorhanden.</span><span class="sxs-lookup"><span data-stu-id="e7d55-p115">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
      - <span data-ttu-id="e7d55-p116">Definieren Sie unter **Standardchatverlauf** die Anzahl von Chatnachrichten, die für jeden Chatroom bei der ersten Anforderung verarbeitet werden. Der Standardwert lautet 30. Dies ist der globale Standardwert, und Administratoren können den Chatverlauf pro Kategorie deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e7d55-p116">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="e7d55-158">Der Server für beständigen Chat speichert diese Nachrichten im Arbeitsspeicher, wenn Sie also diese Anzahl erweitern, werden weitere Nachrichten zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="e7d55-158">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="e7d55-159">Sie können jederzeit auf Verlaufs Inhalte zugreifen, indem Sie die Suche durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="e7d55-159">You can always access historical content by search.</span></span> <span data-ttu-id="e7d55-160">Die Standardnummer bestimmt einfach die maximale Anzahl von Nachrichten, die Sie beim Herstellen einer Verbindung mit einem Chatroom anfänglich sehen.</span><span class="sxs-lookup"><span data-stu-id="e7d55-160">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="e7d55-p118">Wählen Sie unter **Maximale Dateigröße (KB)** die maximale Dateigröße für jeden Chatverlauf aus. Der Standardwert lautet 20 MB (20.000 KB). Dies ist die maximale Größe einer Datei, die in einen Chatroom des Systems hochgeladen werden kann (Dateiuploads werden jeweils über die Einstellung **Kategorie** aktiviert).</span><span class="sxs-lookup"><span data-stu-id="e7d55-p118">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="e7d55-164">Diese Einstellung wird auf dem Server erzwungen, da benutzerdefinierte Anwendungen oder frühere Gruppenchatclients (Office Communications Server 2007 R2 &nbsp; Gruppenchatserver oder lync Server 2010, Gruppenchat) Dateien in einem Chatroom bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="e7d55-164">This setting is enforced on the server because custom applications or previous Group Chat clients (Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat) can post files to a room.</span></span> <span data-ttu-id="e7d55-165">Der lync 2013-Client hat keine Dateiupload/Download-Funktion, wenn Sie also über eine reine lync 2013-Bereitstellung oder lync 2013-Client verfügen, ist es nicht möglich, Dateien in einem Chatroom für beständigen Chat Server bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="e7d55-165">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="e7d55-166">Wählen Sie unter **Grenzwert für Teilnehmer Aktualisierung**den Grenzwert für Teilnehmer Aktualisierungen aus.</span><span class="sxs-lookup"><span data-stu-id="e7d55-166">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="e7d55-167">Der Server für beständigen Chat sendet Dienstplan Informationen (die mit einem Chatroom verbunden sind) an alle Teilnehmer, bis die Anzahl der verbundenen Benutzer diese Nummer erreicht.</span><span class="sxs-lookup"><span data-stu-id="e7d55-167">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="e7d55-168">Standardmäßig lautet die Zahl 75.</span><span class="sxs-lookup"><span data-stu-id="e7d55-168">By default, the number is 75.</span></span> <span data-ttu-id="e7d55-169">Dieser Grenzwert gibt die maximale Anzahl von Teilnehmern in einem bestimmten Raum an, über die der Server für beständigen Chat hinaus aufhört, die Dienstplan Aktualisierungen an verbundene Clients zu senden, die sich im Chatroom befinden.</span><span class="sxs-lookup"><span data-stu-id="e7d55-169">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="e7d55-p121">Wählen Sie unter **Raumverwaltungs-URL** die Raumverwaltungs-URL aus. Dies ist die URL für die webbasierte Bereitstellung der Raumverwaltung. Wenn Sie die Raumverwaltung nicht anpassen müssen und lediglich die Standardeinstellung verwenden möchten, können Sie diese Option leer lassen.</span><span class="sxs-lookup"><span data-stu-id="e7d55-p121">In **Room management URL**, select the room management URL. This is the URL for a web-based room management deployment. If you don’t need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
        
        <span data-ttu-id="e7d55-173">Wenn Sie Ihre Raum Erstellungs Erfahrung anpassen und ihren spezifischen geschäftsworkflow einbeziehen möchten, können Sie eine benutzerdefinierte Raum Verwaltungslösung erstellen, indem Sie den Server für beständigen Chat Server Software Development Kit (SDK) verwenden, ihn irgendwo hosten und die URL hier einfügen.</span><span class="sxs-lookup"><span data-stu-id="e7d55-173">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="e7d55-174">Diese URL wird an den Client gesendet, sodass ein Benutzer, der versucht, einen Chatroom anzuzeigen oder zu erstellen, an die benutzerdefinierte Raum Verwaltungslösung weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="e7d55-174">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="e7d55-175">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e7d55-175">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

