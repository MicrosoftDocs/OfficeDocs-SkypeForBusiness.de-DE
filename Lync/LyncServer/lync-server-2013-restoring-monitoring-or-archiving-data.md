---
title: 'Lync Server 2013: Wiederherstellen von Überwachungs-oder Archivierungsdaten'
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
ms.openlocfilehash: 9621fe3c1905dbd34fd3b4da39b2562c608d6355
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733165"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-monitoring-or-archiving-data-in-lync-server-2013"></a><span data-ttu-id="edaa2-102">Wiederherstellen von Überwachungs-oder Archivierungsdaten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="edaa2-102">Restoring monitoring or archiving data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="edaa2-103">_**Letztes Änderungsdatum des Themas:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="edaa2-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="edaa2-104">Das Wiederherstellen von Überwachungs-und Archivierungsdaten ist nicht erforderlich, um den lync-Server nach einem Fehler in Betrieb zu nehmen.</span><span class="sxs-lookup"><span data-stu-id="edaa2-104">Restoring monitoring and archiving data is not required to get Lync Server up and running after a failure.</span></span> <span data-ttu-id="edaa2-105">Wenn die Überwachung und Archivierung von Daten jedoch für Ihre Organisation von entscheidender Bedeutung ist, möchten Sie die Daten nach dem erneuten Erstellen der Datenbanken wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="edaa2-105">However, if monitoring and archiving data is critical to your organization, you will want to restore the data after you re-create the databases.</span></span>

<span data-ttu-id="edaa2-106">Im folgenden Verfahren wird beschrieben, wie Sie mithilfe von SQL Server Management Studio Archivierungs-oder Überwachungsdaten wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="edaa2-106">The following procedure describes how to use SQL Server Management Studio to restore archiving or monitoring data.</span></span>

<div>

## <a name="to-restore-monitoring-or-archiving-data-from-a-backup-file"></a><span data-ttu-id="edaa2-107">So stellen Sie die Überwachung oder Archivierung von Daten aus einer Sicherungsdatei wieder her</span><span class="sxs-lookup"><span data-stu-id="edaa2-107">To restore monitoring or archiving data from a backup file</span></span>

1.  <span data-ttu-id="edaa2-108">Melden Sie sich bei dem Server an, den Sie als Mitglied der Gruppe Administratoren auf dem lokalen Computer oder einer Gruppe mit entsprechenden Benutzerrechten wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="edaa2-108">Log on to the server that you are restoring as a member of the Administrators group on the local computer or a group with equivalent user rights.</span></span>

2.  <span data-ttu-id="edaa2-109">Öffnen Sie SQL Server Management Studio: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft SQL Server 2012** oder **Microsoft SQL Server 2008 R2**, und klicken Sie dann auf **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="edaa2-109">Open SQL Server Management Studio: click **Start**, click **All Programs**, click **Microsoft SQL Server 2012** or **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>

3.  <span data-ttu-id="edaa2-110">Stellen Sie unter **Herstellen einer Verbindung**mit dem Server eine Verbindung mit der SQL Server-Instanz her, indem Sie mindestens den Namen des Servers und die Authentifizierungsinformationen angeben.</span><span class="sxs-lookup"><span data-stu-id="edaa2-110">In **Connect to Server**, connect to the SQL Server instance by providing at least the name of the server and the authentication information.</span></span>

4.  <span data-ttu-id="edaa2-111">Klicken Sie im **Objekt-Explorer**mit der rechten Maustaste auf **Datenbanken**, und klicken Sie dann auf **Datenbank wiederherstellen**.</span><span class="sxs-lookup"><span data-stu-id="edaa2-111">In **Object Explorer**, right-click **Databases**, and then click **Restore Database**.</span></span>

5.  <span data-ttu-id="edaa2-112">Klicken Sie unter **Seite auswählen**auf **Allgemein**, und wählen Sie dann in **zur Datenbank** den Datenbanknamen wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="edaa2-112">Under **Select a page**, click **General**, and then in **To database** select the database name as follows:</span></span>
    
      - <span data-ttu-id="edaa2-113">Wählen Sie für eine Archivierungsdatenbank **LcsLog**aus.</span><span class="sxs-lookup"><span data-stu-id="edaa2-113">For an Archiving database, select **LcsLog**.</span></span>
    
      - <span data-ttu-id="edaa2-114">Wählen Sie für eine CDR-Datenbank (Call Detail Recording) **LcsCDR**aus.</span><span class="sxs-lookup"><span data-stu-id="edaa2-114">For a call detail recording (CDR) database, select **LcsCDR**.</span></span>
    
      - <span data-ttu-id="edaa2-115">Wählen Sie für eine QoE-Datenbank (Quality of Experience) **Datenbank QoEMetrics werden**aus.</span><span class="sxs-lookup"><span data-stu-id="edaa2-115">For a Quality of Experience (QoE) database, select **QoEMetrics**.</span></span>

6.  <span data-ttu-id="edaa2-116">Klicken Sie auf **vom Gerät**.</span><span class="sxs-lookup"><span data-stu-id="edaa2-116">Click **From device**.</span></span>

7.  <span data-ttu-id="edaa2-117">Klicken Sie unter **Wählen Sie die wieder**herzustellenden Sicherungssätze auf die Sicherungsdatei, und klicken Sie dann auf **Wiederherstellen**.</span><span class="sxs-lookup"><span data-stu-id="edaa2-117">Under **Select the backup sets to restore**, click the backup file, and then click **Restore**.</span></span>

8.  <span data-ttu-id="edaa2-118">Klicken Sie unter **Seite auswählen**auf **Optionen**, stellen Sie sicher, dass sich der Datendateipfad und der Protokollpfad im richtigen Ordner befinden, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="edaa2-118">Under **Select a page**, click **Options**, verify that the data file path and log path are in the correct folder, and then click **OK**.</span></span>

</div>

<div>

## <a name="to-make-sure-that-access-control-lists-acls-are-correct"></a><span data-ttu-id="edaa2-119">So stellen Sie sicher, dass Zugriffssteuerungslisten (ACLs) korrekt sind</span><span class="sxs-lookup"><span data-stu-id="edaa2-119">To make sure that access control lists (ACLs) are correct</span></span>

1.  <span data-ttu-id="edaa2-120">Erweitern Sie **Datenbanken**, erweitern Sie die Datenbank Archivierung oder Überwachung, erweitern Sie **Sicherheit**, und erweitern Sie dann **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="edaa2-120">Expand **Databases**, expand the archiving or monitoring database, expand **Security**, and then expand **Users**.</span></span>

2.  <span data-ttu-id="edaa2-121">Überprüfen Sie, ob die RTCComponentUniversalServices der Domänengruppe als Benutzer vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="edaa2-121">Verify that the domain group RTCComponentUniversalServices exists as a user.</span></span>

3.  <span data-ttu-id="edaa2-122">Wenn RTCComponentUniversalServices unter **Benutzer**nicht vorhanden ist, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="edaa2-122">If RTCComponentUniversalServices does not exist under **Users**, do the following:</span></span>
    
    1.  <span data-ttu-id="edaa2-123">Klicken Sie mit der rechten Maustaste auf **Benutzer**, und klicken Sie dann auf **neuer Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="edaa2-123">Right-click **Users**, and then click **New User**.</span></span>
    
    2.  <span data-ttu-id="edaa2-124">Geben Sie unter **Anmeldename**den fehlenden Gruppennamen RTCComponentUniversalServices ein.</span><span class="sxs-lookup"><span data-stu-id="edaa2-124">In **Login name**, type the missing group name, RTCComponentUniversalServices.</span></span>
    
    3.  <span data-ttu-id="edaa2-125">Wählen Sie unter **Datenbankrollenmitgliedschaft**die Berechtigung **serverRole** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="edaa2-125">Under **Database role membership**, select the **ServerRole** permission, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="edaa2-126">Sie müssen den Archivierungs-oder Überwachungsdienst nicht erneut starten.</span><span class="sxs-lookup"><span data-stu-id="edaa2-126">You do not need to restart the archiving or monitoring service.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

