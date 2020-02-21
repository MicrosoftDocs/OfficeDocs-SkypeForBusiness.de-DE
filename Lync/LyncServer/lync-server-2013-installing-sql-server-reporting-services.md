---
title: 'Lync Server 2013: Installieren von SQL Server Reporting Services'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing SQL Server Reporting Services
ms:assetid: 638a1d0c-1ac7-4735-83f2-4df3d03c7cf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204957(v=OCS.15)
ms:contentKeyID: 48184345
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0448802e7de2c00b5c57730c5e95fb99b21b237e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-sql-server-reporting-services-in-lync-server-2013"></a><span data-ttu-id="37bd1-102">Installieren von SQL Server Reporting Services in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37bd1-102">Installing SQL Server Reporting Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37bd1-103">_**Letztes Änderungsstand des Themas:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="37bd1-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="37bd1-104">Wenn Sie Microsoft lync Server 2013-Überwachungsberichte verwenden möchten (Weitere Informationen finden Sie im nächsten Abschnitt dieser Dokumentation), müssen Sie zuerst SQL Server Reporting Services installieren; Reporting Services kann gleichzeitig installiert werden, wenn Sie Microsoft SQL Server oder nach der Installation von SQL Server zu einem beliebigen Zeitpunkt installieren.</span><span class="sxs-lookup"><span data-stu-id="37bd1-104">If you intend to use Microsoft Lync Server 2013 Monitoring Reports (see the next section of this documentation for more information) you must first install SQL Server Reporting Services; Reporting Services can be installed at the same time you install Microsoft SQL Server or any time after SQL Server has been installed.</span></span> <span data-ttu-id="37bd1-105">Wenn Sie SQL Server nicht installiert haben, befolgen Sie die weiter oben in dieser Dokumentation beschriebenen Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="37bd1-105">If you have not installed SQL Server, then follow the instructions provided earlier in this documentation.</span></span> <span data-ttu-id="37bd1-106">Achten Sie beim Installieren von SQL Server darauf, dass Sie auf der Seite Featureauswahl die Option Reporting Services auswählen.</span><span class="sxs-lookup"><span data-stu-id="37bd1-106">When installing SQL Server, make sure that, on the Feature Selection page, you select Reporting Services.</span></span> <span data-ttu-id="37bd1-107">Damit wird SQL Server Reporting Services installiert.</span><span class="sxs-lookup"><span data-stu-id="37bd1-107">That will install SQL Server Reporting Services.</span></span>

<span data-ttu-id="37bd1-108">Wenn Sie SQL Server ohne SQL Server Reporting Services installiert haben, können Sie dieses Feature gemäß der entsprechenden Vorgehensweise für SQL Server 2008 R2 bzw. SQL Server 2012 installieren.</span><span class="sxs-lookup"><span data-stu-id="37bd1-108">If you have already installed SQL Server but did not install SQL Server Reporting Services you can add that feature by following the appropriate set of instructions for SQL Server 2008 R2 or SQL Server 2012, as appropriate.</span></span>

<span data-ttu-id="37bd1-109">Wenn Sie überprüfen möchten, ob die Reporting Services ordnungsgemäß installiert sind, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="37bd1-109">To verify that the reporting Services have been successfully installed, complete the following steps:</span></span>

1.  <span data-ttu-id="37bd1-110">Wenn bei Ihnen Microsoft SQL Server 2008 R2 ausgeführt wird, klicken Sie auf **Start**, **Alle Programme**, **Microsoft SQL Server 2008 R2**, **Konfigurationstools**, und klicken Sie dann auf **Konfigurations-Manager für Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="37bd1-110">If you are running Microsoft SQL Server 2008 R2, then click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>
    
    <span data-ttu-id="37bd1-111">Bei Microsoft SQL Server 2012 klicken Sie auf **Start**, **Alle Programme**, **Microsoft SQL Server 2012**, **Konfigurationstools**, und klicken Sie dann auf **Konfigurations-Manager für Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="37bd1-111">If you are running Microsoft SQL Server 2012, then click **Start**, click **All Programs**, click **Microsoft SQL Server 2012**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>

2.  <span data-ttu-id="37bd1-p102">Überprüfen Sie im Dialogfeld **Konfigurationsverbindung für Reporting Services**, ob im Feld **Servername** der Name Ihres Servers und im Feld **Berichtsserverinstanz** der Name der SQL Server-Instanz, die Ihre Überwachungsdaten speichert, angezeigt werden. Klicken Sie auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="37bd1-p102">In the **Reporting Services Configuration Connection** dialog box, verify that the name of your server appears in the **Server Name** box and that the name of the SQL Server instance that stores your monitoring data appears in the **Report Server Instance** box. Click **Connect**.</span></span>

<span data-ttu-id="37bd1-114">Im Konfigurations-Manager für den Berichtsdienst sollte im Bereich Berichtsserverstatus angezeigt werden, dass SQL Server Reporting Services installiert wurde und dass die Reporting Services derzeit ausgeführt werden: der Status des Berichtsservers sollte als **gestartet** angezeigt werden, und die Schaltfläche **Start** sollte abgeblendet sein und nicht verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="37bd1-114">In the Reporting Service Configuration Manager, the Report Server Status pane should show that SQL Server Reporting Services has been installed and that the Reporting Services are currently running: the Report Server Status should be shown as **Started** and the **Start** button should be grayed-out and unavailable.</span></span> <span data-ttu-id="37bd1-115">Wenn der Berichterstellungsdienst nicht ausgeführt wird, klicken Sie auf **Start**, um den Dienst zu starten.</span><span class="sxs-lookup"><span data-stu-id="37bd1-115">If the Reporting Service is not running, click **Start** in order to start the service.</span></span>

<span data-ttu-id="37bd1-116">Wenn neben "Berichtsserver-Datenbankname" keine Datenbank aufgeführt ist, führen Sie Folgendes durch:</span><span class="sxs-lookup"><span data-stu-id="37bd1-116">If no database is listed next to the Report Server Database Name label then do the following:</span></span>

1.  <span data-ttu-id="37bd1-117">Klicken Sie im Konfigurations-Manager für Reporting Services auf **Datenbank**.</span><span class="sxs-lookup"><span data-stu-id="37bd1-117">In the Reporting Services Configuration Manager click **Database**.</span></span>

2.  <span data-ttu-id="37bd1-118">Klicken Sie im Bereich "Berichtsserver-Datenbank" auf **Datenbank ändern**.</span><span class="sxs-lookup"><span data-stu-id="37bd1-118">In the Report Server Database pane click **Change Database**.</span></span>

3.  <span data-ttu-id="37bd1-119">Aktivieren Sie im Assistenten zum Konfigurieren der Berichtsserver-Datenbank im Bereich "Aktion" den Punkt **Neue Berichtsserver-Datenbank erstellen**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="37bd1-119">In the Report Server Database Configuration wizard, in the Action pane, select **Create a new report server database** and then click **Next**.</span></span>

4.  <span data-ttu-id="37bd1-p104">Überprüfen Sie im Bereich "Datenbankserver", ob die Angaben in den Feldern **Servername**, **Authentifizierungstyp** und **Benutzername** korrekt sind. Klicken Sie auf **Verbindung testen**, um zu überprüfen, ob eine Verbindung zu dem Datenbankserver hergestellt werden kann, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="37bd1-p104">In the Report Server Database Configuration wizard, in the Database Server pane, verify that the information listed in the **Server Name**, **Authentication Type**, and **Username** boxes is correct. Click **Test Connection** to verify that a connection can be made to the database server and then click **Next**.</span></span>

5.  <span data-ttu-id="37bd1-122">Akzeptieren Sie im Bereich "Datenbank" die Standardwerte für **Datenbankname**, **Sprache** und **Berichtsservermodus**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="37bd1-122">In the Report Server Database Configuration wizard, in the Database pane, accept the default values for **Database Name**, **Language**, and **Report Server Mode** and then click **Next**.</span></span>

6.  <span data-ttu-id="37bd1-123">Überprüfen Sie, ob im Bereich "Anmeldeinformationen" in der Dropdownliste **Authentifizierungstyp** und in den Feldern **Benutzername** und **Kennwort** die korrekten Informationen aufgeführt sind, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="37bd1-123">In the Report Server Database Configuration wizard, in the Credentials pane, verify that the correct information is listed in the **Authentication Type** dropdown list and the **User name** and **Password** boxes, and then click **Next**.</span></span>

7.  <span data-ttu-id="37bd1-124">Klicken Sie im Bereich "Zusammenfassung" auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="37bd1-124">In the Report Server Database Configuration wizard, in the Summary pane, click **Next**.</span></span>

8.  <span data-ttu-id="37bd1-125">Klicken Sie im Bereich "Fortsetzen und Fertigstellen" auf **Fertigstellen**.</span><span class="sxs-lookup"><span data-stu-id="37bd1-125">In the Report Server Database Configuration wizard, in the Progress and Finish pane, click **Finish**.</span></span>

<span data-ttu-id="37bd1-p105">Klicken Sie auf **Webdienst-URL**, um zu überprüfen, ob die Berichtsdienst-URLs konfiguriert sind. Unter **URLs für Berichtsserver-Webdienst** sollte mindestens eine URL aufgeführt sein. Klicken Sie auf die einzelnen URLs, um zu überprüfen, ob Sie damit die Startseite für die lokale Installation von SQL Server Reporting Services erreichen.</span><span class="sxs-lookup"><span data-stu-id="37bd1-p105">To verify that the Reporting Service URLs have been configured, click **Web Service URL**. You should see one or more URLs listed under the heading **Report Server Web Service URLs**. Click each of these URLs to verify that you can reach the home page for the local installation of SQL Server Reporting Services.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

