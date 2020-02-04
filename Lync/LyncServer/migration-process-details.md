---
title: Migrationsprozess – Details
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration process - details
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205264(v=OCS.15)
ms:contentKeyID: 48185412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d3b46e2b80d9ad5a4b08108d1dc2bad03cf5f0f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process---details"></a><span data-ttu-id="64975-102">Migrationsprozess – Details</span><span class="sxs-lookup"><span data-stu-id="64975-102">Migration process - details</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64975-103">_**Letztes Änderungsdatum des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="64975-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="64975-104">Verwenden Sie die folgenden Voraussetzungen und detaillierten Schritte zum Migrieren von lync Server 2010, Gruppen-Chat oder Office Communications Server 2007 R2-Gruppen-Chat zu lync Server 2013, beständiger Chat Server.</span><span class="sxs-lookup"><span data-stu-id="64975-104">Use the following prerequisites and detailed steps to migrate either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

<div>

## <a name="prerequisites-for-migration"></a><span data-ttu-id="64975-105">Voraussetzungen für die Migration</span><span class="sxs-lookup"><span data-stu-id="64975-105">Prerequisites for Migration</span></span>

<span data-ttu-id="64975-106">Stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllt haben, bevor Sie entweder lync Server 2010, Gruppen-Chat oder Office Communications Server 2007 R2-Gruppen-Chat zu lync Server 2013, beständiger Chat Server, migrieren.</span><span class="sxs-lookup"><span data-stu-id="64975-106">Be sure that you’ve met the following prerequisites before migrating either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

1.  <span data-ttu-id="64975-107">Bereitstellen von mindestens einem lync Server 2013-Pool</span><span class="sxs-lookup"><span data-stu-id="64975-107">Deploy at least one Lync Server 2013 pool.</span></span> <span data-ttu-id="64975-108">Wenn Sie über mehrere lync Server 2013-Pools verfügen, entscheiden Sie, welcher lync Server 2013-Pool als privater Pool für den neuen lync Server 2013-Serverpool für beständige Chats festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="64975-108">If you have multiple Lync Server 2013 pools, decide which Lync Server 2013 pool will be the home pool for the new Lync Server 2013 Persistent Chat Server pool.</span></span>

2.  <span data-ttu-id="64975-109">Installieren Sie den Serverpool des lync Server 2013, beständigen Chats.</span><span class="sxs-lookup"><span data-stu-id="64975-109">Install the Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="64975-110">Sie ist leer (keine Kategorien, Räume oder Add-Ins).</span><span class="sxs-lookup"><span data-stu-id="64975-110">It will be empty (no categories, rooms, or add-ins).</span></span> <span data-ttu-id="64975-111">Bevor Sie Ihre Legacy Kategorien,-Räume oder-Add-ins migrieren, können Sie Räume, Kategorien oder Add-Ins in ihrer lync Server 2013-Bereitstellung des beständigen Chats erstellen.</span><span class="sxs-lookup"><span data-stu-id="64975-111">Before you migrate your legacy categories, rooms, or add-ins, you can create rooms, categories, or add-ins in your Lync Server 2013, Persistent Chat Server deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="64975-112">Beachten Sie, dass diese neu erstellten Elemente Konflikte mit Legacy Elementen verursachen können, die Sie migrieren.</span><span class="sxs-lookup"><span data-stu-id="64975-112">Be aware that these newly created items may conflict with legacy items that you migrate.</span></span> <span data-ttu-id="64975-113">Vermeiden Sie Namenskonflikte; Andernfalls werden Sie überschrieben, wenn die Legacydaten migriert werden.</span><span class="sxs-lookup"><span data-stu-id="64975-113">Avoid any naming conflicts; otherwise, they will be overwritten when the legacy data is migrated.</span></span>

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a><span data-ttu-id="64975-114">Vorbereiten der Quelldaten für die Migration</span><span class="sxs-lookup"><span data-stu-id="64975-114">Preparing the Source Data for Migration</span></span>

<span data-ttu-id="64975-115">Führen Sie die folgenden Schritte aus, um die Quelldaten für die Migration richtig vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="64975-115">Perform the following steps to properly prepare your source data for migration.</span></span>

1.  <span data-ttu-id="64975-116">Sichern Sie die Quelldatenbanken für lync Server 2010, Gruppen-Chat oder Office Communications Server 2007 R2-Gruppen-Chat.</span><span class="sxs-lookup"><span data-stu-id="64975-116">Back up the source databases for either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span> <span data-ttu-id="64975-117">Details zum Sichern von SQL Server finden Sie unter "Übersicht über Sicherungen (SQL Server)" unter <http://go.microsoft.com/fwlink/p/?linkid=254851>.</span><span class="sxs-lookup"><span data-stu-id="64975-117">For details about backing up SQL Server, see "Backup Overview (SQL Server)" at <http://go.microsoft.com/fwlink/p/?linkid=254851>.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="64975-118">Die Active Directory-Domänendienste sollten identisch sein.</span><span class="sxs-lookup"><span data-stu-id="64975-118">Active Directory Domain Services should be the same.</span></span> <span data-ttu-id="64975-119">Als Bedingung für die Migration können Sie nicht zu einem Pool in einer anderen Bereitstellung (insbesondere in einer anderen Active Directory-Gesamtstruktur) migrieren.</span><span class="sxs-lookup"><span data-stu-id="64975-119">As a condition for migration, you cannot migrate to a pool in a different deployment (specifically, in a different Active Directory forest).</span></span>

    
    </div>

2.  <span data-ttu-id="64975-120">Überprüfen Sie Ihre lync Server 2010, Gruppen-Chat oder Office Communications Server 2007 R2-Gruppen-Chatrooms und die Kategorie-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="64975-120">Inspect your Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat chat rooms and category configuration.</span></span> <span data-ttu-id="64975-121">Alle Änderungen an Kategorien, Räumen oder Add-Ins in Ihrer vorhandenen Legacy Bereitstellung werden vom Gruppen-Chat-Verwaltungs Tool ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="64975-121">Any changes to categories, rooms, or add-ins in your existing legacy deployment will be done by the Group Chat Admin Tool.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="64975-122">Alle Änderungen an Kategorien, Räumen oder Add-Ins in ihrer lync Server 2013-Bereitstellung des beständigen Chats werden von der lync Server Control Panel-oder Windows PowerShell-Cmdlets ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="64975-122">Any changes to categories, rooms, or add-ins in your Lync Server 2013, Persistent Chat Server deployment are performed by the Lync Server Control Panel or Windows PowerShell cmdlets.</span></span>

    
    </div>
    
    <span data-ttu-id="64975-123">Führen Sie die folgenden Schritte aus, um Ihr Legacy System für die Migration vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="64975-123">Follow these steps to prepare your legacy system for migration.</span></span>
    
    1.  <span data-ttu-id="64975-124">Der beständige Chat Server unterstützt eine einzelne Ebene von Kategorien, anders als eine Tiefe hierarchische Gruppe von Kategorien.</span><span class="sxs-lookup"><span data-stu-id="64975-124">Persistent Chat Server supports a single level of categories, unlike a deep hierarchical set of categories.</span></span> <span data-ttu-id="64975-125">Nach der Migration werden den Unterkategorien vollständige übergeordnete Kategorienamen vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="64975-125">After migration, the subcategories are prefixed with full parent category names.</span></span> <span data-ttu-id="64975-126">Möglicherweise möchten Sie die vorhandene Kategorienstruktur vereinfachen und glätten, damit die resultierende Struktur Ihren Anforderungen entspricht.</span><span class="sxs-lookup"><span data-stu-id="64975-126">You might want to simplify and flatten your existing category structure so that the resulting structure meets your requirements.</span></span>
    
    2.  <span data-ttu-id="64975-127">Überprüfen Sie die **Manager** in der Stammkategorie.</span><span class="sxs-lookup"><span data-stu-id="64975-127">Verify the **Managers** at the root Category.</span></span> <span data-ttu-id="64975-128">Wenn Manager auf dieser Ebene vorhanden sind, werden diese Benutzer nach der Migration als **Manager zu allen Chatrooms** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="64975-128">If any Managers exist at this level, these users will be added as **Managers to all rooms** after migration.</span></span> <span data-ttu-id="64975-129">Wenn dies für Ihre Organisation nicht erforderlich ist, müssen Sie diese Manager aus der Stammkategorie entfernen.</span><span class="sxs-lookup"><span data-stu-id="64975-129">If this is not a requirement for your organization, you need to remove these Managers from the root Category.</span></span>
    
    3.  <span data-ttu-id="64975-130">Überprüfen Sie die Länge von Raumnamen.</span><span class="sxs-lookup"><span data-stu-id="64975-130">Verify the length of room names.</span></span> <span data-ttu-id="64975-131">Wenn die Räume unter einer untergeordneten Kategorie vorhanden sind, werden Sie nach der Migration aufgrund vereinfachter Kategorie-Strukturen mit den vollständigen übergeordneten Kategorienamen belegt.</span><span class="sxs-lookup"><span data-stu-id="64975-131">After migration, due to simplified category structures, if the rooms exist under a child category, they are prefixed with full parent category names.</span></span> <span data-ttu-id="64975-132">Die Benennungs Grenze ist 256 Zeichen, einschließlich übergeordneter Kategorienamen.</span><span class="sxs-lookup"><span data-stu-id="64975-132">The naming limit is 256 characters, including parent category names.</span></span> <span data-ttu-id="64975-133">Sie müssen die Länge der Raumnamen überprüfen und möglicherweise die Länge verkürzen, wenn Sie zu lang sind.</span><span class="sxs-lookup"><span data-stu-id="64975-133">You must verify the length of the room names and possibly shorten the length, if they are too long.</span></span>
    
    4.  <span data-ttu-id="64975-134">Wenn in lync Server 2013 die Einstellungen für die Kategorie- **Einladungen** auf "true" festgelegt sind, können Sie für Einladungen zu Räumen unter dieser Kategorie "wahr" oder "falsch" auswählen.</span><span class="sxs-lookup"><span data-stu-id="64975-134">In Lync Server 2013, if the category **invitations** settings are set to true, you can choose true or false for invitations to rooms under that category.</span></span> <span data-ttu-id="64975-135">Wenn die Einstellungen für die Kategorie-Einladungen aber auf "falsch" festgelegt sind, werden in Räumen unter dieser Kategorie Einladungen deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="64975-135">However if the category invitations settings are set to false, rooms under that category have invitations turned off.</span></span> <span data-ttu-id="64975-136">Vor der Migration müssen Sie die Einladungseinstellungen in ihrer älteren lync Server-Gruppen-Chat Server Version zurücksetzen, wenn Sie möchten, dass Raum (e) unter einer bestimmten Kategorie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="64975-136">Before migration, you must reset the invitation settings in your legacy Lync Server Group Chat Server version, if you want room(s) to exist under a specific category.</span></span> <span data-ttu-id="64975-137">Andernfalls zeigt lync Server 2013 während der Migration Warnungen an und legt Räume auf den Standardwert false fest.</span><span class="sxs-lookup"><span data-stu-id="64975-137">Otherwise, during migration, Lync Server 2013 displays warnings and sets rooms to the default value of false.</span></span>
    
    5.  <span data-ttu-id="64975-138">Wenn Sie Dateien in Chatrooms verwendet haben, müssen Sie die Dateien nach der Migration manuell in den neuen beständigen Chat-Dateispeicher herunterladen.</span><span class="sxs-lookup"><span data-stu-id="64975-138">If you used files in chat rooms, you must XCOPY the files manually to the new Persistent Chat file store after migration.</span></span> <span data-ttu-id="64975-139">Die Tools tun dies nicht.</span><span class="sxs-lookup"><span data-stu-id="64975-139">The tools don’t do this.</span></span>
    
    6.  <span data-ttu-id="64975-140">Wenn Sie Verbundbenutzer und Chatrooms mit Verbundbenutzern hatten, beachten Sie, dass der Server für beständigen Chat keine Föderation unterstützt.</span><span class="sxs-lookup"><span data-stu-id="64975-140">If you had federated users and rooms with federated users, be aware that Persistent Chat Server does not support federation.</span></span> <span data-ttu-id="64975-141">Räume mit Verbundbenutzern werden migriert. die Benutzer können jedoch nicht auf die Inhalte zugreifen, da der Verbundzugriff nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="64975-141">Rooms with federated users will be migrated; however, the users themselves won’t be able to access the content, because federated access is not supported.</span></span>
    
    7.  <span data-ttu-id="64975-142">Identifizieren Sie die Chatrooms, die Sie nicht migrieren möchten, und markieren Sie Sie als deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="64975-142">Identify those rooms that you do not want to migrate, and mark them as disabled.</span></span>
    
    8.  <span data-ttu-id="64975-143">Ermitteln Sie das Datum, über das Sie den Chatroom-Inhalt migrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="64975-143">Identify the date beyond which you want to migrate the chat room content.</span></span> <span data-ttu-id="64975-144">So möchten Sie beispielsweise Nachrichten nicht vor dem 1. Januar 2010 migrieren, da diese Nachrichten möglicherweise veraltet oder für die Migration nicht relevant sind.</span><span class="sxs-lookup"><span data-stu-id="64975-144">For example, you may not want to migrate messages earlier than January 1, 2010, because these messages may be obsolete or not relevant for migration.</span></span>

</div>

<div>

## <a name="performing-the-migration"></a><span data-ttu-id="64975-145">Durchführen der Migration</span><span class="sxs-lookup"><span data-stu-id="64975-145">Performing the Migration</span></span>

<span data-ttu-id="64975-146">Führen Sie die folgenden Schritte aus, um Ihren Legacy-Gruppen-Chat Server zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="64975-146">Perform the following steps to migrate your legacy Group Chat Server.</span></span>

1.  <span data-ttu-id="64975-147">Beenden Sie lync Server 2010, Gruppen-Chat, Office Communications Server 2007 R2-Gruppenchat oder lync Server 2013, beständige Chat Server Dienste.</span><span class="sxs-lookup"><span data-stu-id="64975-147">Shut down the Lync Server 2010, Group Chat, Office Communications Server 2007 R2 Group Chat or Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="64975-148">Damit alle Dienste gestoppt werden können, sollten Sie dies zu einem Zeitpunkt planen, zu dem genügend Ausfallzeiten vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="64975-148">All services must be stopped, so plan to do this at a time when there is enough downtime.</span></span> <span data-ttu-id="64975-149">Vergewissern Sie sich wie zuvor beschrieben, dass Sie Ihre aktuelle Gruppen-Chat-Datenbank sichern.</span><span class="sxs-lookup"><span data-stu-id="64975-149">As previously described, make sure to back up your current Group Chat database.</span></span>

2.  <span data-ttu-id="64975-150">Führen Sie das Cmdlet "Windows PowerShell **Export-CsPersistentChatData** " als Mitglied der Administratorrolle "beständiger Chat" (CsPersistentChatAdministrator) aus.</span><span class="sxs-lookup"><span data-stu-id="64975-150">Run the Windows PowerShell **Export-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="64975-151">Details zu den Export/Import-Cmdlets finden Sie unter [Problembehandlung bei der Server Konfiguration für beständigen Chat mit Windows PowerShell-Cmdlets in lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="64975-151">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>
    
    <span data-ttu-id="64975-152">Überprüfen Sie die exportierten Inhalte.</span><span class="sxs-lookup"><span data-stu-id="64975-152">Inspect the exported contents.</span></span>

3.  <span data-ttu-id="64975-153">Bevor Sie zum Importieren bereit sind, beenden Sie lync Server 2013, Server Dienste für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="64975-153">Before you’re ready to import, shut down Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="64975-154">Damit alle Dienste gestoppt werden können, sollten Sie dies zu einem Zeitpunkt planen, zu dem genügend Ausfallzeiten vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="64975-154">All services need to be stopped, so plan to do this at a time when there is enough downtime.</span></span>

4.  <span data-ttu-id="64975-155">Führen Sie eine Sicherungskopie der persistenten Chat-Datenbank aus, wenn Sie vor der Migration Kategorien, Räume oder Add-Ins in ihrer lync Server 2013-Bereitstellung erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="64975-155">Perform a backup of the Persistent Chat database if you had created any categories, rooms, or add-ins in your Lync Server 2013 deployment before the migration.</span></span> <span data-ttu-id="64975-156">Der Export/Import-Prozess kann die Legacydaten in die lync Server 2013-Bereitstellung zusammenführen, doch Sie möchten die Datenbank sichern, falls dieser Inhalt versehentlich überschrieben wird (beispielsweise, wenn Benennungskonflikte weiterhin vorhanden sind).</span><span class="sxs-lookup"><span data-stu-id="64975-156">The export/import process will be able to merge the legacy data into the Lync Server 2013 deployment, but you’ll want to back up the database in case that content is inadvertently overwritten (for example, if naming conflicts still exist).</span></span>

5.  <span data-ttu-id="64975-157">Führen Sie das Windows PowerShell **-Import-CsPersistentChatData-** Cmdlet (Import Tool) mit einem **WhatIf** -Befehl aus, um den Back-End-Server des beständigen Chat Server Pools mit migrierten Daten zu füllen.</span><span class="sxs-lookup"><span data-stu-id="64975-157">Run the Windows PowerShell **Import-CsPersistentChatData** cmdlet (import tool), with a **WhatIf** command to populate the Back End Server of the Persistent Chat Server pool with migrated data.</span></span> <span data-ttu-id="64975-158">Einige Konvertierungen erfolgen im Prozess, um dem vereinfachten Verwaltungsmodell gerecht zu werden.</span><span class="sxs-lookup"><span data-stu-id="64975-158">Some conversions happen in the process to accommodate the simplified administration model.</span></span> <span data-ttu-id="64975-159">Beheben Sie alle angezeigten Fehler oder Warnungen.</span><span class="sxs-lookup"><span data-stu-id="64975-159">Fix any errors or warnings that appear.</span></span>

6.  <span data-ttu-id="64975-160">Führen Sie das Cmdlet "beständiger Chat Server Windows PowerShell **-Import-CsPersistentChatData** " als Mitglied der Administratorrolle "beständiger Chat" (CsPersistentChatAdministrator) aus.</span><span class="sxs-lookup"><span data-stu-id="64975-160">Run the Persistent Chat Server Windows PowerShell **Import-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="64975-161">Details zu den Export/Import-Cmdlets finden Sie unter [Problembehandlung bei der Server Konfiguration für beständigen Chat mit Windows PowerShell-Cmdlets in lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="64975-161">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>

7.  <span data-ttu-id="64975-162">Sie müssen alle hochgeladenen Dateien (den gesamten Ordner) in den neuen lync Server 2013-Dateispeicher für persistente Chats übertragen.</span><span class="sxs-lookup"><span data-stu-id="64975-162">You must XCOPY all uploaded files (the entire folder) to the new Lync Server 2013, Persistent Chat file store.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="64975-163">Lync 2013 (Client) unterstützt das Hochladen oder Anzeigen von Dateien in Chatrooms nicht.</span><span class="sxs-lookup"><span data-stu-id="64975-163">The Lync 2013 (client) does not support uploading or viewing files in chat rooms.</span></span> <span data-ttu-id="64975-164">Sie können den Legacyclient weiterhin verwenden, um Dateien im Chatroom zu Posten und anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="64975-164">You can still use the legacy client to post and view files in the room.</span></span>

    
    </div>

8.  <span data-ttu-id="64975-165">Portieren Sie lync Server 2010, Gruppen-Chat oder Office Communications Server 2007 R2-Gruppen-Chat-Nachschlage Server-URI zum lync Server 2013-Kontaktobjekt für beständigen Chat Server.</span><span class="sxs-lookup"><span data-stu-id="64975-165">Port the Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat Lookup Server URI to the Lync Server 2013, Persistent Chat Server contact object.</span></span> <span data-ttu-id="64975-166">Die folgenden Schritte sind erforderlich, wenn sich entweder Ihr lync 2010-Gruppen-Chat oder die Office Communicator 2007 R2-Gruppen-Chat-Clients nach der Migration ohne clientseitige Konfigurationsänderungen mit dem neuesten lync 2013, beständigen Chat (Client) verbinden müssen:</span><span class="sxs-lookup"><span data-stu-id="64975-166">The following steps are required if either your Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat clients need to connect to the latest Lync 2013, Persistent Chat (client) after migration without any client-side configuration changes:</span></span>
    
      - <span data-ttu-id="64975-167">Löschen Sie das\<OCSChat@ Domain\>Name. com Lookup Server-Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="64975-167">Delete the ocschat@\<domainName\>.com Lookup Server user account.</span></span> <span data-ttu-id="64975-168">Dies wurde verwendet, um auf den Nachschlage Dienst in lync Server 2010, Gruppen-Chat, zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="64975-168">This was used to point to the Lookup Service in Lync Server 2010, Group Chat.</span></span> <span data-ttu-id="64975-169">Sie können den Pool deinstallieren und vertrauenswürdige Einträge später entfernen.</span><span class="sxs-lookup"><span data-stu-id="64975-169">You can uninstall the pool and remove trusted entries later.</span></span>
    
      - <span data-ttu-id="64975-170">Erstellen Sie einen Legacy Endpunkt (Kontaktobjekt für beständigen Chat Server), indem Sie das Windows PowerShell **-Cmdlet New-CsPersistentChatEndpoint**mit dem identischen SIP-URI ausführen, damit der Legacyclient effektiv funktioniert, wenn der Dienst neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="64975-170">Create a legacy endpoint (Persistent Chat Server contact object) by running the Windows PowerShell cmdlet, **New-CsPersistentChatEndpoint**, with the identical SIP URI so that the legacy client will work effectively when the service is restarted.</span></span>
    
    <span data-ttu-id="64975-171">Der obligatorische Migrationsprozess ist an diesem Punkt abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="64975-171">The mandatory migration process is complete at this point.</span></span> <span data-ttu-id="64975-172">Lync 2010-Gruppen-Chats (Clients) oder Office Communicator 2007 R2-Gruppen-Chat (Clients) können jetzt transparent eine Verbindung mit dem neuen beständigen Chat Server Pool herstellen.</span><span class="sxs-lookup"><span data-stu-id="64975-172">Lync 2010 Group Chat (clients) or Office Communicator 2007 R2 Group Chat (clients) can connect to the new Persistent Chat Server pool now, transparently.</span></span>
    
    <span data-ttu-id="64975-173">Befolgen Sie diese zusätzlichen Schritte zur Außerbetriebnahme für lync Server 2010, Gruppen-Chat oder Office Communications Server 2007 R2-Gruppen-Chat.</span><span class="sxs-lookup"><span data-stu-id="64975-173">Follow these additional decommissioning steps for Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span>

9.  <span data-ttu-id="64975-174">Starten Sie die Server Dienste für beständigen Chat, indem Sie alle Computer im neuen beständigen Chat Serverpool aktivieren.</span><span class="sxs-lookup"><span data-stu-id="64975-174">Start the Persistent Chat Server services by turning on all computers in the new Persistent Chat Server pool.</span></span>

10. <span data-ttu-id="64975-175">Verwenden Sie die lync Server-Systemsteuerung und die Windows PowerShell-Cmdlets, um zu überprüfen, ob die Daten erfolgreich migriert wurden.</span><span class="sxs-lookup"><span data-stu-id="64975-175">Use the Lync Server Control Panel and Windows PowerShell cmdlets to verify that the data has migrated successfully.</span></span>

11. <span data-ttu-id="64975-176">Deinstallieren Sie den lync 2010-Gruppen-Chat oder den Office Communicator 2007 R2-Gruppen-Chat von den Computern im Gruppen-Chat-Server Pool.</span><span class="sxs-lookup"><span data-stu-id="64975-176">Uninstall Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat from the computers in the Group Chat Server pool.</span></span>

12. <span data-ttu-id="64975-177">Löschen Sie die vertrauenswürdige Anwendung und den vertrauenswürdigen Anwendungspool mithilfe von Windows PowerShell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="64975-177">Delete the trusted application and trusted application pool using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="64975-178">Dadurch werden diese Elemente aus dem zentralen Verwaltungsspeicher und den zugehörigen TSE (Trusted Service Entries) aus dem Active Directory gelöscht.</span><span class="sxs-lookup"><span data-stu-id="64975-178">This deletes these items from the Central Management store and the associated Trusted Service Entries (TSEs) from the Active Directory.</span></span> <span data-ttu-id="64975-179">Alternativ funktioniert dieser Schritt mithilfe des Topologie-Generators (die vertrauenswürdigen Anwendungen/Pools verfügen ebenfalls über einen dedizierten Knoten).</span><span class="sxs-lookup"><span data-stu-id="64975-179">Alternatively, this step works by using the Topology Builder (the trusted applications/pools have a dedicated node there, also).</span></span>

13. <span data-ttu-id="64975-180">Sie können jetzt beginnen, die Funktion des beständigen Chat Servers über die neuen Clients zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="64975-180">You can now begin to enable Persistent Chat Server functionality through the new clients.</span></span> <span data-ttu-id="64975-181">Ausführliche Informationen zum Aktivieren des Servers für beständigen Chat finden Sie unter [Bereitstellen eines persistenten Chat Servers in lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="64975-181">For details about enabling Persistent Chat Server, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="64975-182">Lync Server 2013 unterstützt mehrere Server Pools für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="64975-182">Lync Server 2013 supports multiple Persistent Chat Server pools.</span></span> <span data-ttu-id="64975-183">Wir unterstützen allerdings die Migration eines lync 2010-Gruppen-oder Office&nbsp;Communications Server 2007 R2-Gruppen-Chat Pools zu einem einzelnen lync Server 2013, beständigen Chat Serverpool.</span><span class="sxs-lookup"><span data-stu-id="64975-183">However, we support migrating a Lync 2010 Group Chat or Office Communications Server 2007 R2&nbsp;Group Chat pool to a single Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="64975-184">Sie können weitere neue Server Pools für beständigen Chat in Ihrer Bereitstellung hinzufügen, um die regulatorischen Anforderungen zu erfüllen (beispielsweise das Beibehalten von Daten in einer bestimmten geografischen Region).</span><span class="sxs-lookup"><span data-stu-id="64975-184">You can add additional new Persistent Chat Server pools in your deployment to meet the regulatory needs (for example, keeping data within a given geography).</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

