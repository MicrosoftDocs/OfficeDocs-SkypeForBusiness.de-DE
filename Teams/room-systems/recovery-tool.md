---
title: Verwenden Sie das Wiederherstellungstools für Microsoft Teams Rooms
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: sohailta
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
description: In diesem Artikel wird erläutert, wie Sie das Wiederherstellungstool für Microsoft Teams-Räume verwenden, mit denen Sie ein veraltetes System in einen unterstützten Zustand bringen.
ms.openlocfilehash: 04fd6b4b0786cffb4f1bb050a7b0bbdac8e2e653
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573649"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a><span data-ttu-id="d9d2d-103">Verwenden Sie das Wiederherstellungstools für Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="d9d2d-103">Use the Microsoft Teams Rooms recovery tool</span></span>
 
<span data-ttu-id="d9d2d-104">In diesem Artikel wird erläutert, wie Sie das Wiederherstellungstool für Microsoft Teams-Räume verwenden, mit denen Sie ein veraltetes System in einen unterstützten Zustand bringen.</span><span class="sxs-lookup"><span data-stu-id="d9d2d-104">This article discusses how to use the recovery tool for Microsoft Teams Rooms, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="d9d2d-105">Sie würden dieses Tool verwenden, wenn die Microsoft Teams rooms-Konsole einen Fehler "Systemkonfiguration veraltet" anzeigt.</span><span class="sxs-lookup"><span data-stu-id="d9d2d-105">You would use this tool when the Microsoft Teams Rooms console shows a "system config out of date" error.</span></span>
  

<span data-ttu-id="d9d2d-106"><a name="Prerequisites"> </a></span><span class="sxs-lookup"><span data-stu-id="d9d2d-106"></span></span>  
## <a name="prerequisites"></a><span data-ttu-id="d9d2d-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="d9d2d-107">Prerequisites</span></span>

<span data-ttu-id="d9d2d-108">Laden Sie das neueste [Microsoft Teams rooms-Installationspaket](https://go.microsoft.com/fwlink/?linkid=851168) herunter, und extrahieren Sie es auf einen USB-Speicherstick oder eine Netzwerkfreigabe, auf die das Microsoft Teams rooms-Gerät zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="d9d2d-108">Download the latest [Microsoft Teams Rooms installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Microsoft Teams Rooms device.</span></span>

<span data-ttu-id="d9d2d-109">Möglicherweise müssen Sie auch [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)installieren.</span><span class="sxs-lookup"><span data-stu-id="d9d2d-109">You may also need to install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span>

<span data-ttu-id="d9d2d-110"><a name="Windows-ver"> </a></span><span class="sxs-lookup"><span data-stu-id="d9d2d-110"></span></span>
## <a name="verify-windows-version"></a><span data-ttu-id="d9d2d-111">Überprüfen der Windows-Version</span><span class="sxs-lookup"><span data-stu-id="d9d2d-111">Verify Windows Version</span></span> 

1. <span data-ttu-id="d9d2d-112">Melden Sie sich bei einem Administratorkonto an, indem Sie unter **Einstellungen> Windows-Einstellung> Administrator** beim Microsoft Teams rooms-Gerät anmelden.</span><span class="sxs-lookup"><span data-stu-id="d9d2d-112">Login to an admin account by going to **Settings> Windows Setting> Admin Sign In** from the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="d9d2d-113">Mit dieser Option gelangen Sie zum Anmeldebildschirm.</span><span class="sxs-lookup"><span data-stu-id="d9d2d-113">This option brings you to the login screen.</span></span>
2. <span data-ttu-id="d9d2d-114">Melden Sie sich `admin` bei einem Administratorkonto an, dem standardmäßigen Administrator `sfb`Konto, das das Kennwort hat.</span><span class="sxs-lookup"><span data-stu-id="d9d2d-114">Sign into an admin account, the default admin account being `admin` with the password `sfb`.</span></span>
3. <span data-ttu-id="d9d2d-115">Klicken Sie auf das Startmenü und geben `winver.exe` Sie in das Suchfeld ein und klicken Sie auf*Befehl "ausführen* " im Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="d9d2d-115">Click on the start menu and type `winver.exe` into the search box and click \**Run Command* on the result.</span></span>
4. <span data-ttu-id="d9d2d-116">Notieren Sie sich die Zahl nach "Version" in der zweiten Zeile des Infobereichs.</span><span class="sxs-lookup"><span data-stu-id="d9d2d-116">Make note of the number after 'Version' on the second line of the info pane.</span></span>

>[!NOTE]
><span data-ttu-id="d9d2d-117">Wenn die angezeigte Version 1607 oder früher ist, führen Sie die Schritte in den Schritten unter <a href="#Windows-up">Aktualisieren von Windows vor der Wiederherstellung</a> vor vorgegangen, um die Schritte zum <a href="#Perform">Ausführen einer Wiederherstellung auszuführen</a> .</span><span class="sxs-lookup"><span data-stu-id="d9d2d-117">If the Version shown is 1607 or earlier, follow the steps in the <a href="#Windows-up">Update Windows before recovery</a> steps before proceding to the <a href="#Perform">Perform a recovery</a> steps.</span></span> <span data-ttu-id="d9d2d-118">Wenn die angezeigte Version größer als 1607 ist, führen Sie nur die Schritte unter <a href="#Perform">Durchführen einer Wiederherstellung</a>aus.</span><span class="sxs-lookup"><span data-stu-id="d9d2d-118">If the Version shown is greater than 1607, follow only the steps in <a href="#Perform">Perform a recovery</a>.</span></span>

<span data-ttu-id="d9d2d-119"><a name="Windows-up"> </a></span><span class="sxs-lookup"><span data-stu-id="d9d2d-119"></span></span>
## <a name="update-windows-before-recovery-if-needed"></a><span data-ttu-id="d9d2d-120">Aktualisieren von Windows vor der Wiederherstellung (falls erforderlich)</span><span class="sxs-lookup"><span data-stu-id="d9d2d-120">Update Windows before recovery (if needed)</span></span>

1. <span data-ttu-id="d9d2d-121">Wenn Sie weiterhin als Administrator angemeldet sind, starten Sie eine Eingabeaufforderung mit erhöhten PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d9d2d-121">While still logged in as an admin user, launch an elevated Powershell prompt.</span></span>
2. <span data-ttu-id="d9d2d-122">Führen Sie den `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="d9d2d-122">Run the command `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span></span>
3. <span data-ttu-id="d9d2d-123">Führen Sie Windows Update aus, und installieren Sie das Update für Windows 1709.</span><span class="sxs-lookup"><span data-stu-id="d9d2d-123">Run Windows Update and install the update for Windows 1709.</span></span>
4. <span data-ttu-id="d9d2d-124">Nachdem das Update auf 1709 abgeschlossen ist, melden Sie sich erneut beim Administratorkonto an, und installieren Sie [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span><span class="sxs-lookup"><span data-stu-id="d9d2d-124">After the update to 1709 is complete sign back into admin account and install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span> <span data-ttu-id="d9d2d-125">Das Update kann über den Link oder die Verwendung von Windows Update erfolgen.</span><span class="sxs-lookup"><span data-stu-id="d9d2d-125">The update may be done from the link or using Windows Update.</span></span>
5. <span data-ttu-id="d9d2d-126">Als optionalen Schritt installieren Sie alle weiteren Updates, die über Windows Update zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="d9d2d-126">As an optional step, install any additional updates available from Windows Update.</span></span>

<span data-ttu-id="d9d2d-127"><a name="Perform"> </a></span><span class="sxs-lookup"><span data-stu-id="d9d2d-127"></span></span>
## <a name="perform-a-recovery"></a><span data-ttu-id="d9d2d-128">Durchführen einer Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="d9d2d-128">Perform a recovery</span></span>

1. <span data-ttu-id="d9d2d-129">Registrieren Sie sich auf Ihrem Microsoft Teams rooms-Gerät beim Administratorkonto, und starten Sie eine Eingabeaufforderung mit erhöhten Rechten.</span><span class="sxs-lookup"><span data-stu-id="d9d2d-129">Sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.</span></span>
2. <span data-ttu-id="d9d2d-130">Überprüfen Sie im Microsoft Teams rooms-Gerät, dass Sie auf die `RecoveryTool.ps1` Datei zugreifen können, die in den Dateien enthalten ist, die aus dem Installationspaket für Microsoft Teams rooms extrahiert wurden.</span><span class="sxs-lookup"><span data-stu-id="d9d2d-130">Verify from the Microsoft Teams Rooms device that you are able to access the `RecoveryTool.ps1` file, which is included in the files extracted from the Microsoft Teams Rooms installation package.</span></span> <span data-ttu-id="d9d2d-131">Das Kit befindet sich auf der Netzwerkfreigabe oder dem USB-Laufwerk, das bei der Vorbereitung von Voraussetzungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d9d2d-131">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3. <span data-ttu-id="d9d2d-132">Führen Sie den Befehl `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`PowerShell. exe aus.</span><span class="sxs-lookup"><span data-stu-id="d9d2d-132">Run the Powershell.exe command `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4. <span data-ttu-id="d9d2d-133">Wenn Sie von der Option `1:"Repair System"`Skript auswählen aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="d9d2d-133">When prompted by the script select option `1:"Repair System"`.</span></span>
5. <span data-ttu-id="d9d2d-134">Starten Sie nach Abschluss das Microsoft Teams rooms-Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="d9d2d-134">Upon completion, reboot the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="d9d2d-135">Sie wird automatisch neu gestartet und beim zweiten Mal wieder vollständig wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="d9d2d-135">It will reboot again automatically and come up fully recovered the second time.</span></span>



<span data-ttu-id="d9d2d-136"><a name="See"> </a></span><span class="sxs-lookup"><span data-stu-id="d9d2d-136"></span></span>  
## <a name="see-also"></a><span data-ttu-id="d9d2d-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9d2d-137">See also</span></span>
 
[<span data-ttu-id="d9d2d-138">Microsoft Teams Rooms-Hilfe</span><span class="sxs-lookup"><span data-stu-id="d9d2d-138">Microsoft Teams Rooms help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="d9d2d-139">Microsoft Teams Rooms verwalten</span><span class="sxs-lookup"><span data-stu-id="d9d2d-139">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
