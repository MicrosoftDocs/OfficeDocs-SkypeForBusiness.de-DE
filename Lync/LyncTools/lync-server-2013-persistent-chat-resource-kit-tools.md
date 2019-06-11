---
title: Lync Server 2013-Ressourcensatz Tools für beständigen Chat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2013 Persistent Chat Resource Kit Tools
ms:assetid: 7a34d2ba-eb25-4e22-92d1-b9baf81b102c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945599(v=OCS.15)
ms:contentKeyID: 51541423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c851be7bb7046021cc2d37c88ef03bdea60c95a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840043"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-persistent-chat-resource-kit-tools"></a><span data-ttu-id="bc2de-102">Lync Server 2013-Ressourcensatz Tools für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="bc2de-102">Lync Server 2013 Persistent Chat Resource Kit Tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc2de-103">_**Letztes Änderungsdatum des Themas:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="bc2de-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="bc2de-104">Die lync Server 2013-Tools für beständigen Chat-Ressourcen Kits unterstützen Sie bei der Vereinfachung von Routineaufgaben für IT-Administratoren, die lync Server 2013 persistent Chat Server bereitstellen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="bc2de-104">The Lync Server 2013 Persistent Chat Resource Kit tools help to make routine tasks easier for IT administrators who deploy and manage Lync Server 2013 Persistent Chat Server.</span></span> <span data-ttu-id="bc2de-105">In diesem Thema werden neben den Installationsanweisungen auch der Zweck der einzelnen Tools und Beispiele für deren Verwendung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bc2de-105">In addition to installation instructions, this topic describes the purpose of each tool, and examples of its use.</span></span>

<div>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="bc2de-106">Installation der Resource Kit-Tools</span><span class="sxs-lookup"><span data-stu-id="bc2de-106">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="bc2de-107">Zum Installieren der lync Server 2013, Resource Kit-Tools, laden Sie **PersistentChatReskit. msi**herunter.</span><span class="sxs-lookup"><span data-stu-id="bc2de-107">To install the Lync Server 2013, Resource Kit Tools, download **PersistentChatReskit.msi**.</span></span> <span data-ttu-id="bc2de-108">Führen Sie **PersistentChatReskit. msi** aus, um eine einfache Installation durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="bc2de-108">Run **PersistentChatReskit.msi** to do a simple installation.</span></span> <span data-ttu-id="bc2de-109">Mit der MSI-Datei werden alle Tools im folgenden Pfad installiert \\: **Programm\\ Dateien Microsoft lync Server\\2013 beständiger Chat Server Resource Kit**.</span><span class="sxs-lookup"><span data-stu-id="bc2de-109">The .msi installs all the tools in the following path: \\**Program Files\\ Microsoft Lync Server 2013\\Persistent Chat Server Resource Kit**.</span></span> <span data-ttu-id="bc2de-110">Tools, bei denen es sich um eigenständige ausführbare Dateien handelt, befinden sich in diesem Ordner.</span><span class="sxs-lookup"><span data-stu-id="bc2de-110">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="bc2de-111">Tools, die auch Dateien enthalten, befinden sich in ihren eigenen Unterordnern.</span><span class="sxs-lookup"><span data-stu-id="bc2de-111">Tools that also have files are in their own subfolders.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bc2de-112">Nachdem Sie die lync Server 2013, Resource Kit-Tools installiert haben, müssen Sie <STRONG>PsExec. exe</STRONG> installieren und " <STRONG>PsExec. exe</STRONG> " in \\den folgenden Pfad kopieren: <STRONG>Programmdateien \ Microsoft lync Server 2013 \ beständiger Chat Server Ressource Kit\ChatStressTool </STRONG>.</span><span class="sxs-lookup"><span data-stu-id="bc2de-112">After installing the Lync Server 2013, Resource Kit Tools, you must install <STRONG>PsExec.exe</STRONG> and copy <STRONG>PsExec.exe</STRONG> to the following path: \\<STRONG>Program Files\ Microsoft Lync Server 2013\Persistent Chat Server Resource Kit\ChatStressTool</STRONG>.</span></span> <span data-ttu-id="bc2de-113">Wenn Sie " <STRONG>PsExec. exe</STRONG>" nicht kopieren, löst das beständige Chat-Spannungs Tool eine Fehler Ausnahme aus, die nicht ordnungsgemäß ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bc2de-113">If you do not copy <STRONG>PsExec.exe</STRONG>, the Persistent Chat Stress Tool will throw an error exception, and not perform correctly.</span></span> <span data-ttu-id="bc2de-114">Stellen Sie sicher, dass Sie diese Voraussetzungen erfüllen, bevor Sie das Tool ausführen.</span><span class="sxs-lookup"><span data-stu-id="bc2de-114">Make sure that you meet this prerequisite requirement prior to running the tool.</span></span> <span data-ttu-id="bc2de-115">Informationen zum Installieren von <STRONG>PsExec. exe</STRONG>finden Sie <A href="http://go.microsoft.com/fwlink/p/?linkid=282246">http://go.microsoft.com/fwlink/p/?LinkId=282246</A>unter.</span><span class="sxs-lookup"><span data-stu-id="bc2de-115">For details about installing <STRONG>PsExec.exe</STRONG>, see <A href="http://go.microsoft.com/fwlink/p/?linkid=282246">http://go.microsoft.com/fwlink/p/?LinkId=282246</A>.</span></span>



</div>

</div>

<div>

## <a name="supported-environments"></a><span data-ttu-id="bc2de-116">Unterstützte Umgebungen</span><span class="sxs-lookup"><span data-stu-id="bc2de-116">Supported Environments</span></span>

<span data-ttu-id="bc2de-117">Um eine optimale Leistung zu erzielen, sollten die lync Server 2013, Resource Kit-Tools in der gleichen Umgebung und mit den gleichen Spezifikationen installiert werden, die für lync Server 2013 erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="bc2de-117">For optimal performance, the Lync Server 2013, Resource Kit Tools should be installed in the same environment and with the same specifications that are required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="bc2de-118">Resource Kit-Tools – Übersicht</span><span class="sxs-lookup"><span data-stu-id="bc2de-118">Resource Kit Tools Overview</span></span>

<span data-ttu-id="bc2de-119">Nachfolgend finden Sie die Tools, die im lync Server 2013-Ressourcen Kit für beständige Chats bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="bc2de-119">Here are the tools that are provided in the Lync Server 2013 Persistent Chat Resource Kit.</span></span> <span data-ttu-id="bc2de-120">Der folgende Abschnitt enthält eine Beschreibung der einzelnen Tools, einschließlich Anforderungen und Beispiel Verwendung.</span><span class="sxs-lookup"><span data-stu-id="bc2de-120">The following section provides a description of each tool, including requirements and example usage.</span></span>

  - <span data-ttu-id="bc2de-121">AffCheck</span><span class="sxs-lookup"><span data-stu-id="bc2de-121">AffCheck</span></span>

  - <span data-ttu-id="bc2de-122">ChatMonitoringSummary</span><span class="sxs-lookup"><span data-stu-id="bc2de-122">ChatMonitoringSummary</span></span>

  - <span data-ttu-id="bc2de-123">ChatStress-Tool</span><span class="sxs-lookup"><span data-stu-id="bc2de-123">ChatStress Tool</span></span>

  - <span data-ttu-id="bc2de-124">ChatUpgradeVerifier</span><span class="sxs-lookup"><span data-stu-id="bc2de-124">ChatUpgradeVerifier</span></span>

  - <span data-ttu-id="bc2de-125">ChatUsageReport</span><span class="sxs-lookup"><span data-stu-id="bc2de-125">ChatUsageReport</span></span>

  - <span data-ttu-id="bc2de-126">ScheduleADSyncforPrincipal</span><span class="sxs-lookup"><span data-stu-id="bc2de-126">ScheduleADSyncforPrincipal</span></span>

</div>

<div>

## <a name="affcheck"></a><span data-ttu-id="bc2de-127">AffCheck</span><span class="sxs-lookup"><span data-stu-id="bc2de-127">AffCheck</span></span>

<div>

## <a name="description"></a><span data-ttu-id="bc2de-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bc2de-128">Description</span></span>

<span data-ttu-id="bc2de-129">Das AffCheck-Tool bestätigt, dass die Datensätze des beständigen Chat-Datenbankbenutzers und der Gruppenzugehörigkeit mit denen der Active Directory-Domänendienste übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="bc2de-129">The AffCheck tool confirms that the Persistent Chat back-end database user and group affiliation records match that of Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="bc2de-130">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="bc2de-130">Requirements</span></span>

<span data-ttu-id="bc2de-131">Das Tool wird mit dem PersistentChatResKit-Installationsprogramm auf einem Computer mit Domänenbeitritt installiert.</span><span class="sxs-lookup"><span data-stu-id="bc2de-131">The tool is installed with the PersistentChatResKit installer on a domain joined machine.</span></span>

<span data-ttu-id="bc2de-132">Das Benutzerkonto, unter dem das Tool ausgeführt wird, muss über Lesezugriff auf die Back-End-Datenbank des beständigen Chats und die Active Directory-Domänendienste verfügen.</span><span class="sxs-lookup"><span data-stu-id="bc2de-132">The user account under which the tool is run must have Read access to the Persistent Chat back-end database and Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="bc2de-133">Verwendung</span><span class="sxs-lookup"><span data-stu-id="bc2de-133">Usage</span></span>

<span data-ttu-id="bc2de-134">Konfigurieren Sie die Datei "AffCheck. exe. config" gemäß den Anweisungen in der config-Datei, und führen Sie das AffCheck-Tool ohne Befehlszeilenparameter aus.</span><span class="sxs-lookup"><span data-stu-id="bc2de-134">Configure the AffCheck.exe.config file according to the instructions in the config file and run the AffCheck tool without command-line parameters.</span></span> <span data-ttu-id="bc2de-135">Im folgenden finden Sie den Inhalt der standardmäßigen Datei "AffCheck. exe. config".</span><span class="sxs-lookup"><span data-stu-id="bc2de-135">Following are the contents of the default AffCheck.exe.config.</span></span>

<span data-ttu-id="bc2de-136">**AffCheck. exe. config:**</span><span class="sxs-lookup"><span data-stu-id="bc2de-136">**AffCheck.exe.config:**</span></span>

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

## <a name="chatmonitoringsummary"></a><span data-ttu-id="bc2de-137">ChatMonitoringSummary</span><span class="sxs-lookup"><span data-stu-id="bc2de-137">ChatMonitoringSummary</span></span>

<div>

## <a name="description"></a><span data-ttu-id="bc2de-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bc2de-138">Description</span></span>

<span data-ttu-id="bc2de-139">Das PersistentChatMonitoringSummary-Tool verschiebt permanente Chat Überwachungsinformationen aus der Überwachungsdatenbank in eine angegebene CSV-Protokolldatei.</span><span class="sxs-lookup"><span data-stu-id="bc2de-139">The PersistentChatMonitoringSummary tool moves Persistent Chat monitoring information from the monitoring database into a specified CSV log file.</span></span>

<span data-ttu-id="bc2de-140">Die CSV-Datei enthält eine Aufschlüsselung der beständigen Chat Sitzungen nach Anzahl der Gesamt Sitzungen, erfolgreichen Sitzungen, unerwarteten Fehlern, erwarteten Fehlern und einer Aufschlüsselung der unerwarteten Fehler durch Diagnose-ID, Anzahl der Fehler und Fehlerbeschreibung.</span><span class="sxs-lookup"><span data-stu-id="bc2de-140">The CSV file will contain a breakdown of Persistent Chat sessions by number of total sessions, successful sessions, unexpected failures, expected failures, and a breakdown of the unexpected failures by diagnostic ID, number of failures, and failure description.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="bc2de-141">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="bc2de-141">Requirements</span></span>

<span data-ttu-id="bc2de-142">Installieren Sie die Ressourcen Kit-Tools für beständigen Chat auf einem Computer mit Domänenbeitritt, der Zugriff auf die Überwachungsdatenbank hat.</span><span class="sxs-lookup"><span data-stu-id="bc2de-142">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Monitoring database.</span></span>

<span data-ttu-id="bc2de-143">Das Benutzerkonto, unter dem das Tool ausgeführt wird, muss über Lesezugriff auf die Überwachungsdatenbank verfügen.</span><span class="sxs-lookup"><span data-stu-id="bc2de-143">The user account under which the tool runs must have Read access to the Monitoring database.</span></span>

<span data-ttu-id="bc2de-144">Die Datei "PersistentChatMonitoringSummary. exe. config \<\> " muss einen connectionStrings-Abschnitt enthalten, der die Verbindungszeichenfolge zur Überwachungsdatenbank definiert.</span><span class="sxs-lookup"><span data-stu-id="bc2de-144">The file, PersistentChatMonitoringSummary.exe.config, must contain a \<connectionStrings\> section that defines the connection string to the Monitoring database.</span></span> <span data-ttu-id="bc2de-145">Darüber hinaus muss ein Schlüssel für das PersistentChatEndpointUri-Objekt enthalten sein, für das die Überwachungsdaten gesammelt werden, und ein Dateipfad zu einem Speicherort für die CSV-Datei, die generiert wird.</span><span class="sxs-lookup"><span data-stu-id="bc2de-145">It must also contain a key for the PersistentChatEndpointUri that the monitoring data will be gathered for, and a file path to a location for the CSV file that will be generated.</span></span> <span data-ttu-id="bc2de-146">Beispiele finden Sie in der installierten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="bc2de-146">Refer to the installed config file for examples.</span></span> <span data-ttu-id="bc2de-147">Die Datei muss sich im gleichen Verzeichnis wie das Tool befinden.</span><span class="sxs-lookup"><span data-stu-id="bc2de-147">The file must be located in the same directory as the tool.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="bc2de-148">Verwendung</span><span class="sxs-lookup"><span data-stu-id="bc2de-148">Usage</span></span>

```Batch
    PersistentChatMonitoringSummary [-StartDateTime <date>] [-EndDateTime <date>]
```

<span data-ttu-id="bc2de-149">Diese Parameter definieren die Auswahl der Daten:</span><span class="sxs-lookup"><span data-stu-id="bc2de-149">These parameters define the selection of data:</span></span>

<span data-ttu-id="bc2de-150">Start **Datum:** Gibt optional das Startdatum des Auswahlzeitraums an.</span><span class="sxs-lookup"><span data-stu-id="bc2de-150">**StartDateTime:** Optionally specifies the start date of the selection period.</span></span> <span data-ttu-id="bc2de-151">Standard: 1/1/1753 12:00:00 am</span><span class="sxs-lookup"><span data-stu-id="bc2de-151">Default: 1/1/1753 12:00:00 AM</span></span>

<span data-ttu-id="bc2de-152">**Enddatum:** Gibt optional das letzte Datum des Auswahlzeitraums an.</span><span class="sxs-lookup"><span data-stu-id="bc2de-152">**EndDateTime:** Optionally specifies the last date of the selection period.</span></span> <span data-ttu-id="bc2de-153">Standard: jetzt</span><span class="sxs-lookup"><span data-stu-id="bc2de-153">Default: Now</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="bc2de-154">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bc2de-154">Example</span></span>

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

## <a name="persistent-chat-stress-tool"></a><span data-ttu-id="bc2de-155">Stress Tool für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="bc2de-155">Persistent Chat Stress Tool</span></span>

<div>

## <a name="description"></a><span data-ttu-id="bc2de-156">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bc2de-156">Description</span></span>

<span data-ttu-id="bc2de-157">Das Stress Tool für beständigen Chat bietet eine einfache Möglichkeit, die Nutzung von beständigem Chat zu simulieren, um die Leistung in der realen Welt zu testen, einschließlich unterschiedlicher Benutzermodelle, die ihren erwarteten Nutzungsszenarien besser entsprechen.</span><span class="sxs-lookup"><span data-stu-id="bc2de-157">The Persistent Chat Stress tool provides an easy way to simulate usage of Persistent Chat to test real-world performance, including varied user models to better fit your expected usage scenarios.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="bc2de-158">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="bc2de-158">Requirements</span></span>

<span data-ttu-id="bc2de-159">Installieren Sie die Ressourcen Kit-Tools für beständigen Chat auf einem Computer mit Domänenbeitritt, der Zugriff auf die Back-End-Datenbank des beständigen Chats hat.</span><span class="sxs-lookup"><span data-stu-id="bc2de-159">Install the Persistent Chat Resource Kit tools onto a domain-joined machine that has access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="bc2de-160">Zusätzlich zu diesem *Controller* -Computer sind mehrere *Loader* -Maschinen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bc2de-160">In addition to this *controller* machine, you will need several *loader* machines.</span></span> <span data-ttu-id="bc2de-161">Für alle 10K-Benutzer in Ihrem Benutzermodell benötigen Sie mindestens 4 GB freien RAM auf einem Loader-Computer.</span><span class="sxs-lookup"><span data-stu-id="bc2de-161">For every 10K users in your user model, you will need at least 4GB of free RAM on a loader machine.</span></span> <span data-ttu-id="bc2de-162">Beispielsweise erfordert ein Run mit 80K-Benutzern etwa 32 GB Arbeitsspeicher, die auf allen Loader-Computern verbreitet werden.</span><span class="sxs-lookup"><span data-stu-id="bc2de-162">For example, a run with 80K users will require about 32GB of RAM spread across all loader machines.</span></span> <span data-ttu-id="bc2de-163">Wir empfehlen, dass Sie über mindestens drei Ladegeräte verfügen, unabhängig von der erwarteten Auslastung.</span><span class="sxs-lookup"><span data-stu-id="bc2de-163">We recommend that you have at least three loader machines, regardless of expected load.</span></span>

<span data-ttu-id="bc2de-164">Loader-Computer müssen das .NET 4,5-Framework sowie die Visual C++ 2012-verteilbare Version installiert haben.</span><span class="sxs-lookup"><span data-stu-id="bc2de-164">Loader machines must have the .NET 4.5 Framework as well as the Visual C++ 2012 Redistributable installed.</span></span>

</div>

<div>

## <a name="configuration"></a><span data-ttu-id="bc2de-165">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="bc2de-165">Configuration</span></span>

<span data-ttu-id="bc2de-166">Kopieren Sie ChatStressTool-Dateien in einen freigegebenen Ordner, auf den alle Loader-Computer zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="bc2de-166">Copy ChatStressTool files into a shared folder accessible from all loader machines.</span></span>

<span data-ttu-id="bc2de-167">Erstellen von Benutzern und Kanälen zur Verwendung im Spannungsverlauf:</span><span class="sxs-lookup"><span data-stu-id="bc2de-167">Create users and channels for use in the stress run:</span></span>

  - <span data-ttu-id="bc2de-168">Erstellen Sie so viele Benutzer, wie Sie von Ihrem Benutzermodell aufgerufen werden, aktivieren Sie diese für lync, und legen Sie die Richtlinie für beständigen Chat auf aktiviert fest.</span><span class="sxs-lookup"><span data-stu-id="bc2de-168">Create as many users as your user model calls for, enable them for Lync, and set their Persistent Chat policy to Enabled.</span></span>

  - <span data-ttu-id="bc2de-169">Erstellen Sie eine Kategorie für Ihre Spannungskanäle, und erstellen Sie dann so viele Räume, wie Sie unter dieser Kategorie benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="bc2de-169">Create a category for your stress channels, and then create as many rooms as are needed under that category.</span></span> <span data-ttu-id="bc2de-170">In der Kategorie sollten alle Belastungs Benutzer in \*\*\*\* der Liste der zulässigen Daten enthalten sein (indem Sie Ihre OU hinzufügen), und bei den Belastungs Räumen sollte eine Privatsphäre-Einstellung **geöffnet**sein.</span><span class="sxs-lookup"><span data-stu-id="bc2de-170">The category should have all stress users in its **Allowed** list (by way of adding their OU), and stress rooms should have a privacy setting of **Open**.</span></span>

  - <span data-ttu-id="bc2de-171">Wir empfehlen, zusätzliche Belastungs Räume zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bc2de-171">We recommend creating extra stress rooms.</span></span> <span data-ttu-id="bc2de-172">Sie können 50.000-Räume mit dem folgenden Befehlszeilen-Schnittstellenbefehl der Windows PowerShell erstellen:</span><span class="sxs-lookup"><span data-stu-id="bc2de-172">You can create 50,000 rooms with the following Windows PowerShell command-line interface command:</span></span>
    ```Powershell
        for ($i = 0; $i -le 50000; $i++) { New-CsPersistentChatRoom -Category <parent category> -Name "StressChan_$i" -Privacy Open }
    ```    

<span data-ttu-id="bc2de-173">Bearbeiten Sie die Konfigurationsdateien so, dass Sie in Ihre Topologie passen:</span><span class="sxs-lookup"><span data-stu-id="bc2de-173">Edit the configuration files to fit your topology:</span></span>

<span data-ttu-id="bc2de-174">Ändern Sie in **LoaderProcess. exe. config**"Controller.contoso.com" in den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Controllers.</span><span class="sxs-lookup"><span data-stu-id="bc2de-174">In **LoaderProcess.exe.config**, change “controller.contoso.com” to the controller machine’s fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="bc2de-175">In **StressLauncher. exe. config:**</span><span class="sxs-lookup"><span data-stu-id="bc2de-175">In **StressLauncher.exe.config:**</span></span>

1.  <span data-ttu-id="bc2de-176">Ändern Sie den Wert für die Einstellung "LoaderBinary" in den Pfad des freigegebenen Ordners.</span><span class="sxs-lookup"><span data-stu-id="bc2de-176">Change the “LoaderBinary” setting value to the shared folder’s path.</span></span>

2.  <span data-ttu-id="bc2de-177">Ändern Sie "abzüglicher"/"AdminPassword" in Anmeldeinformationen, die Administratorzugriff auf Loader-Computer haben.</span><span class="sxs-lookup"><span data-stu-id="bc2de-177">Change “AdminUser”/”AdminPassword” to credentials that have admin access to loader machines.</span></span>

3.  <span data-ttu-id="bc2de-178">Ändern Sie "ChannelCategory" in den Namen der Kategorie, unter der Spannungskanäle erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="bc2de-178">Change “ChannelCategory” to the name of the category that stress channels have been created under.</span></span>

4.  <span data-ttu-id="bc2de-179">Ändern Sie "UserNamePattern" und "UserPasswordPattern" in eine Vorlage, die Ihren Stress-Benutzeranmeldeinformationen entspricht.</span><span class="sxs-lookup"><span data-stu-id="bc2de-179">Change “UserNamePattern” and “UserPasswordPattern” to a template that matches your stress user credentials.</span></span> <span data-ttu-id="bc2de-180">{0}wird durch die Indexnummer des Benutzers ersetzt.</span><span class="sxs-lookup"><span data-stu-id="bc2de-180">{0} is replaced with the user’s index number.</span></span>

5.  <span data-ttu-id="bc2de-181">Ändern Sie "Domäne" in die SIP-Domäne ihrer Testtopologie.</span><span class="sxs-lookup"><span data-stu-id="bc2de-181">Change “Domain” to the SIP domain of your test topology.</span></span>

6.  <span data-ttu-id="bc2de-182">Ändern Sie "ConnectionString" in eine Verbindungszeichenfolge für die Back-End-Datenbank des beständigen Chats.</span><span class="sxs-lookup"><span data-stu-id="bc2de-182">Change “ConnectionString” to a connection string for your Persistent Chat back-end database.</span></span>

7.  <span data-ttu-id="bc2de-183">Ändern Sie "UserIndexStart" in den Index des ersten Belastungs Benutzers.</span><span class="sxs-lookup"><span data-stu-id="bc2de-183">Change “UserIndexStart” to the index of the first stress user.</span></span>

8.  <span data-ttu-id="bc2de-184">Ändern Sie "LyncFQDN" in den FQDN des Front-End-Pools.</span><span class="sxs-lookup"><span data-stu-id="bc2de-184">Change “LyncFQDN” to the FQDN of your Front End pool.</span></span>

9.  <span data-ttu-id="bc2de-185">Ändern Sie die Liste "Computer", um Computernamen für alle Ladegeräte Computer einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="bc2de-185">Modify the “Machines” list to include machine names for all of your loader machines.</span></span>

10. <span data-ttu-id="bc2de-186">Ändern Sie die BaseAddress des Dienstendpunkts (Standard ist "Controller.contoso.com") auf den FQDN Ihres Controllercomputers.</span><span class="sxs-lookup"><span data-stu-id="bc2de-186">Change the baseAddress of the service endpoint (default is “controller.contoso.com”) to the FQDN of your controller machine.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="bc2de-187">Verwendung</span><span class="sxs-lookup"><span data-stu-id="bc2de-187">Usage</span></span>

<span data-ttu-id="bc2de-188">Öffnen Sie nach Abschluss der Konfiguration StressLauncher. exe auf dem Controllercomputer.</span><span class="sxs-lookup"><span data-stu-id="bc2de-188">After configuration is complete, open StressLauncher.exe on the controller machine.</span></span> <span data-ttu-id="bc2de-189">Sie können StressLauncher als beliebigen Benutzer starten.</span><span class="sxs-lookup"><span data-stu-id="bc2de-189">You can launch StressLauncher as any user.</span></span> <span data-ttu-id="bc2de-190">Die Anmeldeinformationen, unter denen die Loader-Prozesse auf den Loader-Computern gestartet werden, müssen in der config-Datei angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="bc2de-190">The credentials under which the loader processes start on the loader machines must be specified in the config file.</span></span> <span data-ttu-id="bc2de-191">Sie müssen auch eine Verbindungszeichenfolge angeben, die über Lesezugriff auf die Back-End-Datenbank des beständigen Chats verfügt.</span><span class="sxs-lookup"><span data-stu-id="bc2de-191">You also must give a connection string that has Read access to the Persistent Chat back-end database.</span></span> <span data-ttu-id="bc2de-192">Wenn diese Verbindungszeichenfolge die integrierte Windows-Authentifizierung verwendet, müssen Sie StressLauncher als Benutzer mit diesem Zugriff starten.</span><span class="sxs-lookup"><span data-stu-id="bc2de-192">If this connection string uses integrated Windows authentication, you must launch StressLauncher as a user that has this access.</span></span>

<span data-ttu-id="bc2de-193">Ändern Sie die Benutzermodell Einstellungen nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="bc2de-193">Alter the user model settings as needed.</span></span> <span data-ttu-id="bc2de-194">Klicken Sie auf **Load starten** , um einen Testlauf zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="bc2de-194">Click **Start Load** to initiate a run.</span></span> <span data-ttu-id="bc2de-195">Nach ungefähr einer Minute werden die Benutzer angemeldet, und die Statusleiste beginnt zu füllen.</span><span class="sxs-lookup"><span data-stu-id="bc2de-195">After a minute or so, users will start being signed in, and the progress bar will begin to fill.</span></span> <span data-ttu-id="bc2de-196">An diesem Punkt können Sie den Controller-Computer verwenden und Leistungsmessungen durchführen.</span><span class="sxs-lookup"><span data-stu-id="bc2de-196">At this point, you may can the controller machine working and take performance measurements.</span></span>

</div>

</div>

<div>

## <a name="chatupgradeverifier"></a><span data-ttu-id="bc2de-197">ChatUpgradeVerifier</span><span class="sxs-lookup"><span data-stu-id="bc2de-197">ChatUpgradeVerifier</span></span>

<div>

## <a name="description"></a><span data-ttu-id="bc2de-198">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bc2de-198">Description</span></span>

<span data-ttu-id="bc2de-199">ChatUpgradeVerifier ist ein beständiger Chat-spezifischer Datenbankvergleichstool.</span><span class="sxs-lookup"><span data-stu-id="bc2de-199">ChatUpgradeVerifier is a Persistent Chat specific database comparison tool.</span></span> <span data-ttu-id="bc2de-200">Das Tool vergleicht entweder die Gruppen-Chat-2007 R2-oder Gruppen-Chat 2010-Datenbank (2007/2010Db) mit der beständigen Chat-2013-Datenbank (2013Db).</span><span class="sxs-lookup"><span data-stu-id="bc2de-200">The tool compares either the Group Chat 2007 R2 or Group Chat 2010 Database (2007/2010Db) to the Persistent Chat 2013 Database (2013Db).</span></span>

<span data-ttu-id="bc2de-201">Das Tool überprüft einzeln jede Kategorie, beständigen Chatroom und Add-in in 2007/2010Db, um festzustellen, ob Sie im 2013Db angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="bc2de-201">The tool will check, one by one, each category, Persistent Chat room, and add-in in 2007/2010Db to see if it appears in the 2013Db.</span></span> <span data-ttu-id="bc2de-202">Der Vergleich umfasst die Überprüfung aller Einstellungen für die Kategorie, den Chatroom oder das Add-in, alle Prinzipale im Bereich der Kategorie sowie alle Prinzipale in einer Rolle in der Kategorie oder im Chatroom.</span><span class="sxs-lookup"><span data-stu-id="bc2de-202">The comparison includes checking all settings on the category, chat room, or add-in, any principals in scope on the category, and any principal in a role on either the category or the chat room.</span></span> <span data-ttu-id="bc2de-203">Wenn eine Kategorie oder ein Chatroom im 2013Db nicht richtig angezeigt wird, werden die Unterschiede in einer Konfliktdatei ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="bc2de-203">If a category or a chat room does not appear correctly in the 2013Db, the differences will be output to a conflicts file.</span></span> <span data-ttu-id="bc2de-204">Wenn nach dem Upgrade die Version 2007/2010Db geändert wird und dann dieses Tool ausgeführt wird, gibt es Unterschiede, die in der Dateikonflikte ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="bc2de-204">If, after the upgrade has occurred, the 2007/2010Db is changed and then this tool is run, there will be a differences output to the conflicts file.</span></span> <span data-ttu-id="bc2de-205">Beachten Sie, dass diese Anwendung nur ein Tool zum Vergleichen von Datenbanken ist und den Upgradeprozess nicht überprüft.</span><span class="sxs-lookup"><span data-stu-id="bc2de-205">Note that this application is a database comparison tool only and does not validate the upgrade process.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="bc2de-206">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="bc2de-206">Requirements</span></span>

<span data-ttu-id="bc2de-207">Installieren Sie die Ressourcen Kit-Tools für beständigen Chat auf einem Computer mit Domänenbeitritt, der Zugriff auf die Back-End-Datenbanken des beständigen Chats (frühere und aktuelle Versionen für beständigen Chat) hat.</span><span class="sxs-lookup"><span data-stu-id="bc2de-207">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Persistent Chat back-end databases (previous and current versions for Persistent Chat).</span></span>

<span data-ttu-id="bc2de-208">Das Benutzerkonto, unter dem das Tool ausgeführt wird, muss über Lesezugriff auf die persistenten Chat Datenbanken verfügen.</span><span class="sxs-lookup"><span data-stu-id="bc2de-208">The user account under which the tool runs must have Read access to the Persistent Chat databases.</span></span>

<span data-ttu-id="bc2de-209">Die Datei "ChatUpgradeVerifier. exe. config" muss entweder den GroupChat2007R2Db-Parameter oder den GroupChat2010Db-Parameter enthalten, mit einer Verbindungszeichenfolge zur entsprechenden Gruppen Chat Datenbank (entweder Groupchat 2007R2 oder 2010).</span><span class="sxs-lookup"><span data-stu-id="bc2de-209">The ChatUpgradeVerifier.exe.config file must contain either the GroupChat2007R2Db parameter or the GroupChat2010Db parameter, with a connection string to the appropriate Group Chat database (either Groupchat 2007R2 or 2010).</span></span> <span data-ttu-id="bc2de-210">Sie muss auch einen PersistentChat2013Db-Parameter mit einer Verbindungszeichenfolge zur 2013-Datenbank des beständigen Chats enthalten.</span><span class="sxs-lookup"><span data-stu-id="bc2de-210">It must also contain a PersistentChat2013Db parameter, with a connection string to the Persistent Chat 2013 database.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="bc2de-211">Verwendung</span><span class="sxs-lookup"><span data-stu-id="bc2de-211">Usage</span></span>

<span data-ttu-id="bc2de-212">Führen Sie **ChatUpgradeVerifier** ohne Parameter aus.</span><span class="sxs-lookup"><span data-stu-id="bc2de-212">Run **ChatUpgradeVerifier** without any parameters.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="bc2de-213">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bc2de-213">Example</span></span>

<span data-ttu-id="bc2de-214">![Ausführen von ChatUpgradeVerifier. exe.] (images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "Ausführen von ChatUpgradeVerifier. exe.")</span><span class="sxs-lookup"><span data-stu-id="bc2de-214">![Running ChatUpgradeVerifier.exe.](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "Running ChatUpgradeVerifier.exe.")</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-usage-report"></a><span data-ttu-id="bc2de-215">Verwendungsbericht für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="bc2de-215">Persistent Chat Usage Report</span></span>

<div>

## <a name="description"></a><span data-ttu-id="bc2de-216">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bc2de-216">Description</span></span>

<span data-ttu-id="bc2de-217">Das ChatUsageReport-Tool generiert einen HTML-Bericht zur Verwendung des beständigen Chat Diensts.</span><span class="sxs-lookup"><span data-stu-id="bc2de-217">The ChatUsageReport tool generates an HTML report of Persistent Chat service usage.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="bc2de-218">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="bc2de-218">Requirements</span></span>

<span data-ttu-id="bc2de-219">Installieren Sie die Ressourcen Kit-Tools für beständigen Chat auf einem Computer mit Domänenbeitritt, der Zugriff auf die Back-End-Datenbank des beständigen Chats hat.</span><span class="sxs-lookup"><span data-stu-id="bc2de-219">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="bc2de-220">Das Benutzerkonto, unter dem das Tool ausgeführt wird, muss über Lesezugriff auf die Back-End-Datenbank des beständigen Chats verfügen.</span><span class="sxs-lookup"><span data-stu-id="bc2de-220">The user account under which the tool is run must have Read access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="bc2de-221">Die Datei "ChatUsageReport. exe. config \<\> " muss einen connectionStrings-Abschnitt enthalten, der die Verbindungszeichenfolge für die Back-End-Datenbank des beständigen Chats definiert.</span><span class="sxs-lookup"><span data-stu-id="bc2de-221">The file, ChatUsageReport.exe.config, must contain a \<connectionStrings\> section defining the connection string to the Persistent Chat back-end database.</span></span> <span data-ttu-id="bc2de-222">Der Inhalt der Standardkonfigurationsdatei wird hier als Referenz angegeben.</span><span class="sxs-lookup"><span data-stu-id="bc2de-222">The contents of the default config file are included here, for your reference.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="bc2de-223">Verwendung</span><span class="sxs-lookup"><span data-stu-id="bc2de-223">Usage</span></span>

```Powershell
    ChatUsageReport [-StartDate {date}] [-EndDate {date}] [-TopActiveUsers {n}] [-TopActiveRooms {n}] [-LeastActiveRooms {n}] [-RoomsInactiveSince {Date}] [-OutputFolder {path}]
```
<span data-ttu-id="bc2de-224">Diese Parameter definieren die Auswahl der Daten:</span><span class="sxs-lookup"><span data-stu-id="bc2de-224">These parameters define the selection of data:</span></span>

<span data-ttu-id="bc2de-225">**StartDate:** Gibt optional das UTC-Anfangsdatum des Auswahlzeitraums an.</span><span class="sxs-lookup"><span data-stu-id="bc2de-225">**StartDate:** Optionally specifies the UTC start date of the selection period.</span></span> <span data-ttu-id="bc2de-226">Standard: frühestes Datum</span><span class="sxs-lookup"><span data-stu-id="bc2de-226">Default: Earliest Date</span></span>

<span data-ttu-id="bc2de-227">**EndDate:** Gibt optional das UTC-Enddatum des Auswahlzeitraums an.</span><span class="sxs-lookup"><span data-stu-id="bc2de-227">**EndDate:** Optionally specifies the UTC end date of the selection period.</span></span> <span data-ttu-id="bc2de-228">Standard: jetzt</span><span class="sxs-lookup"><span data-stu-id="bc2de-228">Default: Now</span></span>

<span data-ttu-id="bc2de-229">Diese Parameter definieren, wie und welche Daten angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="bc2de-229">These parameters define how and what data is displayed:</span></span>

<span data-ttu-id="bc2de-230">**TopActiveUsers:** Wenn dies angegeben ist, enthält der Bericht die n meisten aktiven Benutzer in Bezug auf die Anzahl der Nachrichten, die der Benutzer im Chatroom für den ausgewählten Zeitraum gepostet hat.</span><span class="sxs-lookup"><span data-stu-id="bc2de-230">**TopActiveUsers:** If this is specified, the report will include the n most active users in terms of the number of messages the user has posted in the chat room for the selected period.</span></span> <span data-ttu-id="bc2de-231">Standard: 10</span><span class="sxs-lookup"><span data-stu-id="bc2de-231">Default: 10</span></span>

<span data-ttu-id="bc2de-232">**TopActiveRooms:** Wenn dies angegeben ist, enthält der Bericht die n aktivsten Chatrooms in Bezug auf die Anzahl der Nachrichten, die in dem Raum für den ausgewählten Zeitraum gepostet wurden.</span><span class="sxs-lookup"><span data-stu-id="bc2de-232">**TopActiveRooms:** If this is specified, the report will include the n most active chat rooms in terms of the number of messages posted in the room for the selected period.</span></span> <span data-ttu-id="bc2de-233">Standard: 10</span><span class="sxs-lookup"><span data-stu-id="bc2de-233">Default: 10</span></span>

<span data-ttu-id="bc2de-234">**LeastActiveRooms:** Wenn dieser Wert angegeben wird, enthält der Bericht die mindestens aktiven Chatrooms in Bezug auf die Anzahl der Nachrichten, die im Chatroom für den ausgewählten Zeitraum gepostet wurden.</span><span class="sxs-lookup"><span data-stu-id="bc2de-234">**LeastActiveRooms:** If this is specified, the report will include the n least active chat rooms in terms of the number of messages posted in the chat room for the selected period.</span></span> <span data-ttu-id="bc2de-235">Für Chatrooms wird mindestens eine Nachricht bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="bc2de-235">Rooms will have at least one message posted.</span></span> <span data-ttu-id="bc2de-236">Standard: 10</span><span class="sxs-lookup"><span data-stu-id="bc2de-236">Default: 10</span></span>

<span data-ttu-id="bc2de-237">**RoomsInactiveSince:** Wenn dieser Wert angegeben wird, enthält der Bericht eine Liste der Chatrooms, die seit dem angegebenen Datum inaktiv sind.</span><span class="sxs-lookup"><span data-stu-id="bc2de-237">**RoomsInactiveSince:** If this is specified, the report will include a list of chat rooms that have been inactive since the specified date.</span></span> <span data-ttu-id="bc2de-238">Standard: ganze Zeit</span><span class="sxs-lookup"><span data-stu-id="bc2de-238">Default: Entire Time</span></span>

<span data-ttu-id="bc2de-239">**OutputFolder:** Der Ordner, in dem die ChatUsageReport. html-und die Graph-Bilder abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="bc2de-239">**OutputFolder:** The folder where the ChatUsageReport.html and the graph images will be placed.</span></span> <span data-ttu-id="bc2de-240">Dies muss in der config-Datei oder in der Befehlszeile definiert werden.</span><span class="sxs-lookup"><span data-stu-id="bc2de-240">This must be defined in the config file or on the command line.</span></span>

<span data-ttu-id="bc2de-241">Alle Befehlszeilenparameter Werte können auch in der Datei "ChatUsageReport. exe. config" angegeben werden, die sich im gleichen Verzeichnis wie das Tool befindet.</span><span class="sxs-lookup"><span data-stu-id="bc2de-241">All of the command line parameter values can also be specified in the ChatUsageReport.exe.config file that is located in the same directory as the tool.</span></span> <span data-ttu-id="bc2de-242">Wenn ein beliebiger Wert sowohl in der config-Datei als auch in der Befehlszeile angegeben wird, wird der Wert der config-Datei durch den Befehlszeilenwert überschrieben.</span><span class="sxs-lookup"><span data-stu-id="bc2de-242">If any value is specified in both the config file and the command line, the command line value will override the config file value.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="bc2de-243">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="bc2de-243">Output</span></span>

<span data-ttu-id="bc2de-244">Der Bericht enthält immer die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="bc2de-244">The report will always include the following output:</span></span>

  - <span data-ttu-id="bc2de-245">Die meisten aktiven Chatrooms nach Anzahl der Nachrichten Beiträge für den ausgewählten Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="bc2de-245">Top n most active chat rooms by number of message posts for selected period.</span></span>

  - <span data-ttu-id="bc2de-246">Die meisten aktiven Benutzer nach der Anzahl der Nachrichten Beiträge für den ausgewählten Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="bc2de-246">Top n most active users by number of message posts for selected period.</span></span>

  - <span data-ttu-id="bc2de-247">Top n least Active Chatrooms nach Anzahl der Nachrichten Beiträge für den ausgewählten Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="bc2de-247">Top n least active chat rooms by number of message posts for selected period.</span></span>

  - <span data-ttu-id="bc2de-248">Chatrooms, die für die gesamte Lebensdauer der Datenbank oder seit dem angegebenen Datum inaktiv sind.</span><span class="sxs-lookup"><span data-stu-id="bc2de-248">Chat rooms that are inactive for the entire life of the database, or since the specified date.</span></span>

  - <span data-ttu-id="bc2de-249">Täglicher Nachrichten-Trend für ausgewählten Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="bc2de-249">Daily message post trend for selected period.</span></span>

  - <span data-ttu-id="bc2de-250">Wöchentlicher Nachrichten Post-Trend für ausgewählten Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="bc2de-250">Weekly message post trend for selected period.</span></span>

  - <span data-ttu-id="bc2de-251">Monatlicher Nachrichten-Post-Trend für ausgewählten Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="bc2de-251">Monthly message post trend for selected period.</span></span>

  - <span data-ttu-id="bc2de-252">Nachrichten Beiträge für ausgewählten Zeitraum insgesamt.</span><span class="sxs-lookup"><span data-stu-id="bc2de-252">Total message posts for selected period.</span></span>

  - <span data-ttu-id="bc2de-253">Die Gesamtzahl der aktivierten Chatrooms.</span><span class="sxs-lookup"><span data-stu-id="bc2de-253">Total number of enabled rooms.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="bc2de-254">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bc2de-254">Example</span></span>

<span data-ttu-id="bc2de-255">Im folgenden Beispiel wird ein Nutzungsbericht für das gesamte Jahr 2001 generiert, und der Bericht wird in der in der Datei "ChatUsageReport. exe. config" angegebenen OutputFolder platziert.</span><span class="sxs-lookup"><span data-stu-id="bc2de-255">The following example generates a usage report for the entire year 2001 and places the report in the OutputFolder specified in the ChatUsageReport.exe.config.</span></span>

```Powershell
    ChatUsageReport -RoomsInactiveSince 06-20-2010
```
<span data-ttu-id="bc2de-256">ChatUsageReport. exe. config:</span><span class="sxs-lookup"><span data-stu-id="bc2de-256">ChatUsageReport.exe.config:</span></span>

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

## <a name="scheduleadsyncforprincipal"></a><span data-ttu-id="bc2de-257">ScheduleADSyncForPrincipal</span><span class="sxs-lookup"><span data-stu-id="bc2de-257">ScheduleADSyncForPrincipal</span></span>

<div>

## <a name="description"></a><span data-ttu-id="bc2de-258">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bc2de-258">Description</span></span>

<span data-ttu-id="bc2de-259">ScheduleADSyncForPrincipal ist ein Microsoft SQL Server 2012-Skript, das direkt in SQL Server Management Studio ausgeführt werden muss, wenn eine Verbindung mit der Back-End-Datenbank des beständigen Chats besteht.</span><span class="sxs-lookup"><span data-stu-id="bc2de-259">ScheduleADSyncForPrincipal is a Microsoft SQL Server 2012 script that must be run directly from within SQL Server Management Studio when connected to the Persistent Chat back-end database.</span></span> <span data-ttu-id="bc2de-260">Mit diesem Skript können Sie beständigen Chat zwingen, seine Einträge eines Benutzers mit denen der Active Directory-Domänendienste zu synchronisieren, anstatt auf die geplante Synchronisierungszeit zu warten.</span><span class="sxs-lookup"><span data-stu-id="bc2de-260">This script enables you to force Persistent Chat to synchronize its records of a user with those of Active Directory Domain Services, rather than waiting for the scheduled synchronization time.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="bc2de-261">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="bc2de-261">Requirements</span></span>

<span data-ttu-id="bc2de-262">Das Benutzerkonto, unter dem das Skript ausgeführt wird, muss über Besitzer Zugriff auf die Back-End-Datenbank des beständigen Chats verfügen.</span><span class="sxs-lookup"><span data-stu-id="bc2de-262">The user account under which the script is run must have owner access to the Persistent Chat back-end database.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="bc2de-263">Verwendung</span><span class="sxs-lookup"><span data-stu-id="bc2de-263">Usage</span></span>

<span data-ttu-id="bc2de-264">Im folgenden finden Sie die Inhalte des Standardskripts:</span><span class="sxs-lookup"><span data-stu-id="bc2de-264">Following are the contents of the default script:</span></span>

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

