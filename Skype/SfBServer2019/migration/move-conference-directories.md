---
title: Verschieben von Konferenzverzeichnissen
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Vor der Außerbetriebnahme eines Pools müssen Sie das folgende Verfahren für jedes Konferenzverzeichnis in Ihrem Legacy Pool ausführen.
ms.openlocfilehash: 8a25b955ae769a712750ff08325b3fa29538be8a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752497"
---
# <a name="move-conference-directories"></a><span data-ttu-id="a9aee-103">Verschieben von Konferenzverzeichnissen</span><span class="sxs-lookup"><span data-stu-id="a9aee-103">Move Conference Directories</span></span>

<span data-ttu-id="a9aee-104">Vor dem Außerbetriebnahme eines Pools müssen Sie das folgende Verfahren für jedes Konferenzverzeichnis in Ihrem Legacy Pool ausführen.</span><span class="sxs-lookup"><span data-stu-id="a9aee-104">Before decommissioning a pool, you must perform the following procedure for each conference directory in your legacy pool.</span></span>
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a><span data-ttu-id="a9aee-105">So migrieren Sie ein Konferenzverzeichnis in Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="a9aee-105">To Move a Conference Directory to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="a9aee-106">Öffnen Sie die Skype for Business Server Management-Shell.</span><span class="sxs-lookup"><span data-stu-id="a9aee-106">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="a9aee-107">Um die Identität der Konferenzverzeichnisse in Ihrer Organisation zu erhalten, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="a9aee-107">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
   ```PowerShell
   Get-CsConferenceDirectory
   ```

    <span data-ttu-id="a9aee-108">Der obige Befehl gibt alle Konferenzverzeichnisse in Ihrer Organisation zurück.</span><span class="sxs-lookup"><span data-stu-id="a9aee-108">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="a9aee-109">Aus diesem Grund möchten Sie möglicherweise die Ergebnisse auf den Pool beschränken, der außer Betrieb genommen wird.</span><span class="sxs-lookup"><span data-stu-id="a9aee-109">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="a9aee-110">Wenn Sie beispielsweise den Pool mit dem vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) pool01.contoso.net, verwenden Sie diesen Befehl, um die zurückgegebenen Daten auf Konferenzverzeichnisse aus diesem Pool zu begrenzen:</span><span class="sxs-lookup"><span data-stu-id="a9aee-110">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    <span data-ttu-id="a9aee-111">Dieser Befehl gibt nur die Konferenzverzeichnisse zurück, in denen die Service-Eigenschaft den FQDN pool01.contoso.NET enthält.</span><span class="sxs-lookup"><span data-stu-id="a9aee-111">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>
    
3. <span data-ttu-id="a9aee-112">Um Konferenzverzeichnisse zu migrieren, führen Sie den folgenden Befehl für jedes Konferenzverzeichnis im Pool aus:</span><span class="sxs-lookup"><span data-stu-id="a9aee-112">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    <span data-ttu-id="a9aee-113">Um beispielsweise das Konferenzverzeichnis 3 zu verlagern, verwenden Sie diesen Befehl, um einen Skype for Business Server 2019-Pool als TargetPool anzugeben:</span><span class="sxs-lookup"><span data-stu-id="a9aee-113">For example, to move conference directory 3, use this command, specifying a Skype for Business Server 2019 pool as the TargetPool:</span></span>
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    <span data-ttu-id="a9aee-114">Wenn Sie alle Konferenzverzeichnisse in einem Pool verlagern möchten, verwenden Sie einen Befehl wie den folgenden:</span><span class="sxs-lookup"><span data-stu-id="a9aee-114">If you want to move all the conference directories on a pool, use a command similar to the following:</span></span>
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

<span data-ttu-id="a9aee-115">Laden Sie das [Deinstallieren von Microsoft Legacy und das Entfernen von Server Rollen](https://go.microsoft.com/fwlink/p/?linkId=246227) für eine umfassende, schrittweise Anleitung zur Außerbetriebnahme von Legacy Pools herunter.</span><span class="sxs-lookup"><span data-stu-id="a9aee-115">Download [Uninstalling Microsoft legacy and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227) for comprehensive, step-by-step instructions on decommissioning legacy pools.</span></span>
  
<span data-ttu-id="a9aee-116">Beim Verschieben von Konferenz Verzeichnissen kann der folgende Fehler auftreten:</span><span class="sxs-lookup"><span data-stu-id="a9aee-116">When moving conference directories, you might encounter the following error:</span></span>
  
```console
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

<span data-ttu-id="a9aee-117">Dieser Fehler tritt normalerweise auf, wenn die Skype for Business Server-Verwaltungsshell eine aktualisierte Gruppe von Active Directory Berechtigungen erfordert, um eine Aufgabe abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="a9aee-117">This error typically occurs when the Skype for Business Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="a9aee-118">Um das Problem zu beheben, schließen Sie die aktuelle Instanz der Verwaltungsshell, öffnen Sie dann eine neue Instanz der Shell, und führen Sie den Befehl erneut aus, um das Konferenzverzeichnis zu verlagern.</span><span class="sxs-lookup"><span data-stu-id="a9aee-118">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command to move the conference directory.</span></span>
  

