---
title: 'Lync Server 2013: Problembehandlung beim lync VDI-Plug-in'
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
ms.openlocfilehash: f1dfd8082ef0f0cdfc2a7931a675398507daaa51
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-the-lync-vdi-plug-in-in-lync-server-2013"></a><span data-ttu-id="b8863-102">Problembehandlung beim lync VDI-Plug-in in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8863-102">Troubleshooting the Lync VDI plug-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8863-103">_**Letztes Änderungsdatum des Themas:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="b8863-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<div>

## <a name="troubleshooting-issues-with-installing-the-lync-vdi-plug-in-on-a-thin-client"></a><span data-ttu-id="b8863-104">Behandeln von Problemen bei der Installation des lync VDI-Plug-Ins auf einem Thin Client</span><span class="sxs-lookup"><span data-stu-id="b8863-104">Troubleshooting Issues with Installing the Lync VDI Plug-in on a Thin Client</span></span>

<span data-ttu-id="b8863-105">Wenn Probleme beim Installieren des VDI-Plug-Ins auf einem Thin Client auftreten, überprüfen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b8863-105">If there are issues with installing the VDI plug-in on a thin client, check the following:</span></span>

  - <span data-ttu-id="b8863-106">Stellen Sie sicher, dass in dem Ordner, den Sie in den Systemvariablen „TEMP“ und „TMP“ angegeben haben, ausreichend Speicherplatz vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="b8863-106">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>

  - <span data-ttu-id="b8863-p101">Stellen Sie sicher, dass der Schreibschutz deaktiviert ist. Entsprechende Anweisungen finden Sie in der Dokumentation des Geräteherstellers.</span><span class="sxs-lookup"><span data-stu-id="b8863-p101">Ensure that write-protect is turned off. Refer to your device manufacturer’s documentation for instructions.</span></span>

</div>

<div>

## <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="b8863-109">Problembehandlung für die Kopplung</span><span class="sxs-lookup"><span data-stu-id="b8863-109">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="b8863-110">Wenn die VDI-Plug-in-Kopplung fehlschlägt, wird das Kopplungs Symbol in der unteren rechten Ecke als rotes "X" angezeigt:</span><span class="sxs-lookup"><span data-stu-id="b8863-110">When VDI plug-in pairing fails, the pairing icon in the lower right displays as a red “X” as shown:</span></span>

<span data-ttu-id="b8863-111">![Lync-VDI-Symbol mit erfolgreicher Kopplung](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync-VDI-Symbol mit erfolgreicher Kopplung")</span><span class="sxs-lookup"><span data-stu-id="b8863-111">![Lync VDI icon showing successful pairing](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync VDI icon showing successful pairing")</span></span>

<span data-ttu-id="b8863-112">Im folgenden sind mögliche Ursachen für Fehler und die erforderlichen Korrekturmaßnahmen zu finden.</span><span class="sxs-lookup"><span data-stu-id="b8863-112">The following are possible reasons for failures and the corrective actions you can take.</span></span>

  - <span data-ttu-id="b8863-113">**Die Benutzer haben bei der Anmeldung falsche Anmeldeinformationen eingegeben.**</span><span class="sxs-lookup"><span data-stu-id="b8863-113">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="b8863-114">Der Benutzer sollte sich bei lync abmelden und sich erneut mit den korrekten Anmeldeinformationen anmelden.</span><span class="sxs-lookup"><span data-stu-id="b8863-114">The user should sign out of Lync and sign in again with the correct credentials.</span></span> <span data-ttu-id="b8863-115">Das Kopplungsdialogfeld wird erneut angezeigt und gibt an, ob die Kopplung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="b8863-115">The pairing dialog box will reappear and show whether pairing is successful.</span></span>

  - <span data-ttu-id="b8863-116">**Eine andere Instanz des Remotedesktopclients wird bereits ausgeführt.**</span><span class="sxs-lookup"><span data-stu-id="b8863-116">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="b8863-117">Wenn Sie in Windows die Remote Desktop Verbindung verwenden, sollten die Benutzer die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="b8863-117">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
    1.  <span data-ttu-id="b8863-118">Starten Sie den Task-Manager: Drücken Sie **ALT+STRG+ENTF**, und klicken Sie dann auf **Task-Manager starten**.</span><span class="sxs-lookup"><span data-stu-id="b8863-118">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
    2.  <span data-ttu-id="b8863-119">Klicken Sie auf die Registerkarte **Prozesse**, und suchen Sie in der Liste nach allen Prozessen mit dem Namen **mstsc.exe**.</span><span class="sxs-lookup"><span data-stu-id="b8863-119">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
    3.  <span data-ttu-id="b8863-120">Markieren Sie alle **mstsc.exe**-Prozesse, und klicken Sie dann auf **Prozess beenden**. </span><span class="sxs-lookup"><span data-stu-id="b8863-120">Highlight each **mstsc.exe** process and then click **End Process**.</span></span>
    
    4.  <span data-ttu-id="b8863-121">Starten Sie eine neue Remotedesktopsitzung, und versuchen Sie erneut, eine Verbindung herzustellen. </span><span class="sxs-lookup"><span data-stu-id="b8863-121">Start a new remote desktop session and try connecting again.</span></span>

  - <span data-ttu-id="b8863-122">**Die erforderlichen Dateien wurden nicht ordnungsgemäß installiert.**</span><span class="sxs-lookup"><span data-stu-id="b8863-122">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="b8863-123">Nachdem das Plug-in auf dem lokalen Computer installiert wurde, sollten die folgenden Dateien unter C:\\Programmdateien\\Microsoft Office\\Ordner office15 (oder der entsprechende Laufwerkbuchstabe) vorhanden sein:</span><span class="sxs-lookup"><span data-stu-id="b8863-123">After the plug-in is installed on the local computer, the following files should be present under C:\\Program Files\\Microsoft Office\\Office15 (or the appropriate drive letter):</span></span>
    
      - <span data-ttu-id="b8863-124">LyncVdiPlugin.dll</span><span class="sxs-lookup"><span data-stu-id="b8863-124">LyncVdiPlugin.dll</span></span>
    
      - <span data-ttu-id="b8863-125">UcVdi.dll</span><span class="sxs-lookup"><span data-stu-id="b8863-125">UcVdi.dll</span></span>
    
    <span data-ttu-id="b8863-126">Wenn Probleme mit der VDI-Kopplung auftreten, stellen Sie sicher, dass diese Dateien auf dem lokalen Computer vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="b8863-126">If there are any issues with VDI pairing, check to make sure that these files are present on the local computer.</span></span>

  - <span data-ttu-id="b8863-127">**Der lync-Client wird auf dem lokalen Computer ausgeführt.**</span><span class="sxs-lookup"><span data-stu-id="b8863-127">**The Lync client is running on the local computer.**</span></span>
    
    <span data-ttu-id="b8863-128">Wenn Sie das lync-VDI-Plug-in verwenden möchten, muss ein lync-Client nicht auf dem lokalen Computer ausgeführt werden, da andernfalls die Kopplung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="b8863-128">To use the Lync VDI plugin, a Lync client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="b8863-129">Als bewährte Methode sollte der Benutzer keinen lync-Client auf dem lokalen Computer installieren.</span><span class="sxs-lookup"><span data-stu-id="b8863-129">As a best practice, the user should not install a Lync client on the local computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

