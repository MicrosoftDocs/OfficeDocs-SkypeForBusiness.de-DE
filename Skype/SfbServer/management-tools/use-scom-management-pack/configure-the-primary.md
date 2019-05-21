---
title: Konfigurieren des primären Verwaltungsservers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7e21cce-1dd2-489a-a2eb-f632799f7523
description: 'Zusammenfassung: Konfigurieren Sie Ihren primären Verwaltungsserver, installieren Sie System Center Operations Manager, und importieren Sie Management Packs für Skype for Business Server 2015.'
ms.openlocfilehash: a89ee8ca7c7f5601d9219ef49643adc2ebf99883
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277671"
---
# <a name="configure-the-primary-management-server"></a><span data-ttu-id="4a5db-103">Konfigurieren des primären Verwaltungsservers</span><span class="sxs-lookup"><span data-stu-id="4a5db-103">Configure the Primary Management Server</span></span>

<span data-ttu-id="4a5db-104">**Zusammenfassung:** Konfigurieren Sie Ihren primären Verwaltungsserver, installieren Sie System Center Operations Manager, und importieren Sie Management Packs für Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="4a5db-104">**Summary:** Configure your primary management server, install System Center Operations Manager, and import management packs for Skype for Business Server 2015.</span></span>

<span data-ttu-id="4a5db-105">Um die neuen Integritäts Überwachungsfunktionen in Skype for Business Server 2015 optimal nutzen zu können, müssen Sie zunächst einen Computer als primären Verwaltungs Server festlegen.</span><span class="sxs-lookup"><span data-stu-id="4a5db-105">To take full advantage of the new health monitoring capabilities included in Skype for Business Server 2015, you must first designate a computer to act as your primary management server.</span></span> <span data-ttu-id="4a5db-106">Sie müssen dann System Center Operations Manager 2012 SP1 oder R2 oder System Center Operations Manager 2007 R2 auf diesem Computer installieren.</span><span class="sxs-lookup"><span data-stu-id="4a5db-106">You must then install System Center Operations Manager 2012 SP1 or R2 or System Center Operations Manager 2007 R2 on that computer.</span></span> <span data-ttu-id="4a5db-107">Darüber hinaus müssen Sie zuerst eine unterstützte Version von SQL Server installieren, um als Operations Manager-Back-End-Datenbank zu funktionieren.</span><span class="sxs-lookup"><span data-stu-id="4a5db-107">In addition, you must first install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span>

<span data-ttu-id="4a5db-108">Wenn Sie System Center Operations Manager installieren, müssen Sie alle Komponenten dieses Produkts installieren, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="4a5db-108">When you install System Center Operations Manager, you will need to install all the components of that product, including:</span></span>

- <span data-ttu-id="4a5db-109">Betriebsdatenbank</span><span class="sxs-lookup"><span data-stu-id="4a5db-109">Operational database</span></span>

- <span data-ttu-id="4a5db-110">Server</span><span class="sxs-lookup"><span data-stu-id="4a5db-110">Server</span></span>

- <span data-ttu-id="4a5db-111">Konsole</span><span class="sxs-lookup"><span data-stu-id="4a5db-111">Console</span></span>

- <span data-ttu-id="4a5db-112">Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="4a5db-112">Windows PowerShell cmdlets</span></span>

- <span data-ttu-id="4a5db-113">Webkonsole</span><span class="sxs-lookup"><span data-stu-id="4a5db-113">Web console</span></span>

- <span data-ttu-id="4a5db-114">Berichterstellung</span><span class="sxs-lookup"><span data-stu-id="4a5db-114">Reporting</span></span>

- <span data-ttu-id="4a5db-115">Data Warehouse</span><span class="sxs-lookup"><span data-stu-id="4a5db-115">Data warehouse</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4a5db-116">Bevor Sie System Center Operations Manager 2012 installieren, muss das "[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/en-us/download/details.aspx?id=6442)" installiert werden.</span><span class="sxs-lookup"><span data-stu-id="4a5db-116">The "[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/en-us/download/details.aspx?id=6442)" needs to be installed before you install System Center Operations Manager 2012.</span></span>

<span data-ttu-id="4a5db-117">Ausführliche Informationen zu diesen Produkten und ihrer Installation finden Sie unter folgenden Links:</span><span class="sxs-lookup"><span data-stu-id="4a5db-117">For details about these products and their installation, see the following links:</span></span>

- [<span data-ttu-id="4a5db-118">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="4a5db-118">System Center Operations Manager 2012</span></span>](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [<span data-ttu-id="4a5db-119">System Center Operations Manager 2007</span><span class="sxs-lookup"><span data-stu-id="4a5db-119">System Center Operations Manager 2007</span></span>](https://technet.microsoft.com/en-us/library/bb735860.aspx)

<span data-ttu-id="4a5db-120">Beachten Sie, dass pro Skype for Business Server-Bereitstellung nur ein Stammverwaltungsserver vorhanden sein kann.</span><span class="sxs-lookup"><span data-stu-id="4a5db-120">Keep in mind that you can have only one Root Management Server per Skype for Business Server deployment.</span></span>

## <a name="importing-the-skype-for-business-server-2015-management-packs"></a><span data-ttu-id="4a5db-121">Importieren der Skype for Business Server 2015 Management Packs</span><span class="sxs-lookup"><span data-stu-id="4a5db-121">Importing the Skype for Business Server 2015 Management Packs</span></span>

<span data-ttu-id="4a5db-122">Sie können die Funktionen von System Center Operations Manager erweitern, indem Sie Management Packs installieren – Software, die festlegt, welche Elemente System Center Operations Manager überwachen kann, wie diese Elemente überwacht werden sollen und wie Benachrichtigungen ausgelöst werden sollen und berichtet.</span><span class="sxs-lookup"><span data-stu-id="4a5db-122">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, how those items should be monitored, and how alerts should be triggered and reported.</span></span> <span data-ttu-id="4a5db-123">Skype for Business Server 2015 umfasst zwei System Center Operations Manager-Verwaltungspakete, die die folgenden Funktionen bieten:</span><span class="sxs-lookup"><span data-stu-id="4a5db-123">Skype for Business Server 2015 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

- <span data-ttu-id="4a5db-124">**Das Komponenten-und Benutzer Verwaltungspaket** (Microsoft.ls.2015.Monitoring.ComponentAndUser.MP) verfolgt Skype for Business-Server Probleme, die in Ereignisprotokollen aufgezeichnet, von Leistungsindikatoren registriert oder in den Anruf Detaildatensätzen (CDRs) oder den QoE-Datenbanken (Quality of Experience) protokolliert wurden.</span><span class="sxs-lookup"><span data-stu-id="4a5db-124">**The Component and User Management Pack** (Microsoft.LS.2015.Monitoring.ComponentAndUser.mp) tracks Skype for Business Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDRs) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="4a5db-125">Bei kritischen Problemen kann System Center Operations Manager so konfiguriert werden, dass Administratoren sofort per e-Mail, Sofortnachricht oder SMS benachrichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="4a5db-125">For critical issues, System Center Operations Manager can be configured to immediately notify administrators through email, instant message, or SMS messaging.</span></span> <span data-ttu-id="4a5db-126">(SMS ist die Technologie, die verwendet wird, um Textnachrichten von einem Mobilgerät an ein anderes zu senden.)</span><span class="sxs-lookup"><span data-stu-id="4a5db-126">(SMS, or Short Message Service, is the technology used to send text messages from one mobile device to another.)</span></span>

    > [!NOTE]
    >  <span data-ttu-id="4a5db-127">Details zum Konfigurieren der Operations Manager-Benachrichtigung finden Sie unter [Konfigurieren der Benachrichtigung](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="4a5db-127">For details about configuring Operations Manager notification, see [Configuring Notification](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).</span></span>

- <span data-ttu-id="4a5db-128">**Das aktive Überwachungs Management Pack** (Microsoft.ls.2015.Monitoring.ActiveMonitoring.MP) testet die Schlüsselkomponenten von Skype for Business Server proaktiv, beispielsweise die Anmeldung beim System, den Austausch von Sofortnachrichten oder Anrufe an ein Telefon, das sich im öffentlichen Telefonnetz befindet (PSTN ).</span><span class="sxs-lookup"><span data-stu-id="4a5db-128">**The Active Monitoring Management Pack** (Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp) proactively tests key Skype for Business Server components, such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="4a5db-129">Diese Tests werden mithilfe der Skype for Business Server-Cmdlets für synthetische Transaktionen durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="4a5db-129">These tests are conducted by using the Skype for Business Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="4a5db-130">Zum Beispiel wird das **Test-CsIM**-Cmdlet verwendet, um eine Sofortnachrichtenunterhaltung zwischen zwei Testbenutzern zu simulieren.</span><span class="sxs-lookup"><span data-stu-id="4a5db-130">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="4a5db-131">Wenn bei dieser simulierten Nachrichtenunterhaltung ein Fehler auftritt, wird eine Benachrichtigung erzeugt.</span><span class="sxs-lookup"><span data-stu-id="4a5db-131">If this simulated conversation fails, an alert is generated.</span></span>

<span data-ttu-id="4a5db-p105">Das Importieren der Management Packs ist ein wichtiger Schritt. Wenn die Management Packs nicht importiert werden, können Sie Operations Manager nicht zum Überwachen von Skype for Business Server-Ereignissen verwenden und keine synthetischen Skype for Business Server-Transaktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="4a5db-p105">Importing the management packs is a crucial step. If the management packs are not imported, you will not be able to use Operations Manager to monitor Skype for Business Server events or run Skype for Business Server synthetic transactions.</span></span>

<span data-ttu-id="4a5db-p106">Das Component and User Management Pack wird nur zum Überwachen von Skype for Business Server 2015 verwendet. Wenn Sie sich in einem Koexistenzszenario befinden, wo sowohl Skype for Business Server 2015 als auch Lync Server 2013 installiert sind, sollten Sie weiterhin die Lync Server 2013 Management Packs für Ihre Lync Server 2013-Computer verwenden.</span><span class="sxs-lookup"><span data-stu-id="4a5db-p106">The Component and User Management Pack is used to monitor only Skype for Business Server 2015. If you are in a coexistence scenario where both Skype for Business Server 2015 and Lync Server 2013 are installed, you should continue to use the Lync Server 2013 management packs for your Lync Server 2013 computers.</span></span>

> [!NOTE]
> <span data-ttu-id="4a5db-136">Management Packs für Skype for Business Server 2015 umfassen das Skype for Business Server 2015 Component and User Management Pack und das Skype for Business Server 2015 Active Monitoring Management Pack.</span><span class="sxs-lookup"><span data-stu-id="4a5db-136">Management packs for Skype for Business Server 2015 include the Skype for Business Server 2015 Component and User Management Pack and the Skype for Business Server 2015 Active Monitoring Management Pack.</span></span>

<span data-ttu-id="4a5db-137">Zum Importieren der Management Packs können folgende Tools verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="4a5db-137">You can use one of the following tools to import management packs:</span></span>

- <span data-ttu-id="4a5db-138">**System Center Operations Manager** Mit dieser Methode verwenden Sie den Operations Manager, um die Überwachung für Skype for Business Server hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="4a5db-138">**System Center Operations Manager** With this method, you use the Operations Manager to add monitoring for Skype for Business Server.</span></span>

- <span data-ttu-id="4a5db-139">**Operations Manager-Shell** Sie können die Operations Manager-Shell verwenden, um direkt zu importieren oder Probleme zu beheben, die beim Importieren von Management Packs mithilfe der System Center Operations Manager-Konsole auftreten.</span><span class="sxs-lookup"><span data-stu-id="4a5db-139">**Operations Manager Shell** You can use the Operations Manager Shell to import directly, or to troubleshoot any issues that you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="4a5db-140">Importieren der Management Packs mit System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="4a5db-140">Importing the Management Packs by Using System Center Operations Manager</span></span>

1. <span data-ttu-id="4a5db-141">Laden Sie die Datei SkypeForBusiness2015ManagementPacks.msi über die Microsoft Web-Downloads herunter und installieren Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="4a5db-141">Download the SkypeForBusiness2015ManagementPacks.msi from the Microsoft Web downloads, and install the msi.</span></span>

2. <span data-ttu-id="4a5db-142">Klicken Sie in System Center Operations Manager auf **Verwaltung**.</span><span class="sxs-lookup"><span data-stu-id="4a5db-142">In System Center Operations Manager, click **Administration**.</span></span>

3. <span data-ttu-id="4a5db-143">Klicken Sie im Verwaltungsbereich mit der rechten Maustaste auf **Management Packs**, und klicken Sie dann auf **Management Packs importieren**.</span><span class="sxs-lookup"><span data-stu-id="4a5db-143">In the Administration pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4. <span data-ttu-id="4a5db-144">Klicken Sie im Dialogfeld **Management Packs auswählen** auf **Hinzufügen** und anschließend auf **Von Datenträger hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4a5db-144">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5. <span data-ttu-id="4a5db-145">Im Dialogfeld **Verbindung mit dem Onlinekatalog** klicken Sie auf **Keine**.</span><span class="sxs-lookup"><span data-stu-id="4a5db-145">In the **Online Catalog Connection** dialog box, click **No**.</span></span>

6. <span data-ttu-id="4a5db-p107">Suchen Sie im Dialogfeld **Zu importierende Management Packs auswählen** die Dateien Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp und Microsoft.LS.2015.Monitoring.ComponentAndUser.mp und wählen Sie sie aus und klicken Sie anschließend auf **Öffnen**. Wenn Sie mehrere Dateien im Dialogfeld auswählen möchten, klicken Sie auf die erste Datei, halten Sie dann die STRG-Taste gedrückt und klicken Sie dann auf alle weiteren Dateien.</span><span class="sxs-lookup"><span data-stu-id="4a5db-p107">In the **Select Management Packs to import** dialog box, locate and select the files Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2015.Monitoring.ComponentAndUser.mp, and then click **Open**. To select multiple files in the dialog box, click the first file, and then hold down the Ctrl key and click the subsequent files.</span></span>

7. <span data-ttu-id="4a5db-p108">Klicken Sie im Dialogfeld **Management Packs auswählen** auf **Installieren**. Wenn eine Fehlermeldung angezeigt wird und bei der Installation ein Fehler auftritt, bedeutet das normalerweise, dass sich die Management Pack-Dateien in einem Ordner befinden, der durch die Windows-Benutzerkontensteuerung geschützt ist. Wenn dies der Fall ist, kopieren Sie die Dateien in einen anderen Ordner und starten Sie den Import- und Installationsvorgang erneut.</span><span class="sxs-lookup"><span data-stu-id="4a5db-p108">In the **Select Management Packs** dialog box, click **Install**. If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control. If this occurs, copy the files to a different folder, and then restart the import and installation process.</span></span>

8. <span data-ttu-id="4a5db-p109">Klicken Sie im Dialogfeld **Management Packs auswählen** auf **Schließen**. Der Import- und Installationsvorgang kann mehrere Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="4a5db-p109">In the **Select Management Packs** dialog box, click **Close**. The import and installation process might require several minutes to complete.</span></span>

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="4a5db-153">Importieren der Management Packs mit der Operations Manager-Shell</span><span class="sxs-lookup"><span data-stu-id="4a5db-153">Importing the Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="4a5db-p110">Im Allgemeinen ist es einfacher, die Management Packs mit der Operations Manager-Konsole zu importieren. Wenn jedoch ein Fehler auftritt und bei der Installation Fehler auftreten, stellt die Konsole nicht immer ausreichende Fehlerberichte bereit. Im Vergleich dazu bietet die Operations Manager-Shell detaillierte Informationen. Wenn Sie Operations Manager verwenden und beim Importieren eines Management Packs Fehler auftreten, importieren Sie das Management Pack mit der Operations Manager-Shell. Die Operations Manager-Shell kann weitere hilfreiche Informationen bieten, um festzustellen, warum beim Import Fehler aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="4a5db-p110">In general, it is easier to import the management packs by using the Operations Manager console. However, if an error occurs and the import fails, the console does not always provide adequate error reports. By comparison, the Operations Manager Shell provides detailed information. If you are using Operations Manager and you encounter issues when importing a management pack, import the pack by using the Operations Manager Shell. The information provided by Operations Manager Shell can help you determine why the import failed.</span></span>

1. <span data-ttu-id="4a5db-159">Klicken Sie auf **Start**, klicken Sie dann auf **Alle Programme**, anschließend auf **Microsoft System Center 2012**, dann auf **Operations Manager** und anschließend auf **Operations Manager-Shell**.</span><span class="sxs-lookup"><span data-stu-id="4a5db-159">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2. <span data-ttu-id="4a5db-160">Geben Sie in der Operations Manager-Shell den folgenden Befehl an der Eingabeaufforderung ein und drücken Sie die EINGABETASTE. Verwenden Sie dabei den tatsächlichen Pfad zur Kopie der Datei „Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp“:</span><span class="sxs-lookup"><span data-stu-id="4a5db-160">In Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>

   ```
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp"
   ```

3. <span data-ttu-id="4a5db-161">Wiederholen Sie nach dem Importieren des ersten Management Packs den Prozess, indem Sie den Pfad zur Kopie der Datei „Microsoft.LS.2015.Monitoring.ComponentAndUser.mp“ verwenden:</span><span class="sxs-lookup"><span data-stu-id="4a5db-161">After you have imported the first management pack, repeat the process, using the path to your copy of the file Microsoft.LS.2015.Monitoring.ComponentAndUser.mp:</span></span>

   ```
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ComponentAndUser.mp"
   ```
