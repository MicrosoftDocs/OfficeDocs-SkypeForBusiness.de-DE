---
title: Migrationsprozess – Details
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process - details
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205264(v=OCS.15)
ms:contentKeyID: 48185412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c15c5cf8a2eaa207467f53d57d82e6cf4491e13
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527202"
---
# <a name="migration-process---details"></a><span data-ttu-id="36ae5-102">Migrationsprozess – Details</span><span class="sxs-lookup"><span data-stu-id="36ae5-102">Migration process - details</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36ae5-103">_**Letztes Änderungsstand des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="36ae5-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="36ae5-104">Verwenden Sie die folgenden Voraussetzungen und detaillierten Schritte zum Migrieren von lync Server 2010, Gruppenchats oder Office Communications Server 2007 R2 Gruppenchats zu lync Server 2013 persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="36ae5-104">Use the following prerequisites and detailed steps to migrate either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

<div>

## <a name="prerequisites-for-migration"></a><span data-ttu-id="36ae5-105">Voraussetzungen für die Migration</span><span class="sxs-lookup"><span data-stu-id="36ae5-105">Prerequisites for Migration</span></span>

<span data-ttu-id="36ae5-106">Stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllt haben, bevor Sie entweder lync Server 2010, Gruppenchat oder Office Communications Server 2007 R2 Gruppenchat in lync Server 2013 persistent Chat Server migrieren.</span><span class="sxs-lookup"><span data-stu-id="36ae5-106">Be sure that you’ve met the following prerequisites before migrating either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

1.  <span data-ttu-id="36ae5-107">Stellen Sie mindestens einen lync Server 2013 Pool bereit.</span><span class="sxs-lookup"><span data-stu-id="36ae5-107">Deploy at least one Lync Server 2013 pool.</span></span> <span data-ttu-id="36ae5-108">Wenn Sie über mehrere lync Server 2013 Pools verfügen, müssen Sie entscheiden, welcher lync Server 2013 Pool als Home-Pool für den neuen beständiger Chat von lync Server 2013 Server Pool verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="36ae5-108">If you have multiple Lync Server 2013 pools, decide which Lync Server 2013 pool will be the home pool for the new Lync Server 2013 Persistent Chat Server pool.</span></span>

2.  <span data-ttu-id="36ae5-109">Installieren Sie den Server Pool für beständigen Chat lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="36ae5-109">Install the Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="36ae5-110">Sie wird leer sein (keine Kategorien, Räume oder Add-Ins).</span><span class="sxs-lookup"><span data-stu-id="36ae5-110">It will be empty (no categories, rooms, or add-ins).</span></span> <span data-ttu-id="36ae5-111">Bevor Sie Ihre Legacy Kategorien,-Räume oder-Add-ins migrieren, können Sie Räume, Kategorien oder Add-Ins in ihrer lync Server 2013-Server Bereitstellung für beständigen Chat erstellen.</span><span class="sxs-lookup"><span data-stu-id="36ae5-111">Before you migrate your legacy categories, rooms, or add-ins, you can create rooms, categories, or add-ins in your Lync Server 2013, Persistent Chat Server deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="36ae5-112">Beachten Sie, dass diese neu erstellten Elemente möglicherweise mit Legacy Elementen in Konflikt stehen, die Sie migrieren.</span><span class="sxs-lookup"><span data-stu-id="36ae5-112">Be aware that these newly created items may conflict with legacy items that you migrate.</span></span> <span data-ttu-id="36ae5-113">Vermeiden von Namenskonflikten Andernfalls werden Sie bei der Migration der Legacydaten überschrieben.</span><span class="sxs-lookup"><span data-stu-id="36ae5-113">Avoid any naming conflicts; otherwise, they will be overwritten when the legacy data is migrated.</span></span>

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a><span data-ttu-id="36ae5-114">Vorbereiten der Quelldaten für die Migration</span><span class="sxs-lookup"><span data-stu-id="36ae5-114">Preparing the Source Data for Migration</span></span>

<span data-ttu-id="36ae5-115">Führen Sie die folgenden Schritte aus, um die Quelldaten für die Migration ordnungsgemäß vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="36ae5-115">Perform the following steps to properly prepare your source data for migration.</span></span>

1.  <span data-ttu-id="36ae5-116">Sichern Sie die Quelldatenbanken entweder für lync Server 2010, Gruppenchat oder Office Communications Server 2007 R2 Gruppenchat.</span><span class="sxs-lookup"><span data-stu-id="36ae5-116">Back up the source databases for either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span> <span data-ttu-id="36ae5-117">Ausführliche Informationen zum Sichern von SQL Server finden Sie unter "Übersicht über Sicherungen (SQL Server)" unter <https://go.microsoft.com/fwlink/p/?linkid=254851> .</span><span class="sxs-lookup"><span data-stu-id="36ae5-117">For details about backing up SQL Server, see "Backup Overview (SQL Server)" at <https://go.microsoft.com/fwlink/p/?linkid=254851>.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="36ae5-118">Active Directory-Domänendienste sollte identisch sein.</span><span class="sxs-lookup"><span data-stu-id="36ae5-118">Active Directory Domain Services should be the same.</span></span> <span data-ttu-id="36ae5-119">Als Bedingung für die Migration können Sie nicht zu einem Pool in einer anderen Bereitstellung migrieren (insbesondere in einer anderen Active Directory Gesamtstruktur).</span><span class="sxs-lookup"><span data-stu-id="36ae5-119">As a condition for migration, you cannot migrate to a pool in a different deployment (specifically, in a different Active Directory forest).</span></span>

    
    </div>

2.  <span data-ttu-id="36ae5-120">Überprüfen Sie Ihre lync Server 2010, Gruppenchats oder Chaträume für Chats in Office Communications Server 2007 R2 Gruppen und die Kategorien Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="36ae5-120">Inspect your Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat chat rooms and category configuration.</span></span> <span data-ttu-id="36ae5-121">Alle Änderungen an Kategorien, Räumen oder Add-Ins in Ihrer vorhandenen Legacy-Bereitstellung werden vom Gruppen Chat-Verwaltungs Tool ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="36ae5-121">Any changes to categories, rooms, or add-ins in your existing legacy deployment will be done by the Group Chat Admin Tool.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="36ae5-122">Alle Änderungen an Kategorien, Chatrooms oder Add-Ins in ihrer lync Server 2013, die Bereitstellung von persistent Chat Server werden von den Cmdlets lync Server-Systemsteuerung oder Windows PowerShell ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="36ae5-122">Any changes to categories, rooms, or add-ins in your Lync Server 2013, Persistent Chat Server deployment are performed by the Lync Server Control Panel or Windows PowerShell cmdlets.</span></span>

    
    </div>
    
    <span data-ttu-id="36ae5-123">Führen Sie die folgenden Schritte aus, um Ihr Legacy System auf die Migration vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="36ae5-123">Follow these steps to prepare your legacy system for migration.</span></span>
    
    1.  <span data-ttu-id="36ae5-124">Der Server für beständigen Chat unterstützt eine einzelne Ebene von Kategorien, im Gegensatz zu einer tiefen hierarchischen Gruppe von Kategorien.</span><span class="sxs-lookup"><span data-stu-id="36ae5-124">Persistent Chat Server supports a single level of categories, unlike a deep hierarchical set of categories.</span></span> <span data-ttu-id="36ae5-125">Nach der Migration wird den Unterkategorien der vollständige Name der übergeordneten Kategorie vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="36ae5-125">After migration, the subcategories are prefixed with full parent category names.</span></span> <span data-ttu-id="36ae5-126">Möglicherweise möchten Sie die vorhandene Kategorienstruktur vereinfachen und so reduzieren, dass die resultierende Struktur Ihren Anforderungen entspricht.</span><span class="sxs-lookup"><span data-stu-id="36ae5-126">You might want to simplify and flatten your existing category structure so that the resulting structure meets your requirements.</span></span>
    
    2.  <span data-ttu-id="36ae5-127">Überprüfen Sie die **Manager** in der Stammkategorie.</span><span class="sxs-lookup"><span data-stu-id="36ae5-127">Verify the **Managers** at the root Category.</span></span> <span data-ttu-id="36ae5-128">Wenn auf dieser Ebene Manager vorhanden sind, werden diese Benutzer nach der Migration als **Manager zu allen Chatrooms** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="36ae5-128">If any Managers exist at this level, these users will be added as **Managers to all rooms** after migration.</span></span> <span data-ttu-id="36ae5-129">Wenn dies für Ihre Organisation nicht erforderlich ist, müssen Sie diese Manager aus der Stammkategorie entfernen.</span><span class="sxs-lookup"><span data-stu-id="36ae5-129">If this is not a requirement for your organization, you need to remove these Managers from the root Category.</span></span>
    
    3.  <span data-ttu-id="36ae5-130">Überprüfen Sie die Länge von Raum Namen.</span><span class="sxs-lookup"><span data-stu-id="36ae5-130">Verify the length of room names.</span></span> <span data-ttu-id="36ae5-131">Wenn die Räume unter einer untergeordneten Kategorie vorhanden sind, werden Sie nach der Migration aufgrund vereinfachter Kategorien Strukturen mit den vollständigen übergeordneten Kategorienamen vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="36ae5-131">After migration, due to simplified category structures, if the rooms exist under a child category, they are prefixed with full parent category names.</span></span> <span data-ttu-id="36ae5-132">Die Benennungs Grenze beträgt 256 Zeichen, einschließlich übergeordneter Kategorienamen.</span><span class="sxs-lookup"><span data-stu-id="36ae5-132">The naming limit is 256 characters, including parent category names.</span></span> <span data-ttu-id="36ae5-133">Sie müssen die Länge der Raumnamen überprüfen und möglicherweise die Länge kürzen, wenn Sie zu lang sind.</span><span class="sxs-lookup"><span data-stu-id="36ae5-133">You must verify the length of the room names and possibly shorten the length, if they are too long.</span></span>
    
    4.  <span data-ttu-id="36ae5-134">Wenn die Einstellungen für Kategorie- **Einladungen** in lync Server 2013 auf "true" festgelegt sind, können Sie "true" oder "false" für Einladungen zu Räumen unter dieser Kategorie auswählen.</span><span class="sxs-lookup"><span data-stu-id="36ae5-134">In Lync Server 2013, if the category **invitations** settings are set to true, you can choose true or false for invitations to rooms under that category.</span></span> <span data-ttu-id="36ae5-135">Wenn die Einstellungen für Kategorie-Einladungen jedoch auf "false" festgelegt sind, sind für die Räume unter dieser Kategorie Einladungen deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="36ae5-135">However if the category invitations settings are set to false, rooms under that category have invitations turned off.</span></span> <span data-ttu-id="36ae5-136">Vor der Migration müssen Sie die Einstellungen für die Einladung in Ihrer Legacy-lync Server-Gruppen Chat Server Version zurücksetzen, wenn Sie möchten, dass in einer bestimmten Kategorie Raum (e) vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="36ae5-136">Before migration, you must reset the invitation settings in your legacy Lync Server Group Chat Server version, if you want room(s) to exist under a specific category.</span></span> <span data-ttu-id="36ae5-137">Andernfalls zeigt lync Server 2013 während der Migration Warnungen an und legt die Räume auf den Standardwert false fest.</span><span class="sxs-lookup"><span data-stu-id="36ae5-137">Otherwise, during migration, Lync Server 2013 displays warnings and sets rooms to the default value of false.</span></span>
    
    5.  <span data-ttu-id="36ae5-138">Wenn Sie Dateien in Chatrooms verwendet haben, müssen Sie die Dateien nach der Migration manuell in den neuen Dateispeicher für beständigen Chat einbetten.</span><span class="sxs-lookup"><span data-stu-id="36ae5-138">If you used files in chat rooms, you must XCOPY the files manually to the new Persistent Chat file store after migration.</span></span> <span data-ttu-id="36ae5-139">Die Tools tun dies nicht.</span><span class="sxs-lookup"><span data-stu-id="36ae5-139">The tools don’t do this.</span></span>
    
    6.  <span data-ttu-id="36ae5-140">Wenn Sie Verbundbenutzer und-Räume mit Verbundbenutzern hatten, beachten Sie, dass der Server für beständigen Chat keinen Partnerverbund unterstützt.</span><span class="sxs-lookup"><span data-stu-id="36ae5-140">If you had federated users and rooms with federated users, be aware that Persistent Chat Server does not support federation.</span></span> <span data-ttu-id="36ae5-141">Räume mit Verbundbenutzern werden migriert; die Benutzer können jedoch nicht auf den Inhalt zugreifen, da der Verbundzugriff nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="36ae5-141">Rooms with federated users will be migrated; however, the users themselves won’t be able to access the content, because federated access is not supported.</span></span>
    
    7.  <span data-ttu-id="36ae5-142">Identifizieren Sie die Räume, die nicht migriert werden sollen, und markieren Sie Sie als deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="36ae5-142">Identify those rooms that you do not want to migrate, and mark them as disabled.</span></span>
    
    8.  <span data-ttu-id="36ae5-143">Bestimmen Sie das Datum, über dem der Chatroom-Inhalt migriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="36ae5-143">Identify the date beyond which you want to migrate the chat room content.</span></span> <span data-ttu-id="36ae5-144">Beispielsweise können Sie Nachrichten nicht vor dem 1. Januar 2010 migrieren, da diese Nachrichten möglicherweise veraltet sind oder für die Migration nicht relevant sind.</span><span class="sxs-lookup"><span data-stu-id="36ae5-144">For example, you may not want to migrate messages earlier than January 1, 2010, because these messages may be obsolete or not relevant for migration.</span></span>

</div>

<div>

## <a name="performing-the-migration"></a><span data-ttu-id="36ae5-145">Durchführen der Migration</span><span class="sxs-lookup"><span data-stu-id="36ae5-145">Performing the Migration</span></span>

<span data-ttu-id="36ae5-146">Führen Sie die folgenden Schritte aus, um Ihren Legacy-Gruppen Chat Server zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="36ae5-146">Perform the following steps to migrate your legacy Group Chat Server.</span></span>

1.  <span data-ttu-id="36ae5-147">Beenden Sie die lync Server 2010, Gruppenchat, Office Communications Server 2007 R2 Gruppenchat oder lync Server 2013, Server Dienste für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="36ae5-147">Shut down the Lync Server 2010, Group Chat, Office Communications Server 2007 R2 Group Chat or Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="36ae5-148">Alle Dienste müssen angehalten werden, daher sollten Sie dies zu einem Zeitpunkt planen, an dem genügend Ausfallzeiten vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="36ae5-148">All services must be stopped, so plan to do this at a time when there is enough downtime.</span></span> <span data-ttu-id="36ae5-149">Wie bereits beschrieben, müssen Sie die aktuelle Gruppen Chat Datenbank sichern.</span><span class="sxs-lookup"><span data-stu-id="36ae5-149">As previously described, make sure to back up your current Group Chat database.</span></span>

2.  <span data-ttu-id="36ae5-150">Führen Sie das Windows PowerShell **-Cmdlet Export-CsPersistentChatData** als Mitglied der Administratorrolle für beständigen Chat ("cspersistentchatadministrator") aus.</span><span class="sxs-lookup"><span data-stu-id="36ae5-150">Run the Windows PowerShell **Export-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="36ae5-151">Ausführliche Informationen zu den Export/Import-Cmdlets finden Sie unter [Troubleshooting persistent Chat Server Configuration using Windows PowerShell Cmdlets in lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="36ae5-151">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>
    
    <span data-ttu-id="36ae5-152">Überprüfen Sie die exportierten Inhalte.</span><span class="sxs-lookup"><span data-stu-id="36ae5-152">Inspect the exported contents.</span></span>

3.  <span data-ttu-id="36ae5-153">Bevor Sie den Import vorbereiten können, fahren Sie lync Server 2013 Server Dienste für beständigen Chat herunter.</span><span class="sxs-lookup"><span data-stu-id="36ae5-153">Before you’re ready to import, shut down Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="36ae5-154">Alle Dienste müssen angehalten werden, daher sollten Sie dies zu einem Zeitpunkt planen, an dem genügend Ausfallzeiten vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="36ae5-154">All services need to be stopped, so plan to do this at a time when there is enough downtime.</span></span>

4.  <span data-ttu-id="36ae5-155">Führen Sie eine Sicherung der Datenbank für beständigen Chat aus, wenn Sie vor der Migration Kategorien, Räume oder Add-Ins in ihrer lync Server 2013-Bereitstellung erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="36ae5-155">Perform a backup of the Persistent Chat database if you had created any categories, rooms, or add-ins in your Lync Server 2013 deployment before the migration.</span></span> <span data-ttu-id="36ae5-156">Der Export/Import-Prozess kann die Legacydaten in die lync Server 2013-Bereitstellung zusammenführen, aber Sie sollten die Datenbank sichern, falls der Inhalt versehentlich überschrieben wird (beispielsweise wenn noch Benennungskonflikte bestehen).</span><span class="sxs-lookup"><span data-stu-id="36ae5-156">The export/import process will be able to merge the legacy data into the Lync Server 2013 deployment, but you’ll want to back up the database in case that content is inadvertently overwritten (for example, if naming conflicts still exist).</span></span>

5.  <span data-ttu-id="36ae5-157">Führen Sie das Windows PowerShell **Import-CsPersistentChatData-** Cmdlet (Import Tool) mit dem Befehl **WhatIf** aus, um den Back-End-Server des Server Pools für beständigen Chat mit migrierten Daten aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="36ae5-157">Run the Windows PowerShell **Import-CsPersistentChatData** cmdlet (import tool), with a **WhatIf** command to populate the Back End Server of the Persistent Chat Server pool with migrated data.</span></span> <span data-ttu-id="36ae5-158">Einige Konvertierungen geschehen im Prozess, um das vereinfachte Verwaltungsmodell aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="36ae5-158">Some conversions happen in the process to accommodate the simplified administration model.</span></span> <span data-ttu-id="36ae5-159">Beheben Sie alle angezeigten Fehler oder Warnungen.</span><span class="sxs-lookup"><span data-stu-id="36ae5-159">Fix any errors or warnings that appear.</span></span>

6.  <span data-ttu-id="36ae5-160">Führen Sie den Server für beständigen Chat Windows PowerShell Cmdlets **Import-CsPersistentChatData** als Mitglied der Rolle "Administratorrollen für beständigen Chat" ("cspersistentchatadministrator") aus.</span><span class="sxs-lookup"><span data-stu-id="36ae5-160">Run the Persistent Chat Server Windows PowerShell **Import-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="36ae5-161">Ausführliche Informationen zu den Export/Import-Cmdlets finden Sie unter [Troubleshooting persistent Chat Server Configuration using Windows PowerShell Cmdlets in lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="36ae5-161">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>

7.  <span data-ttu-id="36ae5-162">Sie müssen alle hochgeladenen Dateien (den gesamten Ordner) in den Dateispeicher des neuen lync Server 2013 persistent Chats xcopy.</span><span class="sxs-lookup"><span data-stu-id="36ae5-162">You must XCOPY all uploaded files (the entire folder) to the new Lync Server 2013, Persistent Chat file store.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="36ae5-163">Der lync 2013 (Client) unterstützt das Hochladen oder Anzeigen von Dateien in Chatrooms nicht.</span><span class="sxs-lookup"><span data-stu-id="36ae5-163">The Lync 2013 (client) does not support uploading or viewing files in chat rooms.</span></span> <span data-ttu-id="36ae5-164">Sie können den Legacy-Client weiterhin verwenden, um Dateien im Chatroom zu veröffentlichen und anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="36ae5-164">You can still use the legacy client to post and view files in the room.</span></span>

    
    </div>

8.  <span data-ttu-id="36ae5-165">Portieren Sie den lync Server 2010-, Gruppenchat-oder Office Communications Server 2007 R2 Gruppenchat-Suchserver-URI in das Kontaktobjekt für den lync Server 2013 persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="36ae5-165">Port the Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat Lookup Server URI to the Lync Server 2013, Persistent Chat Server contact object.</span></span> <span data-ttu-id="36ae5-166">Die folgenden Schritte sind erforderlich, wenn Ihre lync 2010 Gruppenchats oder Office Communicator 2007 R2 Gruppenchatclients nach der Migration ohne clientseitige Konfigurationsänderungen eine Verbindung mit dem neuesten lync 2013, beständigen Chat (Client) herstellen müssen:</span><span class="sxs-lookup"><span data-stu-id="36ae5-166">The following steps are required if either your Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat clients need to connect to the latest Lync 2013, Persistent Chat (client) after migration without any client-side configuration changes:</span></span>
    
      - <span data-ttu-id="36ae5-167">Löschen Sie das \<domainName\> Benutzerkonto OCSChat@. com Lookup Server.</span><span class="sxs-lookup"><span data-stu-id="36ae5-167">Delete the ocschat@\<domainName\>.com Lookup Server user account.</span></span> <span data-ttu-id="36ae5-168">Dies wurde verwendet, um auf den Suchdienst in lync Server 2010, Gruppen Chat, zu deuten.</span><span class="sxs-lookup"><span data-stu-id="36ae5-168">This was used to point to the Lookup Service in Lync Server 2010, Group Chat.</span></span> <span data-ttu-id="36ae5-169">Sie können den Pool deinstallieren und später vertrauenswürdige Einträge entfernen.</span><span class="sxs-lookup"><span data-stu-id="36ae5-169">You can uninstall the pool and remove trusted entries later.</span></span>
    
      - <span data-ttu-id="36ae5-170">Erstellen Sie einen Legacy Endpunkt (Kontaktobjekt für beständigen Chat Server), indem Sie das Windows PowerShell **-Cmdlet New-cspersistentchatendpoint "** mit dem identischen SIP-URI ausführen, sodass der Legacyclient beim Neustart des Diensts effektiv funktioniert.</span><span class="sxs-lookup"><span data-stu-id="36ae5-170">Create a legacy endpoint (Persistent Chat Server contact object) by running the Windows PowerShell cmdlet, **New-CsPersistentChatEndpoint**, with the identical SIP URI so that the legacy client will work effectively when the service is restarted.</span></span>
    
    <span data-ttu-id="36ae5-171">Der obligatorische Migrationsprozess ist an dieser Position abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="36ae5-171">The mandatory migration process is complete at this point.</span></span> <span data-ttu-id="36ae5-172">Lync 2010 Gruppenchat (Clients) oder Office Communicator 2007 R2 Gruppenchat (Clients) können jetzt transparent eine Verbindung mit dem neuen Server Pool für beständigen Chat herstellen.</span><span class="sxs-lookup"><span data-stu-id="36ae5-172">Lync 2010 Group Chat (clients) or Office Communicator 2007 R2 Group Chat (clients) can connect to the new Persistent Chat Server pool now, transparently.</span></span>
    
    <span data-ttu-id="36ae5-173">Befolgen Sie diese zusätzlichen außerbetriebnahmes Schritte für lync Server 2010, Gruppenchat oder Office Communications Server 2007 R2 Gruppenchat.</span><span class="sxs-lookup"><span data-stu-id="36ae5-173">Follow these additional decommissioning steps for Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span>

9.  <span data-ttu-id="36ae5-174">Starten Sie die Server Dienste für beständigen Chat, indem Sie alle Computer im neuen Serverpool für beständigen Chat aktivieren.</span><span class="sxs-lookup"><span data-stu-id="36ae5-174">Start the Persistent Chat Server services by turning on all computers in the new Persistent Chat Server pool.</span></span>

10. <span data-ttu-id="36ae5-175">Verwenden Sie die Cmdlets lync Server-Systemsteuerung und Windows PowerShell, um zu überprüfen, ob die Daten erfolgreich migriert wurden.</span><span class="sxs-lookup"><span data-stu-id="36ae5-175">Use the Lync Server Control Panel and Windows PowerShell cmdlets to verify that the data has migrated successfully.</span></span>

11. <span data-ttu-id="36ae5-176">Deinstallieren Sie lync 2010 Gruppenchat oder Office Communicator 2007 R2 Gruppenchat von den Computern im Gruppenchat Server-Pool.</span><span class="sxs-lookup"><span data-stu-id="36ae5-176">Uninstall Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat from the computers in the Group Chat Server pool.</span></span>

12. <span data-ttu-id="36ae5-177">Löschen Sie den vertrauenswürdigen Anwendungspool mit Windows PowerShell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="36ae5-177">Delete the trusted application and trusted application pool using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="36ae5-178">Dadurch werden diese Elemente aus dem zentralen Verwaltungsspeicher und den zugeordneten TSE (Trusted Service Entries) aus dem Active Directory gelöscht.</span><span class="sxs-lookup"><span data-stu-id="36ae5-178">This deletes these items from the Central Management store and the associated Trusted Service Entries (TSEs) from the Active Directory.</span></span> <span data-ttu-id="36ae5-179">Alternativ funktioniert dieser Schritt mithilfe des Topologie-Generators (die vertrauenswürdigen Anwendungen/Pools verfügen ebenfalls über einen dedizierten Knoten).</span><span class="sxs-lookup"><span data-stu-id="36ae5-179">Alternatively, this step works by using the Topology Builder (the trusted applications/pools have a dedicated node there, also).</span></span>

13. <span data-ttu-id="36ae5-180">Sie können jetzt mit dem Aktivieren der Funktion für beständigen Chat Server über die neuen Clients beginnen.</span><span class="sxs-lookup"><span data-stu-id="36ae5-180">You can now begin to enable Persistent Chat Server functionality through the new clients.</span></span> <span data-ttu-id="36ae5-181">Ausführliche Informationen zum Aktivieren des Servers für beständigen Chat finden Sie unter [Deploying persistent Chat Server in lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="36ae5-181">For details about enabling Persistent Chat Server, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="36ae5-182">Lync Server 2013 unterstützt mehrere Server Pools für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="36ae5-182">Lync Server 2013 supports multiple Persistent Chat Server pools.</span></span> <span data-ttu-id="36ae5-183">Wir unterstützen jedoch die Migration eines lync 2010 Gruppenchats oder Office Communications Server 2007 R2 &nbsp; Gruppen-Chat Pools in einen einzelnen lync Server 2013 Server Pool für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="36ae5-183">However, we support migrating a Lync 2010 Group Chat or Office Communications Server 2007 R2&nbsp;Group Chat pool to a single Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="36ae5-184">Sie können zusätzliche neue Server Pools für beständigen Chat in Ihrer Bereitstellung hinzufügen, um die regulatorischen Anforderungen zu erfüllen (beispielsweise das Beibehalten von Daten in einer bestimmten Geografie).</span><span class="sxs-lookup"><span data-stu-id="36ae5-184">You can add additional new Persistent Chat Server pools in your deployment to meet the regulatory needs (for example, keeping data within a given geography).</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

