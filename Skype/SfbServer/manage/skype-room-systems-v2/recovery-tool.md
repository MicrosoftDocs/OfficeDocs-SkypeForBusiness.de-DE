---
title: Verwenden Sie das Skype Raum Systemen v2 Recovery-tool
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: In diesem Artikel wird erläutert, wie das Wiederherstellungstool verwenden für Skype Raum Systemen v2, Sie verwenden würden, um ein veraltet System in einem unterstützten Zustand bringen.
ms.openlocfilehash: fd71fc189b7471e4e315b6602014a967be09f9c0
ms.sourcegitcommit: febd51fd7988602a8c9839e4e9872ae8f5d77c63
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2018
---
# <a name="use-the-skype-room-systems-v2-recovery-tool"></a><span data-ttu-id="5fc9f-103">Verwenden Sie das Skype Raum Systemen v2 Recovery-tool</span><span class="sxs-lookup"><span data-stu-id="5fc9f-103">Use the Skype Room Systems v2 recovery tool</span></span>
 
<span data-ttu-id="5fc9f-104">In diesem Artikel wird erläutert, wie das Wiederherstellungstool verwenden für Skype Raum Systemen v2, Sie verwenden würden, um ein veraltet System in einem unterstützten Zustand bringen.</span><span class="sxs-lookup"><span data-stu-id="5fc9f-104">This article discusses how to use the recovery tool for Skype Room Systems v2, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="5fc9f-105">Verwenden Sie dieses Tool, wenn die Skype Raum Systemen v2-Konsole einen "veraltet System Config" Fehler angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="5fc9f-105">You would use this tool when the Skype Room Systems v2 console shows a "system config out of date" error.</span></span>
  

<span data-ttu-id="5fc9f-106"><a name="Prerequisites"> </a></span><span class="sxs-lookup"><span data-stu-id="5fc9f-106"></span></span>  
## <a name="prerequisites"></a><span data-ttu-id="5fc9f-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="5fc9f-107">Prerequisites</span></span>

<span data-ttu-id="5fc9f-108">Laden Sie das neueste [Skype Raum Systemen v2 Installationspaket](https://go.microsoft.com/fwlink/?linkid=851168) und Entpacken Sie es auf einem USB-Speicher Stick oder einer Netzwerkressource Skype Raum Systemen v2 Gerät zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="5fc9f-108">Download the latest [Skype Room Systems v2 installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Skype Room Systems v2 device.</span></span>

<span data-ttu-id="5fc9f-109">Sie müssen auch [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)installieren.</span><span class="sxs-lookup"><span data-stu-id="5fc9f-109">You may also need to install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span>

<span data-ttu-id="5fc9f-110"><a name="Windows-ver"> </a></span><span class="sxs-lookup"><span data-stu-id="5fc9f-110"></span></span>
## <a name="verify-windows-version"></a><span data-ttu-id="5fc9f-111">Überprüfen der Windows-Version</span><span class="sxs-lookup"><span data-stu-id="5fc9f-111">Verify Windows Version</span></span> 

1. <span data-ttu-id="5fc9f-112">Melden Sie sich ein Administratorkonto, indem Sie auf **Einstellungen > Windows-Einstellung > Admin anmelden** vom Gerät v2 Skype Raum Systeme.</span><span class="sxs-lookup"><span data-stu-id="5fc9f-112">Login to an admin account by going to **Settings> Windows Setting> Admin Sign In** from the Skype Room Systems v2 device.</span></span> <span data-ttu-id="5fc9f-113">Diese Option bietet Ihnen zum Anmeldebildschirm.</span><span class="sxs-lookup"><span data-stu-id="5fc9f-113">This option brings you to the login screen.</span></span>
2. <span data-ttu-id="5fc9f-114">Melden Sie sich bei einer Administratorkonto der Standard-Administrator berücksichtigt wird `admin` mit dem Kennwort `sfb`.</span><span class="sxs-lookup"><span data-stu-id="5fc9f-114">Sign into an admin account, the default admin account being `admin` with the password `sfb`.</span></span>
3. <span data-ttu-id="5fc9f-115">Klicken Sie auf das Startmenü und Typ `winver.exe` in das Suchfeld, und klicken Sie auf \* das Ergebnis der*Befehl ausführen* .</span><span class="sxs-lookup"><span data-stu-id="5fc9f-115">Click on the start menu and type `winver.exe` into the search box and click \**Run Command* on the result.</span></span>
4. <span data-ttu-id="5fc9f-116">Notieren Sie die Nummer nach "Version" in der zweiten Zeile im Infobereich.</span><span class="sxs-lookup"><span data-stu-id="5fc9f-116">Make note of the number after 'Version' on the second line of the info pane.</span></span>

>[!NOTE]
><span data-ttu-id="5fc9f-117">Wenn die Version dargestellt 1607 oder früher ist, führen Sie die Schritte in den Schritten <a href="#Windows-up">Update Windows vor der Wiederherstellung</a> vor Proceding zu den Schritten zum <a href="#Perform">Ausführen einer Wiederherstellung</a> .</span><span class="sxs-lookup"><span data-stu-id="5fc9f-117">If the Version shown is 1607 or earlier, follow the steps in the <a href="#Windows-up">Update Windows before recovery</a> steps before proceding to the <a href="#Perform">Perform a recovery</a> steps.</span></span> <span data-ttu-id="5fc9f-118">Wenn die Version dargestellt 1607 größer ist, führen Sie nur die Schritte unter <a href="#Perform">Perform Wiederherstellung</a>.</span><span class="sxs-lookup"><span data-stu-id="5fc9f-118">If the Version shown is greater than 1607, follow only the steps in <a href="#Perform">Perform a recovery</a>.</span></span>

<span data-ttu-id="5fc9f-119"><a name="Windows-up"> </a></span><span class="sxs-lookup"><span data-stu-id="5fc9f-119"></span></span>
## <a name="update-windows-before-recovery-if-needed"></a><span data-ttu-id="5fc9f-120">Aktualisieren von Windows vor der Wiederherstellung (falls erforderlich)</span><span class="sxs-lookup"><span data-stu-id="5fc9f-120">Update Windows before recovery (if needed)</span></span>

1. <span data-ttu-id="5fc9f-121">Zwar weiterhin als Benutzer mit Administratorberechtigung angemeldet haben, starten Sie ein Powershell-Eingabeaufforderung mit erhöhten Rechten.</span><span class="sxs-lookup"><span data-stu-id="5fc9f-121">While still logged in as an admin user, launch an elevated Powershell prompt.</span></span>
2. <span data-ttu-id="5fc9f-122">Führen Sie den Befehl `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span><span class="sxs-lookup"><span data-stu-id="5fc9f-122">Run the command `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span></span>
3. <span data-ttu-id="5fc9f-123">Führen Sie Windows Update, und installieren Sie das Update für Windows 1709.</span><span class="sxs-lookup"><span data-stu-id="5fc9f-123">Run Windows Update and install the update for Windows 1709.</span></span>
4. <span data-ttu-id="5fc9f-124">Nachdem die Aktualisierung auf 1709 ist vollständige Anmeldung wieder in den Administratorkonto und [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)installieren.</span><span class="sxs-lookup"><span data-stu-id="5fc9f-124">After the update to 1709 is complete sign back into admin account and install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span> <span data-ttu-id="5fc9f-125">Das Update kann über den Link durchgeführt werden, oder über Windows Update.</span><span class="sxs-lookup"><span data-stu-id="5fc9f-125">The update may be done from the link or using Windows Update.</span></span>
5. <span data-ttu-id="5fc9f-126">Als optionalen Schritt installieren Sie zusätzliche verfügbare Updates von Windows Update.</span><span class="sxs-lookup"><span data-stu-id="5fc9f-126">As an optional step, install any additional updates available from Windows Update.</span></span>

<span data-ttu-id="5fc9f-127"><a name="Perform"> </a></span><span class="sxs-lookup"><span data-stu-id="5fc9f-127"></span></span>
## <a name="perform-a-recovery"></a><span data-ttu-id="5fc9f-128">Führen Sie eine Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="5fc9f-128">Perform a recovery</span></span>

1. <span data-ttu-id="5fc9f-129">Melden Sie sich an das Administratorkonto auf dem mobilen Gerät Skype Raum Systeme-v2, und starten Sie eine Eingabeaufforderung mit erhöhten Rechten.</span><span class="sxs-lookup"><span data-stu-id="5fc9f-129">Sign in to the admin account on your Skype Room Systems v2 device, and launch an elevated command prompt.</span></span>
2. <span data-ttu-id="5fc9f-130">Vergewissern Sie sich vom Gerät v2 Skype Raum Systeme, dass Sie Zugriff auf sind die `RecoveryTool.ps1` -Datei, die in die Dateien extrahiert haben, aus dem Skype Raum Systemen v2-Installationspaket enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="5fc9f-130">Verify from the Skype Room Systems v2 device that you are able to access the `RecoveryTool.ps1` file, which is included in the files extracted from the Skype Room Systems v2 installation package.</span></span> <span data-ttu-id="5fc9f-131">Das Kit finden Sie auf der Netzwerkfreigabe oder USB-Laufwerk beim Vorbereiten der erforderlichen Komponenten verwendet.</span><span class="sxs-lookup"><span data-stu-id="5fc9f-131">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3. <span data-ttu-id="5fc9f-132">Führen Sie den Befehl Powershell.exe `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span><span class="sxs-lookup"><span data-stu-id="5fc9f-132">Run the Powershell.exe command `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4. <span data-ttu-id="5fc9f-133">Bei Aufforderung durch die Option "Skript auswählen" `1:"Repair System"`.</span><span class="sxs-lookup"><span data-stu-id="5fc9f-133">When prompted by the script select option `1:"Repair System"`.</span></span>
5. <span data-ttu-id="5fc9f-134">Starten Sie nach dem Abschluss das Skype Raum Systemen v2 Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="5fc9f-134">Upon completion, reboot the Skype Room Systems v2 device.</span></span> <span data-ttu-id="5fc9f-135">Es wird erneut automatisch neu gestartet und könnten vollständig wiederhergestellte zweites Mal.</span><span class="sxs-lookup"><span data-stu-id="5fc9f-135">It will reboot again automatically and come up fully recovered the second time.</span></span>



<span data-ttu-id="5fc9f-136"><a name="See"> </a></span><span class="sxs-lookup"><span data-stu-id="5fc9f-136"></span></span>  
## <a name="see-also"></a><span data-ttu-id="5fc9f-137">Waren diese Schritte hilfreich? Wenn ja, teilen Sie uns dies bitte unterhalb des Artikels mit. Wenn nicht, schreiben Sie uns, was für Sie unklar war, und wir verwenden Ihr Feedback, um unsere Schritte zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="5fc9f-137">See also</span></span>


#### 
[<span data-ttu-id="5fc9f-138">Skype Raum Systeme Version 2-Hilfe</span><span class="sxs-lookup"><span data-stu-id="5fc9f-138">Skype Room Systems version 2 help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="5fc9f-139">Verwalten von Skype Raum Systemen v2</span><span class="sxs-lookup"><span data-stu-id="5fc9f-139">Manage Skype Room Systems v2</span></span>](skype-room-systems-v2.md)
#### 
