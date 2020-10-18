---
title: 'Lync Server 2013: Wiederherstellen von Überwachungs-oder Archivierungsdaten'
description: 'Lync Server 2013: Wiederherstellen von Überwachungs-oder Archivierungsdaten.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring monitoring or archiving data
ms:assetid: 60118526-13bb-4b03-803e-6ffae219d436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202175(v=OCS.15)
ms:contentKeyID: 51541483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 169a5da2d606b97c7cd3f59d6cbae3d4c584e6e7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575515"
---
# <a name="restoring-monitoring-or-archiving-data-in-lync-server-2013"></a><span data-ttu-id="142f1-103">Wiederherstellen von Überwachungs-oder Archivierungsdaten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="142f1-103">Restoring monitoring or archiving data in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="142f1-104">_**Letztes Änderungsstand des Themas:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="142f1-104">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="142f1-105">Das Wiederherstellen von Überwachungs-und Archivierungsdaten ist nicht erforderlich, um nach einem Ausfall lync Server aufzunehmen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="142f1-105">Restoring monitoring and archiving data is not required to get Lync Server up and running after a failure.</span></span> <span data-ttu-id="142f1-106">Wenn Überwachungs-und Archivierungsdaten jedoch für Ihre Organisation wichtig sind, sollten Sie die Daten wiederherstellen, nachdem Sie die Datenbanken neu erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="142f1-106">However, if monitoring and archiving data is critical to your organization, you will want to restore the data after you re-create the databases.</span></span>

<span data-ttu-id="142f1-107">Im folgenden Verfahren wird die Verwendung von SQL Server Management Studio zum Wiederherstellen von Archivierungs-oder Überwachungsdaten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="142f1-107">The following procedure describes how to use SQL Server Management Studio to restore archiving or monitoring data.</span></span>

<div>

## <a name="to-restore-monitoring-or-archiving-data-from-a-backup-file"></a><span data-ttu-id="142f1-108">So stellen Sie Überwachungs-oder Archivierungsdaten aus einer Sicherungsdatei wieder her</span><span class="sxs-lookup"><span data-stu-id="142f1-108">To restore monitoring or archiving data from a backup file</span></span>

1.  <span data-ttu-id="142f1-109">Melden Sie sich bei dem Server an, den Sie als Mitglied der Gruppe Administratoren auf dem lokalen Computer oder einer Gruppe mit gleichwertigen Benutzerrechten wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="142f1-109">Log on to the server that you are restoring as a member of the Administrators group on the local computer or a group with equivalent user rights.</span></span>

2.  <span data-ttu-id="142f1-110">Öffnen Sie SQL Server Management Studio: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft SQL Server 2012** oder **Microsoft SQL Server 2008 R2**, und klicken Sie dann auf **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="142f1-110">Open SQL Server Management Studio: click **Start**, click **All Programs**, click **Microsoft SQL Server 2012** or **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>

3.  <span data-ttu-id="142f1-111">Stellen Sie unter **Verbindung mit Server herstellen**eine Verbindung mit der SQL Server Instanz her, indem Sie mindestens den Namen des Servers und die Authentifizierungsinformationen angeben.</span><span class="sxs-lookup"><span data-stu-id="142f1-111">In **Connect to Server**, connect to the SQL Server instance by providing at least the name of the server and the authentication information.</span></span>

4.  <span data-ttu-id="142f1-112">Klicken Sie im **Objekt-Explorer**mit der rechten Maustaste auf **Datenbanken**, und klicken Sie dann auf **Datenbank wiederherstellen**.</span><span class="sxs-lookup"><span data-stu-id="142f1-112">In **Object Explorer**, right-click **Databases**, and then click **Restore Database**.</span></span>

5.  <span data-ttu-id="142f1-113">Klicken Sie unter **Seite auswählen**auf **Allgemein**, und wählen Sie dann in **Datenbank** den Datenbanknamen wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="142f1-113">Under **Select a page**, click **General**, and then in **To database** select the database name as follows:</span></span>
    
      - <span data-ttu-id="142f1-114">Wählen Sie für ein Archivierungsdatenbank die Option **LcsLog**aus.</span><span class="sxs-lookup"><span data-stu-id="142f1-114">For an Archiving database, select **LcsLog**.</span></span>
    
      - <span data-ttu-id="142f1-115">Wählen Sie für eine KDS-Datenbank (Call Detail Recording) die Option **LcsCDR**aus.</span><span class="sxs-lookup"><span data-stu-id="142f1-115">For a call detail recording (CDR) database, select **LcsCDR**.</span></span>
    
      - <span data-ttu-id="142f1-116">Wählen Sie für eine QoE-Datenbank (Quality of Experience) die Option **QoEMetrics**aus.</span><span class="sxs-lookup"><span data-stu-id="142f1-116">For a Quality of Experience (QoE) database, select **QoEMetrics**.</span></span>

6.  <span data-ttu-id="142f1-117">Klicken Sie auf **von Gerät**.</span><span class="sxs-lookup"><span data-stu-id="142f1-117">Click **From device**.</span></span>

7.  <span data-ttu-id="142f1-118">Klicken Sie unter **Wählen Sie die wiederherzustellenden Sicherungssätze aus**auf die Sicherungsdatei, und klicken Sie dann auf **Wiederherstellen**.</span><span class="sxs-lookup"><span data-stu-id="142f1-118">Under **Select the backup sets to restore**, click the backup file, and then click **Restore**.</span></span>

8.  <span data-ttu-id="142f1-119">Klicken Sie unter **Seite auswählen**auf **Optionen**, stellen Sie sicher, dass sich der Pfad und der Protokollpfad der Datendatei im richtigen Ordner befinden, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="142f1-119">Under **Select a page**, click **Options**, verify that the data file path and log path are in the correct folder, and then click **OK**.</span></span>

</div>

<div>

## <a name="to-make-sure-that-access-control-lists-acls-are-correct"></a><span data-ttu-id="142f1-120">So stellen Sie sicher, dass Zugriffssteuerungslisten (Access Control Lists, ACLs) korrekt sind</span><span class="sxs-lookup"><span data-stu-id="142f1-120">To make sure that access control lists (ACLs) are correct</span></span>

1.  <span data-ttu-id="142f1-121">Erweitern Sie **Datenbanken**, erweitern Sie die Datenbank Archivierung oder Überwachung, erweitern Sie **Sicherheit**, und erweitern Sie dann **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="142f1-121">Expand **Databases**, expand the archiving or monitoring database, expand **Security**, and then expand **Users**.</span></span>

2.  <span data-ttu-id="142f1-122">Stellen Sie sicher, dass die Domänengruppe RTCComponentUniversalServices als Benutzer vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="142f1-122">Verify that the domain group RTCComponentUniversalServices exists as a user.</span></span>

3.  <span data-ttu-id="142f1-123">Wenn RTCComponentUniversalServices unter **Benutzer**nicht vorhanden ist, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="142f1-123">If RTCComponentUniversalServices does not exist under **Users**, do the following:</span></span>
    
    1.  <span data-ttu-id="142f1-124">Klicken Sie mit der rechten Maustaste auf **Benutzer**, und klicken Sie anschließend auf **Neuer Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="142f1-124">Right-click **Users**, and then click **New User**.</span></span>
    
    2.  <span data-ttu-id="142f1-125">Geben Sie unter **Anmeldename**den fehlenden Gruppennamen RTCComponentUniversalServices.</span><span class="sxs-lookup"><span data-stu-id="142f1-125">In **Login name**, type the missing group name, RTCComponentUniversalServices.</span></span>
    
    3.  <span data-ttu-id="142f1-126">Wählen Sie unter **Mitgliedschaft in Datenbankrollen**die Berechtigung **serverRole** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="142f1-126">Under **Database role membership**, select the **ServerRole** permission, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="142f1-127">Sie müssen den Archivierungs-oder Überwachungsdienst nicht neu starten.</span><span class="sxs-lookup"><span data-stu-id="142f1-127">You do not need to restart the archiving or monitoring service.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

