---
title: 'Lync Server 2013: Konfigurieren eines Trunks mit medienumgehung'
description: 'Lync Server 2013: Konfigurieren eines Trunks mit medienumgehung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trunk with media bypass
ms:assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398792(v=OCS.15)
ms:contentKeyID: 48184959
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51bd58a685e1f4c222a863c21022b3c9dc7c70d6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566751"
---
# <a name="configure-a-trunk-with-media-bypass-in-lync-server-2013"></a><span data-ttu-id="088fb-103">Konfigurieren eines Trunks mit medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="088fb-103">Configure a trunk with media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="088fb-104">_**Letztes Änderungsstand des Themas:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="088fb-104">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="088fb-105">Führen Sie die folgenden Schritte aus, um einen trunk mit aktivierter medienumgehung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="088fb-105">Follow these steps to configure a trunk with media bypass enabled.</span></span> <span data-ttu-id="088fb-106">Informationen zum Konfigurieren eines Trunks mit deaktivierter medienumgehung finden Sie unter [Configure a trunk without Media Bypass in lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="088fb-106">To configure a trunk with media bypass disabled, see [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md).</span></span> <span data-ttu-id="088fb-107">Die Medienumgehung ist nützlich, wenn Sie die Anzahl von bereitgestellten Vermittlungsservern reduzieren möchten.</span><span class="sxs-lookup"><span data-stu-id="088fb-107">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="088fb-108">Üblicherweise wird ein Vermittlungsserverpool an einem zentralen Standort bereitgestellt und steuert die Gateways an den Zweigstellenstandorten.</span><span class="sxs-lookup"><span data-stu-id="088fb-108">Typically, a Mediation Server pool will be deployed at a central site, and it will control gateways at branch sites.</span></span> <span data-ttu-id="088fb-109">Durch Aktivierung der Medienumgehung können Mediendaten für PSTN-Anrufe (Telefonfestnetz) von Clients an Zweigstellenstandorten direkt durch die Gateways an diesen Standorten geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="088fb-109">Enabling media bypass allows media for public switched telephone network (PSTN) calls from clients at branch sites to flow directly through the gateways at those sites.</span></span> <span data-ttu-id="088fb-110">Lync Server 2013 ausgehenden Anrufrouten und Enterprise-VoIP-Richtlinien müssen ordnungsgemäß konfiguriert sein, damit PSTN-Anrufe von Clients an einem Zweigstellenstandort an das entsprechende Gateway weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="088fb-110">Lync Server 2013 outbound call routes and Enterprise Voice policies must be properly configured so that PSTN calls from clients at a branch site are routed to the appropriate gateway.</span></span>

<span data-ttu-id="088fb-111">Es wird dringend empfohlen, die medienumgehung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="088fb-111">We strongly recommend that you enable media bypass.</span></span> <span data-ttu-id="088fb-112">Bevor Sie jedoch die medienumgehung für einen SIP-Trunk aktivieren, müssen Sie sicherstellen, dass der qualifizierte SIP-Trunk Anbieter die medienumgehung unterstützt und die Anforderungen für die erfolgreiche Aktivierung des Szenarios erfüllen kann.</span><span class="sxs-lookup"><span data-stu-id="088fb-112">However, before you enable media bypass on a SIP trunk, confirm that your qualified SIP trunk provider supports media bypass and is able to accommodate the requirements for successfully enabling the scenario.</span></span> <span data-ttu-id="088fb-113">Insbesondere muss der Anbieter über die IP-Adressen von Servern im internen Netzwerk Ihrer Organisation verfügen.</span><span class="sxs-lookup"><span data-stu-id="088fb-113">Specifically, the provider must have the IP addresses of servers in your organization’s internal network.</span></span> <span data-ttu-id="088fb-114">Wenn der Anbieter dieses Szenario nicht unterstützen kann, ist die Medienumgehung nicht erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="088fb-114">If the provider cannot support this scenario, media bypass will not succeed.</span></span> <span data-ttu-id="088fb-115">Ausführliche Informationen finden Sie unter [Planning for Media Bypass in lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="088fb-115">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="088fb-116">Die medienumgehung kann nicht mit jedem PSTN-Gateway (Public Switched Telephone Network), IP-PBX-Gerät und einem SBC (Session Border Controller) zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="088fb-116">Media bypass will not interoperate with every public switched telephone network (PSTN) gateway, IP-PBX, and Session Border Controller (SBC).</span></span> <span data-ttu-id="088fb-117">Microsoft hat eine Reihe von PSTN-Gateways und SBCS mit zertifizierten Partnern getestet und einige Tests mit Cisco IP-PBX durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="088fb-117">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="088fb-118">Die medienumgehung wird nur mit Produkten und Versionen unterstützt, die unter Unified Communications Open Interoperability Program – lync Server unter aufgeführt sind <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> .</span><span class="sxs-lookup"><span data-stu-id="088fb-118">Media bypass is supported only with products and versions that are listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="088fb-119">Eine trunkkonfiguration wie unten beschrieben gruppiert eine Gruppe von Parametern, die auf Trunks angewendet werden, denen diese trunkkonfiguration zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="088fb-119">A trunk configuration as described below groups a set of parameters that are applied to trunks assigned this trunk configuration.</span></span> <span data-ttu-id="088fb-120">Eine bestimmte Trunkkonfiguration kann auf globale Ebene (für alle Trunks, die keine speziellere Standort- oder Poolkonfiguration haben) oder für einen Standort oder Pool festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="088fb-120">A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool.</span></span> <span data-ttu-id="088fb-121">Die Trunkkonfiguration auf Poolebene wird verwendet, um eine bestimmte Trunkkonfiguration auf einen einzelnen Trunk anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="088fb-121">The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

<span id="BKMK_ConfigTrunkMediaBypassSteps"></span>

<div>

## <a name="to-configure-a-trunk-with-media-bypass"></a><span data-ttu-id="088fb-122">So konfigurieren Sie einen trunk mit medienumgehung</span><span class="sxs-lookup"><span data-stu-id="088fb-122">To configure a trunk with media bypass</span></span>

1.  <span data-ttu-id="088fb-123">Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an.</span><span class="sxs-lookup"><span data-stu-id="088fb-123">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="088fb-124">Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="088fb-124">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="088fb-125">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="088fb-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="088fb-126">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="088fb-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="088fb-127">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Trunkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="088fb-127">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="088fb-128">Verwenden Sie auf der Seite **Trunkkonfiguration** eine der folgenden Methoden, um einen Trunk zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="088fb-128">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>
    
      - <span data-ttu-id="088fb-129">Doppelklicken Sie auf einen vorhandenen Trunk (z. B. den Trunk **Global**), um das Dialogfeld **Trunkkonfiguration bearbeiten** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="088fb-129">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
      - <span data-ttu-id="088fb-130">Klicken Sie auf **Neu**, und wählen Sie einen Bereich für die neue Trunkkonfiguration aus:</span><span class="sxs-lookup"><span data-stu-id="088fb-130">Click **New**, and then select a scope for the new trunk configuration:</span></span>
        
          - <span data-ttu-id="088fb-131">**Website trunk:** Wählen Sie den Standort für diese trunkkonfiguration aus **Standort auswählen**aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="088fb-131">**Site trunk:** Choose the site for this trunk configuration from **Select a Site**, and then click **OK**.</span></span> <span data-ttu-id="088fb-132">Wenn bereits eine Trunkkonfiguration für einen Standort erstellt wurde, wird der Standort nicht unter **Standort auswählen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="088fb-132">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="088fb-133">Diese Trunkkonfiguration wird auf alle Trunks am Standort angewendet.</span><span class="sxs-lookup"><span data-stu-id="088fb-133">This trunk configuration will be applied to all trunks in the site.</span></span>
        
          - <span data-ttu-id="088fb-134">**Pool trunk:** Wählen Sie den Namen des Trunks aus, für den diese trunkkonfiguration gilt.</span><span class="sxs-lookup"><span data-stu-id="088fb-134">**Pool trunk:** Choose the name of the trunk that this trunk configuration applies to.</span></span> <span data-ttu-id="088fb-135">Bei diesem trunk kann es sich um den Stamm trunk oder um zusätzliche Trunks handeln, die im Topologie-Generator definiert sind.</span><span class="sxs-lookup"><span data-stu-id="088fb-135">This trunk can be the root trunk or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="088fb-136">Klicken Sie unter **Dienst auswählen**auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="088fb-136">From **Select a Service**, click **OK**.</span></span> <span data-ttu-id="088fb-137">Wenn bereits eine Trunkkonfiguration für einen bestimmten Trunk erstellt wurde, erscheint dieser Trunk nicht unter **Dienst auswählen**.</span><span class="sxs-lookup"><span data-stu-id="088fb-137">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="088fb-138">Nachdem Sie den Bereich für die Trunkkonfiguration ausgewählt haben, kann dieser nicht mehr geändert werden.</span><span class="sxs-lookup"><span data-stu-id="088fb-138">After you select the scope of the trunk configuration, it cannot be changed.</span></span><BR><span data-ttu-id="088fb-139">Das Feld <STRONG>Name</STRONG> wird mit dem Namen der Trunkkonfiguration vorausgefüllt, der dem Standort oder Dienst zugeordnet ist, und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="088fb-139">The <STRONG>Name</STRONG> field is prepopulated with the name of the trunk configuration’s associated site or service and cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="088fb-140">Geben Sie einen Wert in **maximal unterstützten frühen Dialogfeldern**an.</span><span class="sxs-lookup"><span data-stu-id="088fb-140">Specify a value in **Maximum early dialogs supported**.</span></span> <span data-ttu-id="088fb-141">Hierbei handelt es sich um die maximale Anzahl von gegabelten Antworten, die ein PSTN-Gateway (Public Switched Telephone Network), eine IP-Nebenstellenanlage oder einen ITSP-Sitzungs Rahmen Controller (SBC) an eine Einladung empfangen kann, die an den Vermittlungsserver gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="088fb-141">This is the maximum number of forked responses a public switched telephone network (PSTN) gateway, IP-PBX, or ITSP Session Border Controller (SBC) can receive to an INVITE that it sent to the Mediation Server.</span></span> <span data-ttu-id="088fb-142">Der Standardwert lautet 20.</span><span class="sxs-lookup"><span data-stu-id="088fb-142">The default value is 20.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="088fb-143">Bevor Sie diesen Wert ändern, setzen Sie sich mit Ihrem Dienstanbieter oder Gerätehersteller in Verbindung, um genaue Informationen zu den Funktionen Ihres Systems zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="088fb-143">Before you change this value, consult your service provider or equipment manufacturer for details about the capabilities of your system.</span></span>

    
    </div>

6.  <span data-ttu-id="088fb-144">Wählen Sie unter **Unterstützte Verschlüsselungsstufe** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="088fb-144">Select one of the following **Encryption support level** options:</span></span>
    
      - <span data-ttu-id="088fb-145">**Erforderlich:** Die SRTP-Verschlüsselung (Secure Real-Time Transport Protocol) muss verwendet werden, um den Datenverkehr zwischen dem Vermittlungsserver und dem Gateway oder der Nebenstellenanlage (Private Branch Exchange, PBX) zu schützen.</span><span class="sxs-lookup"><span data-stu-id="088fb-145">**Required:** Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>
    
      - <span data-ttu-id="088fb-146">**Optional:** Die SRTP-Verschlüsselung wird verwendet, wenn der Dienstanbieter oder Gerätehersteller dies unterstützt.</span><span class="sxs-lookup"><span data-stu-id="088fb-146">**Optional:** SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>
    
      - <span data-ttu-id="088fb-147">**Nicht unterstützt:** Die SRTP-Verschlüsselung wird vom Dienstanbieter oder Gerätehersteller nicht unterstützt und wird daher nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="088fb-147">**Not Supported:** SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

7.  <span data-ttu-id="088fb-148">Aktivieren Sie das Kontrollkästchen **Medienumgehung aktivieren**, wenn Sie eine Umgehung des Vermittlungsservers zur Verarbeitung durch den Trunkpeer wünschen.</span><span class="sxs-lookup"><span data-stu-id="088fb-148">Select the **Enable media bypass** check box if you want media to bypass the Mediation Server for processing by the trunk peer.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="088fb-149">Damit die Medienumgehung ordnungsgemäß funktioniert, müssen das PSTN-Gateway, die IP-Nebenstellenanlage oder der SBC beim Dienstanbieter bestimmte Funktionen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="088fb-149">For media bypass to work successfully, the PSTN gateway, IP-PBX, or ITSP Session Border Controller must support certain capabilities.</span></span> <span data-ttu-id="088fb-150">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-planning-for-media-bypass.md">Planning for Media Bypass in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="088fb-150">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="088fb-p111">Aktivieren Sie das Kontrollkästchen **Zentrale Medienverarbeitung**, wenn ein bekannter Medienendpunkt vorhanden ist (beispielsweise ein PSTN-Gateway, bei dem der Medienendpunkt dieselbe IP-Adresse aufweist wie der signalgebende Endpunkt). Deaktivieren Sie dieses Kontrollkästchen, wenn der Trunk über keinen bekannten Medienendpunkt verfügt.</span><span class="sxs-lookup"><span data-stu-id="088fb-p111">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a PSTN gateway where the media termination has the same IP as the signaling termination). Clear this check box if the trunk does not have a well-known media termination point.</span></span>

9.  <span data-ttu-id="088fb-153">Wenn der trunk Peer das Empfangen von SIP-Refer-Anforderungen vom Vermittlungsserver unterstützt, aktivieren Sie das Kontrollkästchen **Senden von referieren auf das Gateway aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="088fb-153">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="088fb-154">Wenn Sie diese Option deaktivieren, während die Option <STRONG>Medienumgehung aktivieren</STRONG> ausgewählt ist, sind zusätzliche Einstellungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="088fb-154">If you disable this option while the <STRONG>Enable media bypass</STRONG> option is selected, additional settings are required.</span></span> <span data-ttu-id="088fb-155">Wenn der Trunkpeer den Empfang von SIP REFER-Anforderungen vom Vermittlungsserver nicht unterstützt und die Medienumgehung aktiviert ist, müssen Sie außerdem das Cmdlet <STRONG>Set-CsTrunkConfiguration</STRONG> ausführen, um RTCP für aktive und gehaltene Anrufe zu deaktivieren, um geeignete Bedingungen für die Medienumgehung zu schaffen.</span><span class="sxs-lookup"><span data-stu-id="088fb-155">If the trunk peer does not support receiving SIP REFER requests from the Mediation Server and media bypass is enabled, you must also run the <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet to disable RTCP for active and held calls in order to support proper conditions for media bypass.</span></span> <span data-ttu-id="088fb-156">Ausführliche Informationen finden Sie in der Dokumentation zur <A href="lync-server-2013-lync-server-management-shell.md">lync Server 2013 Management Shell</A> .</span><span class="sxs-lookup"><span data-stu-id="088fb-156">For details, see the <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A> documentation.</span></span><BR><span data-ttu-id="088fb-157">Alternativ können Sie die Option <STRONG>Refer mithilfe von Drittanbieter Anrufsteuerung aktivieren</STRONG> auswählen, wenn die Übertragung von Anrufen auf Medien umgangen werden soll und das Gateway SIP-Refer-Anforderungen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="088fb-157">Alternatively, you can select <STRONG>Enable refer using third-party-call control</STRONG> if you want transferred calls to be media bypassed, and the gateway does not support SIP REFER requests.</span></span>

    
    </div>

10. <span data-ttu-id="088fb-p113">(Optional) Um Routing zwischen Trunks zu ermöglichen, können Sie dieser Trunkkonfiguration PSTN-Verwendungseinträge zuordnen und konfigurieren. Die dieser Trunkkonfiguration zugeordneten PSTN-Verwendungen werden auf alle über den Trunk eingehenden Anrufe angewendet, der nicht aus einem Lync-Endpunkt stammt. Verwenden Sie eine der folgenden Methoden, um die einer Trunkkonfiguration zugeordneten PSTN-Verwendungseinträge zu verwalten:</span><span class="sxs-lookup"><span data-stu-id="088fb-p113">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration. The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Lync endpoint. To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>
    
      - <span data-ttu-id="088fb-161">Klicken Sie auf **auswählen**, um einen oder mehrere Datensätze aus einer Liste aller in Ihrer Enterprise-VoIP-Bereitstellung verfügbaren PSTN-Verwendungseinträge auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="088fb-161">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="088fb-162">Markieren Sie die Einträge, die Sie dieser Trunkkonfiguration zuordnen möchten, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="088fb-162">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>
    
      - <span data-ttu-id="088fb-163">Markieren Sie einen Eintrag, und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungseintrag aus dieser Trunkkonfiguration zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="088fb-163">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="088fb-164">Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungseintrag zu definieren und dieser Trunkkonfiguration zuzuordnen:</span><span class="sxs-lookup"><span data-stu-id="088fb-164">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="088fb-165">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="088fb-165">Click **New**.</span></span>
        
        2.  <span data-ttu-id="088fb-166">Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Eintrag ein.</span><span class="sxs-lookup"><span data-stu-id="088fb-166">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="088fb-p115">Der Name des PSTN-Verwendungsdatensatzes muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Datensatzes kann das Feld <STRONG>Name</STRONG> nicht mehr bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="088fb-p115">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="088fb-169">Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="088fb-169">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="088fb-170">Klicken Sie auf **auswählen**, um eine oder mehrere Routen aus der Liste aller verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="088fb-170">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="088fb-171">Markieren Sie die Routen, die Sie dieser Trunkkonfiguration zuordnen möchten, und klicken Sie dann auf**OK**.</span><span class="sxs-lookup"><span data-stu-id="088fb-171">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="088fb-172">Zum Entfernen einer Route aus dem PSTN-Verwendungseintrag markieren Sie die Route, und klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="088fb-172">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="088fb-173">Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="088fb-173">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="088fb-174">Ausführliche Informationen finden Sie unter [Erstellen einer VoIP-Route in lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="088fb-174">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="088fb-175">Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die dem PSTN-Verwendungseintrag zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="088fb-175">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="088fb-176">Ausführliche Informationen finden Sie unter [Ändern einer VoIP-Route in lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="088fb-176">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="088fb-177">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="088fb-177">Click **OK**.</span></span>
    
      - <span data-ttu-id="088fb-178">Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungseintrag zu bearbeiten, der bereits dieser Trunkkonfiguration zugeordnet ist:</span><span class="sxs-lookup"><span data-stu-id="088fb-178">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="088fb-179">Markieren Sie den PSTN-Verwendungseintrag, den Sie bearbeiten möchten, und klicken Sie auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="088fb-179">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="088fb-180">Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="088fb-180">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="088fb-181">Klicken Sie auf **auswählen**, um eine oder mehrere Routen aus der Liste aller verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="088fb-181">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="088fb-182">Markieren Sie die Routen, die Sie dieser Trunkkonfiguration zuordnen möchten, und klicken Sie dann auf**OK**.</span><span class="sxs-lookup"><span data-stu-id="088fb-182">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="088fb-183">Zum Entfernen einer Route aus dem PSTN-Verwendungseintrag markieren Sie die Route, und klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="088fb-183">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="088fb-184">Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="088fb-184">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="088fb-185">Ausführliche Informationen finden Sie unter [Erstellen einer VoIP-Route in lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="088fb-185">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="088fb-186">Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die dem PSTN-Verwendungseintrag zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="088fb-186">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="088fb-187">Ausführliche Informationen finden Sie unter [Ändern einer VoIP-Route in lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="088fb-187">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="088fb-188">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="088fb-188">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="088fb-189">Es ist wichtig, PSTN-Verwendungsdaten Sätze gemäß dem Vermittlungsserver Peer zuzuordnen, der dem zu konfigurierenden trunk zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="088fb-189">It important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="088fb-190">Wenn es sich bei dem Vermittlungsserver Peer um ein PSTN-Gateway oder einen SBC (Session Border Controller) handelt, wird dringend empfohlen, dass die trunkkonfiguration keinem PSTN-Verwendungsdaten Satz zugeordnet ist, der an ein PSTN-Ziel oder andere nachgeschaltete Systeme weitergeleitet wird, die über lync Server verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="088fb-190">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Lync Server.</span></span>

    
    </div>

11. <span data-ttu-id="088fb-p123">Ordnen Sie die PSTN-Verwendungseinträge zur Erzielung optimaler Leistung an. Wenn Sie die Position eines Eintrags in der Liste ändern möchten, markieren Sie den PSTN-Verwendungseintrag, und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.</span><span class="sxs-lookup"><span data-stu-id="088fb-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="088fb-193">Die Reihenfolge, in der PSTN-Verwendungseinträge in der Trunkkonfiguration aufgeführt werden, ist relevant.</span><span class="sxs-lookup"><span data-stu-id="088fb-193">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="088fb-194">Lync Server die Liste von oben nach unten durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="088fb-194">Lync Server traverses the list from top to down.</span></span>

    
    </div>

12. <span data-ttu-id="088fb-195">**Aktivieren Sie RTP-Latching** , um die Umgehung von Medien für Clients hinter einer Netzwerkadressübersetzung (Network Address Translation, NAT) oder einer Firewall und einen SBC zu aktivieren, der das Latching unterstützt.</span><span class="sxs-lookup"><span data-stu-id="088fb-195">**Enable RTP Latching** should be selected to enable bypass media for clients behind a network address translation (NAT) or firewall and an SBC that supports latching.</span></span>

13. <span data-ttu-id="088fb-196">**Enable Forward Call History** sollte ausgewählt sein, um das Senden von Anrufverlaufs Informationen an den Gateway-Peer des Vermittlungsserver zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="088fb-196">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

14. <span data-ttu-id="088fb-197">**Enable Forward p-asserted-Identity Data** sollte ausgewählt sein, damit die p-asserted-Identity (Pai)-Anruf Absenderinformationen zwischen der Vermittlungsserver Seite und der Gatewayseite (und umgekehrt) weitergeleitet werden können, sofern vorhanden.</span><span class="sxs-lookup"><span data-stu-id="088fb-197">**Enable forward P-Asserted-Identity data** should be selected to enable the P-Asserted-Identity (PAI) call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

15. <span data-ttu-id="088fb-198">**Failovertimer für Ausgangsrouting aktivieren** sollte ausgewählt sein, um ein schnelleres Failover zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="088fb-198">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="088fb-199">Das diesem Trunk zugeordnete Gateway kann innerhalb von 10 Sekunden eine Benachrichtigung senden, dass ein ausgehender Anruf verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="088fb-199">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="088fb-200">Das erneute Routing an einen anderen trunk erfolgt, wenn diese Benachrichtigung nicht vom Vermittlungsserver empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="088fb-200">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="088fb-201">In Netzwerken, in denen Latenz die Reaktionszeit verzögern kann oder das Gateway länger als 10 Sekunden benötigt, um zu antworten, sollte das schnelle Failover deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="088fb-201">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

16. <span data-ttu-id="088fb-202">(Optional) Zuordnen und Konfigurieren von **Übersetzungsregeln für die wählende Nummer** für den Trunk.</span><span class="sxs-lookup"><span data-stu-id="088fb-202">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="088fb-203">Diese Übersetzungsregeln werden bei ausgehenden Anrufen auf die wählende Nummer angewendet.</span><span class="sxs-lookup"><span data-stu-id="088fb-203">These translation rules apply to the calling number for outbound calls</span></span>
    
      - <span data-ttu-id="088fb-204">Klicken Sie auf **auswählen**, um eine oder mehrere Regeln aus einer Liste aller Übersetzungsregeln auszuwählen, die in Ihrer Enterprise-VoIP-Bereitstellung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="088fb-204">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="088fb-205">Klicken Sie im Abschnitt **Übersetzungsregeln auswählen** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="088fb-205">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="088fb-206">Klicken Sie auf **Neu**, um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="088fb-206">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="088fb-207">Ausführliche Informationen zum Definieren einer neuen Regel finden Sie unter [Definieren von Übersetzungsregeln in lync Server 2013](lync-server-2013-defining-translation-rules.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="088fb-207">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="088fb-208">Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die bereits dem Trunk zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="088fb-208">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="088fb-209">Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in lync Server 2013](lync-server-2013-defining-translation-rules.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="088fb-209">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="088fb-210">Um eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel zu verwenden, klicken Sie auf den Regelnamen, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**.</span><span class="sxs-lookup"><span data-stu-id="088fb-210">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="088fb-211">Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="088fb-211">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="088fb-212">Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen, und klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="088fb-212">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="088fb-213">Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den zwei Regeln Konflikte auftreten können.</span><span class="sxs-lookup"><span data-stu-id="088fb-213">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

17. <span data-ttu-id="088fb-p131">(Optional) Zuordnen und Konfigurieren von **Übersetzungsregeln für die gewählte Nummer** für den Trunk. Diese Übersetzungsregeln werden bei ausgehenden Anrufen auf die gewählte Nummer angewendet.</span><span class="sxs-lookup"><span data-stu-id="088fb-p131">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>
    
      - <span data-ttu-id="088fb-216">Klicken Sie auf **auswählen**, um eine oder mehrere Regeln aus einer Liste aller Übersetzungsregeln auszuwählen, die in Ihrer Enterprise-VoIP-Bereitstellung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="088fb-216">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="088fb-217">Klicken Sie im Abschnitt **Übersetzungsregeln auswählen** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="088fb-217">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="088fb-218">Klicken Sie auf **Neu**, um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="088fb-218">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="088fb-219">Ausführliche Informationen zum Definieren einer neuen Regel finden Sie unter [Definieren von Übersetzungsregeln in lync Server 2013](lync-server-2013-defining-translation-rules.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="088fb-219">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="088fb-220">Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die bereits dem Trunk zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="088fb-220">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="088fb-221">Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in lync Server 2013](lync-server-2013-defining-translation-rules.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="088fb-221">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="088fb-222">Um eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel zu verwenden, klicken Sie auf den Regelnamen, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**.</span><span class="sxs-lookup"><span data-stu-id="088fb-222">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="088fb-223">Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="088fb-223">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="088fb-224">Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen, und klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="088fb-224">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="088fb-225">Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den zwei Regeln Konflikte auftreten können.</span><span class="sxs-lookup"><span data-stu-id="088fb-225">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

18. <span data-ttu-id="088fb-226">Stellen Sie sicher, dass die Übersetzungsregeln des Trunks in der richtigen Reihenfolge angeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="088fb-226">Make sure that the trunk’s translation rules are arranged in the correct order.</span></span> <span data-ttu-id="088fb-227">Wenn Sie die Position einer Regel in der Liste ändern möchten, markieren Sie den Regelnamen, und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.</span><span class="sxs-lookup"><span data-stu-id="088fb-227">To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="088fb-228">Lync Server 2013 durchläuft die Liste der Übersetzungsregeln von oben nach unten und verwendet die erste Regel, die mit der gewählten Nummer übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="088fb-228">Lync Server 2013 traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="088fb-229">Wenn Sie einen Trunk so konfigurieren, dass eine gewählte Nummer mit mehr als einer Übersetzungsregel übereinstimmen kann, müssen Sie sicherstellen, dass die einschränkenderen Regeln über den weniger einschränkenden Regeln angeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="088fb-229">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="088fb-230">Wenn Sie beispielsweise eine Übersetzungsregel verwenden, die mit einer beliebigen elfstelligen Nummer übereinstimmt, und eine andere Übersetzungsregel auf elfstellige Nummern zutrifft, die mit +1425 beginnen, muss die Regel für eine beliebige elfstellige Nummer <EM>unter</EM> der restriktiveren Regel platziert werden.</span><span class="sxs-lookup"><span data-stu-id="088fb-230">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted <EM>below</EM> the more restrictive rule.</span></span>

    
    </div>

19. <span data-ttu-id="088fb-231">Nachdem Sie die Trunkkonfiguration abgeschlossen haben, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="088fb-231">When you are finished configuring the trunk, click **OK**.</span></span>

20. <span data-ttu-id="088fb-232">Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit**, und klicken Sie anschließend auf **Commit für alle**.</span><span class="sxs-lookup"><span data-stu-id="088fb-232">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="088fb-233">Jedes Mal, wenn Sie eine Trunkkonfiguration erstellen oder ändern, müssen Sie den Befehl <STRONG>Commit für alle</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="088fb-233">Whenever you create or modify a trunk configuration, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="088fb-234">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="088fb-234">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

<span data-ttu-id="088fb-235">Nachdem Sie den trunk konfiguriert haben, fahren Sie mit dem Konfigurieren der medienumgehung fort, indem Sie zwischen den Optionen für die globale medienumgehung auswählen, wie unter [globale Medien Umgehungs Optionen in lync Server 2013](lync-server-2013-global-media-bypass-options.md) in der Bereitstellungsdokumentation beschrieben.</span><span class="sxs-lookup"><span data-stu-id="088fb-235">After you have configured the trunk, continue configuring media bypass by choosing between global media bypass options, as described in [Global media bypass options in Lync Server 2013](lync-server-2013-global-media-bypass-options.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="088fb-236">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="088fb-236">See Also</span></span>


[<span data-ttu-id="088fb-237">Konfigurieren eines Trunks ohne medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="088fb-237">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  


[<span data-ttu-id="088fb-238">Konfigurieren der medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="088fb-238">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="088fb-239">Optionen für die globale medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="088fb-239">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="088fb-240">Definieren von Übersetzungsregeln in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="088fb-240">Defining translation rules in Lync Server 2013</span></span>](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

