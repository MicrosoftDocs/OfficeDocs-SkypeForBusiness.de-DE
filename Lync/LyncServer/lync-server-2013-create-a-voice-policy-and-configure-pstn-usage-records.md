---
title: 'Lync Server 2013: Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice policy and configure PSTN usage records
ms:assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399027(v=OCS.15)
ms:contentKeyID: 48185693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1a4a240334dd83fd226586ac409c1bd91a871be
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145534"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="a7d6d-102">Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7d6d-102">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7d6d-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a7d6d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a7d6d-104">Führen Sie die folgenden Schritte aus, um eine neue VoIP-Richtlinie zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-104">Follow these steps if you want to create a new voice policy.</span></span> <span data-ttu-id="a7d6d-105">Wenn Sie eine VoIP-Richtlinie bearbeiten möchten, lesen Sie [Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md) für die Prozedur.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-105">If you want to edit a voice policy, see [Modify a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md) for the procedure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a7d6d-106">Jeder VoIP-Richtlinie muss mindestens ein PSTN-Verwendungseintrag zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-106">Each voice policy must have at least one associated public switched telephone network (PSTN) usage record.</span></span> <span data-ttu-id="a7d6d-107">Um eine Liste aller in Ihrer Enterprise-VoIP-Bereitstellung verfügbaren PSTN-Verwendungseinträge anzuzeigen und deren Eigenschaften anzuzeigen, lesen Sie <A href="lync-server-2013-view-pstn-usage-records.md">Anzeigen von PSTN-Verwendungsdatensätzen in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-107">To see a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-a-voice-policy"></a><span data-ttu-id="a7d6d-108">So erstellen Sie eine VoIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="a7d6d-108">To create a voice policy</span></span>

1.  <span data-ttu-id="a7d6d-109">Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="a7d6d-110">Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="a7d6d-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="a7d6d-111">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a7d6d-112">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a7d6d-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a7d6d-113">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **VoIP-Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-113">In the left navigation bar, click **Voice Routing** and then click **Voice Policy**.</span></span>

4.  <span data-ttu-id="a7d6d-114">Klicken Sie auf der Seite **VoIP-Richtlinie** auf **Neu**, und wählen Sie einen Bereich für die neue Richtlinie:</span><span class="sxs-lookup"><span data-stu-id="a7d6d-114">On the **Voice Policy** page, click **New** and then select a scope for the new policy:</span></span>
    
      - <span data-ttu-id="a7d6d-p105">Eine **Standortrichtlinie** wird auf einen gesamten Standort angewendet, ausgenommen auf Benutzer oder Gruppen, die einer Benutzerrichtlinie zugeordnet wurden. Wenn Sie eine Richtlinie auf Standortebene erstellen möchten, wählen Sie den gewünschten Standort im Dialogfeld **Standort auswählen**. Wenn bereits eine VoIP-Richtlinie für einen Standort erstellt wurde, wird der Standort nicht im Dialogfeld **Standort auswählen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-p105">**Site policy** applies to an entire site, except any users or groups that are assigned to a user policy. If you select Site for a policy scope, choose the site from the **Select a Site** dialog box. If a voice policy has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>
    
      - <span data-ttu-id="a7d6d-118">Eine **Benutzerrichtlinie** kann auf bestimmte Benutzer oder Gruppen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-118">**User policy** can be applied to specified users or groups.</span></span>

5.  <span data-ttu-id="a7d6d-119">Wenn Sie eine VoIP-Richtlinie auf Benutzerebene erstellen, geben Sie im Feld **Name** einen beschreibenden Namen für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-119">If the voice policy scope is User, enter a descriptive name for the policy in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a7d6d-120">Bei Erstellung einer VoIP-Richtlinie auf Standortebene wird das Feld <STRONG>Name</STRONG> unter <STRONG>Neue VoIP-Richtlinie</STRONG> mit dem Standortnamen vorausgefüllt und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-120">If the voice policy scope is Site, the <STRONG>Name</STRONG> field in <STRONG>New Voice Policy</STRONG> is prepopulated with the site name and cannot be changed.</span></span>

    
    </div>

6.  <span data-ttu-id="a7d6d-121">(Optional) Geben Sie zusätzliche beschreibende Informationen zur VoIP-Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-121">(Optional) Enter additional descriptive information for the voice policy.</span></span>

7.  <span data-ttu-id="a7d6d-122">Aktivieren oder deaktivieren Sie die folgenden Kontrollkästchen, um die **Anruffunktionen** für diese VoIP-Richtlinie zu aktivieren oder zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="a7d6d-122">Select or clear the following check boxes to enable or disable each of the **Calling features** for this voice policy:</span></span>
    
      - <span data-ttu-id="a7d6d-123">**Voicemail-Escape** verhindert, dass Anrufe sofort an das Voicemail-System des Mobiltelefons des Benutzers weitergeleitet werden, wenn das gleichzeitige Klingeln konfiguriert ist und das Handy ausgeschaltet, entladen oder ohne Netz ist.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-123">**Voice mail escape** prevents calls from being immediately routed to the user’s mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a7d6d-124">Dieses Feature kann nur über die lync Server-Verwaltungsshell konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-124">This feature is only configurable through the Lync Server Management Shell</span></span>

        
        </div>
    
      - <span data-ttu-id="a7d6d-125">**Anrufweiterleitung** ermöglicht Benutzern das Weiterleiten von Anrufen an andere Telefone und Clientgeräte.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-125">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="a7d6d-126">Lync Server 2013 bietet eine wesentlich breitere Palette von Konfigurationsoptionen für die Anrufweiterleitung.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-126">Lync Server 2013 provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="a7d6d-127">Wenn beispielsweise eine Organisation nicht möchte, dass eingehende Anrufe extern an das PSTN weitergeleitet werden, kann ein Administrator eine spezielle VoIP-Richtlinie geltend machen, um diese Einschränkung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-127">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="a7d6d-128">Diese Option ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-128">Enabled by default.</span></span>
    
      - <span data-ttu-id="a7d6d-129">**Delegierung** ermöglicht Benutzern die Angabe anderer Benutzer, die in ihrem Namen Anrufe tätigen und empfangen können.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-129">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="a7d6d-130">In lync Server 2013 kann ein Delegat das gleichzeitige Klingeln konfigurieren, mit dem eingehende Anrufe an seinen Vorgesetzten alle gleichzeitigen Klingel Ziele des Stellvertreters Klingeln können.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-130">In Lync Server 2013, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate’s simultaneous ringing targets.</span></span> <span data-ttu-id="a7d6d-131">Auf diese Weise kann der Stellvertreter flexibler auf die für seinen Manager bestimmten Anrufe reagieren.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-131">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="a7d6d-132">Diese Option ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-132">Enabled by default.</span></span>
    
      - <span data-ttu-id="a7d6d-p108">**Anrufdurchstellung** ermöglicht es, Anrufe an andere Benutzer durchzustellen. Diese Option ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-p108">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>
    
      - <span data-ttu-id="a7d6d-p109">**Anruf parken** ermöglicht es Benutzern, Anrufe in der Warteschleife zu parken und den Anruf von einem anderen Telefon oder Client aus wiederaufzunehmen. Diese Option ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-p109">**Call park** enables users to park calls on hold and then pick up the call from a different phone or client. Disabled by default.</span></span>
    
      - <span data-ttu-id="a7d6d-137">**Gleichzeitiges Klingeln** ermöglicht bei eingehenden Anrufen das gleichzeitige Klingeln auf zusätzlichen Telefonen (z. B. einem Mobiltelefon) oder anderen Endpunktgeräten.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-137">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="a7d6d-138">Lync Server 2013 bietet eine wesentlich breitere Palette von Konfigurationsoptionen für das gleichzeitige Klingeln.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-138">Lync Server 2013 provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="a7d6d-139">Diese Option ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-139">Enabled by default.</span></span>
    
      - <span data-ttu-id="a7d6d-p111">**Teamanruf** ermöglicht Benutzern in einem definierten Team die Annahme von Anrufen für andere Teammitglieder. Diese Option ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-p111">**Team call** enables users on a defined team to answer calls for other members of the team. Enabled by default.</span></span>
    
      - <span data-ttu-id="a7d6d-p112">**PSTN-Umleitung** ermöglicht das Umleiten von Anrufen von Benutzern, denen diese Richtlinie zugewiesen wurde, an andere Benutzer im Unternehmen über das Festnetz, wenn das WAN überlastet oder nicht verfügbar ist. Diese Option ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-p112">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable. Enabled by default.</span></span>
    
      - <span data-ttu-id="a7d6d-p113">**Außerkraftsetzung der Bandbreitenrichtlinie** ermöglicht es Administratoren, Richtlinienentscheidungen im Rahmen der Anrufsteuerung für einen bestimmten Benutzer außer Kraft zu setzen. Diese Option ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-p113">**Bandwidth policy override** enables administrators to override call admission control policy decisions for a particular user. Disabled by default.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a7d6d-p114">Die Richtlinie wird nur für eingehende Anrufe an den Benutzer, nicht jedoch für ausgehende Anrufe außer Kraft gesetzt, die vom Benutzer getätigt werden. Nachdem die Sitzung hergestellt wurde, wird die Bandbreitenauslastung genau aufgezeichnet. Diese Einstellung sollte sparsam verwendet und für angemessene Entscheidungen der Anrufsteuerung reserviert werden.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-p114">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user. After the session is established, the bandwidth consumption will be accurately recorded. This setting should be used sparingly and should be reserved for appropriate call admission control decisions.</span></span>

        
        </div>
    
      - <span data-ttu-id="a7d6d-p115">**Nachverfolgung von Missbrauch durch Anrufer** ermöglicht Benutzern das Melden von Drohanrufen (z. B. Bombendrohungen) über die Clientbenutzeroberfläche. Die Anrufe werden anschließend in den Kommunikationsdatensätzen (KDS) gekennzeichnet. Diese Option ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-p115">**Malicious call tracing** enables users to report malicious calls (such as bomb threats) by using the client UI, which in turn flags the calls in the call detail records (CDRs). Disabled by default.</span></span>

8.  <span data-ttu-id="a7d6d-151">Führen Sie eine der folgenden Aktionen aus, um PSTN-Verwendungseinträge für diese VoIP-Richtlinie zuzuordnen und zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="a7d6d-151">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="a7d6d-p116">Klicken Sie auf **Auswählen**, um einen oder mehrere Datensätze aus einer Liste aller PSTN-Verwendungsdatensätze auszuwählen, die für Ihre Enterprise-VoIP-Bereitstellung zur Verfügung stehen. Markieren Sie die Datensätze, die Sie dieser VoIP-Richtlinie zuordnen möchten, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-p116">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**. Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>
    
      - <span data-ttu-id="a7d6d-154">Markieren Sie einen Datensatz, und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungsdatensatz aus der VoIP-Richtlinie zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-154">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="a7d6d-155">Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungsdatensatz zu definieren und dieser VoIP-Richtlinie zuzuordnen:</span><span class="sxs-lookup"><span data-stu-id="a7d6d-155">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="a7d6d-156">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-156">Click **New**.</span></span>
        
        2.  <span data-ttu-id="a7d6d-p117">Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Eintrag ein. Sie könnten beispielsweise einen PSTN-Verwendungseintrag namens **Redmond** für Vollzeitbeschäftigte in Redmond und einen weiteren Eintrag namens **RedmondTemps** für Mitarbeiter mit Zeitverträgen erstellen.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-p117">In the **Name** field, enter a unique descriptive name for the record. For example, you may want to create a PSTN usage record named **Redmond** for full-time employees located in Redmond, and another named **RedmondTemps** for temporary employees.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="a7d6d-p118">Der Name des PSTN-Verwendungseintrags muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Eintrags kann das Feld <STRONG>Name</STRONG> nicht mehr bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-p118">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="a7d6d-161">Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Datensatz zuzuordnen und zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="a7d6d-161">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="a7d6d-162">Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine oder mehrere gewünschte Routen, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-162">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="a7d6d-163">Zum Entfernen einer Route aus dem PSTN-Verwendungseintrag markieren Sie die Route, und klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-163">To remove a route from the PSTN usage record, highlight the route, and then click **Remove**.</span></span>
            
              - <span data-ttu-id="a7d6d-164">Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungsdatensatz zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-164">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="a7d6d-165">Ausführliche Informationen finden Sie unter [Erstellen einer VoIP-Route in lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="a7d6d-165">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="a7d6d-166">Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungsdatensatz bereits zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-166">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="a7d6d-167">Ausführliche Informationen finden Sie unter [Ändern einer VoIP-Route in lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="a7d6d-167">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="a7d6d-168">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-168">Click **OK**.</span></span>
    
      - <span data-ttu-id="a7d6d-169">Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungsdatensatz zu bearbeiten, der bereits dieser VoIP-Richtlinie zugeordnet ist:</span><span class="sxs-lookup"><span data-stu-id="a7d6d-169">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="a7d6d-170">Markieren Sie den PSTN-Verwendungseintrag, den Sie bearbeiten möchten, und klicken Sie auf **Details einblenden**.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-170">Highlight the PSTN usage record that you want to edit, and then click **Show details**.</span></span>
        
        2.  <span data-ttu-id="a7d6d-171">Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Datensatz zuzuordnen und zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="a7d6d-171">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="a7d6d-172">Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine oder mehrere gewünschte Routen, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-172">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="a7d6d-173">Zum Entfernen einer Route aus diesem PSTN-Verwendungseintrag markieren Sie die Route, und klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-173">To remove a route from this PSTN usage record, highlight the route, and then click **Remove**.</span></span>
            
              - <span data-ttu-id="a7d6d-174">Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungsdatensatz zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-174">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="a7d6d-175">Ausführliche Informationen finden Sie unter [Erstellen einer VoIP-Route in lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="a7d6d-175">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="a7d6d-176">Markieren Sie die Route, und klicken Sie auf **Details einblenden**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungseintrag bereits zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-176">To edit a route that is already associated with this PSTN usage record, highlight the route and lick **Show details**.</span></span> <span data-ttu-id="a7d6d-177">Ausführliche Informationen finden Sie unter [Ändern einer VoIP-Route in lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="a7d6d-177">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="a7d6d-178">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-178">Click **OK**.</span></span>

9.  <span data-ttu-id="a7d6d-p123">Ordnen Sie die PSTN-Verwendungsdatensätze zur Erzielung optimaler Leistung an. Wenn Sie die Position eines Datensatzes in der Liste ändern möchten, markieren Sie den Datensatznamen, und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a7d6d-181">Die Reihenfolge, in der die PSTN-Verwendungsdaten Sätze in der VoIP-Richtlinie aufgeführt werden, ist bedeutend.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-181">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="a7d6d-182">Lync Server die Liste von oben nach unten durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-182">Lync Server traverses the list from the top down.</span></span> <span data-ttu-id="a7d6d-183">Es wird empfohlen, die Liste nach Verwendungshäufigkeit zu organisieren, beispielsweise: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-183">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

    
    </div>

10. <span data-ttu-id="a7d6d-184">Führen Sie eine der folgenden Aktionen aus, um PSTN-Verwendungsdatensätze für die Anrufweiterleitung und gleichzeitiges Klingeln in dieser VoIP-Richtlinie zuzuordnen und zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="a7d6d-184">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="a7d6d-185">Um dieselben PSTN-Verwendungseinträge für die Anrufweiterleitung und für das gleichzeitige Klingeln wie in dieser VoIP-Richtlinie zu verwenden, wählen Sie aus dem Dropdownmenü die Option **Mithilfe der PSTN-Anrufverwendung weiterleiten** aus.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-185">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>
    
      - <span data-ttu-id="a7d6d-p125">Um die Anrufweiterleitung und das gleichzeitige Klingeln nur für interne Lync-Benutzer zu aktivieren, wählen Sie aus dem Dropdownmenü die Option **Nur an interne Lync-Benutzer weiterleiten** aus. Anrufe werden nicht an externe PSTN-Nummern weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-p125">To allow call forwarding and simultaneous ringing to internal Lync users only, select the option **Route to internal Lync users only** from the drop-down menu. Calls will not be forwarded to external PSTN numbers.</span></span>
    
      - <span data-ttu-id="a7d6d-p126">Um andere PSTN-Verwendungseinträge für die Anrufweiterleitung und für das gleichzeitige Klingeln wie für diese VoIP-Richtlinie anzugeben, wählen Sie aus dem Dropdownmenü die Option **Mithilfe benutzerdefinierter PSTN-Verwendung weiterleiten** aus. Mit dieser Option wird ein Steuerelement angezeigt, um vorhandene PSTN-Verwendungseinträge auszuwählen oder um neue PSTN-Verwendungseinträge speziell für die Anrufweiterleitung und für das gleichzeitige Klingeln zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-p126">To specify different PSTN usage records for call forwarding and simultaneous ringing than used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu. This option displays a control to select existing PSTN usage records or create new PSTN usage records specifically for call forwarding and simultaneous ringing.</span></span>
        
          - <span data-ttu-id="a7d6d-p127">Klicken Sie auf **Auswählen**, um einen oder mehrere Einträge aus einer Liste von PSTN-Verwendungseinträgen für die Anrufweiterleitung und das gleichzeitige Klingeln auszuwählen. Markieren Sie die Einträge, die Sie dieser Richtlinie für die Anrufweiterleitung und das gleichzeitige Klingeln zuordnen möchten, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-p127">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**. Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>
        
          - <span data-ttu-id="a7d6d-192">Markieren Sie einen Datensatz, und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungsdatensatz aus dieser Richtlinie für die Anrufweiterleitung und gleichzeitiges Klingeln zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-192">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>
        
          - <span data-ttu-id="a7d6d-193">Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungsdatensatz zu definieren und dieser Richtlinie für die Anrufweiterleitung und gleichzeitiges Klingeln zuzuordnen:</span><span class="sxs-lookup"><span data-stu-id="a7d6d-193">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>
            
            1.  <span data-ttu-id="a7d6d-194">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-194">Click **New**.</span></span>
            
            2.  <span data-ttu-id="a7d6d-195">Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Datensatz ein.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-195">In the **Name** field, enter a unique descriptive name for the record.</span></span>
                
                <div>
                

                > [!NOTE]  
                > <span data-ttu-id="a7d6d-p128">Der Name des PSTN-Verwendungsdatensatzes muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Datensatzes kann das Feld <STRONG>Name</STRONG> nicht mehr bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-p128">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

                
                </div>
            
            3.  <span data-ttu-id="a7d6d-198">Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Datensatz zuzuordnen und zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="a7d6d-198">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="a7d6d-199">Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine oder mehrere gewünschte Routen, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-199">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="a7d6d-200">Zum Entfernen einer Route aus dem PSTN-Verwendungsdatensatz markieren Sie die Route, und klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-200">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="a7d6d-201">Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungsdatensatz zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-201">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="a7d6d-202">Ausführliche Informationen finden Sie unter [Erstellen einer VoIP-Route in lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="a7d6d-202">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="a7d6d-203">Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungsdatensatz bereits zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-203">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="a7d6d-204">Ausführliche Informationen finden Sie unter [Ändern einer VoIP-Route in lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="a7d6d-204">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            4.  <span data-ttu-id="a7d6d-205">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-205">Click **OK**.</span></span>
        
          - <span data-ttu-id="a7d6d-206">Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungseintrag zu bearbeiten, der bereits dieser VoIP-Richtlinie zugeordnet ist:</span><span class="sxs-lookup"><span data-stu-id="a7d6d-206">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
            
            1.  <span data-ttu-id="a7d6d-207">Markieren Sie den PSTN-Verwendungseintrag, den Sie bearbeiten möchten, und klicken Sie auf **Details einblenden**.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-207">Highlight the PSTN usage record you want to edit and click **Show details**.</span></span>
            
            2.  <span data-ttu-id="a7d6d-208">Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Datensatz zuzuordnen und zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="a7d6d-208">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="a7d6d-209">Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine oder mehrere gewünschte Routen, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-209">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="a7d6d-210">Zum Entfernen einer Route aus diesem PSTN-Verwendungsdatensatz markieren Sie die Route, und klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-210">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="a7d6d-211">Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungsdatensatz zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-211">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="a7d6d-212">Ausführliche Informationen finden Sie unter [Erstellen einer VoIP-Route in lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="a7d6d-212">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="a7d6d-213">Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungsdatensatz bereits zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-213">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="a7d6d-214">Ausführliche Informationen finden Sie unter [Ändern einer VoIP-Route in lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="a7d6d-214">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            3.  <span data-ttu-id="a7d6d-215">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-215">Click **OK**.</span></span>

11. <span data-ttu-id="a7d6d-p133">(Optional) Geben Sie eine Nummer zum Testen der VoIP-Richtlinie ein, und klicken Sie auf **Los**. Die Testergebnisse werden unter **Übersetzte Nummer für Test** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-p133">(Optional) Enter a number to test the voice policy and click **Go**. The test results are displayed under **Translated number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a7d6d-218">Sie können eine VoIP-Richtlinie speichern, die den Test nicht bestanden hat, und sie später neu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-218">You can save a voice policy that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="a7d6d-219">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-test-voice-routing.md">Testen der VoIP-Weiterleitung in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-219">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="a7d6d-220">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-220">Click **OK**.</span></span>

13. <span data-ttu-id="a7d6d-221">Klicken Sie auf der Seite **VoIP-Richtlinie** auf **Commit**, und klicken Sie anschließend auf **Commit für alle**.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-221">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a7d6d-222">Jedes Mal, wenn Sie eine VoIP-Richtlinie erstellen oder ändern, müssen Sie den Befehl <STRONG>Commit für alle Elemente ausführen</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-222">Any time you create or modify a voice policy, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="a7d6d-223">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-223">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

14. <span data-ttu-id="a7d6d-224">(Optional) Die Voicemail-Umgehung erkennt, dass ein Anruf sofort von der Voicemail des Mobiltelefons des Benutzers entgegengenommen wurde, und trennt den Anruf von der Voicemail des Mobiltelefons.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-224">(Optional) Voicemail Escape detects that a call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="a7d6d-225">Somit kann der Anruf weiterhin auf den anderen Endpunkten des Benutzers klingeln, sodass der Benutzer die Möglichkeit hat, den Anruf entgegenzunehmen.</span><span class="sxs-lookup"><span data-stu-id="a7d6d-225">This allows the call to continue to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="a7d6d-226">Ausführliche Informationen zum Konfigurieren einer VoIP-Richtlinie finden Sie unter [Configuring Voice Mail Escape in lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span><span class="sxs-lookup"><span data-stu-id="a7d6d-226">For details on how to configure a voice mail policy, see [Configuring voice mail escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a7d6d-227">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7d6d-227">See Also</span></span>


[<span data-ttu-id="a7d6d-228">Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7d6d-228">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="a7d6d-229">Anzeigen von PSTN-Verwendungsdatensätzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7d6d-229">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="a7d6d-230">Erstellen einer VoIP-Route in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7d6d-230">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="a7d6d-231">Ändern einer VoIP-Route in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7d6d-231">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="a7d6d-232">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7d6d-232">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[<span data-ttu-id="a7d6d-233">Konfigurieren von Voicemail-Escapes in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7d6d-233">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="a7d6d-234">Testen des VoIP-Routings in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7d6d-234">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

