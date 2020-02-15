---
title: 'Lync Server 2013: Konfigurieren von Einstellungen für die Voicemail-Umleitung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure voice mail rerouting settings
ms:assetid: 7ab6be28-eabb-4a79-a796-648887d71b83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398606(v=OCS.15)
ms:contentKeyID: 48184593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fa98050e026c90438b1df0811daa4b5235c9732
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-voice-mail-rerouting-settings-in-lync-server-2013"></a><span data-ttu-id="2b5ee-102">Konfigurieren von Einstellungen für das Umleiten von Voicemail in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b5ee-102">Configure voice mail rerouting settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b5ee-103">_**Letztes Änderungsstand des Themas:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="2b5ee-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="2b5ee-104">Survivable Branch Appliances und Survivable Branch-Server können während eines WAN-Ausfalls die Überlebensfähigkeit von Voicemail für Zweigstellenbenutzer ermöglichen, wenn Exchange Unified Messaging (um) am zentralen Standort installiert ist und eine Exchange um automatische Nachrichtenzentrale (AA) bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="2b5ee-104">Survivable Branch Appliances and Survivable Branch Servers can provide voice mail survivability for branch users during a WAN outage, if Exchange Unified Messaging (UM) is installed at the central site and an Exchange UM Message Auto Attendant (AA) is deployed.</span></span> <span data-ttu-id="2b5ee-105">Es wird empfohlen, dass Ihr Exchange-Administrator die AA so konfigurieren, dass nur Nachrichten akzeptiert werden, wodurch andere generische Funktionen wie die Übertragung an einen Benutzer oder die Übertragung an einen Operator deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="2b5ee-105">We recommend that your Exchange administrator configure the AA to accept messages only, which disables other generic functionality, such as transfer to a user or transfer to an operator.</span></span> <span data-ttu-id="2b5ee-106">Alternativ können Sie ein generisches AA oder ein AA-Benutzerdefiniert verwenden, um den Anruf weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="2b5ee-106">Alternatively, you might use a generic AA or an AA customized to route the call.</span></span>

<span data-ttu-id="2b5ee-107">Ausführliche Informationen finden Sie im Abschnitt "Vorbereiten der Überlebensfähigkeit von Voicemail" der Anforderungen an die [Ausfallsicherheit für Zweigstellenstandorte für lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="2b5ee-107">For details, see the “Preparing for Voice Mail Survivability” section of [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) in the Planning documentation.</span></span>

<div>

## <a name="to-configure-voice-mail-survivability"></a><span data-ttu-id="2b5ee-108">So konfigurieren Sie die Ausfallsicherheit für VoIP-Funktionen</span><span class="sxs-lookup"><span data-stu-id="2b5ee-108">To configure voice mail survivability</span></span>

1.  <span data-ttu-id="2b5ee-109">Bitten Sie Ihren Exchange-Administrator, die AA so zu konfigurieren, dass nur Nachrichten akzeptiert werden (verwenden Sie in der Exchange-Shell das folgende Cmdlet: **UMAutoAttendant \<AA Name\> -CallSomeoneEnabled $false**.</span><span class="sxs-lookup"><span data-stu-id="2b5ee-109">Ask your Exchange administrator to configure the AA to accept messages only (in the Exchange Shell use the following cmdlet: **Set-UMAutoAttendant \<AA name\> -CallSomeoneEnabled $false**.</span></span> <span data-ttu-id="2b5ee-110">Der Parameter, der angibt, dass das verlassen von Nachrichten zulässig ist (*SendVoiceMsgEnabled*), ist standardmäßig true.</span><span class="sxs-lookup"><span data-stu-id="2b5ee-110">The parameter that specifies to allow leaving messages (*SendVoiceMsgEnabled*) is true by default.</span></span>

2.  <span data-ttu-id="2b5ee-111">Verwenden Sie im lync Server-Verwaltungsshell das Cmdlet **New-CSVoiceMailReroutingConfiguration** , um die AA-Telefonnummer Exchange um als Telefonnummer der automatischen Telefonzentrale in der Konfiguration für die Voicemail-Umleitung auf dem Survivable Branch Appliance oder Survivable Branch Server festzulegen.</span><span class="sxs-lookup"><span data-stu-id="2b5ee-111">In the Lync Server Management Shell, use the **New-CSVoiceMailReroutingConfiguration** cmdlet to set the AA phone number as the Exchange UM Auto Attendant phone number in the voice mail rerouting configuration on the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2b5ee-112">Wenn Sie die Voicemailumleitungseinstellungen ändern müssen, verwenden Sie das Cmdlet <STRONG>Set-CsVoiceMailReRoutingConfiguration</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="2b5ee-112">If you need to modify the voice mail rerouting setting later, use the <STRONG>Set-CsVoiceMailReRoutingConfiguration</STRONG> cmdlet to do so.</span></span> <span data-ttu-id="2b5ee-113">Ausführliche Informationen zu den Cmdlets <STRONG>New-</STRONG> und <STRONG>Set-CSVoiceMailReroutingConfiguration</STRONG> finden Sie in den Hilfethemen der Shell.</span><span class="sxs-lookup"><span data-stu-id="2b5ee-113">For details, about <STRONG>New-</STRONG> and <STRONG>Set-CSVoiceMailReroutingConfiguration</STRONG>, in the Shell Help topics.</span></span>

    
    </div>

3.  <span data-ttu-id="2b5ee-114">Legen Sie die Exchange um Teilnehmerzugriffsnummer, die den Exchange UM Wähleinstellungen des Zweig Benutzers entspricht, als Exchange um Teilnehmerzugriffsnummer in der Konfiguration für die Voicemail-Umleitung auf dem Survivable Branch Appliance oder Survivable Branch Server fest.</span><span class="sxs-lookup"><span data-stu-id="2b5ee-114">Set the Exchange UM subscriber access number that corresponds to the branch user’s Exchange UM dial plan as the Exchange UM subscriber access number in the voice mail rerouting configuration on the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2b5ee-115">Konfigurieren Sie die Exchange UM Wähleinstellungen der Benutzer so, dass allen Zweigstellenbenutzern nur ein Wählplan zugeordnet ist, der während eines WAN-Ausfalls auf die Funktion Get Voice Mail zugreifen muss.</span><span class="sxs-lookup"><span data-stu-id="2b5ee-115">Configure the Exchange UM users’ dial plan so that there is only one dial plan associated with all branch users who need access to the Get Voice Mail functionality during a WAN outage.</span></span>

    
    </div>

<span data-ttu-id="2b5ee-116">**Nächster Schritt** für Survivable Branch Appliances oder Survivable Branch Servers: [Privatbenutzer auf einem Survivable Branch Appliance oder Server in lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="2b5ee-116">**Next step** for Survivable Branch Appliances or Survivable Branch Servers: [Home users on a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

