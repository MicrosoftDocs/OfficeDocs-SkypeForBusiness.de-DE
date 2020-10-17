---
title: 'Lync Server 2013: Konfigurieren der Telefonie für einen Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure telephony for a user
ms:assetid: 4546432e-c839-4517-a2c5-bc0d4d8c6a03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520988(v=OCS.15)
ms:contentKeyID: 48183987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86eade8f7a2ac1db627668ca78b8fb7869e6da71
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520372"
---
# <a name="configure-telephony-for-a-user-in-lync-server-2013"></a><span data-ttu-id="c37e1-102">Konfigurieren der Telefonie für einen Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c37e1-102">Configure telephony for a user in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c37e1-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c37e1-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c37e1-104">Die Telefonieeinstellungen sind einige der individuellen Einstellungen eines Benutzerkontos, die in lync Server-Systemsteuerung für den Benutzer konfiguriert werden können (das heißt, wenn der einzelne Benutzer für lync Server 2013 aktiviert wurde und die Organisation Telefonie unterstützt).</span><span class="sxs-lookup"><span data-stu-id="c37e1-104">Telephony settings are some of the individual settings of a user account that can be configured in Lync Server Control Panel for the user (that is, if the individual user has been enabled for Lync Server 2013 and the organization supports telephony).</span></span>

<span data-ttu-id="c37e1-105">Lync Server Benutzer Telefonie-Optionen umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c37e1-105">Lync Server user telephony options include the following:</span></span>

  - <span data-ttu-id="c37e1-106">**Audio/Video deaktiviert**     Der Benutzer kann mit Audio und Video keine Anrufe tätigen.</span><span class="sxs-lookup"><span data-stu-id="c37e1-106">**Audio/video disabled**   The user cannot make calls with audio and video.</span></span>

  - <span data-ttu-id="c37e1-107">Nur PC- **zu-PC**     Der Benutzer kann nur PC-zu-PC-Audio-oder-Videoanrufe tätigen.</span><span class="sxs-lookup"><span data-stu-id="c37e1-107">**PC-to-PC only**   The user can make only PC-to-PC audio or video calls.</span></span>

  - <span data-ttu-id="c37e1-108">**Enterprise-VoIP**     Der Benutzer kann die lync Server 2013-Infrastruktur verwenden, um alle eingehenden und ausgehenden Anrufe weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="c37e1-108">**Enterprise Voice**   The user can use the Lync Server 2013 infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="c37e1-109">Außerdem kann der Benutzer Anrufe von PC zu PC tätigen.</span><span class="sxs-lookup"><span data-stu-id="c37e1-109">The user can also make PC-to-PC calls.</span></span>

  - <span data-ttu-id="c37e1-110">**Remote Anrufsteuerung**     Der Benutzer kann lync Server 2013 verwenden, um das Desktoptelefon zu steuern, und kann auch PC-zu-PC-Anrufe tätigen.</span><span class="sxs-lookup"><span data-stu-id="c37e1-110">**Remote call control**   The user can use Lync Server 2013 to control the desktop phone, and can also make PC-to-PC calls.</span></span>

<span data-ttu-id="c37e1-111">Ausführliche Informationen zum Konfigurieren der Telefonie für eine Organisation finden Sie unter [Konfigurieren der Telefonie für einen Benutzer in lync Server 2013](lync-server-2013-configure-telephony-for-a-user.md) und [Bereitstellen von Enterprise-VoIP in lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c37e1-111">For details about configuring telephony for an organization, see [Configure telephony for a user in Lync Server 2013](lync-server-2013-configure-telephony-for-a-user.md) and [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span>

<div>

## <a name="to-configure-telephony-for-a-specific-user-account"></a><span data-ttu-id="c37e1-112">So konfigurieren Sie Telefonieoptionen für ein bestimmtes Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="c37e1-112">To configure telephony for a specific user account</span></span>

1.  <span data-ttu-id="c37e1-113">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="c37e1-113">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c37e1-114">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c37e1-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c37e1-115">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c37e1-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c37e1-116">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="c37e1-116">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="c37e1-117">Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des gewünschten Benutzerkontos ein, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="c37e1-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="c37e1-118">Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="c37e1-118">In the table, click the user account that you want to modify.</span></span>

6.  <span data-ttu-id="c37e1-119">Klicken Sie im Menü **Bearbeiten** auf **Ändern**.</span><span class="sxs-lookup"><span data-stu-id="c37e1-119">On the **Edit** menu, click **Modify**.</span></span>

7.  <span data-ttu-id="c37e1-120">Führen Sie im Dialogfeld **Telefonie** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="c37e1-120">In **Telephony**, do the following:</span></span>
    
      - <span data-ttu-id="c37e1-121">Klicken Sie zum Deaktivieren von Audio- und Videoanrufen für den Benutzer auf **Audio/Video deaktiviert**.</span><span class="sxs-lookup"><span data-stu-id="c37e1-121">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
      - <span data-ttu-id="c37e1-p103">Wenn Sie für den Benutzer die Audiokommunikation von PC zu PC, jedoch nicht die Remoteanrufsteuerung oder Enterprise-VoIP aktivieren möchten, klicken Sie auf **Nur PC zu PC**. Geben Sie einen Wert für **Anschluss-URI** für das Telefon an, das der Benutzer für die Audiokommunikation von PC zu PC verwendet.</span><span class="sxs-lookup"><span data-stu-id="c37e1-p103">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**. Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
      - <span data-ttu-id="c37e1-124">Klicken Sie auf **Enterprise-VoIP**, um die Telefonanrufe des Benutzers mithilfe der lync Server 2010-Infrastruktur gemäß der Dienstleistungsklasse-Richtlinie weiterzuleiten, einschließlich der PC-zu-PC-Audiokommunikation.</span><span class="sxs-lookup"><span data-stu-id="c37e1-124">To route the user's phone calls by using the Lync Server 2010 infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="c37e1-125">Geben Sie unter **Anschluss-URI** die Telefonnummer für Enterprise-VoIP an.</span><span class="sxs-lookup"><span data-stu-id="c37e1-125">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="c37e1-126">Geben Sie unter **Richtlinie für Wähleinstellungen** und **VoIP-Richtlinie** die entsprechenden Richtlinien für den Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="c37e1-126">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="c37e1-127">Wählen Sie unter **Ortungsrichtlinie** das angemessene Standortprofil aus, um die Normalisierungsregeln für die Übersetzung der vom Benutzer gewählten Telefonnummern in das E.164-Format anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c37e1-127">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
      - <span data-ttu-id="c37e1-128">Klicken Sie zum Aktivieren der Remoteanrufsteuerung, mit der Benutzer Ihre Desktop-Telefonleitung von lync Server 2013 aus steuern können, um PC-zu-PC-Anrufe und Anrufe von PC zu Telefon zu tätigen, auf **Remoteanrufsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="c37e1-128">To enable remote call control, which enables users to control their desktop phone line from Lync Server 2013 to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="c37e1-129">Geben Sie unter **Leitungs-URI**die Telefonnummer für die Remoteanrufsteuerung an.</span><span class="sxs-lookup"><span data-stu-id="c37e1-129">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="c37e1-130">Der Benutzer muss über eine Telefon-und PBX-Verbindung (Private Branch Exchange) für die Anrufweiterleitung verfügen.</span><span class="sxs-lookup"><span data-stu-id="c37e1-130">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c37e1-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c37e1-131">See Also</span></span>


[<span data-ttu-id="c37e1-132">Ändern von Benutzerkontoeigenschaften in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c37e1-132">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

