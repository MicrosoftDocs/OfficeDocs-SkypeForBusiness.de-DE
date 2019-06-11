---
title: 'Lync Server 2013: Erstellen von Registrierungsstellen-Konfigurationseinstellungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create Registrar configuration settings
ms:assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182601(v=OCS.15)
ms:contentKeyID: 48185758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 624dc1cfcc8ba8de1f749d6a1a50de9989783070
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832774"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-registrar-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="01a84-102">Erstellen von Registrierungs Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01a84-102">Create Registrar configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01a84-103">_**Letztes Änderungsdatum des Themas:** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="01a84-103">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="01a84-p101">Mithilfe der Registrierungsstelle können Sie Proxyserver-Authentifizierungsmethoden konfigurieren. Das angegebene Authentifizierungsprotokoll legt fest, welche Art von Authentifizierungsaufforderungen die Server im Pool an die Clients senden. Die folgenden Protokolle sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="01a84-p101">You can use the Registrar to configure proxy server authentication methods. The authentication protocol you specify determines which type of challenges the servers in the pool issue to clients. The available protocols are:</span></span>

  - <span data-ttu-id="01a84-107">**Kerberos**   Dies ist das am stärksten für Clients verfügbare kennwortbasierte Authentifizierungsschema, das jedoch normalerweise nur für Unternehmensclients verfügbar ist, da es eine Clientverbindung mit einem Schlüssel Verteilungs Center (Kerberos-Domänencontroller) erfordert.</span><span class="sxs-lookup"><span data-stu-id="01a84-107">**Kerberos**   This is the strongest password-based authentication scheme available to clients, but it is normally available only to enterprise clients because it requires client connection to a Key Distribution Center (Kerberos domain controller).</span></span> <span data-ttu-id="01a84-108">Diese Einstellung ist geeignet, wenn der Server nur Enterprise-Clients authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="01a84-108">This setting is appropriate if the server authenticates only enterprise clients.</span></span>

  - <span data-ttu-id="01a84-109">**NTLM**   hierbei handelt es sich um die kennwortbasierte Authentifizierung, die für Clients verfügbar ist, die ein Hash Schema für Abfrage Antworten auf das Kennwort verwenden.</span><span class="sxs-lookup"><span data-stu-id="01a84-109">**NTLM**   This is the password-based authentication available to clients that use a challenge-response hashing scheme on the password.</span></span> <span data-ttu-id="01a84-110">Für Clients ohne Verbindung mit einem Schlüsselverteilungscenter (Kerberos-Domänencontroller), beispielsweise für Remotebenutzer, steht nur diese Form der Authentifizierung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="01a84-110">This is the only form of authentication available to clients without connectivity to a Key Distribution Center (Kerberos domain controller), such as remote users.</span></span> <span data-ttu-id="01a84-111">Wenn ein Server ausschließlich Remotebenutzer authentifiziert, sollten Sie NTLM auswählen.</span><span class="sxs-lookup"><span data-stu-id="01a84-111">If a server authenticates only remote users, you should choose NTLM.</span></span>

  - <span data-ttu-id="01a84-112">**Zertifikatauthentifizierung**   Dies ist die neue Authentifizierungsmethode, wenn der Serverzertifikate von lync Phone Edition-Clients, öffentlichen Telefonen, lync 2013 und der lync Windows Store-App abrufen muss.</span><span class="sxs-lookup"><span data-stu-id="01a84-112">**Certificate authentication**   This is the new authentication method when the server needs to obtain certificates from Lync Phone Edition clients, common area phones, Lync 2013 and the Lync Windows Store app.</span></span> <span data-ttu-id="01a84-113">Wenn sich ein Benutzer bei lync Phone Edition-Clients anmeldet und erfolgreich durch Bereitstelleneiner Personal Identification Number (PIN) authentifiziert wird, stellt lync Server 2013 den SIP-URI dem Telefon zur Verfügung und stellt ein signiertes lync Server-Zertifikat oder ein Benutzerzertifikat bereit. , die Joe (ex: SN=Joe@Contoso.com) auf dem Smartphone identifiziert.</span><span class="sxs-lookup"><span data-stu-id="01a84-113">On Lync Phone Edition clients, after a user signs in and is successfully authenticated by providing a personal identification number (PIN), Lync Server 2013 then provisions the SIP URI to the phone and provisions a Lync Server signed certificate or a user certificate that identifies Joe (Ex: SN=joe@contoso.com ) to the phone.</span></span> <span data-ttu-id="01a84-114">Dieses Zertifikat wird für die Authentifizierung beim Registrierungsdienst und den Webdiensten verwendet.</span><span class="sxs-lookup"><span data-stu-id="01a84-114">This certificate is used for authenticating with the Registrar and Web Services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="01a84-p105">Es wird empfohlen, sowohl Kerberos als auch NTLM zu aktivieren, wenn ein Server die Authentifizierung von Remote- und Unternehmensclients unterstützt. Durch eine Kommunikation des Edgeservers mit den internen Servern wird gewährleistet, dass Remoteclients nur die NTLM-Authentifizierung verwenden können. Wenn auf diesen Servern nur Kerberos verwendet wird, ist eine Authentifizierung von Remotebenutzern nicht möglich. Wenn Unternehmensbenutzer sich ebenfalls über den Server authentifizieren, wird Kerberos verwendet.</span><span class="sxs-lookup"><span data-stu-id="01a84-p105">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span><BR><span data-ttu-id="01a84-119">Wenn Sie lync Windows Store-App-Clients verwenden, müssen Sie die Zertifikatauthentifizierung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="01a84-119">If you will use Lync Windows Store app clients, you must enable certificate authentication.</span></span>



</div>

<span data-ttu-id="01a84-120">Führen Sie die folgenden Schritte aus, um eine neue Registrierungsstelle zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="01a84-120">Follow these steps to create a new Registrar.</span></span>

<div>

## <a name="to-create-new-registrar-configuration-settings"></a><span data-ttu-id="01a84-121">So erstellen Sie neue Konfigurationseinstellungen für eine Registrierungsstelle</span><span class="sxs-lookup"><span data-stu-id="01a84-121">To create new Registrar configuration settings</span></span>

1.  <span data-ttu-id="01a84-122">Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="01a84-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="01a84-123">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="01a84-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="01a84-124">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="01a84-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="01a84-125">Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Registrierungsstelle**.</span><span class="sxs-lookup"><span data-stu-id="01a84-125">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>

4.  <span data-ttu-id="01a84-126">Klicken Sie auf der Seite **Registrierungsstelle** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="01a84-126">On the **Registrar** page, click **New**</span></span>

5.  <span data-ttu-id="01a84-127">Klicken Sie unter **Dienst auswählen** auf den Dienst, auf den die Registrierungsstelle angewendet werden soll, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="01a84-127">In **Select a Service**, click the service to which the Registrar is to be applied and then click **OK**.</span></span>

6.  <span data-ttu-id="01a84-128">Wählen Sie im Abschnitt **Neue Registrierungsstelleneinstellung** je nach Funktionen der Clients und der Unterstützung in Ihrer Umgebung eine oder mehrere der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="01a84-128">In **New Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="01a84-129">**Kerberos-Authentifizierung aktivieren**: Die Server im Pool stellen Authentifizierungsaufforderungen mithilfe der Kerberos-Authentifizierung aus.</span><span class="sxs-lookup"><span data-stu-id="01a84-129">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
      - <span data-ttu-id="01a84-130">**NTLM-Authentifizierung aktivieren**: Die Server im Pool stellen Authentifizierungsaufforderungen mithilfe von NTLM aus.</span><span class="sxs-lookup"><span data-stu-id="01a84-130">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
      - <span data-ttu-id="01a84-131">**Zertifikatauthentifizierung aktivieren**: Die Server im Pool stellen Zertifikate an Clients aus.</span><span class="sxs-lookup"><span data-stu-id="01a84-131">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>

7.  <span data-ttu-id="01a84-132">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="01a84-132">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

