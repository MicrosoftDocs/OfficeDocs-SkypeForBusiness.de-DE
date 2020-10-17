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
ms.openlocfilehash: b51a529ee7bc4fd1148413058ceaf1f1f6d61e06
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520182"
---
# <a name="configure-voice-mail-rerouting-settings-in-lync-server-2013"></a>Konfigurieren von Einstellungen für das Umleiten von Voicemail in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-18_

Survivable Branch Appliances und Survivable Branch-Server können während eines WAN-Ausfalls die Überlebensfähigkeit von Voicemail für Zweigstellenbenutzer ermöglichen, wenn Exchange Unified Messaging (um) am zentralen Standort installiert ist und eine Exchange um automatische Nachrichtenzentrale (AA) bereitgestellt wird. Es wird empfohlen, dass Ihr Exchange-Administrator die AA so konfigurieren, dass nur Nachrichten akzeptiert werden, wodurch andere generische Funktionen wie die Übertragung an einen Benutzer oder die Übertragung an einen Operator deaktiviert werden. Alternativ können Sie ein generisches AA oder ein AA-Benutzerdefiniert verwenden, um den Anruf weiterzuleiten.

Ausführliche Informationen finden Sie im Abschnitt "Vorbereiten der Überlebensfähigkeit von Voicemail" der Anforderungen an die [Ausfallsicherheit für Zweigstellenstandorte für lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) in der Planungsdokumentation.

<div>

## <a name="to-configure-voice-mail-survivability"></a>So konfigurieren Sie die Ausfallsicherheit für VoIP-Funktionen

1.  Bitten Sie Ihren Exchange-Administrator, die AA so zu konfigurieren, dass nur Nachrichten akzeptiert werden (verwenden Sie in der Exchange-Shell das folgende Cmdlet: **festlegen-UMAutoAttendant \<AA name\> -CallSomeoneEnabled $false**. Der Parameter, der angibt, dass das verlassen von Nachrichten zulässig ist (*SendVoiceMsgEnabled*), ist standardmäßig true.

2.  Verwenden Sie im lync Server-Verwaltungsshell das Cmdlet **New-CSVoiceMailReroutingConfiguration** , um die AA-Telefonnummer Exchange um als Telefonnummer der automatischen Telefonzentrale in der Konfiguration für die Voicemail-Umleitung auf dem Survivable Branch Appliance oder Survivable Branch Server festzulegen.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie die Voicemailumleitungseinstellungen ändern müssen, verwenden Sie das Cmdlet <STRONG>Set-CsVoiceMailReRoutingConfiguration</STRONG>. Ausführliche Informationen zu den Cmdlets <STRONG>New-</STRONG> und <STRONG>Set-CSVoiceMailReroutingConfiguration</STRONG> finden Sie in den Hilfethemen der Shell.

    
    </div>

3.  Legen Sie die Exchange um Teilnehmerzugriffsnummer, die den Exchange UM Wähleinstellungen des Zweig Benutzers entspricht, als Exchange um Teilnehmerzugriffsnummer in der Konfiguration für die Voicemail-Umleitung auf dem Survivable Branch Appliance oder Survivable Branch Server fest.
    
    <div>
    

    > [!NOTE]  
    > Konfigurieren Sie die Exchange UM Wähleinstellungen der Benutzer so, dass allen Zweigstellenbenutzern nur ein Wählplan zugeordnet ist, der während eines WAN-Ausfalls auf die Funktion Get Voice Mail zugreifen muss.

    
    </div>

**Nächster Schritt** für Survivable Branch Appliances oder Survivable Branch Servers: [Privatbenutzer auf einem Survivable Branch Appliance oder Server in lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

