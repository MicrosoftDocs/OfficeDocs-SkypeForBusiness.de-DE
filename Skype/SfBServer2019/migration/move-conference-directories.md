---
title: Verschieben von Konferenzverzeichnissen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vor der Außerbetriebnahme eines Pools müssen Sie die folgenden Schritte für jedes Konferenzverzeichnis in Ihrem Legacy Pool durchführen.
ms.openlocfilehash: cc989e752e69db31f338b493c403b8b8d4c252cc
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237737"
---
# <a name="move-conference-directories"></a><span data-ttu-id="b7311-103">Verschieben von Konferenzverzeichnissen</span><span class="sxs-lookup"><span data-stu-id="b7311-103">Move Conference Directories</span></span>

<span data-ttu-id="b7311-104">Bevor Sie einen Pool außer Betrieb nehmen, müssen Sie für jedes Konferenzverzeichnis in Ihrem Legacy Pool die folgenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="b7311-104">Before decommissioning a pool, you must perform the following procedure for each conference directory in your legacy pool.</span></span>
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a><span data-ttu-id="b7311-105">So verschieben Sie ein Konferenzverzeichnis in Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="b7311-105">To Move a Conference Directory to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="b7311-106">Öffnen Sie die Skype for Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="b7311-106">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="b7311-107">Führen Sie den folgenden Befehl aus, um die Identität der Konferenzverzeichnisse in Ihrer Organisation zu ermitteln:</span><span class="sxs-lookup"><span data-stu-id="b7311-107">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
   ```
   Get-CsConferenceDirectory
   ```

    <span data-ttu-id="b7311-108">Der vorhergehende Befehl gibt alle Konferenzverzeichnisse in Ihrer Organisation zurück.</span><span class="sxs-lookup"><span data-stu-id="b7311-108">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="b7311-109">Aus diesem Grund sollten Sie die Ergebnisse auf den Pool beschränken, der außer Betrieb genommen wird.</span><span class="sxs-lookup"><span data-stu-id="b7311-109">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="b7311-110">Wenn Sie beispielsweise den Pool mit dem vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) pool01.contoso.net, verwenden Sie diesen Befehl, um die zurückgegebenen Daten auf Konferenzverzeichnisse aus diesem Pool zu begrenzen:</span><span class="sxs-lookup"><span data-stu-id="b7311-110">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    <span data-ttu-id="b7311-111">Dieser Befehl gibt nur die Konferenzverzeichnisse zurück, in denen die Service-Eigenschaft den FQDN-pool01.contoso.NET enthält.</span><span class="sxs-lookup"><span data-stu-id="b7311-111">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>
    
3. <span data-ttu-id="b7311-112">Führen Sie zum Verschieben von Konferenz Verzeichnissen den folgenden Befehl für jedes Konferenzverzeichnis im Pool aus:</span><span class="sxs-lookup"><span data-stu-id="b7311-112">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
   ```
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    <span data-ttu-id="b7311-113">Wenn Sie beispielsweise das Konferenzverzeichnis 3 verschieben möchten, verwenden Sie diesen Befehl, und geben Sie einen Skype for Business Server 2019-Pool als TargetPool an:</span><span class="sxs-lookup"><span data-stu-id="b7311-113">For example, to move conference directory 3, use this command, specifying a Skype for Business Server 2019 pool as the TargetPool:</span></span>
    
   ```
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    <span data-ttu-id="b7311-114">Wenn Sie alle Konferenzverzeichnisse in einem Pool verschieben möchten, verwenden Sie einen Befehl wie den folgenden:</span><span class="sxs-lookup"><span data-stu-id="b7311-114">If you want to move all the conference directories on a pool, use a command similar to the following:</span></span>
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

<span data-ttu-id="b7311-115">Laden Sie die Deinstallation von [Microsoft Legacy herunter, und entfernen Sie die Server Rollen](https://go.microsoft.com/fwlink/p/?linkId=246227) , um umfassende, schrittweise Anleitungen zur Außerbetriebnahme von Legacy Pools zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b7311-115">Download [Uninstalling Microsoft legacy and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227) for comprehensive, step-by-step instructions on decommissioning legacy pools.</span></span>
  
<span data-ttu-id="b7311-116">Beim Verschieben von Konferenz Verzeichnissen kann die folgende Fehlermeldung auftreten:</span><span class="sxs-lookup"><span data-stu-id="b7311-116">When moving conference directories, you might encounter the following error:</span></span>
  
```
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

<span data-ttu-id="b7311-117">Dieser Fehler tritt in der Regel auf, wenn die Skype for Business Server-Verwaltungsshell eine aktualisierte Gruppe von Active Directory-Berechtigungen erfordert, um eine Aufgabe abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="b7311-117">This error typically occurs when the Skype for Business Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="b7311-118">Um das Problem zu beheben, schließen Sie die aktuelle Instanz der Verwaltungsshell, öffnen Sie dann eine neue Instanz der Shell, und führen Sie den Befehl erneut aus, um das Konferenzverzeichnis zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="b7311-118">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command to move the conference directory.</span></span>
  

