---
title: Verwenden Sie das Wiederherstellungstools für Microsoft Teams Rooms
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: davgroom
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
ms.collection: M365-voice
localization_priority: Normal
description: In diesem Artikel wird erläutert, wie mit dem Recovery Tool für Microsoft-Teams Chatrooms, die Sie verwenden würden, um ein veraltet System in einem unterstützten Zustand bringen.
ms.openlocfilehash: 9580a94c96b7982a3030ccc0435be8e05f7c4a25
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362815"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a><span data-ttu-id="f0e53-103">Verwenden Sie das Wiederherstellungstools für Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="f0e53-103">Use the Microsoft Teams Rooms recovery tool</span></span>
 
<span data-ttu-id="f0e53-104">In diesem Artikel wird erläutert, wie mit dem Recovery Tool für Microsoft-Teams Chatrooms, die Sie verwenden würden, um ein veraltet System in einem unterstützten Zustand bringen.</span><span class="sxs-lookup"><span data-stu-id="f0e53-104">This article discusses how to use the recovery tool for Microsoft Teams Rooms, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="f0e53-105">Verwenden Sie dieses Tool, wenn die Microsoft-Teams Räume-Konsole einen "veraltet System Config" Fehler angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f0e53-105">You would use this tool when the Microsoft Teams Rooms console shows a "system config out of date" error.</span></span>
  

<span data-ttu-id="f0e53-106"><a name="Prerequisites"> </a></span><span class="sxs-lookup"><span data-stu-id="f0e53-106"></span></span>  
## <a name="prerequisites"></a><span data-ttu-id="f0e53-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="f0e53-107">Prerequisites</span></span>

<span data-ttu-id="f0e53-108">Laden Sie das neueste [Installationspaket für den Microsoft-Teams Chatrooms](https://go.microsoft.com/fwlink/?linkid=851168) und Entpacken Sie es auf ein USB-Speicher Stick oder eine Netzwerkfreigabe für das Microsoft-Teams Chatrooms Gerät zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="f0e53-108">Download the latest [Microsoft Teams Rooms installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Microsoft Teams Rooms device.</span></span>

<span data-ttu-id="f0e53-109">Sie müssen auch [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)installieren.</span><span class="sxs-lookup"><span data-stu-id="f0e53-109">You may also need to install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span>

<span data-ttu-id="f0e53-110"><a name="Windows-ver"> </a></span><span class="sxs-lookup"><span data-stu-id="f0e53-110"></span></span>
## <a name="verify-windows-version"></a><span data-ttu-id="f0e53-111">Überprüfen der Windows-Version</span><span class="sxs-lookup"><span data-stu-id="f0e53-111">Verify Windows Version</span></span> 

1. <span data-ttu-id="f0e53-112">Melden Sie sich an ein Administratorkonto, indem Sie auf **Settings> Setting> Admin Anmeldung im Windows** vom Microsoft-Teams Chatrooms Gerät.</span><span class="sxs-lookup"><span data-stu-id="f0e53-112">Login to an admin account by going to **Settings> Windows Setting> Admin Sign In** from the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="f0e53-113">Diese Option bietet Ihnen zum Anmeldebildschirm.</span><span class="sxs-lookup"><span data-stu-id="f0e53-113">This option brings you to the login screen.</span></span>
2. <span data-ttu-id="f0e53-114">Melden Sie sich bei einer Administratorkonto der Standard-Administrator berücksichtigt wird `admin` mit dem Kennwort `sfb`.</span><span class="sxs-lookup"><span data-stu-id="f0e53-114">Sign into an admin account, the default admin account being `admin` with the password `sfb`.</span></span>
3. <span data-ttu-id="f0e53-115">Klicken Sie auf das Startmenü und Typ `winver.exe` in das Suchfeld, und klicken Sie auf \* das Ergebnis der*Befehl ausführen* .</span><span class="sxs-lookup"><span data-stu-id="f0e53-115">Click on the start menu and type `winver.exe` into the search box and click \**Run Command* on the result.</span></span>
4. <span data-ttu-id="f0e53-116">Notieren Sie die Nummer nach "Version" in der zweiten Zeile im Infobereich.</span><span class="sxs-lookup"><span data-stu-id="f0e53-116">Make note of the number after 'Version' on the second line of the info pane.</span></span>

>[!NOTE]
><span data-ttu-id="f0e53-117">Wenn die Version dargestellt 1607 oder früher ist, führen Sie die Schritte in den Schritten <a href="#Windows-up">Update Windows vor der Wiederherstellung</a> vor Proceding zu den Schritten zum <a href="#Perform">Ausführen einer Wiederherstellung</a> .</span><span class="sxs-lookup"><span data-stu-id="f0e53-117">If the Version shown is 1607 or earlier, follow the steps in the <a href="#Windows-up">Update Windows before recovery</a> steps before proceding to the <a href="#Perform">Perform a recovery</a> steps.</span></span> <span data-ttu-id="f0e53-118">Wenn die Version dargestellt 1607 größer ist, führen Sie nur die Schritte unter <a href="#Perform">Perform Wiederherstellung</a>.</span><span class="sxs-lookup"><span data-stu-id="f0e53-118">If the Version shown is greater than 1607, follow only the steps in <a href="#Perform">Perform a recovery</a>.</span></span>

<span data-ttu-id="f0e53-119"><a name="Windows-up"> </a></span><span class="sxs-lookup"><span data-stu-id="f0e53-119"></span></span>
## <a name="update-windows-before-recovery-if-needed"></a><span data-ttu-id="f0e53-120">Aktualisieren von Windows vor der Wiederherstellung (falls erforderlich)</span><span class="sxs-lookup"><span data-stu-id="f0e53-120">Update Windows before recovery (if needed)</span></span>

1. <span data-ttu-id="f0e53-121">Zwar weiterhin als Benutzer mit Administratorberechtigung angemeldet haben, starten Sie ein Powershell-Eingabeaufforderung mit erhöhten Rechten.</span><span class="sxs-lookup"><span data-stu-id="f0e53-121">While still logged in as an admin user, launch an elevated Powershell prompt.</span></span>
2. <span data-ttu-id="f0e53-122">Führen Sie den Befehl `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span><span class="sxs-lookup"><span data-stu-id="f0e53-122">Run the command `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span></span>
3. <span data-ttu-id="f0e53-123">Führen Sie Windows Update, und installieren Sie das Update für Windows 1709.</span><span class="sxs-lookup"><span data-stu-id="f0e53-123">Run Windows Update and install the update for Windows 1709.</span></span>
4. <span data-ttu-id="f0e53-124">Nachdem die Aktualisierung auf 1709 ist vollständige Anmeldung wieder in den Administratorkonto und [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)installieren.</span><span class="sxs-lookup"><span data-stu-id="f0e53-124">After the update to 1709 is complete sign back into admin account and install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span> <span data-ttu-id="f0e53-125">Das Update kann über den Link durchgeführt werden, oder über Windows Update.</span><span class="sxs-lookup"><span data-stu-id="f0e53-125">The update may be done from the link or using Windows Update.</span></span>
5. <span data-ttu-id="f0e53-126">Als optionalen Schritt installieren Sie zusätzliche verfügbare Updates von Windows Update.</span><span class="sxs-lookup"><span data-stu-id="f0e53-126">As an optional step, install any additional updates available from Windows Update.</span></span>

<span data-ttu-id="f0e53-127"><a name="Perform"> </a></span><span class="sxs-lookup"><span data-stu-id="f0e53-127"></span></span>
## <a name="perform-a-recovery"></a><span data-ttu-id="f0e53-128">Führen Sie eine Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="f0e53-128">Perform a recovery</span></span>

1. <span data-ttu-id="f0e53-129">Melden Sie sich an das Administratorkonto auf dem Gerät Microsoft Teams Chatrooms, und starten Sie eine Eingabeaufforderung mit erhöhten Rechten.</span><span class="sxs-lookup"><span data-stu-id="f0e53-129">Sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.</span></span>
2. <span data-ttu-id="f0e53-130">Vergewissern Sie sich vom Microsoft-Teams Chatrooms Gerät, dass Sie Zugriff auf sind die `RecoveryTool.ps1` -Datei, die in die Dateien extrahiert haben, aus dem Microsoft-Teams Räume-Installationspaket enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="f0e53-130">Verify from the Microsoft Teams Rooms device that you are able to access the `RecoveryTool.ps1` file, which is included in the files extracted from the Microsoft Teams Rooms installation package.</span></span> <span data-ttu-id="f0e53-131">Das Kit finden Sie auf der Netzwerkfreigabe oder USB-Laufwerk beim Vorbereiten der erforderlichen Komponenten verwendet.</span><span class="sxs-lookup"><span data-stu-id="f0e53-131">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3. <span data-ttu-id="f0e53-132">Führen Sie den Befehl Powershell.exe `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span><span class="sxs-lookup"><span data-stu-id="f0e53-132">Run the Powershell.exe command `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4. <span data-ttu-id="f0e53-133">Bei Aufforderung durch die Option "Skript auswählen" `1:"Repair System"`.</span><span class="sxs-lookup"><span data-stu-id="f0e53-133">When prompted by the script select option `1:"Repair System"`.</span></span>
5. <span data-ttu-id="f0e53-134">Starten Sie nach dem Abschluss das Microsoft-Teams Chatrooms Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="f0e53-134">Upon completion, reboot the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="f0e53-135">Es wird erneut automatisch neu gestartet und könnten vollständig wiederhergestellte zweites Mal.</span><span class="sxs-lookup"><span data-stu-id="f0e53-135">It will reboot again automatically and come up fully recovered the second time.</span></span>



<span data-ttu-id="f0e53-136"><a name="See"> </a></span><span class="sxs-lookup"><span data-stu-id="f0e53-136"></span></span>  
## <a name="see-also"></a><span data-ttu-id="f0e53-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0e53-137">See also</span></span>
 
[<span data-ttu-id="f0e53-138">Microsoft Teams Rooms-Hilfe</span><span class="sxs-lookup"><span data-stu-id="f0e53-138">Microsoft Teams Rooms help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="f0e53-139">Microsoft Teams Rooms verwalten</span><span class="sxs-lookup"><span data-stu-id="f0e53-139">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)