---
title: Beständiger Chat von lync Server 2013 Resource Kit-Tools
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Persistent Chat Resource Kit Tools
ms:assetid: 7a34d2ba-eb25-4e22-92d1-b9baf81b102c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945599(v=OCS.15)
ms:contentKeyID: 51541423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffd95611f3033dff992092e3be93815bd0e01915
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-persistent-chat-resource-kit-tools"></a><span data-ttu-id="58675-102">Beständiger Chat von lync Server 2013 Resource Kit-Tools</span><span class="sxs-lookup"><span data-stu-id="58675-102">Lync Server 2013 Persistent Chat Resource Kit Tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58675-103">_**Letztes Änderungsstand des Themas:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="58675-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="58675-104">Mit den beständiger Chat von lync Server 2013 Resource Kit-Tools können Sie Routineaufgaben für IT-Administratoren vereinfachen, die beständiger Chat von lync Server 2013 Server bereitstellen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="58675-104">The Lync Server 2013 Persistent Chat Resource Kit tools help to make routine tasks easier for IT administrators who deploy and manage Lync Server 2013 Persistent Chat Server.</span></span> <span data-ttu-id="58675-105">In diesem Thema werden neben den Installationsanweisungen der Zweck der einzelnen Tools und Beispiele für deren Verwendung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="58675-105">In addition to installation instructions, this topic describes the purpose of each tool, and examples of its use.</span></span>

<div>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="58675-106">Installation der Resource Kit-Tools</span><span class="sxs-lookup"><span data-stu-id="58675-106">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="58675-107">Zum Installieren der lync Server 2013 Resource Kit-Tools laden Sie **PersistentChatReskit. msi**herunter.</span><span class="sxs-lookup"><span data-stu-id="58675-107">To install the Lync Server 2013, Resource Kit Tools, download **PersistentChatReskit.msi**.</span></span> <span data-ttu-id="58675-108">Führen Sie **PersistentChatReskit. msi** aus, um eine einfache Installation durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="58675-108">Run **PersistentChatReskit.msi** to do a simple installation.</span></span> <span data-ttu-id="58675-109">Die MSI-Datei installiert alle Tools im folgenden Pfad: \\ **Programm\\ Dateien Microsoft lync Server 2013\\beständiger Chat Server Resource Kit**.</span><span class="sxs-lookup"><span data-stu-id="58675-109">The .msi installs all the tools in the following path: \\**Program Files\\ Microsoft Lync Server 2013\\Persistent Chat Server Resource Kit**.</span></span> <span data-ttu-id="58675-110">Tools mit eigenständigen ausführbaren Dateien befinden sich in diesem Ordner.</span><span class="sxs-lookup"><span data-stu-id="58675-110">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="58675-111">Tools, die auch Dateien enthalten, befinden sich in ihren eigenen Unterordnern.</span><span class="sxs-lookup"><span data-stu-id="58675-111">Tools that also have files are in their own subfolders.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="58675-112">Nach dem Installieren der lync Server 2013 Resource Kit-Tools müssen Sie <STRONG>PsExec. exe</STRONG> installieren und <STRONG>PsExec. exe</STRONG> in den folgenden Pfad kopieren: \\ <STRONG>Programmdateien \ Microsoft lync Server 2013 \ persistent Chat Server Resource Kit\ChatStressTool</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="58675-112">After installing the Lync Server 2013, Resource Kit Tools, you must install <STRONG>PsExec.exe</STRONG> and copy <STRONG>PsExec.exe</STRONG> to the following path: \\<STRONG>Program Files\ Microsoft Lync Server 2013\Persistent Chat Server Resource Kit\ChatStressTool</STRONG>.</span></span> <span data-ttu-id="58675-113">Wenn Sie <STRONG>PsExec. exe</STRONG>nicht kopieren, löst das Belastungs Tool für beständigen Chat eine Fehler Ausnahme aus und wird nicht ordnungsgemäß ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="58675-113">If you do not copy <STRONG>PsExec.exe</STRONG>, the Persistent Chat Stress Tool will throw an error exception, and not perform correctly.</span></span> <span data-ttu-id="58675-114">Stellen Sie sicher, dass diese Voraussetzungen erfüllt sind, bevor Sie das Tool ausführen.</span><span class="sxs-lookup"><span data-stu-id="58675-114">Make sure that you meet this prerequisite requirement prior to running the tool.</span></span> <span data-ttu-id="58675-115">Ausführliche Informationen zum Installieren von <STRONG>PsExec. exe</STRONG>finden <A href="https://go.microsoft.com/fwlink/p/?linkid=282246">https://go.microsoft.com/fwlink/p/?LinkId=282246</A>Sie unter.</span><span class="sxs-lookup"><span data-stu-id="58675-115">For details about installing <STRONG>PsExec.exe</STRONG>, see <A href="https://go.microsoft.com/fwlink/p/?linkid=282246">https://go.microsoft.com/fwlink/p/?LinkId=282246</A>.</span></span>



</div>

</div>

<div>

## <a name="supported-environments"></a><span data-ttu-id="58675-116">Unterstützte Umgebungen</span><span class="sxs-lookup"><span data-stu-id="58675-116">Supported Environments</span></span>

<span data-ttu-id="58675-117">Für eine optimale Leistung sollten die lync Server 2013 Resource Kit-Tools in derselben Umgebung und mit den gleichen Spezifikationen installiert werden, die für lync Server 2013 erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="58675-117">For optimal performance, the Lync Server 2013, Resource Kit Tools should be installed in the same environment and with the same specifications that are required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="58675-118">Resource Kit-Tools (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="58675-118">Resource Kit Tools Overview</span></span>

<span data-ttu-id="58675-119">Hier sind die Tools, die im beständiger Chat von lync Server 2013 Resource Kit bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="58675-119">Here are the tools that are provided in the Lync Server 2013 Persistent Chat Resource Kit.</span></span> <span data-ttu-id="58675-120">Der folgende Abschnitt enthält eine Beschreibung der einzelnen Tools, einschließlich der Anforderungen und der Beispiel Verwendung.</span><span class="sxs-lookup"><span data-stu-id="58675-120">The following section provides a description of each tool, including requirements and example usage.</span></span>

  - <span data-ttu-id="58675-121">AffCheck</span><span class="sxs-lookup"><span data-stu-id="58675-121">AffCheck</span></span>

  - <span data-ttu-id="58675-122">ChatMonitoringSummary</span><span class="sxs-lookup"><span data-stu-id="58675-122">ChatMonitoringSummary</span></span>

  - <span data-ttu-id="58675-123">ChatStress-Tool</span><span class="sxs-lookup"><span data-stu-id="58675-123">ChatStress Tool</span></span>

  - <span data-ttu-id="58675-124">ChatUpgradeVerifier</span><span class="sxs-lookup"><span data-stu-id="58675-124">ChatUpgradeVerifier</span></span>

  - <span data-ttu-id="58675-125">ChatUsageReport</span><span class="sxs-lookup"><span data-stu-id="58675-125">ChatUsageReport</span></span>

  - <span data-ttu-id="58675-126">ScheduleADSyncforPrincipal</span><span class="sxs-lookup"><span data-stu-id="58675-126">ScheduleADSyncforPrincipal</span></span>

</div>

<div>

## <a name="affcheck"></a><span data-ttu-id="58675-127">AffCheck</span><span class="sxs-lookup"><span data-stu-id="58675-127">AffCheck</span></span>

<div>

## <a name="description"></a><span data-ttu-id="58675-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58675-128">Description</span></span>

<span data-ttu-id="58675-129">Mit dem AffCheck-Tool wird bestätigt, dass die Back-End-Datenbankbenutzer und Gruppen zugehörigkeitsdaten Sätze des persistent Chats mit dem Active Directory-Domänendienste übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="58675-129">The AffCheck tool confirms that the Persistent Chat back-end database user and group affiliation records match that of Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="58675-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="58675-130">Requirements</span></span>

<span data-ttu-id="58675-131">Das Tool wird mit dem PersistentChatResKit-Installationsprogramm auf einem Computer installiert, der einer Domäne angehört.</span><span class="sxs-lookup"><span data-stu-id="58675-131">The tool is installed with the PersistentChatResKit installer on a domain joined machine.</span></span>

<span data-ttu-id="58675-132">Das Benutzerkonto, unter dem das Tool ausgeführt wird, muss über Lesezugriff auf die Back-End-Datenbank für beständigen Chat und Active Directory-Domänendienste verfügen.</span><span class="sxs-lookup"><span data-stu-id="58675-132">The user account under which the tool is run must have Read access to the Persistent Chat back-end database and Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="58675-133">Verwendung</span><span class="sxs-lookup"><span data-stu-id="58675-133">Usage</span></span>

<span data-ttu-id="58675-134">Konfigurieren Sie die Datei AffCheck. exe. config gemäß den Anweisungen in der Konfigurationsdatei, und führen Sie das AffCheck-Tool ohne Befehlszeilenparameter aus.</span><span class="sxs-lookup"><span data-stu-id="58675-134">Configure the AffCheck.exe.config file according to the instructions in the config file and run the AffCheck tool without command-line parameters.</span></span> <span data-ttu-id="58675-135">Im folgenden finden Sie den Inhalt der standardmäßigen Datei "AffCheck. exe. config".</span><span class="sxs-lookup"><span data-stu-id="58675-135">Following are the contents of the default AffCheck.exe.config.</span></span>

<span data-ttu-id="58675-136">**AffCheck. exe. config:**</span><span class="sxs-lookup"><span data-stu-id="58675-136">**AffCheck.exe.config:**</span></span>

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <appSettings>
        <!--Domain Controller IP Address-->
        <add key="LDAP" value="LDAP://0.0.0.0/"/>
        
        <!-- Domain DN  This is case sensitive, it must match exactly-->
        <add key="DomainComponent" value ="DC=DOMAIN,DC=COM"/>
        
        <!--Domain Administrator Login and Password-->
        <add key="DomainLogin" value="DOMAIN\Administrator"/>
        <add key="DomainPassword" value ="password"/>
        
        <!-- Connection string to Group Chat Database-->
        <add key="ConnectionString" value="data source=SQL_SERVER\INSTANCE;initial catalog=DATABASE_NAME;integrated security=SSPI"/>
        
        <!--Check group affiliations-->
        <add key="CheckGroups" value="true"/>
        
        <!--Check user affilations-->
        <add key="CheckUsers" value="true"/>
        
        <!--List all affiliations if there is a mismatch between database and active directory-->
        <add key="ListAffiliations" value="true"/>
    
        <!--If you need to offset the results of the number of affilations in AD(can be negative to add to AD parent count)-->
        <add key="Offset" value ="0"/>
    
        <!--If you need to ignore certain parents, provide a semi colon delimitted list.-->
        <add key="Ignore" value ="DC=uatest,DC=test,DC=contoso,DC=com;DC=test,DC=contoso,DC=com"/>
      </appSettings>
    </configuration>
  ```
</div>

</div>

<div>

## <a name="chatmonitoringsummary"></a><span data-ttu-id="58675-137">ChatMonitoringSummary</span><span class="sxs-lookup"><span data-stu-id="58675-137">ChatMonitoringSummary</span></span>

<div>

## <a name="description"></a><span data-ttu-id="58675-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58675-138">Description</span></span>

<span data-ttu-id="58675-139">Das PersistentChatMonitoringSummary-Tool verschiebt die Überwachungsinformationen für beständigen Chat aus der Überwachungsdatenbank in eine angegebene CSV-Protokolldatei.</span><span class="sxs-lookup"><span data-stu-id="58675-139">The PersistentChatMonitoringSummary tool moves Persistent Chat monitoring information from the monitoring database into a specified CSV log file.</span></span>

<span data-ttu-id="58675-140">Die CSV-Datei enthält eine Aufschlüsselung der Sitzungen für beständigen Chat nach der Anzahl der Sitzungen insgesamt, erfolgreicher Sitzungen, unerwarteter Fehler, erwarteter Fehler und einer Aufschlüsselung der unerwarteten Fehler durch Diagnose-ID, Anzahl der Fehler und Beschreibung des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="58675-140">The CSV file will contain a breakdown of Persistent Chat sessions by number of total sessions, successful sessions, unexpected failures, expected failures, and a breakdown of the unexpected failures by diagnostic ID, number of failures, and failure description.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="58675-141">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="58675-141">Requirements</span></span>

<span data-ttu-id="58675-142">Installieren Sie die Resource Kit-Tools für den beständigen Chat auf einem Computer mit Domänenbeitritt, der Zugriff auf das Überwachungsdatenbank hat.</span><span class="sxs-lookup"><span data-stu-id="58675-142">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Monitoring database.</span></span>

<span data-ttu-id="58675-143">Das Benutzerkonto, unter dem das Tool ausgeführt wird, muss über Lesezugriff auf die Überwachungsdatenbank verfügen.</span><span class="sxs-lookup"><span data-stu-id="58675-143">The user account under which the tool runs must have Read access to the Monitoring database.</span></span>

<span data-ttu-id="58675-144">Die Datei PersistentChatMonitoringSummary. exe. config muss einen \<connectionStrings-\> Abschnitt enthalten, der die Verbindungszeichenfolge für die Überwachungsdatenbank definiert.</span><span class="sxs-lookup"><span data-stu-id="58675-144">The file, PersistentChatMonitoringSummary.exe.config, must contain a \<connectionStrings\> section that defines the connection string to the Monitoring database.</span></span> <span data-ttu-id="58675-145">Es muss auch einen Schlüssel für die PersistentChatEndpointUri enthalten, für die die Überwachungsdaten erfasst werden, und einen Dateipfad zu einem Speicherort für die CSV-Datei, die generiert wird.</span><span class="sxs-lookup"><span data-stu-id="58675-145">It must also contain a key for the PersistentChatEndpointUri that the monitoring data will be gathered for, and a file path to a location for the CSV file that will be generated.</span></span> <span data-ttu-id="58675-146">Beispiele dazu erhalten Sie in der installierten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="58675-146">Refer to the installed config file for examples.</span></span> <span data-ttu-id="58675-147">Die Datei muss sich im gleichen Verzeichnis wie das Tool befinden.</span><span class="sxs-lookup"><span data-stu-id="58675-147">The file must be located in the same directory as the tool.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="58675-148">Verwendung</span><span class="sxs-lookup"><span data-stu-id="58675-148">Usage</span></span>

```Batch
    PersistentChatMonitoringSummary [-StartDateTime <date>] [-EndDateTime <date>]
```

<span data-ttu-id="58675-149">Mit diesen Parametern wird die Auswahl der Daten definiert:</span><span class="sxs-lookup"><span data-stu-id="58675-149">These parameters define the selection of data:</span></span>

<span data-ttu-id="58675-150">**Startdatum:** Gibt optional das Startdatum des Auswahlzeitraums an.</span><span class="sxs-lookup"><span data-stu-id="58675-150">**StartDateTime:** Optionally specifies the start date of the selection period.</span></span> <span data-ttu-id="58675-151">Standard: 1/1/1753 12:00:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="58675-151">Default: 1/1/1753 12:00:00 AM</span></span>

<span data-ttu-id="58675-152">**EndDate:** Gibt optional das letzte Datum des Auswahlzeitraums an.</span><span class="sxs-lookup"><span data-stu-id="58675-152">**EndDateTime:** Optionally specifies the last date of the selection period.</span></span> <span data-ttu-id="58675-153">Standard: jetzt</span><span class="sxs-lookup"><span data-stu-id="58675-153">Default: Now</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="58675-154">Beispiel</span><span class="sxs-lookup"><span data-stu-id="58675-154">Example</span></span>

```Batch
    C:\Users\Administrator.VDOMAIN>Desktop\PersistentChatMonitoringSummary.exe
    Reading database connection information, Persistent Chat endpoint uri, and csv output path information from the application config file...
    Connecting to Monitoring database with connection string specified in the application config file...
    Gathering Persistent Chat Session Summary information between "1/1/1753 12:00:00 AM" and "11/19/2012 10:11:25 AM" for Persistent Chat Endpoint Uri "persistentChatEndpointUri@domain.com"...
    Press enter to continue or hit ctr-c if these settings are incorrect...
    
    The summary information about Persistent Chat sessions from the Monitoring database has been output to C:\PersistentChatMonitoring_dd4ace24-4c8a-4a3d-8fd4-591bdfacf47b.csv
    Press enter to exit...
```

</div>

</div>

<div>

## <a name="persistent-chat-stress-tool"></a><span data-ttu-id="58675-155">Stress Tool für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="58675-155">Persistent Chat Stress Tool</span></span>

<div>

## <a name="description"></a><span data-ttu-id="58675-156">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58675-156">Description</span></span>

<span data-ttu-id="58675-157">Das Stress Tool für beständigen Chat bietet eine einfache Möglichkeit zum Simulieren der Verwendung des beständigen Chats zum Testen der realen Leistung, einschließlich variierter Benutzermodelle, um Ihre erwarteten Nutzungsszenarien besser zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="58675-157">The Persistent Chat Stress tool provides an easy way to simulate usage of Persistent Chat to test real-world performance, including varied user models to better fit your expected usage scenarios.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="58675-158">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="58675-158">Requirements</span></span>

<span data-ttu-id="58675-159">Installieren Sie die Resource Kit-Tools für beständigen Chat auf einem Computer mit Domänenbeitritt, der Zugriff auf die Back-End-Datenbank für beständigen Chat hat.</span><span class="sxs-lookup"><span data-stu-id="58675-159">Install the Persistent Chat Resource Kit tools onto a domain-joined machine that has access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="58675-160">Zusätzlich zu diesem *Controller* -Computer benötigen Sie mehrere *Lade* Geräte.</span><span class="sxs-lookup"><span data-stu-id="58675-160">In addition to this *controller* machine, you will need several *loader* machines.</span></span> <span data-ttu-id="58675-161">Für alle 10K-Benutzer in Ihrem Benutzermodell benötigen Sie mindestens 4 GB freien RAM auf einem Loader-Computer.</span><span class="sxs-lookup"><span data-stu-id="58675-161">For every 10K users in your user model, you will need at least 4GB of free RAM on a loader machine.</span></span> <span data-ttu-id="58675-162">Beispielsweise erfordert ein Run mit 80K-Benutzern etwa 32 GB RAM, verteilt auf alle Loader-Computer.</span><span class="sxs-lookup"><span data-stu-id="58675-162">For example, a run with 80K users will require about 32GB of RAM spread across all loader machines.</span></span> <span data-ttu-id="58675-163">Es wird empfohlen, dass Sie über mindestens drei Loader-Computer verfügen, unabhängig von der erwarteten Last.</span><span class="sxs-lookup"><span data-stu-id="58675-163">We recommend that you have at least three loader machines, regardless of expected load.</span></span>

<span data-ttu-id="58675-164">Loader-Computer müssen das .NET 4,5-Framework sowie die Visual C++ 2012 Redistributable installiert haben.</span><span class="sxs-lookup"><span data-stu-id="58675-164">Loader machines must have the .NET 4.5 Framework as well as the Visual C++ 2012 Redistributable installed.</span></span>

</div>

<div>

## <a name="configuration"></a><span data-ttu-id="58675-165">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="58675-165">Configuration</span></span>

<span data-ttu-id="58675-166">Kopieren Sie ChatStressTool-Dateien in einen freigegebenen Ordner, auf den alle Loader-Computer zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="58675-166">Copy ChatStressTool files into a shared folder accessible from all loader machines.</span></span>

<span data-ttu-id="58675-167">Erstellen von Benutzern und Kanälen zur Verwendung in der Belastungs Ausführung:</span><span class="sxs-lookup"><span data-stu-id="58675-167">Create users and channels for use in the stress run:</span></span>

  - <span data-ttu-id="58675-168">Erstellen Sie so viele Benutzer, wie Ihr Benutzermodell anruft, aktivieren Sie Sie für lync, und legen Sie Ihre Richtlinie für beständigen Chat auf aktiviert fest.</span><span class="sxs-lookup"><span data-stu-id="58675-168">Create as many users as your user model calls for, enable them for Lync, and set their Persistent Chat policy to Enabled.</span></span>

  - <span data-ttu-id="58675-169">Erstellen Sie eine Kategorie für Ihre Spannungskanäle, und erstellen Sie dann so viele Räume, wie Sie in dieser Kategorie benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="58675-169">Create a category for your stress channels, and then create as many rooms as are needed under that category.</span></span> <span data-ttu-id="58675-170">Die Kategorie sollte alle Stress-Benutzer in Ihrer **zulässigen** Liste (durch Hinzufügen Ihrer OU) haben, und Stress rooms sollte eine Einstellung für den Datenschutz von **Open**haben.</span><span class="sxs-lookup"><span data-stu-id="58675-170">The category should have all stress users in its **Allowed** list (by way of adding their OU), and stress rooms should have a privacy setting of **Open**.</span></span>

  - <span data-ttu-id="58675-171">Es wird empfohlen, zusätzliche Belastungs Räume zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="58675-171">We recommend creating extra stress rooms.</span></span> <span data-ttu-id="58675-172">Sie können 50.000-Räume mit dem folgenden Befehl Windows PowerShell Befehlszeilenschnittstelle erstellen:</span><span class="sxs-lookup"><span data-stu-id="58675-172">You can create 50,000 rooms with the following Windows PowerShell command-line interface command:</span></span>
    ```Powershell
        for ($i = 0; $i -le 50000; $i++) { New-CsPersistentChatRoom -Category <parent category> -Name "StressChan_$i" -Privacy Open }
    ```    

<span data-ttu-id="58675-173">Bearbeiten Sie die Konfigurationsdateien so, dass Sie Ihrer Topologie entsprechen:</span><span class="sxs-lookup"><span data-stu-id="58675-173">Edit the configuration files to fit your topology:</span></span>

<span data-ttu-id="58675-174">Ändern Sie in **LoaderProcess. exe. config**"Controller.contoso.com" in den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Controllercomputers.</span><span class="sxs-lookup"><span data-stu-id="58675-174">In **LoaderProcess.exe.config**, change “controller.contoso.com” to the controller machine’s fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="58675-175">In **StressLauncher. exe. config:**</span><span class="sxs-lookup"><span data-stu-id="58675-175">In **StressLauncher.exe.config:**</span></span>

1.  <span data-ttu-id="58675-176">Ändern Sie den Wert für die Einstellung "LoaderBinary" in den Pfad des freigegebenen Ordners.</span><span class="sxs-lookup"><span data-stu-id="58675-176">Change the “LoaderBinary” setting value to the shared folder’s path.</span></span>

2.  <span data-ttu-id="58675-177">Ändern Sie "anzüglicher"/"AdminPassword" auf Anmeldeinformationen, die Administratorzugriff auf Loader-Computer haben.</span><span class="sxs-lookup"><span data-stu-id="58675-177">Change “AdminUser”/”AdminPassword” to credentials that have admin access to loader machines.</span></span>

3.  <span data-ttu-id="58675-178">Ändern Sie "ChannelCategory" in den Namen der Kategorie, unter der die Spannungskanäle erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="58675-178">Change “ChannelCategory” to the name of the category that stress channels have been created under.</span></span>

4.  <span data-ttu-id="58675-179">Ändern Sie "UserNamePattern" und "UserPasswordPattern" in eine Vorlage, die mit Ihren Stress-Benutzeranmeldeinformationen übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="58675-179">Change “UserNamePattern” and “UserPasswordPattern” to a template that matches your stress user credentials.</span></span> <span data-ttu-id="58675-180">{0}wird durch die Indexnummer des Benutzers ersetzt.</span><span class="sxs-lookup"><span data-stu-id="58675-180">{0} is replaced with the user’s index number.</span></span>

5.  <span data-ttu-id="58675-181">Ändern Sie "Domäne" in die SIP-Domäne ihrer Testtopologie.</span><span class="sxs-lookup"><span data-stu-id="58675-181">Change “Domain” to the SIP domain of your test topology.</span></span>

6.  <span data-ttu-id="58675-182">Ändern Sie "ConnectionString" in eine Verbindungszeichenfolge für die Back-End-Datenbank des beständigen Chats.</span><span class="sxs-lookup"><span data-stu-id="58675-182">Change “ConnectionString” to a connection string for your Persistent Chat back-end database.</span></span>

7.  <span data-ttu-id="58675-183">Ändern Sie "UserIndexStart" in den Index des ersten Stress Benutzers.</span><span class="sxs-lookup"><span data-stu-id="58675-183">Change “UserIndexStart” to the index of the first stress user.</span></span>

8.  <span data-ttu-id="58675-184">Ändern Sie "LyncFQDN" in den FQDN Ihrer Front-End-Pool.</span><span class="sxs-lookup"><span data-stu-id="58675-184">Change “LyncFQDN” to the FQDN of your Front End pool.</span></span>

9.  <span data-ttu-id="58675-185">Ändern Sie die Liste "Computer" so, dass Computernamen für alle Ladegeräte Computer enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="58675-185">Modify the “Machines” list to include machine names for all of your loader machines.</span></span>

10. <span data-ttu-id="58675-186">Ändern Sie die BaseAddress des Dienstendpunkts (Standardwert "Controller.contoso.com") in den FQDN des Controllercomputers.</span><span class="sxs-lookup"><span data-stu-id="58675-186">Change the baseAddress of the service endpoint (default is “controller.contoso.com”) to the FQDN of your controller machine.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="58675-187">Verwendung</span><span class="sxs-lookup"><span data-stu-id="58675-187">Usage</span></span>

<span data-ttu-id="58675-188">Öffnen Sie nach Abschluss der Konfiguration StressLauncher. exe auf dem Controllercomputer.</span><span class="sxs-lookup"><span data-stu-id="58675-188">After configuration is complete, open StressLauncher.exe on the controller machine.</span></span> <span data-ttu-id="58675-189">Sie können StressLauncher als beliebigen Benutzer starten.</span><span class="sxs-lookup"><span data-stu-id="58675-189">You can launch StressLauncher as any user.</span></span> <span data-ttu-id="58675-190">Die Anmeldeinformationen, unter denen das Ladeprogramm auf den Loader-Computern gestartet wird, müssen in der Konfigurationsdatei angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="58675-190">The credentials under which the loader processes start on the loader machines must be specified in the config file.</span></span> <span data-ttu-id="58675-191">Außerdem müssen Sie eine Verbindungszeichenfolge mit Lesezugriff für die Back-End-Datenbank für beständigen Chat eingeben.</span><span class="sxs-lookup"><span data-stu-id="58675-191">You also must give a connection string that has Read access to the Persistent Chat back-end database.</span></span> <span data-ttu-id="58675-192">Wenn diese Verbindungszeichenfolge die integrierte Windows-Authentifizierung verwendet, müssen Sie StressLauncher als Benutzer starten, der über diesen Zugriff verfügt.</span><span class="sxs-lookup"><span data-stu-id="58675-192">If this connection string uses integrated Windows authentication, you must launch StressLauncher as a user that has this access.</span></span>

<span data-ttu-id="58675-193">Ändern Sie die Benutzermodell Einstellungen nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="58675-193">Alter the user model settings as needed.</span></span> <span data-ttu-id="58675-194">Klicken Sie auf **Start laden** , um eine Ausführung zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="58675-194">Click **Start Load** to initiate a run.</span></span> <span data-ttu-id="58675-195">Nach etwa einer Minute beginnen Benutzer mit der Anmeldung, und die Statusleiste beginnt zu füllen.</span><span class="sxs-lookup"><span data-stu-id="58675-195">After a minute or so, users will start being signed in, and the progress bar will begin to fill.</span></span> <span data-ttu-id="58675-196">An dieser Stelle können Sie den Controller-Computer arbeiten und Leistungsmessungen durchführen.</span><span class="sxs-lookup"><span data-stu-id="58675-196">At this point, you may can the controller machine working and take performance measurements.</span></span>

</div>

</div>

<div>

## <a name="chatupgradeverifier"></a><span data-ttu-id="58675-197">ChatUpgradeVerifier</span><span class="sxs-lookup"><span data-stu-id="58675-197">ChatUpgradeVerifier</span></span>

<div>

## <a name="description"></a><span data-ttu-id="58675-198">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58675-198">Description</span></span>

<span data-ttu-id="58675-199">ChatUpgradeVerifier ist ein spezifischer Datenbankvergleichstool für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="58675-199">ChatUpgradeVerifier is a Persistent Chat specific database comparison tool.</span></span> <span data-ttu-id="58675-200">Das Tool vergleicht die Datenbank "Group Chat 2007 R2" oder "Group Chat 2010" (2007/2010Db) mit der Datenbank für beständigen Chat 2013 (2013Db).</span><span class="sxs-lookup"><span data-stu-id="58675-200">The tool compares either the Group Chat 2007 R2 or Group Chat 2010 Database (2007/2010Db) to the Persistent Chat 2013 Database (2013Db).</span></span>

<span data-ttu-id="58675-201">Das Tool überprüft eine nach der anderen, jede Kategorie, den beständigen Chatroom und das Add-in in 2007/2010Db, um zu sehen, ob Sie im 2013Db angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="58675-201">The tool will check, one by one, each category, Persistent Chat room, and add-in in 2007/2010Db to see if it appears in the 2013Db.</span></span> <span data-ttu-id="58675-202">Der Vergleich umfasst das Überprüfen aller Einstellungen für die Kategorie, den Chatroom oder das Add-in, alle Prinzipale im Bereich der Kategorie und alle Prinzipale in einer Rolle in der Kategorie oder im Chatroom.</span><span class="sxs-lookup"><span data-stu-id="58675-202">The comparison includes checking all settings on the category, chat room, or add-in, any principals in scope on the category, and any principal in a role on either the category or the chat room.</span></span> <span data-ttu-id="58675-203">Wenn eine Kategorie oder ein Chatroom in der 2013Db nicht ordnungsgemäß angezeigt wird, werden die Unterschiede in einer Konfliktdatei ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="58675-203">If a category or a chat room does not appear correctly in the 2013Db, the differences will be output to a conflicts file.</span></span> <span data-ttu-id="58675-204">Wenn nach dem Upgrade der Wert 2007/2010Db geändert wurde und dieses Tool ausgeführt wird, wird die Ausgabe der Konfliktdatei unterschiedlich ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="58675-204">If, after the upgrade has occurred, the 2007/2010Db is changed and then this tool is run, there will be a differences output to the conflicts file.</span></span> <span data-ttu-id="58675-205">Beachten Sie, dass diese Anwendung nur ein Datenbankvergleichstool ist und den Upgradeprozess nicht überprüft.</span><span class="sxs-lookup"><span data-stu-id="58675-205">Note that this application is a database comparison tool only and does not validate the upgrade process.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="58675-206">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="58675-206">Requirements</span></span>

<span data-ttu-id="58675-207">Installieren Sie die Ressourcen Kit-Tools für den beständigen Chat auf einem Computer mit Domänenbeitritt, der Zugriff auf die Back-End-Datenbanken für beständigen Chat hat (frühere und aktuelle Versionen für beständigen Chat).</span><span class="sxs-lookup"><span data-stu-id="58675-207">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Persistent Chat back-end databases (previous and current versions for Persistent Chat).</span></span>

<span data-ttu-id="58675-208">Das Benutzerkonto, unter dem das Tool ausgeführt wird, muss über Lesezugriff auf die Datenbanken für beständigen Chat verfügen.</span><span class="sxs-lookup"><span data-stu-id="58675-208">The user account under which the tool runs must have Read access to the Persistent Chat databases.</span></span>

<span data-ttu-id="58675-209">Die Datei ChatUpgradeVerifier. exe. config muss entweder den GroupChat2007R2Db-Parameter oder den GroupChat2010Db-Parameter enthalten, mit einer Verbindungszeichenfolge für die entsprechende Gruppen Chat Datenbank (entweder Groupchat 2007R2 oder 2010).</span><span class="sxs-lookup"><span data-stu-id="58675-209">The ChatUpgradeVerifier.exe.config file must contain either the GroupChat2007R2Db parameter or the GroupChat2010Db parameter, with a connection string to the appropriate Group Chat database (either Groupchat 2007R2 or 2010).</span></span> <span data-ttu-id="58675-210">Es muss auch einen PersistentChat2013Db-Parameter mit einer Verbindungszeichenfolge für die Datenbank persistent Chat 2013 enthalten.</span><span class="sxs-lookup"><span data-stu-id="58675-210">It must also contain a PersistentChat2013Db parameter, with a connection string to the Persistent Chat 2013 database.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="58675-211">Verwendung</span><span class="sxs-lookup"><span data-stu-id="58675-211">Usage</span></span>

<span data-ttu-id="58675-212">Führen Sie **ChatUpgradeVerifier** ohne Parameter aus.</span><span class="sxs-lookup"><span data-stu-id="58675-212">Run **ChatUpgradeVerifier** without any parameters.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="58675-213">Beispiel</span><span class="sxs-lookup"><span data-stu-id="58675-213">Example</span></span>

<span data-ttu-id="58675-214">![Running ChatUpgradeVerifier. exe.](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "Running ChatUpgradeVerifier. exe.")</span><span class="sxs-lookup"><span data-stu-id="58675-214">![Running ChatUpgradeVerifier.exe.](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "Running ChatUpgradeVerifier.exe.")</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-usage-report"></a><span data-ttu-id="58675-215">Verwendungsbericht für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="58675-215">Persistent Chat Usage Report</span></span>

<div>

## <a name="description"></a><span data-ttu-id="58675-216">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58675-216">Description</span></span>

<span data-ttu-id="58675-217">Das ChatUsageReport-Tool generiert einen HTML-Bericht über die Verwendung von beständigen Chat Diensten.</span><span class="sxs-lookup"><span data-stu-id="58675-217">The ChatUsageReport tool generates an HTML report of Persistent Chat service usage.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="58675-218">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="58675-218">Requirements</span></span>

<span data-ttu-id="58675-219">Installieren Sie die Resource Kit-Tools für beständigen Chat auf einem Computer mit Domänenbeitritt, der Zugriff auf die Back-End-Datenbank für beständigen Chat hat.</span><span class="sxs-lookup"><span data-stu-id="58675-219">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="58675-220">Das Benutzerkonto, unter dem das Tool ausgeführt wird, muss über Lesezugriff auf die Back-End-Datenbank für beständigen Chat verfügen.</span><span class="sxs-lookup"><span data-stu-id="58675-220">The user account under which the tool is run must have Read access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="58675-221">Die Datei ChatUsageReport. exe. config muss einen \<connectionStrings-\> Abschnitt enthalten, der die Verbindungszeichenfolge für die Back-End-Datenbank des beständigen Chats definiert.</span><span class="sxs-lookup"><span data-stu-id="58675-221">The file, ChatUsageReport.exe.config, must contain a \<connectionStrings\> section defining the connection string to the Persistent Chat back-end database.</span></span> <span data-ttu-id="58675-222">Der Inhalt der Standardkonfigurationsdatei wird hier als Referenz aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="58675-222">The contents of the default config file are included here, for your reference.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="58675-223">Verwendung</span><span class="sxs-lookup"><span data-stu-id="58675-223">Usage</span></span>

```Powershell
    ChatUsageReport [-StartDate {date}] [-EndDate {date}] [-TopActiveUsers {n}] [-TopActiveRooms {n}] [-LeastActiveRooms {n}] [-RoomsInactiveSince {Date}] [-OutputFolder {path}]
```
<span data-ttu-id="58675-224">Mit diesen Parametern wird die Auswahl der Daten definiert:</span><span class="sxs-lookup"><span data-stu-id="58675-224">These parameters define the selection of data:</span></span>

<span data-ttu-id="58675-225">**StartDate:** Gibt optional das UTC-Startdatum des Auswahlzeitraums an.</span><span class="sxs-lookup"><span data-stu-id="58675-225">**StartDate:** Optionally specifies the UTC start date of the selection period.</span></span> <span data-ttu-id="58675-226">Standard: frühestes Datum</span><span class="sxs-lookup"><span data-stu-id="58675-226">Default: Earliest Date</span></span>

<span data-ttu-id="58675-227">**EndDate:** Gibt optional das UTC-Enddatum des Auswahlzeitraums an.</span><span class="sxs-lookup"><span data-stu-id="58675-227">**EndDate:** Optionally specifies the UTC end date of the selection period.</span></span> <span data-ttu-id="58675-228">Standard: jetzt</span><span class="sxs-lookup"><span data-stu-id="58675-228">Default: Now</span></span>

<span data-ttu-id="58675-229">Diese Parameter definieren, wie und welche Daten angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="58675-229">These parameters define how and what data is displayed:</span></span>

<span data-ttu-id="58675-230">**TopActiveUsers:** Wenn dieser Wert angegeben ist, enthält der Bericht die n aktivsten Benutzer im Hinblick auf die Anzahl der Nachrichten, die der Benutzer für den ausgewählten Zeitraum im Chatroom bereitgestellt hat.</span><span class="sxs-lookup"><span data-stu-id="58675-230">**TopActiveUsers:** If this is specified, the report will include the n most active users in terms of the number of messages the user has posted in the chat room for the selected period.</span></span> <span data-ttu-id="58675-231">Standard: 10</span><span class="sxs-lookup"><span data-stu-id="58675-231">Default: 10</span></span>

<span data-ttu-id="58675-232">**TopActiveRooms:** Wenn dieser Wert angegeben ist, enthält der Bericht die n aktivsten Chatrooms im Hinblick auf die Anzahl der Nachrichten, die im Raum für den ausgewählten Zeitraum gebucht werden.</span><span class="sxs-lookup"><span data-stu-id="58675-232">**TopActiveRooms:** If this is specified, the report will include the n most active chat rooms in terms of the number of messages posted in the room for the selected period.</span></span> <span data-ttu-id="58675-233">Standard: 10</span><span class="sxs-lookup"><span data-stu-id="58675-233">Default: 10</span></span>

<span data-ttu-id="58675-234">**LeastActiveRooms:** Wenn dieser Wert angegeben ist, enthält der Bericht die mindestens aktiven Chatrooms im Hinblick auf die Anzahl der Nachrichten, die für den ausgewählten Zeitraum im Chatroom gepostet wurden.</span><span class="sxs-lookup"><span data-stu-id="58675-234">**LeastActiveRooms:** If this is specified, the report will include the n least active chat rooms in terms of the number of messages posted in the chat room for the selected period.</span></span> <span data-ttu-id="58675-235">Für Chatrooms wird mindestens eine Nachricht bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="58675-235">Rooms will have at least one message posted.</span></span> <span data-ttu-id="58675-236">Standard: 10</span><span class="sxs-lookup"><span data-stu-id="58675-236">Default: 10</span></span>

<span data-ttu-id="58675-237">**RoomsInactiveSince:** Wenn dies angegeben wird, enthält der Bericht eine Liste der Chatrooms, die seit dem angegebenen Datum inaktiv sind.</span><span class="sxs-lookup"><span data-stu-id="58675-237">**RoomsInactiveSince:** If this is specified, the report will include a list of chat rooms that have been inactive since the specified date.</span></span> <span data-ttu-id="58675-238">Standard: gesamte Zeit</span><span class="sxs-lookup"><span data-stu-id="58675-238">Default: Entire Time</span></span>

<span data-ttu-id="58675-239">**OutputFolder:** Der Ordner, in dem die ChatUsageReport. html-und die Graph-Bilder eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="58675-239">**OutputFolder:** The folder where the ChatUsageReport.html and the graph images will be placed.</span></span> <span data-ttu-id="58675-240">Dies muss in der Konfigurationsdatei oder in der Befehlszeile definiert werden.</span><span class="sxs-lookup"><span data-stu-id="58675-240">This must be defined in the config file or on the command line.</span></span>

<span data-ttu-id="58675-241">Alle Befehlszeilenparameter Werte können auch in der Datei ChatUsageReport. exe. config angegeben werden, die sich im gleichen Verzeichnis wie das Tool befindet.</span><span class="sxs-lookup"><span data-stu-id="58675-241">All of the command line parameter values can also be specified in the ChatUsageReport.exe.config file that is located in the same directory as the tool.</span></span> <span data-ttu-id="58675-242">Wenn ein beliebiger Wert sowohl in der Konfigurationsdatei als auch in der Befehlszeile angegeben wird, überschreibt der Wert der Befehlszeile den Wert der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="58675-242">If any value is specified in both the config file and the command line, the command line value will override the config file value.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="58675-243">Output</span><span class="sxs-lookup"><span data-stu-id="58675-243">Output</span></span>

<span data-ttu-id="58675-244">Der Bericht wird immer die folgende Ausgabe enthalten:</span><span class="sxs-lookup"><span data-stu-id="58675-244">The report will always include the following output:</span></span>

  - <span data-ttu-id="58675-245">Top n die aktivsten Chatrooms nach der Anzahl der Nachrichten Beiträge für den ausgewählten Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="58675-245">Top n most active chat rooms by number of message posts for selected period.</span></span>

  - <span data-ttu-id="58675-246">Top n die aktivsten Benutzer nach der Anzahl der Nachrichten Beiträge für den ausgewählten Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="58675-246">Top n most active users by number of message posts for selected period.</span></span>

  - <span data-ttu-id="58675-247">Top n mindestens aktive Chatrooms nach der Anzahl der Nachrichten Beiträge für den ausgewählten Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="58675-247">Top n least active chat rooms by number of message posts for selected period.</span></span>

  - <span data-ttu-id="58675-248">Chatrooms, die für die gesamte Lebensdauer der Datenbank oder seit dem angegebenen Datum inaktiv sind.</span><span class="sxs-lookup"><span data-stu-id="58675-248">Chat rooms that are inactive for the entire life of the database, or since the specified date.</span></span>

  - <span data-ttu-id="58675-249">Täglicher Nachrichten Post-Trend für den ausgewählten Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="58675-249">Daily message post trend for selected period.</span></span>

  - <span data-ttu-id="58675-250">Trend zur wöchentlichen Nachrichten Bereitstellung für den ausgewählten Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="58675-250">Weekly message post trend for selected period.</span></span>

  - <span data-ttu-id="58675-251">Monatlicher Nachrichten Post-Trend für den ausgewählten Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="58675-251">Monthly message post trend for selected period.</span></span>

  - <span data-ttu-id="58675-252">Nachrichten Beiträge für den ausgewählten Zeitraum insgesamt.</span><span class="sxs-lookup"><span data-stu-id="58675-252">Total message posts for selected period.</span></span>

  - <span data-ttu-id="58675-253">Die Gesamtzahl der aktivierten Räume.</span><span class="sxs-lookup"><span data-stu-id="58675-253">Total number of enabled rooms.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="58675-254">Beispiel</span><span class="sxs-lookup"><span data-stu-id="58675-254">Example</span></span>

<span data-ttu-id="58675-255">Im folgenden Beispiel wird ein Verwendungsbericht für das gesamte Jahr 2001 generiert, und der Bericht wird in der OutputFolder angegeben, die in der Datei "ChatUsageReport. exe. config" angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="58675-255">The following example generates a usage report for the entire year 2001 and places the report in the OutputFolder specified in the ChatUsageReport.exe.config.</span></span>

```Powershell
    ChatUsageReport -RoomsInactiveSince 06-20-2010
```
<span data-ttu-id="58675-256">ChatUsageReport. exe. config:</span><span class="sxs-lookup"><span data-stu-id="58675-256">ChatUsageReport.exe.config:</span></span>

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <connectionStrings>
        <!-- The PersistentChat connection string must be defined in this file. -->
        <add name="PersistentChat" connectionString="Data Source=contoso.com\RTC;Initial Catalog=mgc;Integrated Security=SSPI"/>
      </connectionStrings>
      <appSettings>
        <!-- The OutputFolder must be defined here or on the command line. -->
        <add key="OutputFolder" value="."/>
        <!-- The values below are the same as the application defaults. -->
        <add key="StartDate" value="01/01/0001"/>
        <add key="EndDate" value="12/31/9999"/>
        <add key="TopActiveUsers" value="10"/>
        <add key="TopActiveRooms" value="10"/>
        <add key="LeastActiveRooms" value="10"/>
        <add key="RoomsInactiveSince" value="01/01/0001"/>
      </appSettings>
    </configuration></configuration>
```
</div>

</div>

<div>

## <a name="scheduleadsyncforprincipal"></a><span data-ttu-id="58675-257">ScheduleADSyncForPrincipal</span><span class="sxs-lookup"><span data-stu-id="58675-257">ScheduleADSyncForPrincipal</span></span>

<div>

## <a name="description"></a><span data-ttu-id="58675-258">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58675-258">Description</span></span>

<span data-ttu-id="58675-259">ScheduleADSyncForPrincipal ist ein Microsoft SQL Server 2012-Skript, das direkt in SQL Server Management Studio ausgeführt werden muss, wenn es mit der Back-End-Datenbank des beständigen Chats verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="58675-259">ScheduleADSyncForPrincipal is a Microsoft SQL Server 2012 script that must be run directly from within SQL Server Management Studio when connected to the Persistent Chat back-end database.</span></span> <span data-ttu-id="58675-260">Mit diesem Skript können Sie beständigen Chat zwingen, seine Einträge eines Benutzers mit denen von Active Directory-Domänendienste zu synchronisieren, anstatt auf die geplante Synchronisierungszeit zu warten.</span><span class="sxs-lookup"><span data-stu-id="58675-260">This script enables you to force Persistent Chat to synchronize its records of a user with those of Active Directory Domain Services, rather than waiting for the scheduled synchronization time.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="58675-261">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="58675-261">Requirements</span></span>

<span data-ttu-id="58675-262">Das Benutzerkonto, unter dem das Skript ausgeführt wird, muss über Besitzer Zugriff auf die Back-End-Datenbank für beständigen Chat verfügen.</span><span class="sxs-lookup"><span data-stu-id="58675-262">The user account under which the script is run must have owner access to the Persistent Chat back-end database.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="58675-263">Verwendung</span><span class="sxs-lookup"><span data-stu-id="58675-263">Usage</span></span>

<span data-ttu-id="58675-264">Im folgenden finden Sie den Inhalt des Standardskripts:</span><span class="sxs-lookup"><span data-stu-id="58675-264">Following are the contents of the default script:</span></span>

```Powershell
    /*
    This script will schedule a principal for a forced AD synchronization cycle
    
    If you're using Sql Server Management Studio, pressing Ctrl+Shift+M will 
    allow you to specify values for the template parameter.
    */
    
        insert into
          tblPrincipalMeta
          (
           prinID
          ,prinAffiliationsDirty
          ,prinAttributesDirty
          ,prinDeleted
          )
          select
            prinID
           ,1
           ,1
           ,0
          from
            tblPrincipal
          where
            prinID not in (select prinID from tblPrincipalMeta) and
            prinID = <PrinID,int,0>
     
        update
          tblPrincipalMeta
        set
          prinAffiliationsDirty = 1
         ,prinAttributesDirty = 1
         ,tryCount = 0
         ,nextTry = null
        where
         prinID = <PrinID,int,0>
```

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

