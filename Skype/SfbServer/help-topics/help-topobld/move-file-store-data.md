---
title: Verschieben von Dateispeicherdaten in einen neuen Dateispeicher in Skype for Business Server 2015
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/30/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 'Wenn müssen Sie den Dateiserver zu entfernen, der derzeit fungiert als den Dateispeicher für Ihre Skype für die Bereitstellung von Business Server 2015 ist oder wenn Sie andere vornehmen müssen Änderungen, die die aktuelle Datei vornehmen würden nicht verfügbar speichern, müssen Sie zuerst eine neue Freigabe erstellen. Dann müssen Sie folgende Schritte ausführen:'
ms.openlocfilehash: 364b63c1c93ed9a817596cb90cbe1ea92198a514
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199987"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server-2015"></a><span data-ttu-id="fb523-104">Verschieben von Dateispeicherdaten in einen neuen Dateispeicher in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="fb523-104">Move File Store Data to a New File Store in Skype for Business Server 2015</span></span>

<span data-ttu-id="fb523-105">Wenn müssen Sie den Dateiserver zu entfernen, der derzeit fungiert als den Dateispeicher für Ihre Skype für die Bereitstellung von Business Server 2015 ist oder wenn Sie andere vornehmen müssen Änderungen, die die aktuelle Datei vornehmen würden nicht verfügbar speichern, müssen Sie zuerst eine neue Freigabe erstellen.</span><span class="sxs-lookup"><span data-stu-id="fb523-105">If you need to remove the file server that is currently acting as the file store for your Skype for Business Server 2015 deployment, or if you need to make other changes that would make the current file store unavailable, you first need to create a new share.</span></span> <span data-ttu-id="fb523-106">Dann müssen Sie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="fb523-106">Then you need to perform the following steps:</span></span>

1. <span data-ttu-id="fb523-107">Fahren Sie den Skype für Business Server 2015 Dienste, die den Dateispeicher zu verwenden, den Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="fb523-107">Shut down the Skype for Business Server 2015 services that use the file store that you plan to remove.</span></span>

2. <span data-ttu-id="fb523-108">Definieren Sie des Dateispeichers im Topologie-Generator, und veröffentlichen Sie die Änderungen der neuen Dateispeicher für Ihre Bereitstellung zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="fb523-108">Define the file store in Topology Builder and publish the changes to make the new file store available to your deployment.</span></span>

3. <span data-ttu-id="fb523-109">Verschieben Sie die Dateien in den neuen Dateispeicher.</span><span class="sxs-lookup"><span data-stu-id="fb523-109">Move the data to the new file store.</span></span>

4. <span data-ttu-id="fb523-110">Starten Sie die Server bzw. Dienste neu.</span><span class="sxs-lookup"><span data-stu-id="fb523-110">Restart the servers or services.</span></span>

5. <span data-ttu-id="fb523-111">Optional können Sie die alte Dateifreigabe und den Dateiordner entfernen.</span><span class="sxs-lookup"><span data-stu-id="fb523-111">Optionally, remove the old file share and file folder.</span></span>

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a><span data-ttu-id="fb523-112">So verschieben Sie Dateispeicherdaten von einem Dateispeicher in einen neuen Dateispeicher</span><span class="sxs-lookup"><span data-stu-id="fb523-112">To move file store data from one file store to a new file store</span></span>

1. <span data-ttu-id="fb523-113">Melden Sie sich an einem Computer als Mitglied der Gruppe RTCUniversersalServerAdmins oder CsServerAdministrator, auf dem die Skype für Business Server 2015, Verwaltungstools installiert sind.</span><span class="sxs-lookup"><span data-stu-id="fb523-113">Log on to a computer as a member of the RTCUniversersalServerAdmins or CsServerAdministrator group where the Skype for Business Server 2015, Administrative Tools are installed.</span></span>

2. <span data-ttu-id="fb523-114">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="fb523-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="fb523-115">Klicken Sie in der linken Navigationsleiste auf \*\*Topologie \*\* und dann auf **Status**. </span><span class="sxs-lookup"><span data-stu-id="fb523-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>

4. <span data-ttu-id="fb523-116">Wählen Sie für jede Director-Pool, Director, Standard Edition-Server und Front-End-Pool, den Dateispeicher verwendet, den Sie entfernen möchten den Server oder Pool, klicken Sie auf **Aktion**und klicken Sie dann auf **alle Dienste beenden**.</span><span class="sxs-lookup"><span data-stu-id="fb523-116">For each Director pool, Director, Standard Edition server, and Front End pool that uses the file store that you plan to remove, select the server or pool, click **Action**, and then click **Stop all services**.</span></span>

5. <span data-ttu-id="fb523-117">Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.</span><span class="sxs-lookup"><span data-stu-id="fb523-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

6. <span data-ttu-id="fb523-118">Starten des Topologie-Generators: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Business Server 2015**, und klicken Sie dann auf **Skype für Business Server 2015Topology-Generator**.</span><span class="sxs-lookup"><span data-stu-id="fb523-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>

7. <span data-ttu-id="fb523-119">Wählen Sie einen Server oder Pool aus, der den Dateispeicher verwendet, und gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="fb523-119">Select a server or pool that uses the file store, and do the following:</span></span>

8. <span data-ttu-id="fb523-120">Klicken Sie mit der rechten Maustaste auf den Server oder den Pool, und klicken Sie auf \*\*Eigenschaften bearbeiten \*\*. </span><span class="sxs-lookup"><span data-stu-id="fb523-120">Right-click the server or pool, and then click **Edit Properties**.</span></span>

9. <span data-ttu-id="fb523-121">Klicken Sie in **Eigenschaften bearbeiten** unter **Zuordnungen** und unter **Dateispeicher** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="fb523-121">In **Edit properties**, under **Associations**, under **File store**, click **New**.</span></span>

10. <span data-ttu-id="fb523-p103">Geben Sie in **Neuen Dateispeicher definieren** unter **Dateiserver-FQDN** den vollqualifizierten Domänennamen (FQDN) des Dateiservers ein. Geben Sie unter **Dateifreigabe** den Ordnernamen für die neue Dateifreigabe ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb523-p103">In **Define New File Store**, under **File server FQDN**, type the fully qualified domain name (FQDN) of the file server. Under **File share**, type the folder name for the new file share, and then click **OK**.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="fb523-124">Dieser Schritt definiert einen neuen Dateispeicher für die Verwendung im Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="fb523-124">This step defines a new file store for use in Topology Builder.</span></span> <span data-ttu-id="fb523-125">Die Definition erfolgt nur einmal, nicht für jeden Server.</span><span class="sxs-lookup"><span data-stu-id="fb523-125">You define it only once, not for each server.</span></span> <span data-ttu-id="fb523-126">Bevor Sie die Topologie veröffentlichen, müssen Sie die definierte Dateifreigabe auf dem definierten Dateiserver erstellen.</span><span class="sxs-lookup"><span data-stu-id="fb523-126">Before you publish the topology, you must create the defined file share on the defined file server.</span></span> <span data-ttu-id="fb523-127">Einzelheiten finden Sie unter [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span><span class="sxs-lookup"><span data-stu-id="fb523-127">For details, see [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span></span>

11. <span data-ttu-id="fb523-128">Gehen Sie für jeden Server oder Pool, der den Dateispeicher verwendet, wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="fb523-128">For each server or pool that uses the file store, do the following:</span></span>

12. <span data-ttu-id="fb523-129">Klicken Sie mit der rechten Maustaste auf den Server oder den Pool, und klicken Sie auf \*\*Eigenschaften bearbeiten \*\*.</span><span class="sxs-lookup"><span data-stu-id="fb523-129">Right-click the server or pool, and then click **Edit properties**.</span></span>

13. <span data-ttu-id="fb523-130">Wählen Sie in **Eigenschaften bearbeiten** unter **Zuordnungen** in **Dateispeicher** die neue Dateifreigabe aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb523-130">In **Edit Properties**, under **Associations**, in **File store**, select the new file share, and then click **OK**.</span></span>

14. <span data-ttu-id="fb523-131">Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus und führen Sie dann die Skype für Business Server-Bereitstellungs-Assistenten aus, je nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="fb523-131">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> <span data-ttu-id="fb523-132">Weitere Einzelheiten finden Sie unter [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span><span class="sxs-lookup"><span data-stu-id="fb523-132">For details, see [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span></span>

15. <span data-ttu-id="fb523-133">Starten Sie eine Eingabeaufforderung: Klicken Sie auf **Start**, klicken Sie auf **Ausführen**, und geben Sie cmd.exe.</span><span class="sxs-lookup"><span data-stu-id="fb523-133">Start a command prompt: Click **Start**, click **Run**, and then type cmd.exe.</span></span>

16. <span data-ttu-id="fb523-134">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="fb523-134">At the command line, type the following:</span></span>

    ```
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > <span data-ttu-id="fb523-135">Der Switch „/S“ kopiert Dateien, Verzeichnisse und Unterverzeichnisse.</span><span class="sxs-lookup"><span data-stu-id="fb523-135">The /S switch copies over files, directories and subdirectories.</span></span> <span data-ttu-id="fb523-136">Der Switch „/XF“ überspringt alle Dateien mit dem Namen „Meeting.Active“.</span><span class="sxs-lookup"><span data-stu-id="fb523-136">The /XF switch skips any files that are named Meeting.Active.</span></span> <span data-ttu-id="fb523-137">Aktuelle Versionen von „robocopy.exe“ mit dem Switch „/MT“ erhöhen die Kopiergeschwindigkeit erheblich, da mehrere Threads verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fb523-137">Current versions of the robocopy.exe with the /MT switch greatly increase copy speed by using multiple threads.</span></span> <span data-ttu-id="fb523-138">Verwenden Sie für die Option Befehlszeilenoption/log zusammen einen Directory Pfad und Protokolldateien Dateinamen in Form von C:\Logfiles\log.txt.</span><span class="sxs-lookup"><span data-stu-id="fb523-138">For the /LOG switch, use a directory path and log file name in the form of C:\Logfiles\log.txt.</span></span> <span data-ttu-id="fb523-139">Mit diesem Switch wird eine Protokolldatei der Vorgänge an dem benannten Speicherort erstellt.</span><span class="sxs-lookup"><span data-stu-id="fb523-139">This switch creates a log file of operations at the named location.</span></span>

17. <span data-ttu-id="fb523-140">Wenn das Kopieren der Daten in Lync Server-Systemsteuerung abgeschlossen ist, klicken Sie auf **Topologie**, und klicken Sie dann auf **Status**.</span><span class="sxs-lookup"><span data-stu-id="fb523-140">When the data copy is complete, in Lync Server Control Panel, click **Topology**, and then click **Status**.</span></span>

18. <span data-ttu-id="fb523-141">Wählen Sie für jeden Server oder Pool, für den Sie Dienste beendet haben, den Server oder Pool aus, klicken Sie auf **Aktion** und dann auf **Alle Dienste starten**.         </span><span class="sxs-lookup"><span data-stu-id="fb523-141">For each server or pool where you stopped services, select the server or pool, click **Action**, and then click **Start all services**.</span></span>

19. <span data-ttu-id="fb523-p107">Entfernen Sie den alten Dateispeicher aus der Topologie und veröffentlichen Sie dann die Topologie. Einzelheiten finden Sie unter [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span><span class="sxs-lookup"><span data-stu-id="fb523-p107">Remove the old file store from the topology and then publish the topology. For details, see [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span></span>

20. <span data-ttu-id="fb523-144">(Optional) Melden Sie sich bei dem Computer, der den soeben entfernten Dateispeicher enthält, als Mitglied der lokalen Administratorgruppe oder der Domänenadministratorgruppe an, und entfernen Sie dann die alte Dateifreigabe und das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="fb523-144">(Optional) Log on to the computer that contains the file store that you just removed as a member of the local Administrators group or the Domain Admins group, and then remove the old file share and directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="fb523-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb523-145">See also</span></span>

[<span data-ttu-id="fb523-146">Erneutes Zuweisen eines Servers auf einen anderen Dateispeicher</span><span class="sxs-lookup"><span data-stu-id="fb523-146">Reassign a Server to a Different File Store</span></span>](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[<span data-ttu-id="fb523-147">Entfernen eines Dateispeichers</span><span class="sxs-lookup"><span data-stu-id="fb523-147">Remove a file store</span></span>](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)
