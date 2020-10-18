---
title: Erstellen oder Ändern einer Sammlung von Besprechungs Konfigurationseinstellungen
description: Erstellen oder ändern Sie eine Sammlung von Besprechungs Konfigurationseinstellungen.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of meeting configuration settings
ms:assetid: ce6773c1-a0d5-4405-8e32-33a6f3a46a1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721889(v=OCS.15)
ms:contentKeyID: 49733822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51dd68b3d149e5a96628fc3343d0d7eb3ae8020d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578241"
---
# <a name="create-or-modify-a-collection-of-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="a39de-103">Erstellen oder Ändern einer Sammlung von Besprechungs Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a39de-103">Create or modify a collection of meeting configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a39de-104">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="a39de-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="a39de-105">Sie können die Einstellungen auf der Seite besprechungskonfiguration verwenden, um verschiedene Merkmale der Besprechungsteilnahme zu definieren.</span><span class="sxs-lookup"><span data-stu-id="a39de-105">You can use the settings on the Meeting Configuration page to define various characteristics of the meeting join experience.</span></span> <span data-ttu-id="a39de-106">Standardmäßig definieren die globalen Einstellungen die Verknüpfungs Umgebung.</span><span class="sxs-lookup"><span data-stu-id="a39de-106">By default, the global settings define the join experience.</span></span> <span data-ttu-id="a39de-107">Sie können auch Besprechungs Verknüpfungseinstellungen auf Websiteebene und Poolebene erstellen.</span><span class="sxs-lookup"><span data-stu-id="a39de-107">You can also create site-level and pool-level meeting join settings.</span></span> <span data-ttu-id="a39de-108">Wenn Sie Einstellungen auf Poolebene erstellen, gelten diese Einstellungen für alle Besprechungen, die von diesem Pool gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="a39de-108">If you create pool-level settings, those settings apply to all meetings hosted by that pool.</span></span> <span data-ttu-id="a39de-109">Wenn Sie keine Einstellungen auf Poolebene erstellen, gelten die Einstellungen auf Websiteebene, sofern vorhanden.</span><span class="sxs-lookup"><span data-stu-id="a39de-109">If you do not create pool-level settings, site-level settings apply, if they exist.</span></span> <span data-ttu-id="a39de-110">Wenn Sie keine Einstellungen auf Websiteebene definieren, gelten die globalen Einstellungen für alle Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="a39de-110">If you do not define site-level settings, the global settings apply to all meetings.</span></span>

<div>

## <a name="to-create-new-meeting-join-settings"></a><span data-ttu-id="a39de-111">So erstellen Sie neue Einstellungen für den besprechungsbeitritt</span><span class="sxs-lookup"><span data-stu-id="a39de-111">To create new meeting join settings</span></span>

1.  <span data-ttu-id="a39de-112">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="a39de-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a39de-113">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a39de-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a39de-114">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a39de-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a39de-115">Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und dann auf **Besprechungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="a39de-115">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="a39de-116">Klicken Sie auf der Seite **besprechungskonfiguration** auf **neu**, und führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="a39de-116">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="a39de-117">Klicken Sie auf **Websitekonfiguration**, um eine Richtlinie auf Standortebene zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a39de-117">To create a site-level policy, click **Site configuration**.</span></span> <span data-ttu-id="a39de-118">Geben Sie im Feld **Website Suche auswählen** den vollständigen oder Teil des Namens der Website ein, für die Sie die Einstellungen für den besprechungsbeitritt definieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a39de-118">In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings.</span></span> <span data-ttu-id="a39de-119">Klicken Sie in der resultierenden Liste der Standorte auf den gewünschten Standort, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a39de-119">In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="a39de-120">Klicken Sie zum Erstellen einer Richtlinie auf Poolebene auf **Poolkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="a39de-120">To create a pool-level policy, click **Pool configuration**.</span></span> <span data-ttu-id="a39de-121">Geben Sie im Suchfeld **Dienst auswählen einen** Teil oder den vollständigen Namen des Pool Diensts ein, für den Sie die Einstellungen für den besprechungsbeitritt definieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a39de-121">In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings.</span></span> <span data-ttu-id="a39de-122">Klicken Sie in der daraufhin angezeigten Liste mit den Diensten auf den gewünschten Pool, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a39de-122">In the resulting list of services, click the pool you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="a39de-p105">Deaktivieren Sie das Kontrollkästchen **PSTN-Anrufer umgehen Lobby**, um Teilnehmer, die sich über das Festnetz einwählen, zunächst an die Lobby weiterzuleiten. In der Standardeinstellung gelangen Anrufer, die sich über das Festnetz einwählen, direkt zur Besprechung.</span><span class="sxs-lookup"><span data-stu-id="a39de-p105">To route participants who dial in from the public switched telephone network (PSTN) through the lobby, clear the **PSTN callers bypass lobby** check box. By default, participants dialing in from the PSTN go directly to the meeting.</span></span>

6.  <span data-ttu-id="a39de-125">Legen Sie im Abschnitt **Als Referent benennen** fest, wer in der Besprechung als Referent agieren kann:</span><span class="sxs-lookup"><span data-stu-id="a39de-125">To configure who can be a presenter in the meeting, in **Designate as presenter**, do one of the following:</span></span>
    
      - <span data-ttu-id="a39de-126">Klicken Sie auf **Keiner**, um nur dem Organisator die Rolle des Referenten zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="a39de-126">To not allow anyone other than the organizer to be a presenter, click **None**.</span></span>
    
      - <span data-ttu-id="a39de-p106">Klicken Sie auf **Unternehmen**, um nur denjenigen Teilnehmern die Funktion des Referenten zu ermöglichen, die Mitglieder Ihrer Organisation sind. Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="a39de-p106">To allow only participants who are members of your organization to be a presenter, click **Company**. This is the default setting.</span></span>
    
      - <span data-ttu-id="a39de-129">Klicken Sie auf **Jeder**, um allen Teilnehmern das Agieren als Referent zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a39de-129">To allow any participants to be a presenter, click **Everyone**.</span></span>

7.  <span data-ttu-id="a39de-p107">Wenn der Organisator bei der Planung einer Besprechung einen Konferenztyp auswählen soll, deaktivieren Sie das Kontrollkästchen **Konferenztyp standardmäßig zuweisen**. In der Standardeinstellung wird der Konferenztyp automatisch zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="a39de-p107">To have the organizer select a conference type when scheduling a meeting, clear the **Assigned conference type by default** check box. By default, the conference type is automatically assigned.</span></span>

8.  <span data-ttu-id="a39de-p108">Wenn Sie verhindern möchten, dass anonyme (nicht authentifizierte) Benutzer automatisch zugelassen werden, deaktivieren Sie das Kontrollkästchen **Anonyme Benutzer standardmäßig zulassen**. In der Standardeinstellung werden anonyme Benutzer automatisch für Besprechungen zugelassen.</span><span class="sxs-lookup"><span data-stu-id="a39de-p108">To prevent anonymous (unauthenticated) users from being automatically admitted, clear the **Admit anonymous users by default** check box. By default, anonymous users are automatically admitted to meetings.</span></span>

9.  <span data-ttu-id="a39de-134">Gehen Sie folgendermaßen vor, um die Besprechungseinladung anzupassen, die an die Teilnehmer gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="a39de-134">To customize the meeting invite that is sent out to participants, do the following.</span></span> <span data-ttu-id="a39de-135">Beachten Sie, dass die maximale Länge für URLs und benutzerdefinierter Fußzeilentext 1KB ist.</span><span class="sxs-lookup"><span data-stu-id="a39de-135">Note that the maximum length for URLs and custom footer text is 1KB.</span></span> <span data-ttu-id="a39de-136">Wenn Sie für die Anpassungen keinen Wert angeben, werden diese nicht in die Besprechung aufgenommen, außer bei der **Hilfe-URL**.</span><span class="sxs-lookup"><span data-stu-id="a39de-136">Except for **Help URL**, if you do not specify a value for the customizations, they will not be included in the meeting.</span></span> <span data-ttu-id="a39de-137">Wenn Sie keine benutzerdefinierte Hilfe-URL einschließen, wird die standardmäßige Hilfe-URL für lync in der Einladung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a39de-137">If you do not include a custom help URL, the default help URL for Lync will be displayed in the invite.</span></span>
    
      - <span data-ttu-id="a39de-138">Um das Logo anzupassen, das in der Besprechungseinladung angezeigt wird, geben Sie in **Logo-URL**den Speicherort des Logos ein.</span><span class="sxs-lookup"><span data-stu-id="a39de-138">To customize the logo that appears in the meeting invite, in **Logo URL**, enter the location of the logo.</span></span>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="a39de-139">Das Logo muss ein GIF-oder JPG-Bild mit einer Größe von 188 x 30 Pixel sein.</span><span class="sxs-lookup"><span data-stu-id="a39de-139">The logo must be a GIF or JPG image with a size of 188 by 30 pixels.</span></span>

        
        </div>
    
      - <span data-ttu-id="a39de-140">Um den Hilfetext anzupassen, der in der Besprechungseinladung angezeigt wird, geben Sie in der **Hilfe-URL**den Speicherort des Hilfetexts ein.</span><span class="sxs-lookup"><span data-stu-id="a39de-140">To customize the help text that appears in the meeting invite, in **Help URL**, enter the location of the help text.</span></span>
    
      - <span data-ttu-id="a39de-141">Um den rechtlichen Text anzupassen, der in der Besprechungseinladung angezeigt wird, geben Sie unter **rechtlicher Text**die Adresse des rechtlichen Texts ein.</span><span class="sxs-lookup"><span data-stu-id="a39de-141">To customize the legal text that appears in the meeting invite, in **Legal text URL**, enter the location of the legal text.</span></span>
    
      - <span data-ttu-id="a39de-142">Zum Anpassen des Fußzeilentexts, der in der Besprechungseinladung angezeigt wird, geben Sie in **benutzerdefinierter Fußzeilen**Text Text ein.</span><span class="sxs-lookup"><span data-stu-id="a39de-142">To customize the footer text that appears in the meeting invite, in **Custom footer text**, enter text.</span></span>

10. <span data-ttu-id="a39de-143">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="a39de-143">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-collection-of-meeting-configurations"></a><span data-ttu-id="a39de-144">So ändern Sie eine vorhandene Sammlung von Besprechungs Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="a39de-144">To modify an existing collection of meeting configurations</span></span>

1.  <span data-ttu-id="a39de-145">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="a39de-145">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a39de-146">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a39de-146">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a39de-147">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a39de-147">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a39de-148">Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und dann auf **Besprechungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="a39de-148">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="a39de-149">Klicken Sie in der Liste der Besprechungs Konfigurationen auf die Konfiguration, die Sie ändern möchten, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="a39de-149">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="a39de-150">Ändern Sie in **besprechungskonfiguration bearbeiten**alle Konfigurationseinstellungen außer dem Konfigurationsnamen, der nicht geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="a39de-150">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>

6.  <span data-ttu-id="a39de-151">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="a39de-151">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-new-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a39de-152">Erstellen neuer Besprechungs Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="a39de-152">Creating New Meeting Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a39de-153">Besprechungs Konfigurationseinstellungen können (nur auf Standortebene) mithilfe von Windows PowerShell und dem New-CsMeetingConfiguration-Cmdlet erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="a39de-153">Meeting configuration settings can be created (at the site scope only) by using Windows PowerShell and the New-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="a39de-154">Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a39de-154">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a39de-155">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="a39de-155">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-meeting-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="a39de-156">So erstellen Sie Besprechungs Konfigurationseinstellungen, die die Standardwerte verwenden</span><span class="sxs-lookup"><span data-stu-id="a39de-156">To create meeting configuration settings that use the default values</span></span>

  - <span data-ttu-id="a39de-157">Mit diesem Befehl wird eine neue Gruppe von Besprechungs Konfigurationseinstellungen für den Standort "Redmond" erstellt:</span><span class="sxs-lookup"><span data-stu-id="a39de-157">This command creates a new set of meeting configuration settings for the Redmond site:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="a39de-158">Da im vorherigen Befehl keine Parameter (außer dem obligatorischen Identity-Parameter) angegeben wurden, werden in den neuen Besprechungs Konfigurationseinstellungen die Standardwerte für alle Eigenschaften verwendet.</span><span class="sxs-lookup"><span data-stu-id="a39de-158">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new meeting configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-property-value-when-creating-meeting-configuration-settings"></a><span data-ttu-id="a39de-159">So ändern Sie einen Eigenschaftswert beim Erstellen von Besprechungs Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="a39de-159">To change a property value when creating meeting configuration settings</span></span>

  - <span data-ttu-id="a39de-160">Zum Erstellen von Einstellungen, die verschiedene Eigenschaftswerte verwenden, geben Sie einfach den entsprechenden Parameter und den Parameterwert an.</span><span class="sxs-lookup"><span data-stu-id="a39de-160">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="a39de-161">Um beispielsweise eine Sammlung von Besprechungs Konfigurationseinstellungen zu erstellen, die standardmäßig jeder zu einer Besprechung als Referent zulässt, verwenden Sie einen Befehl wie den folgenden:</span><span class="sxs-lookup"><span data-stu-id="a39de-161">For example, to create a collection of meeting configuration settings that, by default, admit everyone to a meeting as a presenter use a command like this:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-meeting-configuration-settings"></a><span data-ttu-id="a39de-162">So ändern Sie beim Erstellen von Besprechungs Konfigurationseinstellungen mehrere Eigenschaftswerte</span><span class="sxs-lookup"><span data-stu-id="a39de-162">To change multiple property values when creating meeting configuration settings</span></span>

  - <span data-ttu-id="a39de-163">Mehrere Eigenschaftswerte können durch die Angabe mehrerer Parameter geändert werden.</span><span class="sxs-lookup"><span data-stu-id="a39de-163">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="a39de-164">Dieser Befehl gibt beispielsweise alle Personen zu einer Besprechung als Referenten an und zwingt PSTN-Benutzer dazu, in der Lobby zu warten, bis Sie offiziell zur Besprechung zugelassen sind:</span><span class="sxs-lookup"><span data-stu-id="a39de-164">For example, this command admits everyone to a meeting as a presenter and also forces PSTN users to wait in the lobby until they are formally admitted to the meeting:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True

</div>

<span data-ttu-id="a39de-165">Weitere Informationen finden Sie im Hilfethema zum [New-CsMeetingConfiguration-](https://technet.microsoft.com/library/Gg398065(v=OCS.15)) Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a39de-165">For more information, see the help topic for the [New-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

