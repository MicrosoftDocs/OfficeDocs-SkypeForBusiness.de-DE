---
title: Konfigurieren der Seite für den Besprechungsbeitritt
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: End User
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Wenn ein Benutzer in einer Besprechungsanfrage auf einen Besprechungslink klickt, wird auf der Seite für den besprechungsbeitritt ermittelt, welcher Client auf dem Computer des Benutzers bereits installiert ist. Ist bereits ein Client installiert, wird dieser Client geöffnet und für den Besprechungsbeitritt verwendet. Wenn ein Client nicht installiert ist, wird die Webanwendung standardmäßig geöffnet.
ms.openlocfilehash: a7bb0983438708bbc0d30cd527eb494491c3cbf2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754025"
---
# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="cf744-105">Konfigurieren der Seite für den Besprechungsbeitritt</span><span class="sxs-lookup"><span data-stu-id="cf744-105">Configure the meeting join page</span></span>

<span data-ttu-id="cf744-106">Wenn ein Benutzer in einer Besprechungsanfrage auf einen Besprechungslink klickt, wird auf der Seite für den besprechungsbeitritt ermittelt, welcher Client auf dem Computer des Benutzers bereits installiert ist.</span><span class="sxs-lookup"><span data-stu-id="cf744-106">When a user clicks a meeting link in a meeting request, the meeting join page detects which client is already installed on the user's computer.</span></span> <span data-ttu-id="cf744-107">Ist bereits ein Client installiert, wird dieser Client geöffnet und für den Besprechungsbeitritt verwendet.</span><span class="sxs-lookup"><span data-stu-id="cf744-107">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="cf744-108">Wenn ein Client nicht installiert ist, wird die Webanwendung standardmäßig geöffnet.</span><span class="sxs-lookup"><span data-stu-id="cf744-108">If a client is not installed, by default the Web App opens.</span></span>
  
<span data-ttu-id="cf744-109">Sie können das Verhalten der Seite für den besprechungsbeitritt ändern, wenn Sie zulassen möchten, dass Benutzer an Besprechungen teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="cf744-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings.</span></span> <span data-ttu-id="cf744-110">Diese Konfigurationsoptionen wurden aus der Systemsteuerung entfernt, Sie werden jedoch mithilfe des CsWebServiceConfiguration-Cmdlets konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="cf744-110">These configuration options have been removed from the Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="cf744-111">**CsWebServiceConfiguration-Parameter der Seite für den Besprechungsbeitritt**</span><span class="sxs-lookup"><span data-stu-id="cf744-111">**Meeting Join Page CsWebServiceConfiguration Parameters**</span></span>

|<span data-ttu-id="cf744-112">**CsWebServiceConfiguration-Parameter**</span><span class="sxs-lookup"><span data-stu-id="cf744-112">**CsWebServiceConfiguration Parameter**</span></span>|<span data-ttu-id="cf744-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="cf744-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cf744-114">"Showjoinusinglegacyclientlink"</span><span class="sxs-lookup"><span data-stu-id="cf744-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="cf744-115">Bei Festlegung auf "true" wird Benutzern, die einer Besprechung mit einer anderen Clientanwendung als lync beitreten, die Möglichkeit gegeben, an der Besprechung teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="cf744-115">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting.</span></span> <span data-ttu-id="cf744-116">Der Standardwert lautet "False".</span><span class="sxs-lookup"><span data-stu-id="cf744-116">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="cf744-117">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="cf744-117">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="cf744-118">Bei Festlegung auf "true" werden alternative Optionen für die Teilnahme an einer Onlinekonferenz automatisch erweitert und Benutzern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cf744-118">When set to True, alternate options for joining an online conference will automatically be expanded and shown to users.</span></span> <span data-ttu-id="cf744-119">Bei Festlegung auf "false" (Standardwert) sind diese Optionen verfügbar, aber der Benutzer muss die Liste der Optionen für sich selbst anzeigen.</span><span class="sxs-lookup"><span data-stu-id="cf744-119">When set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="cf744-120">So konfigurieren Sie die Seite für den besprechungsbeitritt mithilfe Skype for Business Server 2019-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="cf744-120">To configure the meeting join page by using Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="cf744-121">Starten Sie die Skype for Business Server 2019-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, dann auf **Microsoft Skype for Business Server 2019**, und klicken Sie dann auf **Skype for Business Server Verwaltungskonsole**.</span><span class="sxs-lookup"><span data-stu-id="cf744-121">Start the Skype for Business Server 2019 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="cf744-122">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="cf744-122">Run the following cmdlet:</span></span> 
    
   ```PowerShell
   Get-CsWebServiceConfiguration
   ```

    <span data-ttu-id="cf744-123">Dieses Cmdlet gibt die Konfigurationseinstellungen für den Webdienst zurück.</span><span class="sxs-lookup"><span data-stu-id="cf744-123">This cmdlet returns the web service configuration settings.</span></span>
    
3. <span data-ttu-id="cf744-124">Führen Sie den folgenden Befehl aus, wobei die Parameter abhängig von Ihren Einstellungen auf true oder false festgelegt sind (Ausführliche Informationen zu den Parametern für dieses Cmdlet finden Sie in der Dokumentation zur [Skype for Business Server Verwaltungsshell](../../SfbServer/manage/management-shell.md) ):</span><span class="sxs-lookup"><span data-stu-id="cf744-124">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the [Skype for Business Server Management Shell](../../SfbServer/manage/management-shell.md) documentation):</span></span>
    
   ```PowerShell
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


