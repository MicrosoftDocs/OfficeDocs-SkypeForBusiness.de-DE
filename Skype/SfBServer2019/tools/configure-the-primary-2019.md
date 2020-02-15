---
title: Konfigurieren des primären Verwaltungsservers
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Zusammenfassung: Konfigurieren des primären Verwaltungsservers, Installieren von System Center Operations Manager und Importieren von Management Packs für Skype for Business Server 2019.'
ms.openlocfilehash: ccc522da216b98e6f18ea381a74aff19fc5cc24d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006050"
---
# <a name="configure-the-primary-management-server"></a><span data-ttu-id="69222-103">Konfigurieren des primären Verwaltungsservers</span><span class="sxs-lookup"><span data-stu-id="69222-103">Configure the Primary Management Server</span></span>

<span data-ttu-id="69222-104">**Zusammenfassung:** Konfigurieren des primären Verwaltungsservers, Installieren von System Center Operations Manager und Importieren von Management Packs für Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="69222-104">**Summary:** Configure your primary management server, install System Center Operations Manager, and import management packs for Skype for Business Server 2019.</span></span>

<span data-ttu-id="69222-105">Um die neuen Integritäts Überwachungsfunktionen in Skype for Business Server 2019 vollständig nutzen zu können, müssen Sie zunächst einen Computer festlegen, der als primärer Verwaltungs Server fungieren soll.</span><span class="sxs-lookup"><span data-stu-id="69222-105">To take full advantage of the new health monitoring capabilities included in Skype for Business Server 2019, you must first designate a computer to act as your primary management server.</span></span> <span data-ttu-id="69222-106">Anschließend müssen Sie System Center Operations Manager 2012 SP1 oder R2 oder System Center Operations Manager 2007 R2 auf diesem Computer installieren.</span><span class="sxs-lookup"><span data-stu-id="69222-106">You must then install System Center Operations Manager 2012 SP1 or R2 or System Center Operations Manager 2007 R2 on that computer.</span></span> <span data-ttu-id="69222-107">Darüber hinaus müssen Sie zuerst eine unterstützte Version von SQL Server installieren, die als Operations Manager-Back-End-Datenbank fungiert.</span><span class="sxs-lookup"><span data-stu-id="69222-107">In addition, you must first install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span>

<span data-ttu-id="69222-108">Bei der Installation von System Center Operations Manager müssen Sie alle Komponenten des Produkts installieren, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="69222-108">When you install System Center Operations Manager, you will need to install all the components of that product, including:</span></span>

- <span data-ttu-id="69222-109">Betriebsdatenbank</span><span class="sxs-lookup"><span data-stu-id="69222-109">Operational database</span></span>

- <span data-ttu-id="69222-110">Server</span><span class="sxs-lookup"><span data-stu-id="69222-110">Server</span></span>

- <span data-ttu-id="69222-111">Konsole</span><span class="sxs-lookup"><span data-stu-id="69222-111">Console</span></span>

- <span data-ttu-id="69222-112">Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="69222-112">Windows PowerShell cmdlets</span></span>

- <span data-ttu-id="69222-113">Webkonsole</span><span class="sxs-lookup"><span data-stu-id="69222-113">Web console</span></span>

- <span data-ttu-id="69222-114">Reporting</span><span class="sxs-lookup"><span data-stu-id="69222-114">Reporting</span></span>

- <span data-ttu-id="69222-115">Data Warehouse</span><span class="sxs-lookup"><span data-stu-id="69222-115">Data warehouse</span></span>

> [!IMPORTANT]
> <span data-ttu-id="69222-116">Das "[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/download/details.aspx?id=6442)" muss installiert werden, bevor Sie System Center Operations Manager 2012 installieren.</span><span class="sxs-lookup"><span data-stu-id="69222-116">The "[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/download/details.aspx?id=6442)" needs to be installed before you install System Center Operations Manager 2012.</span></span>

<span data-ttu-id="69222-117">Ausführliche Informationen zu diesen Produkten und deren Installation finden Sie unter den folgenden Links:</span><span class="sxs-lookup"><span data-stu-id="69222-117">For details about these products and their installation, see the following links:</span></span>

- [<span data-ttu-id="69222-118">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="69222-118">System Center Operations Manager 2012</span></span>](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [<span data-ttu-id="69222-119">System Center-Operations Manager 2007</span><span class="sxs-lookup"><span data-stu-id="69222-119">System Center Operations Manager 2007</span></span>](https://technet.microsoft.com/library/bb735860.aspx)

<span data-ttu-id="69222-120">Beachten Sie, dass pro Skype for Business Server-Bereitstellung nur ein Stamm Verwaltungs Server vorhanden sein kann.</span><span class="sxs-lookup"><span data-stu-id="69222-120">Keep in mind that you can have only one Root Management Server per Skype for Business Server deployment.</span></span>

## <a name="importing-the-skype-for-business-server-2019-management-packs"></a><span data-ttu-id="69222-121">Importieren der Skype for Business Server 2019-Management Packs</span><span class="sxs-lookup"><span data-stu-id="69222-121">Importing the Skype for Business Server 2019 Management Packs</span></span>

<span data-ttu-id="69222-122">Sie können die Funktionen von System Center Operations Manager erweitern, indem Sie Management Packs installieren – Software, die bestimmt, welche Elemente System Center Operations Manager überwachen kann, wie diese Elemente überwacht werden sollen und wie Warnungen ausgelöst werden sollen und gemeldet.</span><span class="sxs-lookup"><span data-stu-id="69222-122">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, how those items should be monitored, and how alerts should be triggered and reported.</span></span> <span data-ttu-id="69222-123">Skype for Business Server 2019 umfasst zwei System Center Operations Manager-Management Packs, die die folgenden Funktionen bieten:</span><span class="sxs-lookup"><span data-stu-id="69222-123">Skype for Business Server 2019 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

- <span data-ttu-id="69222-124">**Das Component and User Management Pack** (Microsoft.ls.2019.Monitoring.ComponentAndUser.MP) verfolgt Skype for Business Server Probleme, die in Ereignisprotokollen aufgezeichnet, von Leistungsindikatoren registriert oder in den CDRs (Call Detail Records) oder in den QoE-Datenbanken (Quality of Experience) protokolliert wurden.</span><span class="sxs-lookup"><span data-stu-id="69222-124">**The Component and User Management Pack** (Microsoft.LS.2019.Monitoring.ComponentAndUser.mp) tracks Skype for Business Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDRs) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="69222-125">Bei kritischen Problemen kann System Center Operations Manager so konfiguriert werden, dass Administratoren sofort über e-Mail, Sofortnachrichten oder SMS benachrichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="69222-125">For critical issues, System Center Operations Manager can be configured to immediately notify administrators through email, instant message, or SMS messaging.</span></span> <span data-ttu-id="69222-126">(SMS oder kurzer Nachrichtendienst ist die Technologie, mit der Textnachrichten von einem Mobilgerät an ein anderes gesendet werden.)</span><span class="sxs-lookup"><span data-stu-id="69222-126">(SMS, or Short Message Service, is the technology used to send text messages from one mobile device to another.)</span></span>

    > [!NOTE]
    >  <span data-ttu-id="69222-127">Ausführliche Informationen zum Konfigurieren von Operations Manager-Benachrichtigungen finden Sie unter [Konfigurieren von Benachrichtigungen](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="69222-127">For details about configuring Operations Manager notification, see [Configuring Notification](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).</span></span>

- <span data-ttu-id="69222-128">**Das Active Monitoring Management Pack** (Microsoft.ls.2019.Monitoring.ActiveMonitoring.MP) testet die Schlüssel Skype for Business Server Komponenten proaktiv, beispielsweise das Anmelden beim System, das Austauschen von Chatnachrichten oder das tätigen von Anrufen an ein Telefon im öffentlichen Telefonnetz (PSTN).</span><span class="sxs-lookup"><span data-stu-id="69222-128">**The Active Monitoring Management Pack** (Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp) proactively tests key Skype for Business Server components, such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="69222-129">Diese Tests werden mithilfe der Cmdlets für synthetische Transaktionen Skype for Business Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="69222-129">These tests are conducted by using the Skype for Business Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="69222-130">Zum Beispiel wird das **Test-CsIM**-Cmdlet verwendet, um eine Sofortnachrichtenunterhaltung zwischen zwei Testbenutzern zu simulieren.</span><span class="sxs-lookup"><span data-stu-id="69222-130">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="69222-131">Wenn diese simulierte Unterhaltung fehlschlägt, wird eine Warnung generiert.</span><span class="sxs-lookup"><span data-stu-id="69222-131">If this simulated conversation fails, an alert is generated.</span></span>

<span data-ttu-id="69222-132">Das Importieren der Management Packs ist ein wichtiger Schritt.</span><span class="sxs-lookup"><span data-stu-id="69222-132">Importing the management packs is a crucial step.</span></span> <span data-ttu-id="69222-133">Wenn die Management Packs nicht importiert werden, können Sie Operations Manager nicht verwenden, um Skype for Business Server Ereignisse zu überwachen oder Skype for Business Server synthetische Transaktionen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="69222-133">If the management packs are not imported, you will not be able to use Operations Manager to monitor Skype for Business Server events or run Skype for Business Server synthetic transactions.</span></span>

<span data-ttu-id="69222-134">Das Component-und User Management Pack wird nur zum Überwachen von Skype for Business Server 2019 verwendet.</span><span class="sxs-lookup"><span data-stu-id="69222-134">The Component and User Management Pack is used to monitor only Skype for Business Server 2019.</span></span> <span data-ttu-id="69222-135">Wenn Sie sich in einem Szenario mit Koexistenz befinden, in dem sowohl Skype for Business Server 2019 als auch Skype for Business Server 2015 installiert sind, sollten Sie weiterhin die Skype for Business Server 2015 Management Packs für Ihre Skype for Business Server 2015 Computer verwenden.</span><span class="sxs-lookup"><span data-stu-id="69222-135">If you are in a coexistence scenario where both Skype for Business Server 2019 and Skype for Business Server 2015 are installed, you should continue to use the Skype for Business Server 2015 management packs for your Skype for Business Server 2015 computers.</span></span>

> [!NOTE]
> <span data-ttu-id="69222-136">Zu den Management Packs für Skype for Business Server 2019 gehören die Skype for Business Server 2019-Komponente und das User Management Pack sowie das Management Pack für die Skype for Business Server 2019 Active Monitoring.</span><span class="sxs-lookup"><span data-stu-id="69222-136">Management packs for Skype for Business Server 2019 include the Skype for Business Server 2019 Component and User Management Pack and the Skype for Business Server 2019 Active Monitoring Management Pack.</span></span>

<span data-ttu-id="69222-137">Zum Importieren der Management Packs können folgende Tools verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="69222-137">You can use one of the following tools to import management packs:</span></span>

- <span data-ttu-id="69222-138">**System Center Operations Manager** Mit dieser Methode verwenden Sie den Operations Manager, um die Überwachung für Skype for Business Server hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="69222-138">**System Center Operations Manager** With this method, you use the Operations Manager to add monitoring for Skype for Business Server.</span></span>

- <span data-ttu-id="69222-139">**Operations Manager-Shell** Sie können die Operations Manager-Shell verwenden, um direkt zu importieren, oder um Probleme zu beheben, die beim Importieren von Management Packs mithilfe der System Center Operations Manager-Konsole auftreten.</span><span class="sxs-lookup"><span data-stu-id="69222-139">**Operations Manager Shell** You can use the Operations Manager Shell to import directly, or to troubleshoot any issues that you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="69222-140">Importieren der Management Packs mithilfe von System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="69222-140">Importing the Management Packs by Using System Center Operations Manager</span></span>

1. <span data-ttu-id="69222-141">Laden Sie die SkypeForBusiness2019ManagementPacks. msi aus den Microsoft-Webdownloads herunter, und installieren Sie die MSI-Datei.</span><span class="sxs-lookup"><span data-stu-id="69222-141">Download the SkypeForBusiness2019ManagementPacks.msi from the Microsoft Web downloads, and install the msi.</span></span>

2. <span data-ttu-id="69222-142">Klicken Sie in System Center Operations Manager auf **Verwaltung**.</span><span class="sxs-lookup"><span data-stu-id="69222-142">In System Center Operations Manager, click **Administration**.</span></span>

3. <span data-ttu-id="69222-143">Klicken Sie auf der \*\*\*\* Verwaltungsseite mit der rechten Maustaste auf Management Packs, und klicken Sie anschließend auf **Management Packs importieren**.</span><span class="sxs-lookup"><span data-stu-id="69222-143">In the Administration pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4. <span data-ttu-id="69222-144">Klicken Sie im Dialogfeld **Management Packs auswählen** auf **Hinzufügen** und anschließend auf **Von Datenträger hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="69222-144">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5. <span data-ttu-id="69222-145">Klicken Sie im Dialogfeld **Online Katalogverbindung** auf **Nein**.</span><span class="sxs-lookup"><span data-stu-id="69222-145">In the **Online Catalog Connection** dialog box, click **No**.</span></span>

6. <span data-ttu-id="69222-146">Suchen Sie im Dialogfeld **zu importierende Management Packs auswählen nach** den Dateien Microsoft.ls.2019.Monitoring.ActiveMonitoring.MP und Microsoft.ls.2019.Monitoring.ComponentAndUser.MP, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="69222-146">In the **Select Management Packs to import** dialog box, locate and select the files Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2019.Monitoring.ComponentAndUser.mp, and then click **Open**.</span></span> <span data-ttu-id="69222-147">Wenn Sie mehrere Dateien im Dialogfeld auswählen möchten, klicken Sie auf die erste Datei, halten Sie die STRG-Taste gedrückt, und klicken Sie dann auf die nachfolgenden Dateien.</span><span class="sxs-lookup"><span data-stu-id="69222-147">To select multiple files in the dialog box, click the first file, and then hold down the Ctrl key and click the subsequent files.</span></span>

7. <span data-ttu-id="69222-148">Klicken Sie im Dialogfeld **Management Packs auswählen** auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="69222-148">In the **Select Management Packs** dialog box, click **Install**.</span></span> <span data-ttu-id="69222-149">Wenn eine Fehlermeldung angezeigt wird und bei der Installation ein Fehler auftritt, bedeutet das normalerweise, dass sich die Management Pack-Dateien in einem Ordner befinden, der durch die Windows-Benutzerkontensteuerung geschützt ist.</span><span class="sxs-lookup"><span data-stu-id="69222-149">If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control.</span></span> <span data-ttu-id="69222-150">In diesem Fall kopieren Sie die Dateien in einen anderen Ordner, und starten Sie dann den Import-und Installationsvorgang neu.</span><span class="sxs-lookup"><span data-stu-id="69222-150">If this occurs, copy the files to a different folder, and then restart the import and installation process.</span></span>

8. <span data-ttu-id="69222-151">Klicken Sie im Dialogfeld **Management Packs auswählen** auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="69222-151">In the **Select Management Packs** dialog box, click **Close**.</span></span> <span data-ttu-id="69222-152">Der Import-und Installationsvorgang kann mehrere Minuten in Anspruch setzen.</span><span class="sxs-lookup"><span data-stu-id="69222-152">The import and installation process might require several minutes to complete.</span></span>

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="69222-153">Importieren der Management Packs mithilfe der Operations Manager-Shell</span><span class="sxs-lookup"><span data-stu-id="69222-153">Importing the Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="69222-154">Im Allgemeinen ist es einfacher, die Management Packs mithilfe der Operations Manager-Konsole zu importieren.</span><span class="sxs-lookup"><span data-stu-id="69222-154">In general, it is easier to import the management packs by using the Operations Manager console.</span></span> <span data-ttu-id="69222-155">Wenn jedoch ein Fehler auftritt und der Import fehlschlägt, stellt die Konsole nicht immer angemessene Fehlerberichte bereit.</span><span class="sxs-lookup"><span data-stu-id="69222-155">However, if an error occurs and the import fails, the console does not always provide adequate error reports.</span></span> <span data-ttu-id="69222-156">Im Vergleich dazu enthält die Operations Manager-Shell detaillierte Informationen.</span><span class="sxs-lookup"><span data-stu-id="69222-156">By comparison, the Operations Manager Shell provides detailed information.</span></span> <span data-ttu-id="69222-157">Wenn Sie Operations Manager verwenden und beim Importieren eines Management Packs Probleme auftreten, importieren Sie das Paket mithilfe der Operations Manager-Shell.</span><span class="sxs-lookup"><span data-stu-id="69222-157">If you are using Operations Manager and you encounter issues when importing a management pack, import the pack by using the Operations Manager Shell.</span></span> <span data-ttu-id="69222-158">Mithilfe der von Operations Manager-Shell bereitgestellten Informationen können Sie ermitteln, warum der Import fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="69222-158">The information provided by Operations Manager Shell can help you determine why the import failed.</span></span>

1. <span data-ttu-id="69222-159">Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft System Center 2012**, dann auf **Operations Manager**, und klicken Sie dann auf **Operations Manager-Shell**.</span><span class="sxs-lookup"><span data-stu-id="69222-159">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2. <span data-ttu-id="69222-160">Geben Sie in Operations Manager-Shell den folgenden Befehl an der Eingabeaufforderung ein, wobei Sie den tatsächlichen Pfad zu Ihrer Kopie der Datei Microsoft.ls.2019.Monitoring.ActiveMonitoring.MP verwenden, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="69222-160">In Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp"
   ```

3. <span data-ttu-id="69222-161">Nachdem Sie das erste Management Pack importiert haben, wiederholen Sie den Vorgang, indem Sie den Pfad zu Ihrer Kopie der Datei Microsoft.ls.2019.Monitoring.ComponentAndUser.MP:</span><span class="sxs-lookup"><span data-stu-id="69222-161">After you have imported the first management pack, repeat the process, using the path to your copy of the file Microsoft.LS.2019.Monitoring.ComponentAndUser.mp:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ComponentAndUser.mp"
   ```
