---
title: Verschieben von dateispeicherdaten in einen neuen Dateispeicher in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 'Wenn Sie den Dateiserver entfernen müssen, der derzeit als Dateispeicher für Ihre Skype for Business Server-Bereitstellung fungiert, oder wenn Sie andere Änderungen vornehmen müssen, die den aktuellen Dateispeicher nicht mehr verfügbar machen, müssen Sie zuerst eine neue Freigabe erstellen. Dann müssen Sie folgende Schritte ausführen:'
ms.openlocfilehash: e1c4338e33e736c04dbb1a2a2e81a7233df65763
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817106"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a><span data-ttu-id="ddd42-104">Verschieben von dateispeicherdaten in einen neuen Dateispeicher in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ddd42-104">Move File Store Data to a New File Store in Skype for Business Server</span></span>

<span data-ttu-id="ddd42-105">Wenn Sie den Dateiserver entfernen müssen, der derzeit als Dateispeicher für Ihre Skype for Business Server-Bereitstellung fungiert, oder wenn Sie andere Änderungen vornehmen müssen, die den aktuellen Dateispeicher nicht mehr verfügbar machen, müssen Sie zuerst eine neue Freigabe erstellen.</span><span class="sxs-lookup"><span data-stu-id="ddd42-105">If you need to remove the file server that is currently acting as the file store for your Skype for Business Server deployment, or if you need to make other changes that would make the current file store unavailable, you first need to create a new share.</span></span> <span data-ttu-id="ddd42-106">Dann müssen Sie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="ddd42-106">Then you need to perform the following steps:</span></span>

1. <span data-ttu-id="ddd42-107">Beenden Sie die Skype for Business Server-Dienste, die den Dateispeicher verwenden, den Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="ddd42-107">Shut down the Skype for Business Server services that use the file store that you plan to remove.</span></span>

2. <span data-ttu-id="ddd42-108">Definieren Sie den Dateispeicher im Topologie-Generator, und veröffentlichen Sie die Änderungen, damit der neue Dateispeicher für Ihre Bereitstellung zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="ddd42-108">Define the file store in Topology Builder and publish the changes to make the new file store available to your deployment.</span></span>

3. <span data-ttu-id="ddd42-109">Verschieben Sie die Dateien in den neuen Dateispeicher.</span><span class="sxs-lookup"><span data-stu-id="ddd42-109">Move the data to the new file store.</span></span>

4. <span data-ttu-id="ddd42-110">Starten Sie die Server bzw. Dienste neu.</span><span class="sxs-lookup"><span data-stu-id="ddd42-110">Restart the servers or services.</span></span>

5. <span data-ttu-id="ddd42-111">Optional können Sie die alte Dateifreigabe und den Dateiordner entfernen.</span><span class="sxs-lookup"><span data-stu-id="ddd42-111">Optionally, remove the old file share and file folder.</span></span>

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a><span data-ttu-id="ddd42-112">So verschieben Sie Dateispeicherdaten von einem Dateispeicher in einen neuen Dateispeicher</span><span class="sxs-lookup"><span data-stu-id="ddd42-112">To move file store data from one file store to a new file store</span></span>

1. <span data-ttu-id="ddd42-113">Melden Sie sich bei einem Computer als Mitglied der RTCUniversersalServerAdmins-oder CsServerAdministrator-Gruppe an, in der der Skype for Business-Server, Verwaltungs Tools installiert sind.</span><span class="sxs-lookup"><span data-stu-id="ddd42-113">Log on to a computer as a member of the RTCUniversersalServerAdmins or CsServerAdministrator group where the Skype for Business Server, Administrative Tools are installed.</span></span>

2.  <span data-ttu-id="ddd42-114">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ddd42-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="ddd42-115">Klicken Sie in der linken Navigationsleiste auf \*\*Topologie \*\* und dann auf **Status**. </span><span class="sxs-lookup"><span data-stu-id="ddd42-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>

4. <span data-ttu-id="ddd42-116">Wählen Sie für jeden Director-Pool, Director, Standard Edition-Server und Front-End-Pool, der den zu entfernenden Dateispeicher verwendet, den Server oder Pool aus, klicken Sie auf **Aktion**, und klicken Sie dann auf **alle Dienste beenden**.</span><span class="sxs-lookup"><span data-stu-id="ddd42-116">For each Director pool, Director, Standard Edition server, and Front End pool that uses the file store that you plan to remove, select the server or pool, click **Action**, and then click **Stop all services**.</span></span>

5. <span data-ttu-id="ddd42-117">Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.</span><span class="sxs-lookup"><span data-stu-id="ddd42-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

6. <span data-ttu-id="ddd42-118">Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business Server**, und klicken Sie dann auf **Skype for Business Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="ddd42-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

7. <span data-ttu-id="ddd42-119">Wählen Sie einen Server oder Pool aus, der den Dateispeicher verwendet, und gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="ddd42-119">Select a server or pool that uses the file store, and do the following:</span></span>

   <span data-ttu-id="ddd42-120">a.</span><span class="sxs-lookup"><span data-stu-id="ddd42-120">a.</span></span> <span data-ttu-id="ddd42-121">Klicken Sie mit der rechten Maustaste auf den Server oder den Pool, und klicken Sie auf \*\*Eigenschaften bearbeiten \*\*. </span><span class="sxs-lookup"><span data-stu-id="ddd42-121">Right-click the server or pool, and then click **Edit Properties**.</span></span>

   <span data-ttu-id="ddd42-122">b.</span><span class="sxs-lookup"><span data-stu-id="ddd42-122">b.</span></span> <span data-ttu-id="ddd42-123">Klicken Sie in **Eigenschaften bearbeiten** unter **Zuordnungen** und unter **Dateispeicher** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="ddd42-123">In **Edit properties**, under **Associations**, under **File store**, click **New**.</span></span>

   <span data-ttu-id="ddd42-124">c.</span><span class="sxs-lookup"><span data-stu-id="ddd42-124">c.</span></span> <span data-ttu-id="ddd42-125">Geben Sie in **Neuen Dateispeicher definieren** unter **Dateiserver-FQDN** den vollqualifizierten Domänennamen (FQDN) des Dateiservers ein.</span><span class="sxs-lookup"><span data-stu-id="ddd42-125">In **Define New File Store**, under **File server FQDN**, type the fully qualified domain name (FQDN) of the file server.</span></span> <span data-ttu-id="ddd42-126">Geben Sie unter **Dateifreigabe** den Ordnernamen für die neue Dateifreigabe ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ddd42-126">Under **File share**, type the folder name for the new file share, and then click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ddd42-127">In diesem Schritt wird ein neuer Dateispeicher für die Verwendung im Topologie-Generator definiert.</span><span class="sxs-lookup"><span data-stu-id="ddd42-127">This step defines a new file store for use in Topology Builder.</span></span> <span data-ttu-id="ddd42-128">Die Definition erfolgt nur einmal, nicht für jeden Server.</span><span class="sxs-lookup"><span data-stu-id="ddd42-128">You define it only once, not for each server.</span></span> <span data-ttu-id="ddd42-129">Bevor Sie die Topologie veröffentlichen, müssen Sie die definierte Dateifreigabe auf dem definierten Dateiserver erstellen.</span><span class="sxs-lookup"><span data-stu-id="ddd42-129">Before you publish the topology, you must create the defined file share on the defined file server.</span></span> <span data-ttu-id="ddd42-130">Einzelheiten finden Sie unter [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span><span class="sxs-lookup"><span data-stu-id="ddd42-130">For details, see [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span></span>

8. <span data-ttu-id="ddd42-131">Gehen Sie für jeden Server oder Pool, der den Dateispeicher verwendet, wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="ddd42-131">For each server or pool that uses the file store, do the following:</span></span>

   <span data-ttu-id="ddd42-132">a.</span><span class="sxs-lookup"><span data-stu-id="ddd42-132">a.</span></span> <span data-ttu-id="ddd42-133">Klicken Sie mit der rechten Maustaste auf den Server oder den Pool, und klicken Sie auf \*\*Eigenschaften bearbeiten \*\*.</span><span class="sxs-lookup"><span data-stu-id="ddd42-133">Right-click the server or pool, and then click **Edit properties**.</span></span>

   <span data-ttu-id="ddd42-134">b.</span><span class="sxs-lookup"><span data-stu-id="ddd42-134">b.</span></span> <span data-ttu-id="ddd42-135">Wählen Sie in **Eigenschaften bearbeiten** unter **Zuordnungen** in **Dateispeicher** die neue Dateifreigabe aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ddd42-135">In **Edit Properties**, under **Associations**, in **File store**, select the new file share, and then click **OK**.</span></span>

9. <span data-ttu-id="ddd42-136">Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie den Bereitstellungs-Assistenten von Skype for Business Server nach Bedarf aus.</span><span class="sxs-lookup"><span data-stu-id="ddd42-136">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> <span data-ttu-id="ddd42-137">Weitere Einzelheiten finden Sie unter [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span><span class="sxs-lookup"><span data-stu-id="ddd42-137">For details, see [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span></span>

10. <span data-ttu-id="ddd42-138">Starten Sie eine Eingabeaufforderung: Klicken Sie auf **Start**, klicken Sie auf **Ausführen**, und geben Sie dann cmd. exe ein.</span><span class="sxs-lookup"><span data-stu-id="ddd42-138">Start a command prompt: Click **Start**, click **Run**, and then type cmd.exe.</span></span>

11. <span data-ttu-id="ddd42-139">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="ddd42-139">At the command line, type the following:</span></span>

     ```console
     Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>

     ```

    > [!TIP]
    > <span data-ttu-id="ddd42-140">Der Switch „/S“ kopiert Dateien, Verzeichnisse und Unterverzeichnisse.</span><span class="sxs-lookup"><span data-stu-id="ddd42-140">The /S switch copies over files, directories and subdirectories.</span></span> <span data-ttu-id="ddd42-141">Der Switch „/XF“ überspringt alle Dateien mit dem Namen „Meeting.Active“.</span><span class="sxs-lookup"><span data-stu-id="ddd42-141">The /XF switch skips any files that are named Meeting.Active.</span></span> <span data-ttu-id="ddd42-142">Aktuelle Versionen von „robocopy.exe“ mit dem Switch „/MT“ erhöhen die Kopiergeschwindigkeit erheblich, da mehrere Threads verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ddd42-142">Current versions of the robocopy.exe with the /MT switch greatly increase copy speed by using multiple threads.</span></span> <span data-ttu-id="ddd42-143">Verwenden Sie für den/Log-Schalter einen Verzeichnispfad und einen Protokolldateinamen in Form von C:\Logfiles\log.txt.</span><span class="sxs-lookup"><span data-stu-id="ddd42-143">For the /LOG switch, use a directory path and log file name in the form of C:\Logfiles\log.txt.</span></span> <span data-ttu-id="ddd42-144">Mit diesem Switch wird eine Protokolldatei der Vorgänge an dem benannten Speicherort erstellt.</span><span class="sxs-lookup"><span data-stu-id="ddd42-144">This switch creates a log file of operations at the named location.</span></span>

12. <span data-ttu-id="ddd42-145">Klicken Sie nach Abschluss der Datenkopie in der lync Server-Systemsteuerung auf **Topologie**, und klicken Sie dann auf **Status**.</span><span class="sxs-lookup"><span data-stu-id="ddd42-145">When the data copy is complete, in Lync Server Control Panel, click **Topology**, and then click **Status**.</span></span>

13. <span data-ttu-id="ddd42-146">Wählen Sie für jeden Server oder Pool, für den Sie Dienste beendet haben, den Server oder Pool aus, klicken Sie auf **Aktion** und dann auf **Alle Dienste starten**.         </span><span class="sxs-lookup"><span data-stu-id="ddd42-146">For each server or pool where you stopped services, select the server or pool, click **Action**, and then click **Start all services**.</span></span>

14. <span data-ttu-id="ddd42-p111">Entfernen Sie den alten Dateispeicher aus der Topologie und veröffentlichen Sie dann die Topologie. Einzelheiten finden Sie unter [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span><span class="sxs-lookup"><span data-stu-id="ddd42-p111">Remove the old file store from the topology and then publish the topology. For details, see [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span></span>

15. <span data-ttu-id="ddd42-149">(Optional) Melden Sie sich bei dem Computer, der den soeben entfernten Dateispeicher enthält, als Mitglied der lokalen Administratorgruppe oder der Domänenadministratorgruppe an, und entfernen Sie dann die alte Dateifreigabe und das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="ddd42-149">(Optional) Log on to the computer that contains the file store that you just removed as a member of the local Administrators group or the Domain Admins group, and then remove the old file share and directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="ddd42-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ddd42-150">See also</span></span>


[<span data-ttu-id="ddd42-151">Erneutes Zuweisen eines Servers zu einem anderen Dateispeicher</span><span class="sxs-lookup"><span data-stu-id="ddd42-151">Reassign a Server to a Different File Store</span></span>](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[<span data-ttu-id="ddd42-152">Entfernen eines Dateispeichers</span><span class="sxs-lookup"><span data-stu-id="ddd42-152">Remove a file store</span></span>](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)

