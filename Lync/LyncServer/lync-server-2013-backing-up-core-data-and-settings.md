---
title: 'Lync Server 2013: Sichern von Hauptdaten und-Einstellungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up core data and settings
ms:assetid: 278bc95a-7b8d-4e01-a872-a844830459de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202170(v=OCS.15)
ms:contentKeyID: 51541452
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4523dcaaee5931e6bf4df9dd79c09ec92636ec31
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150456"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backing-up-core-data-and-settings-in-lync-server-2013"></a><span data-ttu-id="a3bfe-102">Sichern von Hauptdaten und-Einstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3bfe-102">Backing up core data and settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3bfe-103">_**Letztes Änderungsstand des Themas:** 2014-04-23_</span><span class="sxs-lookup"><span data-stu-id="a3bfe-103">_**Topic Last Modified:** 2014-04-23_</span></span>

<span data-ttu-id="a3bfe-104">In den folgenden Verfahren werden lync Server-Verwaltungsshell-Cmdlets zum Erstellen von Sicherungsdateien für Einstellungen und Daten für Hauptdienste verwendet.</span><span class="sxs-lookup"><span data-stu-id="a3bfe-104">The following procedures use Lync Server Management Shell cmdlets to create backup files for settings and data for core services.</span></span> <span data-ttu-id="a3bfe-105">Ausführliche Informationen zu den in diesem Abschnitt verwendeten Tools, einschließlich der Stelle, an der Sie sich befinden, finden Sie unter [Sicherungs-und Wiederherstellungsanforderungen in lync Server 2013: Tools and Permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="a3bfe-105">For details about the tools used in this section, including where they are located, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span> <span data-ttu-id="a3bfe-106">Ausführliche Informationen zum Sichern von Archivierungs-und Überwachungsdaten finden Sie unter [Sichern von Archivierungs-und Überwachungsdatenbanken in lync Server 2013](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).</span><span class="sxs-lookup"><span data-stu-id="a3bfe-106">For details about backing up Archiving and Monitoring data, see [Backing up Archiving and Monitoring databases in Lync Server 2013](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a3bfe-107">Der Schritt in diesem Abschnitt zum Sichern des zentralen Verwaltungsspeichers umfasst die Einstellungen und die Konfiguration für die Archivierung und Überwachung.</span><span class="sxs-lookup"><span data-stu-id="a3bfe-107">The step in this section to back up the Central Management store includes the settings and configuration for Archiving and Monitoring.</span></span>



</div>

<span data-ttu-id="a3bfe-108">Sie können die in diesem Abschnitt beschriebenen Cmdlets lokale oder remote ausführen.</span><span class="sxs-lookup"><span data-stu-id="a3bfe-108">You can run the cmdlets described in this section locally or remotely.</span></span>

<div>

## <a name="to-back-up-core-data-and-settings"></a><span data-ttu-id="a3bfe-109">So sichern Sie wichtige Daten und Einstellungen</span><span class="sxs-lookup"><span data-stu-id="a3bfe-109">To back up core data and settings</span></span>

1.  <span data-ttu-id="a3bfe-110">Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="a3bfe-110">From a user account that is a member of the RTCUniversalServerAdmins group, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a3bfe-111">Zum Speichern der Sicherungen, die Sie in den folgenden Schritten erstellen, legen Sie einen neuen freigegebenen Ordner an und aktualisieren Sie den Pfad, der von **$Backup** referenziert wid, auf den neuen freigegebenen Ordner.</span><span class="sxs-lookup"><span data-stu-id="a3bfe-111">To store the backups you create in the following steps, create a new shared folder and update the path referenced by **$Backup** to the new shared folder.</span></span>

3.  <span data-ttu-id="a3bfe-112">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="a3bfe-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="a3bfe-113">Sichern Sie die Konfigurationsdatei des zentralen Verwaltungsspeichers.</span><span class="sxs-lookup"><span data-stu-id="a3bfe-113">Back up the Central Management store configuration file.</span></span> <span data-ttu-id="a3bfe-114">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a3bfe-114">At the command line, type the following:</span></span>
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    <span data-ttu-id="a3bfe-115">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a3bfe-115">For example:</span></span>
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a3bfe-116">In diesem Schritt werden die lync Server Topologie, die Richtlinien und Konfigurationseinstellungen in eine Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="a3bfe-116">This step exports your Lync Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="a3bfe-117">Weitere Schritte sind zum Sichern der Topologiedaten nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a3bfe-117">No other step is required to backup topology data.</span></span>

    
    </div>

5.  <span data-ttu-id="a3bfe-118">Kopieren Sie die gesicherte Konfigurationsdatei des zentralen Verwaltungsspeichers in $Backup\\.</span><span class="sxs-lookup"><span data-stu-id="a3bfe-118">Copy the backed-up Central Management store configuration file to $Backup\\.</span></span>

6.  <span data-ttu-id="a3bfe-p104">Sichern Sie die Standortinformationsdienst-Daten. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a3bfe-p104">Back up Location Information service data. At the command line, type the following:</span></span>
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    <span data-ttu-id="a3bfe-121">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a3bfe-121">For example:</span></span>
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  <span data-ttu-id="a3bfe-122">Kopieren Sie die gesicherte Standortinformationsdienst Konfigurationsdatei in $Backup\\.</span><span class="sxs-lookup"><span data-stu-id="a3bfe-122">Copy the backed-up Location Information service configuration file to $Backup\\.</span></span>

8.  <span data-ttu-id="a3bfe-123">Sichern von Benutzerdaten in jeder Back-End-Datenbank eines Front-End-Pool und jeder Standard Edition-Server.</span><span class="sxs-lookup"><span data-stu-id="a3bfe-123">Back up user data on every back-end database of a Front End pool and every Standard Edition server.</span></span> <span data-ttu-id="a3bfe-124">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a3bfe-124">At the command line, type the following:</span></span>
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    <span data-ttu-id="a3bfe-125">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a3bfe-125">For example:</span></span>
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  <span data-ttu-id="a3bfe-126">Kopieren Sie die gesicherte Benutzerdatei in $Backup\\.</span><span class="sxs-lookup"><span data-stu-id="a3bfe-126">Copy the backed up user file to $Backup\\.</span></span>

10. <span data-ttu-id="a3bfe-127">Sichern Sie in jedem Pool, der das Reaktionsgruppenanwendung ausführt, die Konfiguration der Reaktionsgruppe.</span><span class="sxs-lookup"><span data-stu-id="a3bfe-127">On every pool that runs the Response Group application, back up the Response Group configuration.</span></span> <span data-ttu-id="a3bfe-128">Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="a3bfe-128">Do the following:</span></span>
    
    1.  <span data-ttu-id="a3bfe-129">Geben Sie in die Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a3bfe-129">At the command line, type:</span></span>
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        <span data-ttu-id="a3bfe-130">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a3bfe-130">For example:</span></span>
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. <span data-ttu-id="a3bfe-131">Kopieren Sie die gesicherte Antwortgruppen-Konfigurationsdatei in $Backup\\.</span><span class="sxs-lookup"><span data-stu-id="a3bfe-131">Copy the backed up Response Group configuration file to $Backup\\.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

