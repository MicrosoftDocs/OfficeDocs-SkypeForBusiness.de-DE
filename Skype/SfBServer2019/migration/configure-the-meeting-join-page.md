---
title: Konfigurieren der Seite für den Besprechungsbeitritt
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: End User
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Wenn ein Benutzer in einer Besprechungsanfrage auf einen Besprechungslink klickt, erkennt die Seite "Besprechungsteilnahme", welcher Client bereits auf dem Computer des Benutzers installiert ist. Wenn ein Client bereits installiert ist, wird dieser Client geöffnet und der Besprechung beitreten. Wenn ein Client nicht installiert ist, wird die Web-App standardmäßig geöffnet.
ms.openlocfilehash: 5c9e6653783d90411e0f701b5d3395c569d8bdff
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989560"
---
# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="12cb0-105">Konfigurieren der Seite für den Besprechungsbeitritt</span><span class="sxs-lookup"><span data-stu-id="12cb0-105">Configure the meeting join page</span></span>

<span data-ttu-id="12cb0-106">Wenn ein Benutzer in einer Besprechungsanfrage auf einen Besprechungslink klickt, erkennt die Seite "Besprechungsteilnahme", welcher Client bereits auf dem Computer des Benutzers installiert ist.</span><span class="sxs-lookup"><span data-stu-id="12cb0-106">When a user clicks a meeting link in a meeting request, the meeting join page detects which client is already installed on the user's computer.</span></span> <span data-ttu-id="12cb0-107">Wenn ein Client bereits installiert ist, wird dieser Client geöffnet und der Besprechung beitreten.</span><span class="sxs-lookup"><span data-stu-id="12cb0-107">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="12cb0-108">Wenn ein Client nicht installiert ist, wird die Web-App standardmäßig geöffnet.</span><span class="sxs-lookup"><span data-stu-id="12cb0-108">If a client is not installed, by default the Web App opens.</span></span>
  
<span data-ttu-id="12cb0-109">Sie können das Verhalten der Besprechungsteilnahme Seite ändern, wenn Sie Benutzern die Teilnahme an Besprechungen gestatten möchten.</span><span class="sxs-lookup"><span data-stu-id="12cb0-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings.</span></span> <span data-ttu-id="12cb0-110">Diese Konfigurationsoptionen wurden aus der Systemsteuerung entfernt, aber Sie werden mithilfe des CsWebServiceConfiguration-Cmdlets konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="12cb0-110">These configuration options have been removed from the Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="12cb0-111">**CsWebServiceConfiguration-Parameter für Besprechungsteilnehmer Seite**</span><span class="sxs-lookup"><span data-stu-id="12cb0-111">**Meeting Join Page CsWebServiceConfiguration Parameters**</span></span>

|<span data-ttu-id="12cb0-112">**CsWebServiceConfiguration-Parameter**</span><span class="sxs-lookup"><span data-stu-id="12cb0-112">**CsWebServiceConfiguration Parameter**</span></span>|<span data-ttu-id="12cb0-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="12cb0-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="12cb0-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="12cb0-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="12cb0-115">Wenn der Wert auf "true" festgelegt ist, wird Benutzern, die an einer Besprechung teilnehmen, mithilfe einer anderen Clientanwendung als lync die Möglichkeit gegeben, an der Besprechung teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="12cb0-115">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting.</span></span> <span data-ttu-id="12cb0-116">Der Standardwert lautet "False".</span><span class="sxs-lookup"><span data-stu-id="12cb0-116">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="12cb0-117">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="12cb0-117">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="12cb0-118">Wenn Sie auf "true" festgelegt ist, werden alternative Optionen für den Beitritt zu einer Onlinekonferenz automatisch erweitert und für die Benutzer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="12cb0-118">When set to True, alternate options for joining an online conference will automatically be expanded and shown to users.</span></span> <span data-ttu-id="12cb0-119">Bei Festlegung auf "false" (der Standardwert) sind diese Optionen verfügbar, der Benutzer muss jedoch die Liste der Optionen für sich selbst anzeigen.</span><span class="sxs-lookup"><span data-stu-id="12cb0-119">When set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="12cb0-120">So konfigurieren Sie die Seite "Besprechungsteilnahme" mithilfe der Skype for Business Server 2019-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="12cb0-120">To configure the meeting join page by using Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="12cb0-121">Starten Sie die Skype for Business Server 2019-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype for Business Server 2019**, und klicken Sie dann auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="12cb0-121">Start the Skype for Business Server 2019 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="12cb0-122">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="12cb0-122">Run the following cmdlet:</span></span> 
    
   ```PowerShell
   Get-CsWebServiceConfiguration
   ```

    <span data-ttu-id="12cb0-123">Dieses Cmdlet gibt die Konfigurationseinstellungen des Webdiensts zurück.</span><span class="sxs-lookup"><span data-stu-id="12cb0-123">This cmdlet returns the web service configuration settings.</span></span>
    
3. <span data-ttu-id="12cb0-124">Führen Sie den folgenden Befehl aus, wobei die Parameter je nach ihrer Einstellung auf "true" oder "false" festgelegt sind (Einzelheiten zu den Parametern für dieses Cmdlet finden Sie in der Dokumentation zur [Skype for Business Server-Verwaltungsshell](../../SfbServer/manage/management-shell.md) ):</span><span class="sxs-lookup"><span data-stu-id="12cb0-124">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the [Skype for Business Server Management Shell](../../SfbServer/manage/management-shell.md) documentation):</span></span>
    
   ```PowerShell
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


