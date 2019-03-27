---
title: Konfigurieren der Seite für den Besprechungsbeitritt
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: End User
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Wenn ein Benutzer klickt einen Link zur Besprechung in eine Besprechungsanfrage an der Besprechung teilnehmen Seite erkennt der Client bereits auf dem Computer des Benutzers installiert ist. Wenn ein Client bereits installiert ist, wird dieser Client wird geöffnet und der Besprechung teilnimmt. Wenn ein Client nicht installiert ist, wird standardmäßig geöffnet Web-App.
ms.openlocfilehash: 88ae915318505efef6ae716a17217aaa1e7b12df
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879940"
---
# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="39a3e-105">Konfigurieren der Seite für den Besprechungsbeitritt</span><span class="sxs-lookup"><span data-stu-id="39a3e-105">Configure the meeting join page</span></span>

<span data-ttu-id="39a3e-106">Wenn ein Benutzer klickt einen Link zur Besprechung in eine Besprechungsanfrage an der Besprechung teilnehmen Seite erkennt der Client bereits auf dem Computer des Benutzers installiert ist.</span><span class="sxs-lookup"><span data-stu-id="39a3e-106">When a user clicks a meeting link in a meeting request, the meeting join page detects which client is already installed on the user's computer.</span></span> <span data-ttu-id="39a3e-107">Wenn ein Client bereits installiert ist, wird dieser Client wird geöffnet und der Besprechung teilnimmt.</span><span class="sxs-lookup"><span data-stu-id="39a3e-107">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="39a3e-108">Wenn ein Client nicht installiert ist, wird standardmäßig geöffnet Web-App.</span><span class="sxs-lookup"><span data-stu-id="39a3e-108">If a client is not installed, by default the Web App opens.</span></span>
  
<span data-ttu-id="39a3e-109">Sie können das Verhalten der Teilnahme an einer Besprechung ändern Seite, wenn Sie Benutzer zur Teilnahme an Besprechungen zulassen möchten.</span><span class="sxs-lookup"><span data-stu-id="39a3e-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings.</span></span> <span data-ttu-id="39a3e-110">Diese Konfigurationsoptionen in der Systemsteuerung entfernt wurden, aber Sie mithilfe des Cmdlets "cswebserviceconfiguration" konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="39a3e-110">These configuration options have been removed from the Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="39a3e-111">**Parameter für den Besprechungsbeitritt Besprechungsbeitrittsseite**</span><span class="sxs-lookup"><span data-stu-id="39a3e-111">**Meeting Join Page CsWebServiceConfiguration Parameters**</span></span>

|<span data-ttu-id="39a3e-112">**CsWebServiceConfiguration-Parameter**</span><span class="sxs-lookup"><span data-stu-id="39a3e-112">**CsWebServiceConfiguration Parameter**</span></span>|<span data-ttu-id="39a3e-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="39a3e-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="39a3e-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="39a3e-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="39a3e-115">Wenn auf True festgelegt, teilnehmen an einer Besprechung mithilfe einer anderen Clientanwendung als Lync Benutzer die Möglichkeit, an der Besprechung teilzunehmen gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="39a3e-115">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting.</span></span> <span data-ttu-id="39a3e-116">Der Standardwert lautet "False".</span><span class="sxs-lookup"><span data-stu-id="39a3e-116">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="39a3e-117">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="39a3e-117">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="39a3e-118">Bei Festlegung auf true festgelegt ist, alternative Optionen für die Teilnahme an einer Konferenz online wird automatisch erweitert und anschließend den Benutzern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="39a3e-118">When set to True, alternate options for joining an online conference will automatically be expanded and shown to users.</span></span> <span data-ttu-id="39a3e-119">Bei Festlegung auf False (Standardwert), werden diese Optionen zur Verfügung stehen, aber der Benutzer muss die Liste der Optionen für sich selbst anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="39a3e-119">When set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="39a3e-120">So konfigurieren Sie die Besprechung teilnehmen Seite mithilfe von Skype für Business Server 2019-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="39a3e-120">To configure the meeting join page by using Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="39a3e-121">Starten Sie die Skype für Business Server 2019-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype für Business Server 2019**, und klicken Sie dann auf **Skype für Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="39a3e-121">Start the Skype for Business Server 2019 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="39a3e-122">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="39a3e-122">Run the following cmdlet:</span></span> 
    
   ```
   Get-CsWebServiceConfiguration
   ```

    <span data-ttu-id="39a3e-123">Dieses Cmdlet gibt die Konfigurationseinstellungen zurück.</span><span class="sxs-lookup"><span data-stu-id="39a3e-123">This cmdlet returns the web service configuration settings.</span></span>
    
3. <span data-ttu-id="39a3e-124">Führen Sie den folgenden Befehl ein, mit der Parameter auf True oder False, abhängig von Ihrer Präferenz (Ausführliche Informationen zu den Parametern für dieses Cmdlet finden Sie in der Dokumentation [Skype für Business Server-Verwaltungsshell](../../SfbServer/manage/management-shell.md) ):</span><span class="sxs-lookup"><span data-stu-id="39a3e-124">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the [Skype for Business Server Management Shell](../../SfbServer/manage/management-shell.md) documentation):</span></span>
    
   ```
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


