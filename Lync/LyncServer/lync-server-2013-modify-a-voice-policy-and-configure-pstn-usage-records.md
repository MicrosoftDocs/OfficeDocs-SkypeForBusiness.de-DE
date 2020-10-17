---
title: 'Lync Server 2013: Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen'
description: 'Lync Server 2013: Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen.'
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
ms.openlocfilehash: e26d6c8654ebf758f8b5a185c21468443e0451a9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559371"
---
# <a name="modify-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="73b6e-103">Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73b6e-103">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73b6e-104">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="73b6e-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="73b6e-105">Führen Sie die folgenden Schritte aus, um eine VoIP-Richtlinie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="73b6e-105">Follow these steps if you want to modify a voice policy.</span></span> <span data-ttu-id="73b6e-106">Wenn Sie eine neue VoIP-Richtlinie erstellen möchten, finden Sie weitere Informationen unter [Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md) für die Prozedur.</span><span class="sxs-lookup"><span data-stu-id="73b6e-106">If you want to create a new voice policy, see [Create a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md) for the procedure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="73b6e-107">Wenn ein Benutzer einer VoIP-Richtlinie ohne zugeordnete PSTN-Verwendungsdatensätze (Public Switched Telephone Network, Telefonfestnetz) zugewiesen wird, kann der Benutzer keine ausgehenden Anrufe tätigen.</span><span class="sxs-lookup"><span data-stu-id="73b6e-107">If a user is assigned to a voice policy has no associated public switched telephone network (PSTN) usage records, the user cannot place outbound calls.</span></span> <span data-ttu-id="73b6e-108">Eine Liste aller in Ihrer Enterprise-VoIP-Bereitstellung verfügbaren PSTN-Verwendungsdaten Sätze sowie deren Eigenschaften finden Sie unter <A href="lync-server-2013-view-pstn-usage-records.md">Anzeigen von PSTN-Verwendungsdatensätzen in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="73b6e-108">For a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-modify-a-voice-policy"></a><span data-ttu-id="73b6e-109">So ändern Sie eine VoIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="73b6e-109">To modify a voice policy</span></span>

1.  <span data-ttu-id="73b6e-110">Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an.</span><span class="sxs-lookup"><span data-stu-id="73b6e-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="73b6e-111">Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="73b6e-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="73b6e-112">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="73b6e-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="73b6e-113">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="73b6e-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="73b6e-114">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und anschließend auf **VoIP-Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="73b6e-114">In the left navigation bar, click **Voice Routing**, and then click **Voice Policy**.</span></span>

4.  <span data-ttu-id="73b6e-115">Doppelklicken Sie auf der Seite **VoIP-Richtlinie** auf den Namen einer VoIP-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="73b6e-115">On the **Voice Policy** page, double-click a voice policy name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="73b6e-p105">Der Bereich und der Name wurden bei Erstellung der VoIP-Richtlinie festgelegt. Sie können nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="73b6e-p105">The scope and name were set when the voice policy was created. They cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="73b6e-118">(Optional) Geben Sie in **VoIP-Richtlinie bearbeiten** zusätzliche Informationen zur Beschreibung der VoIP-Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="73b6e-118">(Optional) In **Edit Voice Policy**, enter additional descriptive information for the voice policy.</span></span>

6.  <span data-ttu-id="73b6e-119">Aktivieren oder deaktivieren Sie die folgenden Kontrollkästchen, um die einzelnen **Anruffunktionen** zu aktivieren bzw. zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="73b6e-119">Select or clear the following check boxes to enable or disable each of the **Calling features**:</span></span>
    
      - <span data-ttu-id="73b6e-120">Die **Voicemailumgehung** verhindert, dass Anrufe unmittelbar an das Voicemailsystem des Mobiltelefons des Benutzers weitergeleitet werden, wenn gleichzeitiges Klingeln konfiguriert ist und das Telefon deaktiviert ist, keine Akkukapazitäten mehr hat oder sich außerhalb des abgedeckten Bereichs befindet.</span><span class="sxs-lookup"><span data-stu-id="73b6e-120">**Voice mail escape** prevents calls from being immediately routed to the user’s mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="73b6e-121">Dieses Feature kann nur über die lync Server-Verwaltungsshell konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="73b6e-121">This feature is only configurable through the Lync Server Management Shell</span></span>

        
        </div>
    
      - <span data-ttu-id="73b6e-122">**Anrufweiterleitung** ermöglicht Benutzern das Weiterleiten von Anrufen an andere Telefone und Clientgeräte.</span><span class="sxs-lookup"><span data-stu-id="73b6e-122">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="73b6e-123">Lync Server 2013 bietet eine wesentlich breitere Palette von Konfigurationsoptionen für die Anrufweiterleitung.</span><span class="sxs-lookup"><span data-stu-id="73b6e-123">Lync Server 2013 provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="73b6e-124">Wenn beispielsweise eine Organisation nicht möchte, dass eingehende Anrufe extern an das PSTN weitergeleitet werden, kann ein Administrator eine spezielle VoIP-Richtlinie geltend machen, um diese Einschränkung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="73b6e-124">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="73b6e-125">Diese Option ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="73b6e-125">Enabled by default.</span></span>
    
      - <span data-ttu-id="73b6e-126">**Delegierung** ermöglicht Benutzern die Angabe anderer Benutzer, die in ihrem Namen Anrufe tätigen und empfangen können.</span><span class="sxs-lookup"><span data-stu-id="73b6e-126">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="73b6e-127">In lync Server 2013 kann ein Delegat das gleichzeitige Klingeln konfigurieren, mit dem eingehende Anrufe an seinen Vorgesetzten alle gleichzeitigen Klingel Ziele des Stellvertreters Klingeln können.</span><span class="sxs-lookup"><span data-stu-id="73b6e-127">In Lync Server 2013, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate’s simultaneous ringing targets.</span></span> <span data-ttu-id="73b6e-128">Auf diese Weise kann der Stellvertreter flexibler auf die für seinen Manager bestimmten Anrufe reagieren.</span><span class="sxs-lookup"><span data-stu-id="73b6e-128">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="73b6e-129">Diese Option ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="73b6e-129">Enabled by default.</span></span>
    
      - <span data-ttu-id="73b6e-p108">**Anrufdurchstellung** ermöglicht es, Anrufe an andere Benutzer durchzustellen. Diese Option ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="73b6e-p108">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>
    
      - <span data-ttu-id="73b6e-p109">**Anruf parken** ermöglicht es Benutzern, Anrufe in der Warteschleife zu parken und den Anruf anschließend von einem anderen Telefon oder Client aus wiederaufzunehmen. Diese Option ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="73b6e-p109">**Call park** enables users to park calls on hold, and then pick up the call from a different phone or client. Disabled by default.</span></span>
    
      - <span data-ttu-id="73b6e-134">**Gleichzeitiges Klingeln** ermöglicht bei eingehenden Anrufen das gleichzeitige Klingeln auf zusätzlichen Telefonen (z. B. einem Mobiltelefon) oder anderen Endpunktgeräten.</span><span class="sxs-lookup"><span data-stu-id="73b6e-134">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="73b6e-135">Lync Server 2013 bietet eine wesentlich breitere Palette von Konfigurationsoptionen für das gleichzeitige Klingeln.</span><span class="sxs-lookup"><span data-stu-id="73b6e-135">Lync Server 2013 provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="73b6e-136">Diese Option ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="73b6e-136">Enabled by default.</span></span>
    
      - <span data-ttu-id="73b6e-p111">**Teamanruf** ermöglicht Benutzern in einem definierten Team die Annahme von Anrufen für andere Teammitglieder. Diese Option ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="73b6e-p111">**Team call** enables users on a defined team to answer calls for other members of the team. Enabled by default.</span></span>
    
      - <span data-ttu-id="73b6e-p112">**PSTN-Umleitung** ermöglicht das Umleiten der Anrufe von Benutzern, denen diese Richtlinie zugewiesen wurde, an andere Benutzer im Unternehmen über das Festnetz, wenn das WAN überlastet oder nicht verfügbar ist. Diese Option ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="73b6e-p112">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable. Enabled by default.</span></span>
    
      - <span data-ttu-id="73b6e-p113">**Außerkraftsetzen der Bandbreitenrichtlinie** ermöglicht Administratoren das Außerkraftsetzen der Entscheidungen der Anrufsteuerungsrichtlinie für einen bestimmten Benutzer. Diese Option ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="73b6e-p113">**Bandwidth policy override** enables administrators to override call admission control (CAC) policy decisions for a particular user. Disabled by default.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="73b6e-p114">Die Richtlinie wird nur für eingehende Anrufe an den Benutzer, nicht jedoch für ausgehende Anrufe außer Kraft gesetzt, die vom Benutzer getätigt werden. Nachdem die Sitzung hergestellt wurde, wird die Bandbreitenauslastung genau aufgezeichnet. Diese Einstellung sollte sparsam verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="73b6e-p114">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user. After the session is established, the bandwidth consumption will be accurately recorded. This setting should be used sparingly.</span></span>

        
        </div>
    
      - <span data-ttu-id="73b6e-p115">**Nachverfolgung bei Missbrauch durch Anrufer** ermöglicht Benutzern das Melden von Drohanrufen (z. B. Bombendrohungen) über die Clientbenutzeroberfläche, wo die Anrufe anschließend in den Kommunikationsdatensätzen (KDS) gekennzeichnet werden. Diese Option ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="73b6e-p115">**Malicious call tracing** enables users to report malicious calls (such as bomb threats) using the client UI, which in turn flags the calls in the call detail records (CDRs). Disabled by default.</span></span>

7.  <span data-ttu-id="73b6e-148">Führen Sie eine der folgenden Aktionen aus, um PSTN-Verwendungsdatensätze für diese VoIP-Richtlinie zuzuordnen und zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="73b6e-148">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="73b6e-p116">Klicken Sie auf **Auswählen**, um einen oder mehrere Datensätze aus einer Liste aller PSTN-Verwendungsdatensätze auszuwählen, die für Ihre Enterprise-VoIP-Bereitstellung zur Verfügung stehen. Markieren Sie die Datensätze, die Sie dieser VoIP-Richtlinie zuordnen möchten, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="73b6e-p116">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**. Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>
    
      - <span data-ttu-id="73b6e-151">Markieren Sie einen Datensatz, und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungsdatensatz aus der VoIP-Richtlinie zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="73b6e-151">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="73b6e-152">Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungsdatensatz zu definieren und dieser VoIP-Richtlinie zuzuordnen:</span><span class="sxs-lookup"><span data-stu-id="73b6e-152">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="73b6e-153">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="73b6e-153">Click **New**.</span></span>
        
        2.  <span data-ttu-id="73b6e-p117">Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Datensatz ein. Sie könnten beispielsweise einen PSTN-Verwendungsdatensatz namens **Redmond** für Vollzeitbeschäftigte in Redmond und einen weiteren Datensatz namens **RedmondTemps** für Mitarbeiter mit Zeitverträgen erstellen.</span><span class="sxs-lookup"><span data-stu-id="73b6e-p117">In the **Name** field, enter a unique descriptive name for the record. For example, you may want to create a PSTN usage record named **Redmond** for full-time employees located in Redmond, and another record named **RedmondTemps** for temporary employees.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="73b6e-p118">Der Name des PSTN-Verwendungsdatensatzes muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Datensatzes kann das Feld <STRONG>Name</STRONG> nicht mehr bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="73b6e-p118">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="73b6e-158">Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Datensatz zuzuordnen und zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="73b6e-158">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="73b6e-159">Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine oder mehrere gewünschte Routen, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="73b6e-159">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="73b6e-160">Zum Entfernen einer Route aus dem PSTN-Verwendungsdatensatz markieren Sie die Route, und klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="73b6e-160">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
            
              - <span data-ttu-id="73b6e-161">Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungsdatensatz zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="73b6e-161">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="73b6e-162">Ausführliche Informationen finden Sie unter [Erstellen einer VoIP-Route in lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="73b6e-162">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="73b6e-163">Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungsdatensatz bereits zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="73b6e-163">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="73b6e-164">Ausführliche Informationen finden Sie unter [Ändern einer VoIP-Route in lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="73b6e-164">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="73b6e-165">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="73b6e-165">Click **OK**.</span></span>
    
      - <span data-ttu-id="73b6e-166">Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungsdatensatz zu bearbeiten, der bereits dieser VoIP-Richtlinie zugeordnet ist:</span><span class="sxs-lookup"><span data-stu-id="73b6e-166">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="73b6e-167">Markieren Sie den PSTN-Verwendungsdatensatz, den Sie bearbeiten möchten, und klicken Sie auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="73b6e-167">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="73b6e-168">Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Datensatz zuzuordnen und zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="73b6e-168">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="73b6e-169">Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine oder mehrere gewünschte Routen, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="73b6e-169">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="73b6e-170">Zum Entfernen einer Route aus diesem PSTN-Verwendungsdatensatz markieren Sie die Route, und klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="73b6e-170">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
            
              - <span data-ttu-id="73b6e-171">Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungsdatensatz zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="73b6e-171">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="73b6e-172">Ausführliche Informationen finden Sie unter [Erstellen einer VoIP-Route in lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="73b6e-172">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="73b6e-173">Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungsdatensatz bereits zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="73b6e-173">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="73b6e-174">Ausführliche Informationen finden Sie unter [Ändern einer VoIP-Route in lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="73b6e-174">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="73b6e-175">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="73b6e-175">Click **OK**.</span></span>

8.  <span data-ttu-id="73b6e-p123">Ordnen Sie die PSTN-Verwendungsdatensätze zur Erzielung optimaler Leistung an. Wenn Sie die Position eines Datensatzes in der Liste ändern möchten, markieren Sie den Datensatznamen, und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.</span><span class="sxs-lookup"><span data-stu-id="73b6e-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="73b6e-178">Die Reihenfolge, in der die PSTN-Verwendungsdaten Sätze in der VoIP-Richtlinie aufgeführt werden, ist bedeutend.</span><span class="sxs-lookup"><span data-stu-id="73b6e-178">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="73b6e-179">Lync Server die Liste von oben nach unten durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="73b6e-179">Lync Server traverses the list from the top down.</span></span> <span data-ttu-id="73b6e-180">Es wird empfohlen, die Liste nach Verwendungshäufigkeit zu organisieren, beispielsweise: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="73b6e-180">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

    
    </div>

9.  <span data-ttu-id="73b6e-181">Führen Sie eine der folgenden Aktionen aus, um PSTN-Verwendungsdatensätze für die Anrufweiterleitung und gleichzeitiges Klingeln in dieser VoIP-Richtlinie zuzuordnen und zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="73b6e-181">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="73b6e-182">Um dieselben PSTN-Verwendungsdatensätze für die Anrufweiterleitung und gleichzeitiges Klingeln zu verwenden wie diese VoIP-Richtlinie, wählen Sie die Option **Mithilfe der gleichen PSTN-Verwendungen weiterleiten** im Dropdownmenü aus.</span><span class="sxs-lookup"><span data-stu-id="73b6e-182">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>
    
      - <span data-ttu-id="73b6e-183">Wenn Sie die Anrufweiterleitung und das gleichzeitige Klingeln nur für interne lync-Benutzer zulassen möchten, wählen Sie nur aus dem Dropdownmenü **Weiterleiten an interne lync-Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="73b6e-183">To allow call forwarding and simultaneous ringing to internal Lync users only, select **Route to internal Lync users only** from the drop-down menu.</span></span> <span data-ttu-id="73b6e-184">Die Anrufe werden dann nicht an externe PSTN-Nummern weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="73b6e-184">Calls will not be forwarded to external PSTN numbers.</span></span>
    
      - <span data-ttu-id="73b6e-p126">Um andere PSTN-Verwendungsdatensätze für die Anrufweiterleitung und gleichzeitiges Klingeln zu verwenden, als die für diese VoIP-Richtlinie verwendeten, wählen Sie die Option **Mithilfe benutzerdefinierter PSTN-Verwendungen weiterleiten** im Dropdownmenü aus. Bei Auswahl dieser Option wird ein Steuerelement angezeigt, über das vorhandene PSTN-Verwendungsdatensätze ausgewählt oder neue PSTN-Verwendungsdatensätze erstellt werden können, die speziell auf die Anrufweiterleitung und gleichzeitiges Klingeln ausgerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="73b6e-p126">To specify different PSTN usage records for call forwarding and simultaneous ringing than those used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu. This option displays a control to select existing PSTN usage records or to create new PSTN usage records, specifically for call forwarding and simultaneous ringing.</span></span>
        
          - <span data-ttu-id="73b6e-p127">Klicken Sie auf **Auswählen**, um einen oder mehrere Datensätze aus einer Liste aller PSTN-Verwendungsdatensätze für die Anrufweiterleitung und gleichzeitiges Klingeln auszuwählen. Markieren Sie die Datensätze, die Sie der Richtlinie für die Anrufweiterleitung und gleichzeitiges Klingeln zuordnen möchten, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="73b6e-p127">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**. Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>
        
          - <span data-ttu-id="73b6e-189">Markieren Sie einen Datensatz, und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungsdatensatz aus dieser Richtlinie für die Anrufweiterleitung und gleichzeitiges Klingeln zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="73b6e-189">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>
        
          - <span data-ttu-id="73b6e-190">Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungsdatensatz zu definieren und dieser Richtlinie für die Anrufweiterleitung und gleichzeitiges Klingeln zuzuordnen:</span><span class="sxs-lookup"><span data-stu-id="73b6e-190">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>
            
            1.  <span data-ttu-id="73b6e-191">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="73b6e-191">Click **New**.</span></span>
            
            2.  <span data-ttu-id="73b6e-192">Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Datensatz ein.</span><span class="sxs-lookup"><span data-stu-id="73b6e-192">In the **Name** field, enter a unique descriptive name for the record.</span></span>
                
                <div>
                

                > [!NOTE]  
                > <span data-ttu-id="73b6e-p128">Der Name des PSTN-Verwendungsdatensatzes muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Datensatzes kann das Feld <STRONG>Name</STRONG> nicht mehr bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="73b6e-p128">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

                
                </div>
            
            3.  <span data-ttu-id="73b6e-195">Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Datensatz zuzuordnen und zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="73b6e-195">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="73b6e-196">Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine oder mehrere gewünschte Routen, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="73b6e-196">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="73b6e-197">Zum Entfernen einer Route aus dem PSTN-Verwendungsdatensatz markieren Sie die Route, und klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="73b6e-197">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="73b6e-198">Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungsdatensatz zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="73b6e-198">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="73b6e-199">Ausführliche Informationen finden Sie unter [Erstellen einer VoIP-Route in lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="73b6e-199">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="73b6e-200">Markieren Sie die Route, und klicken Sie anschließend auf **Details anzeigen**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungsdatensatz bereits zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="73b6e-200">To edit a route that is already associated with this PSTN usage record, highlight the route, and then click **Show details**.</span></span> <span data-ttu-id="73b6e-201">Ausführliche Informationen finden Sie unter [Ändern einer VoIP-Route in lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="73b6e-201">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            4.  <span data-ttu-id="73b6e-202">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="73b6e-202">Click **OK**.</span></span>
        
          - <span data-ttu-id="73b6e-203">Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungsdatensatz zu bearbeiten, der bereits dieser VoIP-Richtlinie zugeordnet ist:</span><span class="sxs-lookup"><span data-stu-id="73b6e-203">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
            
            1.  <span data-ttu-id="73b6e-204">Markieren Sie den PSTN-Verwendungsdatensatz, den Sie bearbeiten möchten, und klicken Sie auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="73b6e-204">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>
            
            2.  <span data-ttu-id="73b6e-205">Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Datensatz zuzuordnen und zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="73b6e-205">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="73b6e-206">Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine oder mehrere gewünschte Routen, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="73b6e-206">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="73b6e-207">Zum Entfernen einer Route aus diesem PSTN-Verwendungsdatensatz markieren Sie die Route, und klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="73b6e-207">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="73b6e-208">Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungsdatensatz zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="73b6e-208">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="73b6e-209">Ausführliche Informationen finden Sie unter [Erstellen einer VoIP-Route in lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="73b6e-209">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="73b6e-210">Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungsdatensatz bereits zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="73b6e-210">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="73b6e-211">Ausführliche Informationen finden Sie unter [Ändern einer VoIP-Route in lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="73b6e-211">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            3.  <span data-ttu-id="73b6e-212">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="73b6e-212">Click **OK**.</span></span>

10. <span data-ttu-id="73b6e-p133">(Optional) Geben Sie eine Nummer zum Testen der VoIP-Richtlinie ein, und klicken Sie auf **Los**. Die Testergebnisse werden unter **Übersetzte Nummer für Test** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="73b6e-p133">(Optional) Enter a number to test the voice policy and click **Go**. The test results are displayed under **Translated number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="73b6e-215">Sie können eine VoIP-Richtlinie speichern, die den Test nicht bestanden hat, und sie später neu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="73b6e-215">You can save a voice policy that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="73b6e-216">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-test-voice-routing.md">Testen der VoIP-Weiterleitung in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="73b6e-216">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

11. <span data-ttu-id="73b6e-217">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="73b6e-217">Click **OK**.</span></span>

12. <span data-ttu-id="73b6e-218">Klicken Sie auf der Seite **VoIP-Richtlinie** auf **Commit**, und klicken Sie anschließend auf **Commit für alle**.</span><span class="sxs-lookup"><span data-stu-id="73b6e-218">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="73b6e-219">Jedes Mal, wenn Sie eine VoIP-Richtlinie erstellen oder ändern, müssen Sie den Befehl <STRONG>Commit für alle</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="73b6e-219">Whenever you create or modify a voice policy, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="73b6e-220">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="73b6e-220">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

13. <span data-ttu-id="73b6e-221">(Optional) Die Voicemail-Umgehung erkennt, dass ein Anruf sofort von der Voicemail des Mobiltelefons des Benutzers entgegengenommen wurde, und trennt den Anruf von der Voicemail des Mobiltelefons.</span><span class="sxs-lookup"><span data-stu-id="73b6e-221">(Optional) Voicemail Escape detects that a call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="73b6e-222">Somit kann der Anruf weiterhin auf den anderen Endpunkten des Benutzers klingeln, sodass der Benutzer die Möglichkeit hat, den Anruf entgegenzunehmen.</span><span class="sxs-lookup"><span data-stu-id="73b6e-222">This allows the call to continue to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="73b6e-223">Ausführliche Informationen zum Konfigurieren einer VoIP-Richtlinie finden Sie unter [Configuring Voice Mail Escape in lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span><span class="sxs-lookup"><span data-stu-id="73b6e-223">For details about how to configure a voice mail policy, see [Configuring voice mail escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="73b6e-224">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73b6e-224">See Also</span></span>


[<span data-ttu-id="73b6e-225">Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73b6e-225">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="73b6e-226">Anzeigen von PSTN-Verwendungsdatensätzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73b6e-226">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="73b6e-227">Erstellen einer VoIP-Route in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73b6e-227">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="73b6e-228">Ändern einer VoIP-Route in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73b6e-228">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="73b6e-229">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73b6e-229">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[<span data-ttu-id="73b6e-230">Konfigurieren von Voicemail-Escapes in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73b6e-230">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="73b6e-231">Testen des VoIP-Routings in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73b6e-231">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

