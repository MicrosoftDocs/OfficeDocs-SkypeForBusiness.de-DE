---
title: 'Lync Server 2013: Anzeigen von Besprechungs Konfigurationseinstellungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View meeting configuration settings
ms:assetid: d03a4684-9d8b-4728-917d-5b5c91511e2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721894(v=OCS.15)
ms:contentKeyID: 49733828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9ad61f93cd7c65be04d30cf35638019ddc7ee58
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506332"
---
# <a name="view-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="5fbe9-102">Anzeigen von Besprechungs Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fbe9-102">View meeting configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5fbe9-103">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="5fbe9-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="5fbe9-104">In lync Server 2013 Systemsteuerung verwenden Sie die Einstellung für die besprechungskonfiguration, um zu steuern, wie Besprechungen in Ihrer Bereitstellung implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="5fbe9-104">In Lync Server 2013 Control Panel, you use meeting configuration setting to control how meetings are implemented in your deployment.</span></span> <span data-ttu-id="5fbe9-105">Dies umfasst die folgenden Besprechungs Konfigurationen:</span><span class="sxs-lookup"><span data-stu-id="5fbe9-105">This includes the following meeting configurations:</span></span>

  - <span data-ttu-id="5fbe9-106">Eine globale Konfiguration, die standardmäßig erstellt wird, wenn Sie lync Server 2013 bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="5fbe9-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="5fbe9-107">Optionale Konfigurationen auf Standort-und Benutzerebene, die Sie erstellen und verwenden können, um anzugeben, wie Besprechungen für bestimmte Websites oder Benutzer implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="5fbe9-107">Optional site-level and user-level configurations that you can create and use to specify how meetings are implemented for specific sites or users.</span></span>

<div>

## <a name="to-view-meeting-configuration-settings"></a><span data-ttu-id="5fbe9-108">So zeigen Sie die Besprechungs Konfigurationseinstellungen an</span><span class="sxs-lookup"><span data-stu-id="5fbe9-108">To view meeting configuration settings</span></span>

1.  <span data-ttu-id="5fbe9-109">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="5fbe9-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5fbe9-110">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="5fbe9-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5fbe9-111">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5fbe9-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5fbe9-112">Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und dann auf **Besprechungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="5fbe9-112">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="5fbe9-113">Klicken Sie auf der Seite **besprechungskonfiguration** auf die besprechungskonfiguration, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="5fbe9-113">On the **Meeting Configuration** page, click the meeting configuration that you would like to view.</span></span>

5.  <span data-ttu-id="5fbe9-114">Wählen Sie unter **Datei Filter bearbeiten**die Option **Details anzeigen aus.**</span><span class="sxs-lookup"><span data-stu-id="5fbe9-114">In **Edit File Filter**, select the **Show Details…**</span></span> <span data-ttu-id="5fbe9-115">Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="5fbe9-115">check box.</span></span>
    
    <span data-ttu-id="5fbe9-116">**Bearbeiten der besprechungskonfiguration \<policy\> –** Öffnet die Anzeige der Einstellungen für die ausgewählte Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="5fbe9-116">**Edit Meeting Configuration - \<policy\>** opens displaying the settings for the selected policy.</span></span> <span data-ttu-id="5fbe9-117">Ausführliche Informationen zum Konfigurieren der Einstellungen finden Sie unter [erstellen oder Ändern einer Sammlung von Besprechungs Konfigurationseinstellungen in lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="5fbe9-117">For details about configuring the settings, see [Create or modify a collection of meeting configuration settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span></span>

</div>

<div>

## <a name="viewing-meeting-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5fbe9-118">Anzeigen von Besprechungs Konfigurationsinformationen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="5fbe9-118">Viewing Meeting Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5fbe9-119">Die Besprechungs Konfigurationseinstellungen können mithilfe von Windows PowerShell und dem Get-CsMeetingConfiguration-Cmdlet angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5fbe9-119">Meeting configuration settings can be viewed by using Windows PowerShell and the Get-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="5fbe9-120">Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5fbe9-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="5fbe9-121">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="5fbe9-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-meeting-configuration-information"></a><span data-ttu-id="5fbe9-122">So zeigen Sie Besprechungs Konfigurationsinformationen an</span><span class="sxs-lookup"><span data-stu-id="5fbe9-122">To view meeting configuration information</span></span>

  - <span data-ttu-id="5fbe9-123">Wenn Sie Informationen zu allen Besprechungs Konfigurationseinstellungen anzeigen möchten, geben Sie den folgenden Befehl in das lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="5fbe9-123">To view information about all your meeting configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsMeetingConfiguration
    
    <span data-ttu-id="5fbe9-124">Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:</span><span class="sxs-lookup"><span data-stu-id="5fbe9-124">That will return information similar to this:</span></span>
    
        Identity                        : Global
        PstnCallersBypassLobby          : True
        EnableAssignedConferenceType    : True
        DesignateAsPresenter            : Company
        AssignedConferenceTypeByDefault : True
        AdmitAnonymousUsersByDefault    : True
        RequireRoomSystemsAuthorization : False
        LogoURL                         :
        LegalURL                        :
        HelpURL                         :
        CustomFooterText                :
        AllowConferenceRecording        : True

</div>

<span data-ttu-id="5fbe9-125">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="5fbe9-125">For more information, see the help topic for the [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

