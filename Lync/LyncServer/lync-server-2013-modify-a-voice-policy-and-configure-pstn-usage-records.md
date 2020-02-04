---
title: 'Lync Server 2013: Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a voice policy and configure PSTN usage records
ms:assetid: 6c53aaf5-218b-4bd4-8cea-31bc9d53f1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398511(v=OCS.15)
ms:contentKeyID: 48184419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dda549bbb8b1f29a3aef8690a8e666e7a182bd29
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737165"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="3af93-102">Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3af93-102">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3af93-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3af93-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3af93-104">Führen Sie die folgenden Schritte aus, wenn Sie eine VoIP-Richtlinie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="3af93-104">Follow these steps if you want to modify a voice policy.</span></span> <span data-ttu-id="3af93-105">Wenn Sie eine neue VoIP-Richtlinie erstellen möchten, lesen Sie [Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md) für das Verfahren.</span><span class="sxs-lookup"><span data-stu-id="3af93-105">If you want to create a new voice policy, see [Create a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md) for the procedure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3af93-106">Wenn ein Benutzer einer VoIP-Richtlinie zugewiesen ist, die keine zugehörigen PSTN-Nutzungsdatensätze (Public Switched Telephone Network) hat, kann der Benutzer keine ausgehenden Anrufe tätigen.</span><span class="sxs-lookup"><span data-stu-id="3af93-106">If a user is assigned to a voice policy has no associated public switched telephone network (PSTN) usage records, the user cannot place outbound calls.</span></span> <span data-ttu-id="3af93-107">Eine Auflistung aller für Ihre Enterprise-VoIP-Bereitstellung verfügbaren PSTN-Nutzungsdatensätze und Anzeigen der zugehörigen Eigenschaften finden Sie unter <A href="lync-server-2013-view-pstn-usage-records.md">Anzeigen von PSTN-Nutzungsdaten Sätzen in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3af93-107">For a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-modify-a-voice-policy"></a><span data-ttu-id="3af93-108">So ändern Sie eine VoIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="3af93-108">To modify a voice policy</span></span>

1.  <span data-ttu-id="3af93-109">Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an.</span><span class="sxs-lookup"><span data-stu-id="3af93-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="3af93-110">Ausführliche Informationen finden Sie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="3af93-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="3af93-111">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3af93-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3af93-112">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3af93-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3af93-113">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und anschließend auf **VoIP-Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="3af93-113">In the left navigation bar, click **Voice Routing**, and then click **Voice Policy**.</span></span>

4.  <span data-ttu-id="3af93-114">Doppelklicken Sie auf der Seite **VoIP-Richtlinie** auf den Namen einer VoIP-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="3af93-114">On the **Voice Policy** page, double-click a voice policy name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3af93-p105">Der Bereich und der Name wurden bei Erstellung der VoIP-Richtlinie festgelegt. Sie können nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="3af93-p105">The scope and name were set when the voice policy was created. They cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="3af93-117">(Optional) Geben Sie in **VoIP-Richtlinie bearbeiten** zusätzliche Informationen zur Beschreibung der VoIP-Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="3af93-117">(Optional) In **Edit Voice Policy**, enter additional descriptive information for the voice policy.</span></span>

6.  <span data-ttu-id="3af93-118">Aktivieren oder deaktivieren Sie die folgenden Kontrollkästchen, um die einzelnen **Anruffunktionen** zu aktivieren bzw. zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="3af93-118">Select or clear the following check boxes to enable or disable each of the **Calling features**:</span></span>
    
      - <span data-ttu-id="3af93-119">**Voicemail-Escape** verhindert, dass Anrufe sofort an das Voicemail-System des Mobiltelefons des Benutzers weitergeleitet werden, wenn das gleichzeitige Klingeln konfiguriert ist und das Handy ausgeschaltet, entladen oder ohne Netz ist.</span><span class="sxs-lookup"><span data-stu-id="3af93-119">**Voice mail escape** prevents calls from being immediately routed to the user’s mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="3af93-120">Dieses Feature kann nur über die lync Server-Verwaltungsshell konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="3af93-120">This feature is only configurable through the Lync Server Management Shell</span></span>

        
        </div>
    
      - <span data-ttu-id="3af93-121">**Anrufweiterleitung** ermöglicht Benutzern das Weiterleiten von Anrufen an andere Telefone und Clientgeräte.</span><span class="sxs-lookup"><span data-stu-id="3af93-121">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="3af93-122">Lync Server 2013 bietet eine wesentlich größere Auswahl an Konfigurationsoptionen für die Anrufweiterleitung.</span><span class="sxs-lookup"><span data-stu-id="3af93-122">Lync Server 2013 provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="3af93-123">Wenn z. B. eine Organisation nicht möchte, dass eingehende Anrufe extern an das Festnetz (Public Switched Telephone Network, PSTN) weitergeleitet werden, kann ein Administrator eine spezielle VoIP-Richtlinie anwenden, um diese Einschränkungen durchzusetzen.</span><span class="sxs-lookup"><span data-stu-id="3af93-123">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="3af93-124">Diese Option ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3af93-124">Enabled by default.</span></span>
    
      - <span data-ttu-id="3af93-125">**Delegierung** ermöglicht Benutzern die Angabe anderer Benutzer, die in ihrem Namen Anrufe tätigen und empfangen können.</span><span class="sxs-lookup"><span data-stu-id="3af93-125">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="3af93-126">In lync Server 2013 kann eine Stellvertretung das gleichzeitige Klingeln konfigurieren, mit dem eingehende Anrufe an seinen Manager alle gleichzeitigen Klingel Ziele der Stellvertretung anrufen können.</span><span class="sxs-lookup"><span data-stu-id="3af93-126">In Lync Server 2013, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate’s simultaneous ringing targets.</span></span> <span data-ttu-id="3af93-127">Dies bietet dem Stellvertreter eine größere Flexibilität bei der Reaktion auf Anrufe, die an den Manager weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="3af93-127">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="3af93-128">Diese Option ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3af93-128">Enabled by default.</span></span>
    
      - <span data-ttu-id="3af93-p108">**Anrufdurchstellung** ermöglicht Benutzern, Anrufe an andere Benutzer durchzustellen. Diese Option ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3af93-p108">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>
    
      - <span data-ttu-id="3af93-p109">**Anruf parken** ermöglicht es Benutzern, Anrufe in der Warteschleife zu parken und den Anruf anschließend von einem anderen Telefon oder Client aus wiederaufzunehmen. Diese Option ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="3af93-p109">**Call park** enables users to park calls on hold, and then pick up the call from a different phone or client. Disabled by default.</span></span>
    
      - <span data-ttu-id="3af93-133">**Gleichzeitiges Klingeln** ermöglicht bei eingehenden Anrufen das gleichzeitige Klingeln auf zusätzlichen Telefonen (z. B. einem Mobiltelefon) oder anderen Endpunktgeräten.</span><span class="sxs-lookup"><span data-stu-id="3af93-133">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="3af93-134">Lync Server 2013 bietet eine wesentlich größere Auswahl an Konfigurationsoptionen für das gleichzeitige Klingeln.</span><span class="sxs-lookup"><span data-stu-id="3af93-134">Lync Server 2013 provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="3af93-135">Diese Option ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3af93-135">Enabled by default.</span></span>
    
      - <span data-ttu-id="3af93-136">**Teamanruf** ermöglicht Benutzern in einem definierten Team die Annahme von Anrufen für andere Teammitglieder.</span><span class="sxs-lookup"><span data-stu-id="3af93-136">**Team call** enables users on a defined team to answer calls for other members of the team.</span></span> <span data-ttu-id="3af93-137">Diese Option ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3af93-137">Enabled by default.</span></span>
    
      - <span data-ttu-id="3af93-138">Durch **PSTN-Umleitungen** können Anrufe von Benutzern, denen diese Richtlinie zugewiesen ist, an andere Unternehmensbenutzer weitergeleitet werden, wenn das WAN überlastet ist oder nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="3af93-138">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable.</span></span> <span data-ttu-id="3af93-139">Diese Option ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3af93-139">Enabled by default.</span></span>
    
      - <span data-ttu-id="3af93-140">Die **Überschreibung von Bandbreitenrichtlinien** ermöglicht Administratoren das außer Kraft setzen von Richtlinien Entscheidungen zur Anrufannahme Steuerung für einen bestimmten Benutzer.</span><span class="sxs-lookup"><span data-stu-id="3af93-140">**Bandwidth policy override** enables administrators to override call admission control (CAC) policy decisions for a particular user.</span></span> <span data-ttu-id="3af93-141">Diese ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="3af93-141">Disabled by default.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="3af93-p114">Die Richtlinie wird nur für eingehende Anrufe an den Benutzer, nicht jedoch für ausgehende Anrufe außer Kraft gesetzt, die vom Benutzer getätigt werden. Nachdem die Sitzung hergestellt wurde, wird die Bandbreitenauslastung genau aufgezeichnet. Diese Einstellung sollte sparsam verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3af93-p114">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user. After the session is established, the bandwidth consumption will be accurately recorded. This setting should be used sparingly.</span></span>

        
        </div>
    
      - <span data-ttu-id="3af93-145">Durch eine **böswillige Anrufprotokollierung** können Benutzer bösartige Anrufe (wie Bombendrohungen) mithilfe der Client-UI melden, die wiederum die Anrufe in den Anruf Detaildatensätzen (CDRs) kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="3af93-145">**Malicious call tracing** enables users to report malicious calls (such as bomb threats) using the client UI, which in turn flags the calls in the call detail records (CDRs).</span></span> <span data-ttu-id="3af93-146">Diese Option ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="3af93-146">Disabled by default.</span></span>

7.  <span data-ttu-id="3af93-147">Führen Sie eine der folgenden Aktionen aus, um PSTN-Verwendungseinträge für diese VoIP-Richtlinie zuzuordnen und zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="3af93-147">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="3af93-p116">Klicken Sie auf **Auswählen**, um einen oder mehrere Einträge aus einer Liste aller PSTN-Verwendungseinträge auszuwählen, die für Ihre Enterprise-VoIP-Bereitstellung zur Verfügung stehen. Markieren Sie die Einträge, die Sie dieser VoIP-Richtlinie zuordnen möchten und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3af93-p116">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**. Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>
    
      - <span data-ttu-id="3af93-150">Markieren Sie einen Eintrag und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungseintrag aus der VoIP-Richtlinie zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="3af93-150">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="3af93-151">Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungseintrag zu definieren und dieser VoIP-Richtlinie zuzuordnen:</span><span class="sxs-lookup"><span data-stu-id="3af93-151">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="3af93-152">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="3af93-152">Click **New**.</span></span>
        
        2.  <span data-ttu-id="3af93-p117">Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Datensatz ein. Sie könnten beispielsweise einen PSTN-Verwendungsdatensatz namens **Redmond** für Vollzeitbeschäftigte in Redmond und einen weiteren Datensatz namens **RedmondTemps** für Mitarbeiter mit Zeitverträgen erstellen.</span><span class="sxs-lookup"><span data-stu-id="3af93-p117">In the **Name** field, enter a unique descriptive name for the record. For example, you may want to create a PSTN usage record named **Redmond** for full-time employees located in Redmond, and another record named **RedmondTemps** for temporary employees.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="3af93-p118">Der Name des PSTN-Verwendungseintrags muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Eintrags kann das Feld <STRONG>Name</STRONG> nicht mehr bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="3af93-p118">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="3af93-157">Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="3af93-157">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="3af93-158">Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung die Routen, die Sie diesem PSTN-Verwendungseintrag zuordnen wollen und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3af93-158">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="3af93-159">Zum Entfernen einer Route aus dem PSTN-Verwendungseintrag markieren Sie die Route und klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="3af93-159">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
            
              - <span data-ttu-id="3af93-160">Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="3af93-160">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="3af93-161">Ausführliche Informationen finden Sie unter [Erstellen einer VoIP-Route in lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="3af93-161">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="3af93-162">Markieren Sie die Route und klicken Sie auf **Details einblenden**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungseintrag bereits zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="3af93-162">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="3af93-163">Ausführliche Informationen finden Sie unter [Ändern einer VoIP-Route in lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="3af93-163">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="3af93-164">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3af93-164">Click **OK**.</span></span>
    
      - <span data-ttu-id="3af93-165">Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungseintrag zu bearbeiten, der bereits dieser VoIP-Richtlinie zugeordnet ist:</span><span class="sxs-lookup"><span data-stu-id="3af93-165">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="3af93-166">Markieren Sie den PSTN-Verwendungsdatensatz, den Sie bearbeiten möchten und klicken Sie auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="3af93-166">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="3af93-167">Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="3af93-167">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="3af93-168">Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung die Routen, die Sie diesem PSTN-Verwendungseintrag zuordnen wollen und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3af93-168">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="3af93-169">Zum Entfernen einer Route aus diesem PSTN-Verwendungseintrag markieren Sie die Route und klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="3af93-169">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
            
              - <span data-ttu-id="3af93-170">Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="3af93-170">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="3af93-171">Ausführliche Informationen finden Sie unter [Erstellen einer VoIP-Route in lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="3af93-171">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="3af93-172">Markieren Sie die Route und klicken Sie auf **Details einblenden**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungseintrag bereits zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="3af93-172">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="3af93-173">Ausführliche Informationen finden Sie unter [Ändern einer VoIP-Route in lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="3af93-173">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="3af93-174">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3af93-174">Click **OK**.</span></span>

8.  <span data-ttu-id="3af93-p123">Ordnen Sie die PSTN-Verwendungseinträge zur Erzielung optimaler Leistung an. Wenn Sie die Position eines Eintrags in der Liste ändern möchten, markieren Sie den Eintragsnamen und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.</span><span class="sxs-lookup"><span data-stu-id="3af93-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3af93-177">Die Reihenfolge, in der die Einträge für PSTN-Nutzung in der VoIP-Richtlinie aufgeführt sind, ist erheblich.</span><span class="sxs-lookup"><span data-stu-id="3af93-177">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="3af93-178">Lync Server durchläuft die Liste von oben nach unten.</span><span class="sxs-lookup"><span data-stu-id="3af93-178">Lync Server traverses the list from the top down.</span></span> <span data-ttu-id="3af93-179">Wir empfehlen, die Liste nach Häufigkeit der Verwendung zu organisieren, beispielsweise: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="3af93-179">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

    
    </div>

9.  <span data-ttu-id="3af93-180">Führen Sie eine der folgenden Aktionen aus, um PSTN-Verwendungseinträge für die Anrufweiterleitung und das gleichzeitige Klingeln in dieser VoIP-Richtlinie zuzuordnen und zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="3af93-180">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="3af93-181">Um dieselben PSTN-Verwendungseinträge für die Anrufweiterleitung und für das gleichzeitige Klingeln wie in dieser VoIP-Richtlinie zu verwenden, wählen Sie aus dem Dropdownmenü die Option **Mithilfe der PSTN-Anrufverwendung weiterleiten** aus.</span><span class="sxs-lookup"><span data-stu-id="3af93-181">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>
    
      - <span data-ttu-id="3af93-182">Wenn Sie die Anrufweiterleitung und gleichzeitiges Klingeln nur für interne lync-Benutzer zulassen möchten, wählen Sie nur im Dropdownmenü die Option **an interne lync-Benutzer weiterleiten** aus.</span><span class="sxs-lookup"><span data-stu-id="3af93-182">To allow call forwarding and simultaneous ringing to internal Lync users only, select **Route to internal Lync users only** from the drop-down menu.</span></span> <span data-ttu-id="3af93-183">Anrufe werden nicht an externe PSTN-Nummern weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="3af93-183">Calls will not be forwarded to external PSTN numbers.</span></span>
    
      - <span data-ttu-id="3af93-p126">Um andere PSTN-Verwendungsdatensätze für die Anrufweiterleitung und gleichzeitiges Klingeln zu verwenden, als die für diese VoIP-Richtlinie verwendeten, wählen Sie die Option **Mithilfe benutzerdefinierter PSTN-Verwendungen weiterleiten** im Dropdownmenü aus. Bei Auswahl dieser Option wird ein Steuerelement angezeigt, über das vorhandene PSTN-Verwendungsdatensätze ausgewählt oder neue PSTN-Verwendungsdatensätze erstellt werden können, die speziell auf die Anrufweiterleitung und gleichzeitiges Klingeln ausgerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="3af93-p126">To specify different PSTN usage records for call forwarding and simultaneous ringing than those used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu. This option displays a control to select existing PSTN usage records or to create new PSTN usage records, specifically for call forwarding and simultaneous ringing.</span></span>
        
          - <span data-ttu-id="3af93-p127">Klicken Sie auf **Auswählen**, um einen oder mehrere Einträge aus einer Liste von PSTN-Verwendungseinträgen für die Anrufweiterleitung und das gleichzeitige Klingeln auszuwählen. Markieren Sie die Einträge, die Sie dieser Richtlinie für die Anrufweiterleitung und das gleichzeitige Klingeln zuordnen möchten und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3af93-p127">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**. Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>
        
          - <span data-ttu-id="3af93-188">Markieren Sie einen Eintrag und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungseintrag aus dieser Richtlinie für die Anrufweiterleitung und das gleichzeitige Klingeln zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="3af93-188">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>
        
          - <span data-ttu-id="3af93-189">Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungseintrag zu definieren und dieser Richtlinie für die Anrufweiterleitung und das gleichzeitige Klingeln zuzuordnen:</span><span class="sxs-lookup"><span data-stu-id="3af93-189">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>
            
            1.  <span data-ttu-id="3af93-190">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="3af93-190">Click **New**.</span></span>
            
            2.  <span data-ttu-id="3af93-191">Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Eintrag ein.</span><span class="sxs-lookup"><span data-stu-id="3af93-191">In the **Name** field, enter a unique descriptive name for the record.</span></span>
                
                <div>
                

                > [!NOTE]  
                > <span data-ttu-id="3af93-p128">Der Name des PSTN-Verwendungseintrags muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Eintrags kann das Feld <STRONG>Name</STRONG> nicht mehr bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="3af93-p128">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

                
                </div>
            
            3.  <span data-ttu-id="3af93-194">Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="3af93-194">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="3af93-195">Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung die Routen, die Sie diesem PSTN-Verwendungseintrag zuordnen wollen und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3af93-195">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="3af93-196">Zum Entfernen einer Route aus dem PSTN-Verwendungseintrag markieren Sie die Route und klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="3af93-196">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="3af93-197">Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="3af93-197">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="3af93-198">Ausführliche Informationen finden Sie unter [Erstellen einer VoIP-Route in lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="3af93-198">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="3af93-199">Markieren Sie die Route und klicken Sie anschließend auf **Details anzeigen**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungsdatensatz bereits zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="3af93-199">To edit a route that is already associated with this PSTN usage record, highlight the route, and then click **Show details**.</span></span> <span data-ttu-id="3af93-200">Ausführliche Informationen finden Sie unter [Ändern einer VoIP-Route in lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="3af93-200">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            4.  <span data-ttu-id="3af93-201">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3af93-201">Click **OK**.</span></span>
        
          - <span data-ttu-id="3af93-202">Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungseintrag zu bearbeiten, der bereits dieser VoIP-Richtlinie zugeordnet ist:</span><span class="sxs-lookup"><span data-stu-id="3af93-202">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
            
            1.  <span data-ttu-id="3af93-203">Markieren Sie den PSTN-Verwendungsdatensatz, den Sie bearbeiten möchten und klicken Sie auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="3af93-203">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>
            
            2.  <span data-ttu-id="3af93-204">Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="3af93-204">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="3af93-205">Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine, die Sie diesem PSTN-Verwendungseintrag zuordnen wollen und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3af93-205">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="3af93-206">Zum Entfernen einer Route aus diesem PSTN-Verwendungseintrag markieren Sie die Route und klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="3af93-206">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="3af93-207">Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="3af93-207">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="3af93-208">Ausführliche Informationen finden Sie unter [Erstellen einer VoIP-Route in lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="3af93-208">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="3af93-209">Markieren Sie die Route und klicken Sie auf **Details einblenden**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungseintrag bereits zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="3af93-209">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="3af93-210">Ausführliche Informationen finden Sie unter [Ändern einer VoIP-Route in lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="3af93-210">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            3.  <span data-ttu-id="3af93-211">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3af93-211">Click **OK**.</span></span>

10. <span data-ttu-id="3af93-p133">(Optional) Geben Sie eine Nummer zum Testen der VoIP-Richtlinie ein und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb von **Übersetzte Nummer zum Testen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3af93-p133">(Optional) Enter a number to test the voice policy and click **Go**. The test results are displayed under **Translated number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3af93-214">Sie können eine VoIP-Richtlinie speichern, die den Test noch nicht bestanden hat, und diese dann später erneut konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3af93-214">You can save a voice policy that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="3af93-215">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-test-voice-routing.md">Testen des VoIP-Routings in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3af93-215">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

11. <span data-ttu-id="3af93-216">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3af93-216">Click **OK**.</span></span>

12. <span data-ttu-id="3af93-217">Klicken Sie auf der Seite **VoIP-Richtlinie** auf **Commit ausführen** und klicken Sie anschließend auf **Commit für alle Elemente ausführen**.</span><span class="sxs-lookup"><span data-stu-id="3af93-217">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3af93-218">Jedes Mal, wenn Sie eine VoIP-Richtlinie erstellen oder ändern, müssen Sie den Befehl <STRONG>Commit für alle</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="3af93-218">Whenever you create or modify a voice policy, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="3af93-219">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="3af93-219">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

13. <span data-ttu-id="3af93-220">(Optional) Die Voicemail-Umgehung erkennt, dass ein Anruf sofort von der Voicemail des Mobiltelefons des Benutzers entgegengenommen wurde und trennt den Anruf von der Voicemail des Mobiltelefons.</span><span class="sxs-lookup"><span data-stu-id="3af93-220">(Optional) Voicemail Escape detects that a call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="3af93-221">Somit kann der Anruf weiterhin auf den anderen Endpunkten des Benutzers klingeln, sodass der Benutzer die Möglichkeit hat, den Anruf entgegenzunehmen.</span><span class="sxs-lookup"><span data-stu-id="3af93-221">This allows the call to continue to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="3af93-222">Ausführliche Informationen zum Konfigurieren einer Voicemail-Richtlinie finden Sie unter [Konfigurieren von Voicemail-Escape in lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span><span class="sxs-lookup"><span data-stu-id="3af93-222">For details about how to configure a voice mail policy, see [Configuring voice mail escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3af93-223">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3af93-223">See Also</span></span>


[<span data-ttu-id="3af93-224">Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3af93-224">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="3af93-225">Anzeigen von PSTN-Nutzungsdaten Sätzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3af93-225">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="3af93-226">Erstellen einer VoIP-Route in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3af93-226">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="3af93-227">Ändern einer VoIP-Route in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3af93-227">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="3af93-228">Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3af93-228">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[<span data-ttu-id="3af93-229">Konfigurieren von Voicemail-Escape in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3af93-229">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="3af93-230">Testen des VoIP-Routings in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3af93-230">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

