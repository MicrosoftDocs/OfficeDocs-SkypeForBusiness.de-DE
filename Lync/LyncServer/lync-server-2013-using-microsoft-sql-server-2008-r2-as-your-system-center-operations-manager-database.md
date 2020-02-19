---
title: 'Lync Server 2013: Verwenden von Microsoft SQL Server 2008 R2 als System Center Operations Manager-Datenbank'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database
ms:assetid: 0efe76da-8854-499e-bdc7-3623244a8e85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687969(v=OCS.15)
ms:contentKeyID: 49733555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 800da512c3cc9690c368c9d397774df0dea2d0e0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database-for-lync-server-2013"></a><span data-ttu-id="71f39-102">Verwenden von Microsoft SQL Server 2008 R2 als System Center Operations Manager-Datenbank für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71f39-102">Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71f39-103">_**Letztes Änderungsstand des Themas:** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="71f39-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="71f39-104">Führen Sie die in diesem Thema beschriebenen Schritte aus, um SQL Server 2008 R2 als Back-End-Datenbank zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="71f39-104">To use SQL Server 2008 R2 as your back-end database, complete the steps detailed in this topic.</span></span>

<div>

## <a name="configuring-sql-server-2008-r2-and-sql-server-reporting-services"></a><span data-ttu-id="71f39-105">Konfigurieren SQL Server 2008 R2-und SQL Server Reporting Services</span><span class="sxs-lookup"><span data-stu-id="71f39-105">Configuring SQL Server 2008 R2 and SQL Server Reporting Services</span></span>

<span data-ttu-id="71f39-106">Bevor Sie mit der Installation von System Center Operations Manager beginnen, müssen Sie zwei Änderungen an Ihrer SQL Server 2008 R2 und Ihrer SQL Server Reporting Services-Konfiguration vornehmen.</span><span class="sxs-lookup"><span data-stu-id="71f39-106">Before you begin installing System Center Operations Manager you must make two changes to your SQL Server 2008 R2 and your SQL Server Reporting Services configuration.</span></span> <span data-ttu-id="71f39-107">(Diese Änderungen sind nur erforderlich, wenn Sie SQL Server 2008 R2 als Operations Manager-Datenbank verwenden.) Führen Sie zunächst die folgenden Schritte auf dem Computer aus, auf dem die Operations Manager-Datenbank gehostet wird:</span><span class="sxs-lookup"><span data-stu-id="71f39-107">(These changes are required only if you are using SQL Server 2008 R2 as your Operations Manager database.) First, do the following on the computer that will host your Operations Manager database:</span></span>

1.  <span data-ttu-id="71f39-108">Klicken Sie auf **Start** und dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="71f39-108">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="71f39-109">Geben Sie im Dialogfeld **Ausführen** den **Text C\\: Programm\\Dateien\\ Microsoft SQL Server\_MSRS10 50.\\ARCHINST Reporting\\Services Report Server** ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="71f39-109">In the **Run** dialog box, type **C:\\Program Files\\Microsoft SQL Server\\ MSRS10\_50.ARCHINST\\Reporting Services\\ReportServer** and then press ENTER.</span></span>

3.  <span data-ttu-id="71f39-110">Öffnen Sie im Ordner **Report Server** die Datei **RSReportServer. config** im Editor oder in einem anderen Text-Editor.</span><span class="sxs-lookup"><span data-stu-id="71f39-110">In the **ReportServer** folder, open the file **rsreportserver.config** in Notepad or any other text editor.</span></span>

4.  <span data-ttu-id="71f39-111">In der Nähe des Datei Beginns wird eine Reihe von "Schlüssel hinzufügen"-Knoten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="71f39-111">Near the beginning of the file you will see a series of "Add Key" nodes.</span></span> <span data-ttu-id="71f39-112">Suchen Sie den Eintrag, der \*\* \<Hinzufügen von Key = "SecureConnectionLevel"\*\* beginnt, und legen Sie den Wert auf **0**fest:</span><span class="sxs-lookup"><span data-stu-id="71f39-112">Find the entry that begins **\<Add Key="SecureConnectionLevel"** and set the value to **0**:</span></span>
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  <span data-ttu-id="71f39-113">Speichern Sie die Datei **RSReportServer. config** , und schließen Sie dann den Text-Editor.</span><span class="sxs-lookup"><span data-stu-id="71f39-113">Save the file **rsreportserver.config** and then close your text editor.</span></span>

<span data-ttu-id="71f39-114">Nach dem Aktualisieren der Berichts Server-Konfigurationsdatei müssen Sie SQL Server Reporting Services das richtige Zertifikat zuweisen.</span><span class="sxs-lookup"><span data-stu-id="71f39-114">After updating the Report Server configuration file you must then assign the correct certificate to SQL Server Reporting Services.</span></span> <span data-ttu-id="71f39-115">Gehen Sie dazu wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="71f39-115">To do that:</span></span>

1.  <span data-ttu-id="71f39-116">Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft SQL Server 2008 R2**, dann auf **Konfigurations Tools**, und klicken Sie dann auf **Konfigurations-Manager für Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="71f39-116">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>

2.  <span data-ttu-id="71f39-117">Stellen Sie im Dialogfeld **Reporting Services-Konfigurationsverbindung** sicher, dass der Name des Servers im Feld **Servername** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="71f39-117">In the **Reporting Services Configuration Connection** dialog box, make sure that the name of your server appears in the **Server Name** box.</span></span> <span data-ttu-id="71f39-118">Wählen Sie in der Dropdownliste **Berichts Server Instanz** die SQL Server Instanz aus, in der die Operations Manager-Datenbank gehostet wird (beispielsweise **ARCHINST**), und klicken Sie dann auf **verbinden**.</span><span class="sxs-lookup"><span data-stu-id="71f39-118">Select the SQL Server instance that will host your Operations Manager database (for example, **ARCHINST**) from the **Report Server Instance** drop-down list and then click **Connect**.</span></span>

3.  <span data-ttu-id="71f39-119">Klicken Sie im Konfigurations-Manager für Reporting Services auf **Webdienst-URL**.</span><span class="sxs-lookup"><span data-stu-id="71f39-119">In Reporting Services Configuration Manager, click **Web Service URL**.</span></span>

4.  <span data-ttu-id="71f39-120">Wählen Sie auf der Seite **Webdienst-URL** das Zertifikat aus der Dropdownliste **SSL-Zertifikat** aus, das für Ihre Reporting Services verwendet werden soll, und klicken Sie dann auf über **nehmen**.</span><span class="sxs-lookup"><span data-stu-id="71f39-120">On the **Web Service URL** page, select the certificate to be used for your Reporting Services from the **SSL Certificate** dropdown list and then click **Apply**.</span></span> <span data-ttu-id="71f39-121">Nach ein paar Sekunden wird ein paar von URLs angezeigt, die unter **Report Server-Webdienst-URLs**aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="71f39-121">After a few seconds, you will see a pair of URLs listed under **Report Server Web Service URLs**.</span></span>

5.  <span data-ttu-id="71f39-122">Klicken Sie auf beide URLs, um sicherzustellen, dass Sie auf SQL Server Reporting Services zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="71f39-122">Click both of the URLs to verify that you can access SQL Server Reporting Services.</span></span>

6.  <span data-ttu-id="71f39-123">Schließen Sie den Reporting Services-Konfigurations-Manager.</span><span class="sxs-lookup"><span data-stu-id="71f39-123">Close Reporting Services Configuration Manager.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-database-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="71f39-124">Erstellen einer System Center Operations Manager-Datenbank für die Verwendung mit SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="71f39-124">Creating a System Center Operations Manager database for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="71f39-125">Wenn Sie System Center Operations Manager für die Verwendung einer SQL Server 2008 R2-Datenbank konfigurieren möchten, müssen Sie "manuell" die Operations Manager-Datenbank auf dem Computer erstellen, auf dem SQL Server 2008 R2 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="71f39-125">If you want to configure System Center Operations Manager to use a SQL Server 2008 R2 database, you will need to "manually" create the Operations Manager database on the computer running SQL Server 2008 R2.</span></span> <span data-ttu-id="71f39-126">(Wieder sind diese Schritte nicht erforderlich, wenn Sie SQL Server 2005 oder SQL Server 2008 als Back-End-Datenbank verwenden.)</span><span class="sxs-lookup"><span data-stu-id="71f39-126">(Again, these steps are not required if you are using SQL Server 2005 or SQL Server 2008 as your back-end database.)</span></span>

<span data-ttu-id="71f39-127">Führen Sie die folgenden Schritte aus, um eine Operations Manager-Datenbank manuell zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="71f39-127">To manually create an Operations Manager database do the following:</span></span>

1.  <span data-ttu-id="71f39-128">Doppelklicken Sie auf dem System Center Operations Manager 2007 R2-Setup Medium\\im Support Tools amd64-Ordner auf **DBCreateWizard. exe**.</span><span class="sxs-lookup"><span data-stu-id="71f39-128">On the System Center Operations Manager 2007 R2 setup media, in the SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="71f39-129">Klicken Sie im Assistenten für die Datenbankkonfiguration auf der Seite **Willkommen beim Assistenten für die Datenbankkonfiguration** auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="71f39-129">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="71f39-130">Lassen Sie auf der Seite **Datenbankinformationen** alle Einstellungen unverändert, und klicken Sie dann auf **weiter** .</span><span class="sxs-lookup"><span data-stu-id="71f39-130">On the **Database Information** page leave all the settings as-is and then click **Next**</span></span>

4.  <span data-ttu-id="71f39-131">Geben Sie auf der Seite **Verwaltungsgruppenkonfiguration** in das Feld **Verwaltungsgruppenname** einen Namen für die Verwaltungsgruppe ein (beispielsweise **lync Server Überwachung**), und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="71f39-131">On the **Management Group Configuration** page type a name for your Management Group (for example, **Lync Server Monitoring**) in the **Management Group name** box and then click **Next**.</span></span>

5.  <span data-ttu-id="71f39-132">Klicken Sie auf der Seite **Fehlerberichte von Operations Manager** auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="71f39-132">On the **Operations Manager Error Reports** page click **Next**.</span></span>

6.  <span data-ttu-id="71f39-133">Klicken Sie auf der **Zusammenfassungs** Seite auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="71f39-133">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-data-warehouse-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="71f39-134">Erstellen eines System Center Operations Manager-Data Warehouse für die Verwendung mit SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="71f39-134">Creating a System Center Operations Manager data warehouse for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="71f39-135">Microsoft lync Server 2013 werden mit drei neuen System Center Operations Manager-Berichten ausgeliefert:</span><span class="sxs-lookup"><span data-stu-id="71f39-135">Microsoft Lync Server 2013 ships with three new System Center Operations Manager reports:</span></span>

  - <span data-ttu-id="71f39-136">**End-to-End-Szenario-Verfügbarkeitsbericht**   in diesem Bericht wird die Verfügbarkeit/Uptime für wichtige lync Server Dienste wie Registrierung oder Anwesenheit erläutert.</span><span class="sxs-lookup"><span data-stu-id="71f39-136">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="71f39-137">**Kapazitäts Bericht**   mit Leistungsindikatorinformationen zeigt dieser Bericht Trends für Systemkomponenten wie Arbeitsspeicher Verfügbarkeit und Prozessorauslastung.</span><span class="sxs-lookup"><span data-stu-id="71f39-137">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="71f39-138">**Komponentenbericht**   in diesem Bericht werden die wichtigsten Warnungs Generatoren aufgelistet, die nach lync Server Komponente gruppiert sind.</span><span class="sxs-lookup"><span data-stu-id="71f39-138">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="71f39-139">Um diese neuen Berichte verwenden zu können, müssen Sie ein System Center Operations Manager-Data Warehouse installieren.</span><span class="sxs-lookup"><span data-stu-id="71f39-139">In order to use these new reports you must install a System Center Operations Manager data warehouse.</span></span> <span data-ttu-id="71f39-140">(Ein Data Warehouse ermöglicht die langfristige Speicherung von Betriebsdaten.) Wenn Sie ein Data Warehouse mit SQL Server 2008 R2 verwenden möchten, müssen Sie die folgenden Schritte auf dem Computer ausführen, auf dem die SQL Server-Datenbank gehostet wird:</span><span class="sxs-lookup"><span data-stu-id="71f39-140">(A data warehouse provides for long-term storage of operations data.) To use a data warehouse with SQL Server 2008 R2 you must carry out the following steps on the computer that hosts your SQL Server database:</span></span>

1.  <span data-ttu-id="71f39-141">Doppelklicken Sie auf den System Center Operations Manager-Setupmedien\\im\\Ordner Setup Support Tools amd64 auf **DBCreateWizard. exe**.</span><span class="sxs-lookup"><span data-stu-id="71f39-141">On the System Center Operations Manager setup media, in the Setup\\SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="71f39-142">Klicken Sie im Assistenten für die Datenbankkonfiguration auf der Seite **Willkommen beim Assistenten für die Datenbankkonfiguration** auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="71f39-142">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="71f39-143">Wählen Sie auf der Seite Daten **Bankinformationen** in der Dropdownliste **Datenbanktyp** die Option **Operations Manager-Data Warehouse-Datenbank** aus, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="71f39-143">On the **Database Information** page, select **Operations Manager Data Warehouse Database** from the **Database Type** dropdown list and then click **Next**.</span></span>

4.  <span data-ttu-id="71f39-144">Klicken Sie auf der **Zusammenfassungs** Seite auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="71f39-144">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="installing-the-system-center-operations-manager-console"></a><span data-ttu-id="71f39-145">Installieren der System Center Operations Manager-Konsole</span><span class="sxs-lookup"><span data-stu-id="71f39-145">Installing the System Center Operations Manager console</span></span>

<span data-ttu-id="71f39-146">Die Operations Manager-Konsole ist das primäre Tool, das zum Verwalten von System Center Operations Manager verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="71f39-146">The Operations Manager console is the primary tool used to manage System Center Operations Manager.</span></span> <span data-ttu-id="71f39-147">Stellen Sie vor dem Installieren der Operations Manager-Konsole sicher, dass Sie eine unterstützte Version von SQL Server zusammen mit dem SQL Server-Berichterstellungsdienst installiert haben.</span><span class="sxs-lookup"><span data-stu-id="71f39-147">Before you install the Operations Manager console, make sure that you have installed a supported version of SQL Server along with the SQL Server Reporting Service.</span></span> <span data-ttu-id="71f39-148">Es wird außerdem empfohlen, den Reporting Services-Konfigurations-Manager von SQL Server auszuführen, um zu überprüfen, ob der Berichterstellungsdienst ordnungsgemäß installiert und konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="71f39-148">It is also recommended that you run SQL Server's Reporting Services Configuration Manager to verify that the Reporting Service has been correctly installed and configured.</span></span>

<span data-ttu-id="71f39-149">So installieren Sie die System Center Operations Manager-Konsole:</span><span class="sxs-lookup"><span data-stu-id="71f39-149">To install the System Center Operations Manager console:</span></span>

1.  <span data-ttu-id="71f39-150">Doppelklicken Sie auf den System Center Operations Manager-Setupmedien auf **SetupOM. exe**.</span><span class="sxs-lookup"><span data-stu-id="71f39-150">On the System Center Operations Manager setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="71f39-151">Klicken Sie in System Center Operations Manager 2007 R2-Setup auf **Voraussetzungen überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="71f39-151">In System Center Operations Manager 2007 R2 Setup, click **Check Prerequisites**.</span></span>

3.  <span data-ttu-id="71f39-152">Wählen Sie in der Voraussetzungs Anzeige von System Center Operations Manager die zu installierenden System Center-Komponenten aus: (**Server**; **Konsole**; und **PowerShell**), und klicken Sie dann auf **überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="71f39-152">In the System Center Operations Manager Prerequisite Viewer, select the System Center components to be installed: (**Server**; **Console**; and **PowerShell**) and then click **Check**.</span></span> <span data-ttu-id="71f39-153">Stellen Sie sicher, dass keine Blockierungsprobleme gemeldet wurden, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="71f39-153">Verify that no blocking issues have been reported and then click **Close**.</span></span> <span data-ttu-id="71f39-154">Wenn ein Blockierungsproblem gemeldet wurde, beheben Sie das Problem, und klicken Sie dann auf **überprüfen** , um die erforderlichen Tests erneut auszuführen.</span><span class="sxs-lookup"><span data-stu-id="71f39-154">If a blocking issue has been reported, correct the problem and then click **Check** to re-run the prerequisite testing.</span></span>

4.  <span data-ttu-id="71f39-155">Klicken Sie im System Center Operations Manager-Setup auf **Operations Manager installieren**.</span><span class="sxs-lookup"><span data-stu-id="71f39-155">In System Center Operations Manager Setup, click **Install Operations Manager**.</span></span>

5.  <span data-ttu-id="71f39-156">Klicken Sie im System Center Operations Manager-Setup-Assistenten auf der Seite **Willkommen beim Setup-Assistenten von System Center Operations Manager** auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="71f39-156">In the System Center Operations Manager Setup wizard, on the **Welcome to the System Center Operations Manager Setup Wizard** page, click **Next**.</span></span>

6.  <span data-ttu-id="71f39-157">Wählen Sie auf der Seite **Endbenutzer-Lizenzvertrag** **die Option Ich stimme den Bedingungen des Lizenzvertrags** zu, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="71f39-157">On the **End-User License Agreement** page, select **I accept the terms in the license agreement** and then click **Next**.</span></span>

7.  <span data-ttu-id="71f39-158">Geben Sie auf der Seite **Produktregistrierung** ihren Namen in das Feld **Benutzername** und den Namen Ihrer Organisation in das Feld **Organisation** ein.</span><span class="sxs-lookup"><span data-stu-id="71f39-158">On the **Product Registration** page, type your name in the **User Name** box and name of your organization in the **Organization** box.</span></span> <span data-ttu-id="71f39-159">Geben Sie den Product Key für System Center Operations Manager in das Feld **Geben Sie Ihre 25-stellige CD ein** , und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="71f39-159">Type your System Center Operations Manager product key in the **Enter your 25 digit CD Key** box and then click **Next**.</span></span>

8.  <span data-ttu-id="71f39-160">Wählen Sie auf der Seite **benutzerdefinierte Installation** die System Center-Optionen aus, die installiert werden sollen, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="71f39-160">On the **Custom Setup** page select the System Center options to be installed and then click **Next**.</span></span> <span data-ttu-id="71f39-161">Sie sollten **Verwaltungs Server**, **Benutzeroberflächen**und **Webkonsolen** auswählen, die installiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="71f39-161">You should select **Management Server**, **User Interfaces**, and **Web Console** to be installed.</span></span> <span data-ttu-id="71f39-162">Die **Datenbank** sollte nicht ausgewählt werden und sollte nicht installiert werden.</span><span class="sxs-lookup"><span data-stu-id="71f39-162">**Database** should not be selected and should not be installed.</span></span>

9.  <span data-ttu-id="71f39-163">Stellen Sie auf der Seite **SC-Datenbankserverinstanz** sicher, dass der Name des Computers, auf dem die Operations Manager-Datenbanken installiert sind, im Feld **System Center-Datenbankserver** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="71f39-163">On the **SC Database Server Instance** page, verify that the name of the computer where the Operations Manager databases are installed appears in the **System Center Database Server** box.</span></span> <span data-ttu-id="71f39-164">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="71f39-164">Click **Next**.</span></span>

10. <span data-ttu-id="71f39-165">Wählen Sie auf der Seite **Verwaltungs Server-Aktionskonto** die Option **Domäne oder lokales Computerkonto** aus, und geben Sie dann die entsprechenden Werte in die Felder **Benutzerkonto**, **Kennwort**und **Domäne oder lokaler Computer** ein.</span><span class="sxs-lookup"><span data-stu-id="71f39-165">On the **Management Server Action Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes.</span></span> <span data-ttu-id="71f39-166">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="71f39-166">Click **Next**.</span></span>

11. <span data-ttu-id="71f39-167">Wählen Sie auf der Seite **SDK-und Konfigurationsdienstkonto** die Option **Domäne oder lokales Computerkonto** aus, und geben Sie dann die entsprechenden Werte in die Felder **Benutzerkonto**, **Kennwort**und **Domäne oder lokaler Computer** ein.</span><span class="sxs-lookup"><span data-stu-id="71f39-167">On the **SDK and Config Service Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes.</span></span> <span data-ttu-id="71f39-168">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="71f39-168">Click **Next**.</span></span>

12. <span data-ttu-id="71f39-169">Klicken Sie auf der Seite **Fehlerberichte von Operations Manager** auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="71f39-169">On the **Operations Manager Error Reports** page click **Next**.</span></span>

13. <span data-ttu-id="71f39-170">Klicken Sie auf der Seite **Programm zur Verbesserung der Benutzerfreundlichkeit** auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="71f39-170">On the **Customer Experience Improvement Program** page click **Next**.</span></span>

14. <span data-ttu-id="71f39-171">Klicken Sie auf der Seite **Programm kann** installiert werden auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="71f39-171">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="71f39-172">Deaktivieren Sie auf der Seite **System Center Operations Manager-Setup abschließen** die Kontrollkästchen **Verschlüsselungsschlüssel sichern** und **Konsole starten** , und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="71f39-172">On the **Completing the System Center Operations Manager Setup** page, clear the **Backup Encryption Key** and **Start the console checkboxes** and then click **Finish**.</span></span>

16. <span data-ttu-id="71f39-173">Klicken Sie im System Center Operations Manager-Setup auf **Beenden**.</span><span class="sxs-lookup"><span data-stu-id="71f39-173">In System Center Operations Manager Setup click **Exit**.</span></span>

</div>

<div>

## <a name="installing-system-center-reporting-services"></a><span data-ttu-id="71f39-174">Installieren von System Center Reporting Services</span><span class="sxs-lookup"><span data-stu-id="71f39-174">Installing System Center Reporting Services</span></span>

<span data-ttu-id="71f39-175">Nachdem Sie die System Center Operations Manager-Konsole installiert und konfiguriert haben, müssen Sie System Center Reporting Services installieren.</span><span class="sxs-lookup"><span data-stu-id="71f39-175">After installing and configuring the System Center Operations Manager console you must then install System Center Reporting Services.</span></span> <span data-ttu-id="71f39-176">Wenn Sie SQL Server 2008 R2 als Back-End-Datenbank für Operations Manager verwenden, müssen Sie zunächst eine temporäre Änderung an der Sicherheitsgruppe vornehmen, die SQL Server Reporting Services zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="71f39-176">If you are using SQL Server 2008 R2 as your Operations Manager back-end database, that means that you must first make a temporary change to the security group associated with SQL Server Reporting Services.</span></span> <span data-ttu-id="71f39-177">Wenn Sie SQL Server 2008 R2 verwenden, müssen Sie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="71f39-177">If you are using SQL Server 2008 R2, you must do the following:</span></span>

1.  <span data-ttu-id="71f39-178">Klicken Sie auf **Start**, zeigen Sie auf **Verwaltung**, und klicken Sie dann auf **Server-Manager**.</span><span class="sxs-lookup"><span data-stu-id="71f39-178">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="71f39-179">Erweitern Sie im Server-Manager die Optionen **Konfiguration** und **Lokale Benutzer und Gruppen**, und klicken Sie dann auf **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="71f39-179">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="71f39-180">Suchen Sie die folgende Gruppe, wobei ATL-SC-001 den Namen Ihres Computers darstellt und ARCHINST die SQL Server Instanz für die System Center-Datenbank darstellt: **SQLServerReportServerUser $ ATL-SC-001 $\_MSRS10 50. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="71f39-180">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the System Center database: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

4.  <span data-ttu-id="71f39-181">Klicken Sie mit der rechten Maustaste auf die Gruppe, und klicken Sie dann auf **Umbenennen**.</span><span class="sxs-lookup"><span data-stu-id="71f39-181">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="71f39-182">Benennen Sie die Gruppe um, indem Sie \*\* \_50\*\* aus dem Gruppennamen löschen.</span><span class="sxs-lookup"><span data-stu-id="71f39-182">Rename the group by deleting **\_50** from the group name.</span></span> <span data-ttu-id="71f39-183">Beispiel: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="71f39-183">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

5.  <span data-ttu-id="71f39-184">Schließen Sie den Server-Manager.</span><span class="sxs-lookup"><span data-stu-id="71f39-184">Close Server Manager.</span></span>

<span data-ttu-id="71f39-185">An diesem Punkt sind Sie für die Installation von System Center Reporting Services gerüstet.</span><span class="sxs-lookup"><span data-stu-id="71f39-185">At this point you are ready to install System Center Reporting Services.</span></span> <span data-ttu-id="71f39-186">Gehen Sie hierfür folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="71f39-186">To do this:</span></span>

1.  <span data-ttu-id="71f39-187">Doppelklicken Sie auf dem System Center Operations Manager 2007 R2-Setup Medien auf **SetupOM. exe**.</span><span class="sxs-lookup"><span data-stu-id="71f39-187">On the System Center Operations Manager 2007 R2 Setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="71f39-188">Klicken Sie in System Center Operations Manager 2007 R2-Setup auf **Operations Manager-Berichterstellung installieren**.</span><span class="sxs-lookup"><span data-stu-id="71f39-188">In System Center Operations Manager 2007 R2 Setup, click **Install Operations Manager Reporting**.</span></span>

3.  <span data-ttu-id="71f39-189">Klicken Sie im System Center Operations Manager 2007 R2-Bericht Erstellungs-Assistenten auf der Seite Willkommen bei der **Installation von Operations Manager** auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="71f39-189">In the System Center Operations Manager 2007 R2 Reporting Setup wizard, on the **Welcome to Operations Manager Reporting Setup** page, click **Next**.</span></span>

4.  <span data-ttu-id="71f39-190">Wählen Sie auf der Seite **Endbenutzer-Lizenzvertrag** **die Option Ich stimme den Bedingungen des Lizenzvertrags** zu, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="71f39-190">On the **End-user License Agreement** page select **I accept the terms of the license agreement** and then click **Next**.</span></span>

5.  <span data-ttu-id="71f39-191">Stellen Sie auf der Seite **Produktregistrierung** sicher, dass Ihr Name und der Name Ihrer Organisation in den Feldern **Benutzername** und **Organisation** angezeigt werden, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="71f39-191">On the **Product Registration** page, ensure that your name and the name of your organization appear in the **User Name** and **Organization** boxes and then click **Next**.</span></span>

6.  <span data-ttu-id="71f39-192">Klicken Sie auf der Seite **benutzerdefinierte Installation** auf **Berichts Server** , und wählen Sie **Diese Komponente aus, und alle abhängigen Komponenten werden auf dem lokalen Datenträger installiert**.</span><span class="sxs-lookup"><span data-stu-id="71f39-192">On the **Custom Setup** page, click **Reporting Server** and select **This component, and all dependent components, will be installed on local disk drive**.</span></span> <span data-ttu-id="71f39-193">Klicken Sie auf **Data Warehouse** , und wählen Sie **Diese Komponente ist nicht verfügbar**, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="71f39-193">Click **Data Warehouse** and select **This component will not be available**, and then click **Next**.</span></span>

7.  <span data-ttu-id="71f39-194">Geben Sie auf der Seite mit **dem Stammverwaltungsserver verbinden** den Namen des Operations Manager-Stammverwaltungsservers in das Feld **Stamm Verwaltungs** Server ein, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="71f39-194">On the **Connect to the Root Management Server** page, type the name of your Operations Manager root management server in the **Root Management Server** box and then click **Next**.</span></span>

8.  <span data-ttu-id="71f39-195">Geben Sie auf der Seite **Verbindung mit dem Operations Manager-Data Warehouse herstellen** die SQL Server Instanz ein, in der sich Ihr Data Warehouse im Feld **SQL Server Instanz** befindet.</span><span class="sxs-lookup"><span data-stu-id="71f39-195">On the **Connect to the Operations Manager Data Warehouse** page, type the SQL Server instance where your data warehouse is located in the **SQL Server Instance** box.</span></span> <span data-ttu-id="71f39-196">(Wenn sich Ihr Data Warehouse in der Standardinstanz befindet, geben Sie einfach den Servernamen ein; Beispiel: ATL-SQL-001.) Stellen Sie sicher, dass der Datenbankname **OperationsManagerDW** im Feld **Name** angezeigt wird und dass Port **1433** im Feld **SQL Server Port** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="71f39-196">(If your data warehouse is located in the Default instance then simply type the server name; for example: atl-sql-001.) Verify that the database name **OperationsManagerDW** appears in the **Name** box, and that port **1433** appears in the **SQL Server port** box.</span></span> <span data-ttu-id="71f39-197">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="71f39-197">Click **Next**.</span></span>

9.  <span data-ttu-id="71f39-198">Wählen Sie auf der Seite **SQL Server Berichtsinstanz** Ihren SQL Server Berichts Server aus der Dropdownliste **Geben Sie den SQL Server Reporting Services-Server ein** , und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="71f39-198">On the **SQL Server Reporting Instance** page, select your SQL Server reporting server from the **Enter the SQL Server Reporting Services Server** dropdown list and then click **Next**.</span></span>

10. <span data-ttu-id="71f39-199">Geben Sie auf der Seite **Data Warehouse-Schreib Konto** den Namen und das Kennwort des Benutzers ein, dem zunächst Schreibberechtigungen für das Data Warehouse in den Feldern **Benutzerkonto** und **Kennwort** zugewiesen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="71f39-199">On the **Data Warehouse Write Account** page, enter the name and password of the user to be initially assigned write permissions to the data warehouse in the **User Account** and **Password** boxes.</span></span> <span data-ttu-id="71f39-200">Wählen Sie in der Dropdownliste **Domäne** die Domäne des Benutzers aus, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="71f39-200">Select the user's domain from the **Domain** dropdown list and then click **Next**.</span></span>

11. <span data-ttu-id="71f39-201">Geben Sie auf der Seite **Datenleser Konto** den Namen und das Kennwort des Benutzerkontos ein, das verwendet werden soll, wenn SQL Reporting Services das Data Warehouse in den Feldern **Benutzerkonto** und **Kennwort** fragt.</span><span class="sxs-lookup"><span data-stu-id="71f39-201">On the **Data Reader Account** page, enter the name and password of the user account to be used when SQL Reporting Services queries the data warehouse in the **User Account** and **Password** boxes.</span></span> <span data-ttu-id="71f39-202">Wählen Sie in der Dropdownliste **Domäne** die Kontodomäne aus, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="71f39-202">Select the account domain from the **Domain** dropdown list and then click **Next**.</span></span>

12. <span data-ttu-id="71f39-203">Klicken Sie auf der Seite **operative Daten Berichte** auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="71f39-203">On the **Operational Data Reports** page, click **Next**.</span></span>

13. <span data-ttu-id="71f39-204">Klicken Sie auf der Seite **Microsoft Update** auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="71f39-204">On the **Microsoft Update** page, click **Next**.</span></span>

14. <span data-ttu-id="71f39-205">Klicken Sie auf der Seite **Programm kann** installiert werden auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="71f39-205">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="71f39-206">Klicken Sie auf der Seite zum **abschließen des Setup-Assistenten für die Operations Manager-Berichtskomponenten** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="71f39-206">On the **Completing the Operations Manager Reporting Components Setup Wizard** page, click **Finish**.</span></span>

16. <span data-ttu-id="71f39-207">Klicken Sie in System Center Operations Manager 2007 R2-Setup auf **Beenden**.</span><span class="sxs-lookup"><span data-stu-id="71f39-207">In System Center Operations Manager 2007 R2 Setup, click **Exit**.</span></span>

<span data-ttu-id="71f39-208">Nachdem Sie die System Center-Berichterstellung installiert haben, verwenden Sie das folgende Verfahren, um den Namen der Sicherheitsgruppe zurückzusetzen, die SQL Server Berichterstellung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="71f39-208">After System Center reporting has been installed you then use the following procedure to reset the name of the security group associated with SQL Server reporting.</span></span> <span data-ttu-id="71f39-209">Dieses Verfahren ist wiederum nur erforderlich, wenn Sie SQL Server verwenden:</span><span class="sxs-lookup"><span data-stu-id="71f39-209">Again, this procedure is only required if you are using SQL Server:</span></span>

1.  <span data-ttu-id="71f39-210">Klicken Sie auf **Start**, zeigen Sie auf **Verwaltung**, und klicken Sie dann auf **Server-Manager**.</span><span class="sxs-lookup"><span data-stu-id="71f39-210">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="71f39-211">Erweitern Sie im Server-Manager die Optionen **Konfiguration** und **Lokale Benutzer und Gruppen**, und klicken Sie dann auf **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="71f39-211">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="71f39-212">Suchen Sie die folgende Gruppe, wobei ATL-SC-001 den Namen Ihres Computers darstellt und ARCHINST die SQL Server Instanz für die Archivierungs-und Überwachungsdatenbanken darstellt: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="71f39-212">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the archiving and monitoring databases: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

4.  <span data-ttu-id="71f39-213">Klicken Sie mit der rechten Maustaste auf die Gruppe, und klicken Sie dann auf **Umbenennen**.</span><span class="sxs-lookup"><span data-stu-id="71f39-213">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="71f39-214">Benennen Sie die Gruppe um, indem Sie \*\* \_50\*\* an das Ende des Gruppennamens, direkt vor dem Namen der SQL Server Instanz, hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="71f39-214">Rename the group by adding **\_50** to the end of the group name, right before the SQL Server instance name.</span></span> <span data-ttu-id="71f39-215">Beispiel: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10\_50. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="71f39-215">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

5.  <span data-ttu-id="71f39-216">Schließen Sie den Server-Manager.</span><span class="sxs-lookup"><span data-stu-id="71f39-216">Close Server Manager.</span></span>

<span data-ttu-id="71f39-217">Wenn die System Center-Betriebskonsole geöffnet ist, müssen Sie die Anwendung schließen und neu starten. Wenn Sie dies nicht tun, wird die Registerkarte " **Berichterstellung** " nicht auf der Benutzeroberfläche der Betriebskonsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="71f39-217">If the System Center Operations Console is open you will need to close the application and then restart it; if you do not do this the **Reporting** tab will not appear in the Operations Console user interface.</span></span> <span data-ttu-id="71f39-218">Beachten Sie, dass es nach dem ersten Neustart der Betriebskonsole einige Minuten dauern kann, bis alle Überwachungsberichte auf der Registerkarte " **Berichterstellung** " angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="71f39-218">Note that, after restarting the Operations Console the first time, it could take several minutes before all the Monitoring Reports appear on the **Reporting** tab.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

