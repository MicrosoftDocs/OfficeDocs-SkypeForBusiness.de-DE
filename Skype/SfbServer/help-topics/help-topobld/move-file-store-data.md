---
title: Dateispeicher Daten in einen neuen Dateispeicher in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/30/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 'Wenn Sie den Dateiserver entfernen möchten, der derzeit als Dateispeicher für Ihre Skype for Business Server 2015-Bereitstellung fungiert, oder wenn Sie weitere Änderungen vornehmen müssen, die den aktuellen Dateispeicher nicht verfügbar machen, müssen Sie zuerst eine neue Freigabe erstellen. Anschließend müssen Sie die folgenden Schritte ausführen:'
ms.openlocfilehash: c9bdc7ac572ecd8a71022e5a267454b795ef7cc6
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215586"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server-2015"></a><span data-ttu-id="edb53-104">Dateispeicher Daten in einen neuen Dateispeicher in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="edb53-104">Move File Store Data to a New File Store in Skype for Business Server 2015</span></span>

<span data-ttu-id="edb53-105">Wenn Sie den Dateiserver entfernen möchten, der derzeit als Dateispeicher für Ihre Skype for Business Server 2015-Bereitstellung fungiert, oder wenn Sie weitere Änderungen vornehmen müssen, die den aktuellen Dateispeicher nicht verfügbar machen, müssen Sie zuerst eine neue Freigabe erstellen.</span><span class="sxs-lookup"><span data-stu-id="edb53-105">If you need to remove the file server that is currently acting as the file store for your Skype for Business Server 2015 deployment, or if you need to make other changes that would make the current file store unavailable, you first need to create a new share.</span></span> <span data-ttu-id="edb53-106">Anschließend müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="edb53-106">Then you need to perform the following steps:</span></span>

1. <span data-ttu-id="edb53-107">Beenden Sie die Skype for Business Server 2015 Dienste, die den Dateispeicher verwenden, den Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="edb53-107">Shut down the Skype for Business Server 2015 services that use the file store that you plan to remove.</span></span>

2. <span data-ttu-id="edb53-108">Definieren Sie den Dateispeicher im Topologie-Generator, und veröffentlichen Sie die Änderungen, um den neuen Dateispeicher für Ihre Bereitstellung zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="edb53-108">Define the file store in Topology Builder and publish the changes to make the new file store available to your deployment.</span></span>

3. <span data-ttu-id="edb53-109">Verschiebt die Daten in den neuen Dateispeicher.</span><span class="sxs-lookup"><span data-stu-id="edb53-109">Move the data to the new file store.</span></span>

4. <span data-ttu-id="edb53-110">Starten Sie die Server oder Dienste neu.</span><span class="sxs-lookup"><span data-stu-id="edb53-110">Restart the servers or services.</span></span>

5. <span data-ttu-id="edb53-111">Entfernen Sie optional den alten Dateifreigabe-und Datei Ordner.</span><span class="sxs-lookup"><span data-stu-id="edb53-111">Optionally, remove the old file share and file folder.</span></span>

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a><span data-ttu-id="edb53-112">So verschieben Sie Dateispeicherdaten von einem Dateispeicher in einen neuen Dateispeicher</span><span class="sxs-lookup"><span data-stu-id="edb53-112">To move file store data from one file store to a new file store</span></span>

1. <span data-ttu-id="edb53-113">Melden Sie sich an einem Computer als Mitglied der RTCUniversersalServerAdmins-oder CsServerAdministrator-Gruppe an, in der die Skype for Business Server 2015, Verwaltungs Tools installiert sind.</span><span class="sxs-lookup"><span data-stu-id="edb53-113">Log on to a computer as a member of the RTCUniversersalServerAdmins or CsServerAdministrator group where the Skype for Business Server 2015, Administrative Tools are installed.</span></span>

2. <span data-ttu-id="edb53-114">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="edb53-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="edb53-115">Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.</span><span class="sxs-lookup"><span data-stu-id="edb53-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>

4. <span data-ttu-id="edb53-116">Wählen Sie für jeden Directorpool, Director, Standard Edition-Server und Front-End-Pool, der den zu entfernenden Dateispeicher verwendet, den Server oder den Pool aus, klicken Sie auf **Aktion**, und klicken Sie dann auf **alle Dienste beenden**.</span><span class="sxs-lookup"><span data-stu-id="edb53-116">For each Director pool, Director, Standard Edition server, and Front End pool that uses the file store that you plan to remove, select the server or pool, click **Action**, and then click **Stop all services**.</span></span>

5. <span data-ttu-id="edb53-117">Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.</span><span class="sxs-lookup"><span data-stu-id="edb53-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

6. <span data-ttu-id="edb53-118">Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Skype for Business Server 2015**, und klicken Sie dann auf **Skype for Business Server 2015Topology-Generator**.</span><span class="sxs-lookup"><span data-stu-id="edb53-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>

7. <span data-ttu-id="edb53-119">Wählen Sie einen Server oder Pool aus, der den Dateispeicher verwendet, und führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="edb53-119">Select a server or pool that uses the file store, and do the following:</span></span>

8. <span data-ttu-id="edb53-120">Klicken Sie mit der rechten Maustaste auf den Server oder den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="edb53-120">Right-click the server or pool, and then click **Edit Properties**.</span></span>

9. <span data-ttu-id="edb53-121">Klicken Sie in **Eigenschaften bearbeiten**unter **Zuordnungen**unter **Dateispeicher**auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="edb53-121">In **Edit properties**, under **Associations**, under **File store**, click **New**.</span></span>

10. <span data-ttu-id="edb53-122">Geben Sie in **neue Dateispeicher definieren**unter **Dateiserver-FQDN**den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Dateiservers ein.</span><span class="sxs-lookup"><span data-stu-id="edb53-122">In **Define New File Store**, under **File server FQDN**, type the fully qualified domain name (FQDN) of the file server.</span></span> <span data-ttu-id="edb53-123">Geben Sie unter **Dateifreigabe**den Ordnernamen für die neue Dateifreigabe ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="edb53-123">Under **File share**, type the folder name for the new file share, and then click **OK**.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="edb53-124">In diesem Schritt wird ein neuer Dateispeicher für die Verwendung im Topologie-Generator definiert.</span><span class="sxs-lookup"><span data-stu-id="edb53-124">This step defines a new file store for use in Topology Builder.</span></span> <span data-ttu-id="edb53-125">Sie definieren Sie nur einmal, nicht für jeden Server.</span><span class="sxs-lookup"><span data-stu-id="edb53-125">You define it only once, not for each server.</span></span> <span data-ttu-id="edb53-126">Vor dem Veröffentlichen der Topologie müssen Sie auf dem definierten Dateiserver die definierte Dateifreigabe erstellen.</span><span class="sxs-lookup"><span data-stu-id="edb53-126">Before you publish the topology, you must create the defined file share on the defined file server.</span></span> <span data-ttu-id="edb53-127">Ausführliche Informationen finden Sie unter [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span><span class="sxs-lookup"><span data-stu-id="edb53-127">For details, see [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span></span>

11. <span data-ttu-id="edb53-128">Führen Sie für jeden Server oder Pool, der den Dateispeicher verwendet, folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="edb53-128">For each server or pool that uses the file store, do the following:</span></span>

12. <span data-ttu-id="edb53-129">Klicken Sie mit der rechten Maustaste auf den Server oder den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="edb53-129">Right-click the server or pool, and then click **Edit properties**.</span></span>

13. <span data-ttu-id="edb53-130">Wählen Sie in **Eigenschaften bearbeiten**unter **Zuordnungen**im **Dateispeicher**die neue Dateifreigabe aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="edb53-130">In **Edit Properties**, under **Associations**, in **File store**, select the new file share, and then click **OK**.</span></span>

14. <span data-ttu-id="edb53-131">Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie dann den Assistenten für die Skype for Business Server-Bereitstellung bei Bedarf aus.</span><span class="sxs-lookup"><span data-stu-id="edb53-131">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> <span data-ttu-id="edb53-132">Ausführliche Informationen finden Sie unter [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span><span class="sxs-lookup"><span data-stu-id="edb53-132">For details, see [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span></span>

15. <span data-ttu-id="edb53-133">Starten einer Eingabeaufforderung: Klicken Sie auf **Start**, klicken Sie auf **Ausführen**, und geben Sie dann cmd.exe ein.</span><span class="sxs-lookup"><span data-stu-id="edb53-133">Start a command prompt: Click **Start**, click **Run**, and then type cmd.exe.</span></span>

16. <span data-ttu-id="edb53-134">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="edb53-134">At the command line, type the following:</span></span>

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > <span data-ttu-id="edb53-135">Der Schalter/s kopiert Dateien, Verzeichnisse und Unterverzeichnisse.</span><span class="sxs-lookup"><span data-stu-id="edb53-135">The /S switch copies over files, directories and subdirectories.</span></span> <span data-ttu-id="edb53-136">Der/XF-Schalter überspringt alle Dateien mit dem Namen "Meeting. Active".</span><span class="sxs-lookup"><span data-stu-id="edb53-136">The /XF switch skips any files that are named Meeting.Active.</span></span> <span data-ttu-id="edb53-137">In aktuellen Versionen von "robocopy.exe" mit dem /MT-Switch ist die Kopiergeschwindigkeit durch die Verwendung mehrerer Threads deutlich höher.</span><span class="sxs-lookup"><span data-stu-id="edb53-137">Current versions of the robocopy.exe with the /MT switch greatly increase copy speed by using multiple threads.</span></span> <span data-ttu-id="edb53-138">Verwenden Sie für den Parameter/Log-Switch einen Verzeichnispfad und einen Namen der Protokolldatei in Form von C:\Logfiles\log.txt.</span><span class="sxs-lookup"><span data-stu-id="edb53-138">For the /LOG switch, use a directory path and log file name in the form of C:\Logfiles\log.txt.</span></span> <span data-ttu-id="edb53-139">Mit dieser Option wird eine Protokolldatei mit Vorgängen am benannten Speicherort erstellt.</span><span class="sxs-lookup"><span data-stu-id="edb53-139">This switch creates a log file of operations at the named location.</span></span>

17. <span data-ttu-id="edb53-140">Klicken Sie nach Abschluss der Datenkopie in lync Server-Systemsteuerung auf **Topologie**, und klicken Sie dann auf **Status**.</span><span class="sxs-lookup"><span data-stu-id="edb53-140">When the data copy is complete, in Lync Server Control Panel, click **Topology**, and then click **Status**.</span></span>

18. <span data-ttu-id="edb53-141">Wählen Sie für jeden Server oder Pool, in dem Sie Dienste beendet haben, den Server oder Pool aus, klicken Sie auf **Aktion**und dann auf **alle Dienste starten**.</span><span class="sxs-lookup"><span data-stu-id="edb53-141">For each server or pool where you stopped services, select the server or pool, click **Action**, and then click **Start all services**.</span></span>

19. <span data-ttu-id="edb53-142">Entfernen Sie den alten Datenspeicher aus der Topologie, und veröffentlichen Sie dann die Topologie.</span><span class="sxs-lookup"><span data-stu-id="edb53-142">Remove the old file store from the topology and then publish the topology.</span></span> <span data-ttu-id="edb53-143">Ausführliche Informationen finden Sie unter [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span><span class="sxs-lookup"><span data-stu-id="edb53-143">For details, see [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span></span>

20. <span data-ttu-id="edb53-144">(Optional) Melden Sie sich als Mitglied der Gruppe der lokalen Administratoren oder der Gruppe "Domänen-Admins" am Computer an, der den eben von Ihnen entfernten Dateispeicher enthält, und entfernen Sie dann die alte Dateifreigabe sowie das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="edb53-144">(Optional) Log on to the computer that contains the file store that you just removed as a member of the local Administrators group or the Domain Admins group, and then remove the old file share and directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="edb53-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="edb53-145">See also</span></span>

[<span data-ttu-id="edb53-146">Erneutes Zuweisen eines Servers an einen anderen Dateispeicher</span><span class="sxs-lookup"><span data-stu-id="edb53-146">Reassign a Server to a Different File Store</span></span>](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[<span data-ttu-id="edb53-147">Entfernen eines Dateispeichers</span><span class="sxs-lookup"><span data-stu-id="edb53-147">Remove a file store</span></span>](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)
