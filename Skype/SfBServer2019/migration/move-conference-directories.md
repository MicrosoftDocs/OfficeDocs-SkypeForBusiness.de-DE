---
title: Verschieben von Konferenzverzeichnissen
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vor der Außerbetriebnahme eines Pools müssen Sie das folgende Verfahren für jedes Konferenzverzeichnis im vorversionspool ausführen.
ms.openlocfilehash: b7526d8c3c032bf8b1f9052dce7da7e8a87b66b5
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372805"
---
# <a name="move-conference-directories"></a><span data-ttu-id="c9599-103">Verschieben von Konferenzverzeichnissen</span><span class="sxs-lookup"><span data-stu-id="c9599-103">Move Conference Directories</span></span>

<span data-ttu-id="c9599-104">Vor der Außerbetriebnahme eines Pools müssen Sie das folgende Verfahren für jedes Konferenzverzeichnis im vorversionspool ausführen.</span><span class="sxs-lookup"><span data-stu-id="c9599-104">Before decommissioning a pool, you must perform the following procedure for each conference directory in your legacy pool.</span></span>
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a><span data-ttu-id="c9599-105">So verschieben Sie ein Konferenzverzeichnis zu Skype für Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="c9599-105">To Move a Conference Directory to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="c9599-106">Öffnen Sie die Skype für Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="c9599-106">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="c9599-107">Um die Identität der konferenzverzeichnisse in Ihrer Organisation zu beziehen, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c9599-107">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
   ```
   Get-CsConferenceDirectory
   ```

    <span data-ttu-id="c9599-108">Mit dem vorstehende Befehl werden alle konferenzverzeichnisse in Ihrer Organisation zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c9599-108">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="c9599-109">Aus diesem Grund möchten Sie möglicherweise das Begrenzen der Ergebnisse an den Pool wird außer Betrieb genommen.</span><span class="sxs-lookup"><span data-stu-id="c9599-109">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="c9599-110">Wenn Sie den Pool mit den vollqualifizierten Domänennamen (FQDN) Namen pool01.contoso.net außer Betrieb nehmen, verwenden Sie diesen Befehl zum Begrenzen der zurückgegebenen Daten auf konferenzverzeichnisse aus diesem Pool fest:</span><span class="sxs-lookup"><span data-stu-id="c9599-110">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    <span data-ttu-id="c9599-111">Dieser Befehl gibt nur die konferenzverzeichnisse zurück, bei denen die ServiceID-Eigenschaft den FQDN pool01.contoso.net enthält.</span><span class="sxs-lookup"><span data-stu-id="c9599-111">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>
    
3. <span data-ttu-id="c9599-112">Wenn konferenzverzeichnisse verschieben möchten, führen Sie den folgenden Befehl für jedes Konferenzverzeichnis im Pool:</span><span class="sxs-lookup"><span data-stu-id="c9599-112">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
   ```
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    <span data-ttu-id="c9599-113">Beispielsweise wenn Konferenzverzeichnis 3 verschieben möchten, verwenden Sie diesen Befehl: Angeben einer Skype für Business Server 2019 Pool als die TargetPool an:</span><span class="sxs-lookup"><span data-stu-id="c9599-113">For example, to move conference directory 3, use this command, specifying a Skype for Business Server 2019 pool as the TargetPool:</span></span>
    
   ```
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    <span data-ttu-id="c9599-114">Wenn Sie alle konferenzverzeichnisse in einem Pool verschieben möchten, verwenden Sie einen Befehl ähnlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="c9599-114">If you want to move all the conference directories on a pool, use a command similar to the following:</span></span>
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

<span data-ttu-id="c9599-115">Laden Sie [Microsoft legacy deinstallieren und Entfernen von Serverrollen](https://go.microsoft.com/fwlink/p/?linkId=246227) umfassende, schrittweisen Anweisungen Außerbetriebnahme von alten Pools.</span><span class="sxs-lookup"><span data-stu-id="c9599-115">Download [Uninstalling Microsoft legacy and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227) for comprehensive, step-by-step instructions on decommissioning legacy pools.</span></span>
  
<span data-ttu-id="c9599-116">Beim Verschieben von konferenzverzeichnissen, können Sie den folgenden Fehler auftreten:</span><span class="sxs-lookup"><span data-stu-id="c9599-116">When moving conference directories, you might encounter the following error:</span></span>
  
```
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

<span data-ttu-id="c9599-117">Dieser Fehler tritt normalerweise auf, wenn die Skype für Business Server-Verwaltungsshell eine aktualisierte Menge von Active Directory-Berechtigungen für die Durchführung eine Aufgabe erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="c9599-117">This error typically occurs when the Skype for Business Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="c9599-118">Um das Problem zu beheben, schließen Sie die aktuelle Instanz der-Verwaltungsshell, und klicken Sie dann öffnen Sie eine neue Instanz der Shell, und führen Sie den Befehl aus, um das Konferenzverzeichnis verschieben erneut aus.</span><span class="sxs-lookup"><span data-stu-id="c9599-118">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command to move the conference directory.</span></span>
  

