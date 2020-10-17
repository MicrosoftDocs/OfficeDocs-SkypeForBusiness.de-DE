---
title: 'Lync Server 2013: Problembehandlung beim lync VDI-Plug-in'
description: 'Lync Server 2013: Problembehandlung für das lync VDI-Plug-in.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting the Lync VDI plug-in
ms:assetid: 183c9449-b907-409c-b5ed-b02af3bd93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204713(v=OCS.15)
ms:contentKeyID: 48183525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cd2c0e3c8a47225f00ce280706dea2287e4dc8b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548941"
---
# <a name="troubleshooting-the-lync-vdi-plug-in-in-lync-server-2013"></a><span data-ttu-id="f70da-103">Problembehandlung für das lync VDI-Plug-in in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f70da-103">Troubleshooting the Lync VDI plug-in in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f70da-104">_**Letztes Änderungsstand des Themas:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="f70da-104">_**Topic Last Modified:** 2012-10-10_</span></span>

<div>

## <a name="troubleshooting-issues-with-installing-the-lync-vdi-plug-in-on-a-thin-client"></a><span data-ttu-id="f70da-105">Beheben von Problemen beim Installieren des lync VDI-Plug-Ins auf einem Thin-Client</span><span class="sxs-lookup"><span data-stu-id="f70da-105">Troubleshooting Issues with Installing the Lync VDI Plug-in on a Thin Client</span></span>

<span data-ttu-id="f70da-106">Wenn beim Installieren des VDI-Plug-Ins auf einem Thin-Client Probleme auftreten, überprüfen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f70da-106">If there are issues with installing the VDI plug-in on a thin client, check the following:</span></span>

  - <span data-ttu-id="f70da-107">Stellen Sie sicher, dass im Ordner, den Sie in den Systemvariablen "TEMP" und "TMP" angegeben haben, ausreichend Speicherplatz vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="f70da-107">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>

  - <span data-ttu-id="f70da-p101">Stellen Sie sicher, dass der Schreibschutz deaktiviert ist. Entsprechende Anweisungen finden Sie Dokumentation des Geräteherstellers.</span><span class="sxs-lookup"><span data-stu-id="f70da-p101">Ensure that write-protect is turned off. Refer to your device manufacturer’s documentation for instructions.</span></span>

</div>

<div>

## <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="f70da-110">Behebung von Problemen bei der Paarung</span><span class="sxs-lookup"><span data-stu-id="f70da-110">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="f70da-111">Wenn die Paarung des VDI-Plug-Ins fehlschlägt, wird das Paarungssymbol unten rechts als rotes “X” angezeigt:</span><span class="sxs-lookup"><span data-stu-id="f70da-111">When VDI plug-in pairing fails, the pairing icon in the lower right displays as a red “X” as shown:</span></span>

<span data-ttu-id="f70da-112">![Lync-VDI-Symbol mit erfolgreicher Kopplung](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync-VDI-Symbol mit erfolgreicher Kopplung")</span><span class="sxs-lookup"><span data-stu-id="f70da-112">![Lync VDI icon showing successful pairing](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync VDI icon showing successful pairing")</span></span>

<span data-ttu-id="f70da-113">Im Folgenden finden Sie mögliche Gründe für Fehler und Korrekturmaßnahmen.</span><span class="sxs-lookup"><span data-stu-id="f70da-113">The following are possible reasons for failures and the corrective actions you can take.</span></span>

  - <span data-ttu-id="f70da-114">**Der Benutzer hat bei der Anmeldung falsche Anmeldeinformationen eingegeben.**</span><span class="sxs-lookup"><span data-stu-id="f70da-114">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="f70da-115">Der Benutzer sollte sich bei lync abmelden und sich mit den korrekten Anmeldeinformationen erneut anmelden.</span><span class="sxs-lookup"><span data-stu-id="f70da-115">The user should sign out of Lync and sign in again with the correct credentials.</span></span> <span data-ttu-id="f70da-116">Das Paarungsdialogfeld wird erneut angezeigt und gibt an, ob die Paarung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="f70da-116">The pairing dialog box will reappear and show whether pairing is successful.</span></span>

  - <span data-ttu-id="f70da-117">**Eine andere Instanz des Remotedesktop-Clients wird bereits ausgeführt**</span><span class="sxs-lookup"><span data-stu-id="f70da-117">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="f70da-118">Wenn die Remote Desktop Verbindung in Windows verwendet wird, sollten Benutzer folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="f70da-118">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
    1.  <span data-ttu-id="f70da-119">Starten Sie den Task-Manager: Drücken Sie **Alt+Strg+Entf**, und klicken Sie dann auf **Task-Manager starten**.</span><span class="sxs-lookup"><span data-stu-id="f70da-119">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
    2.  <span data-ttu-id="f70da-120">Klicken Sie auf die Registerkarte **Prozesse**, und suchen Sie in der Liste nach allen Prozessen mit dem Namen **mstsc.exe**.</span><span class="sxs-lookup"><span data-stu-id="f70da-120">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
    3.  <span data-ttu-id="f70da-121">Markieren Sie alle **mstsc.exe**-Prozesse, und klicken Sie dann auf **Prozess beenden**.</span><span class="sxs-lookup"><span data-stu-id="f70da-121">Highlight each **mstsc.exe** process and then click **End Process**.</span></span>
    
    4.  <span data-ttu-id="f70da-122">Starten Sie eine neue Remotedesktopsitzung, und versuchen Sie erneut, eine Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="f70da-122">Start a new remote desktop session and try connecting again.</span></span>

  - <span data-ttu-id="f70da-123">**Die erforderlichen Dateien wurden nicht ordnungsgemäß installiert.**</span><span class="sxs-lookup"><span data-stu-id="f70da-123">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="f70da-124">Nachdem das Plug-in auf dem lokalen Computer installiert wurde, sollten die folgenden Dateien unter C: \\ Program Files \\ Microsoft Office \\ Office15 (oder dem entsprechenden Laufwerksbuchstaben) vorhanden sein:</span><span class="sxs-lookup"><span data-stu-id="f70da-124">After the plug-in is installed on the local computer, the following files should be present under C:\\Program Files\\Microsoft Office\\Office15 (or the appropriate drive letter):</span></span>
    
      - <span data-ttu-id="f70da-125">LyncVdiPlugin.dll</span><span class="sxs-lookup"><span data-stu-id="f70da-125">LyncVdiPlugin.dll</span></span>
    
      - <span data-ttu-id="f70da-126">UcVdi.dll</span><span class="sxs-lookup"><span data-stu-id="f70da-126">UcVdi.dll</span></span>
    
    <span data-ttu-id="f70da-127">Wenn Probleme mit der VDI-Paarung auftreten, stellen Sie sicher, dass diese Dateien auf dem lokalen Computer vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="f70da-127">If there are any issues with VDI pairing, check to make sure that these files are present on the local computer.</span></span>

  - <span data-ttu-id="f70da-128">**Der lync-Client wird auf dem lokalen Computer gestartet.**</span><span class="sxs-lookup"><span data-stu-id="f70da-128">**The Lync client is running on the local computer.**</span></span>
    
    <span data-ttu-id="f70da-129">Für die Verwendung des lync VDI-Plug-ins darf ein lync-Client nicht auf dem lokalen Computer ausgeführt werden, andernfalls tritt ein Verbindungsfehler auf.</span><span class="sxs-lookup"><span data-stu-id="f70da-129">To use the Lync VDI plugin, a Lync client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="f70da-130">Als bewährte Methode sollte der Benutzer keinen lync-Client auf dem lokalen Computer installieren.</span><span class="sxs-lookup"><span data-stu-id="f70da-130">As a best practice, the user should not install a Lync client on the local computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

