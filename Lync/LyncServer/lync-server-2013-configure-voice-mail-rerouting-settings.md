---
title: 'Lync Server 2013: Konfigurieren von Einstellungen für die Voicemailumleitung'
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
ms.openlocfilehash: b4ea243e87490bcabd48c866cce525d6bbd17077
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733845"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-voice-mail-rerouting-settings-in-lync-server-2013"></a>Konfigurieren von Einstellungen für die Voicemailumleitung in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-18_

Überlebensfähige Zweigstellen-Appliances und überlebensfähige Verzweigungs Server können bei einem WAN-Ausfall die Überlebensfähigkeit von Sprachnachrichten für Zweig Benutzer gewährleisten, wenn Exchange Unified Messaging (um) auf dem zentralen Standort installiert ist und eine Exchange um-Nachrichten automatische Telefonzentrale (AA) bereitgestellt wird. Wir empfehlen, dass Ihr Exchange-Administrator die AA so konfiguriert, dass nur Nachrichten akzeptiert werden, wodurch andere generische Funktionen wie die Übertragung an einen Benutzer oder die Übertragung an einen Operator deaktiviert werden. Alternativ können Sie eine generische AA-oder AA-Karte verwenden, die für die Weiterleitung des Anrufs angepasst wurde.

Ausführliche Informationen finden Sie im Abschnitt "Vorbereiten auf die Überlebensfähigkeit von Voicemail" in der Planning-Dokumentation unter Anforderungen an die [Sicherheit von Zweigstellen für lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) .

<div>

## <a name="to-configure-voice-mail-survivability"></a>So konfigurieren Sie die Überlebensfähigkeit von Voicemail

1.  Bitten Sie Ihren Exchange-Administrator, die AA so zu konfigurieren, dass nur Nachrichten akzeptiert werden (in der Exchange-Shell verwenden Sie das folgende Cmdlet: **UMAutoAttendant \<AA-Name\> -CallSomeoneEnabled $false**. Der Parameter, der angibt, dass das verlassen von Nachrichten (*SendVoiceMsgEnabled*) zulässig ist, ist standardmäßig wahr.

2.  Verwenden Sie in der lync Server-Verwaltungsshell das Cmdlet **New-CSVoiceMailReroutingConfiguration** , um die AA-Telefonnummer als Telefonnummer der Exchange UM-Telefonzentrale in der Konfiguration der Voicemail-Umleitung auf der Survivable Branch-Appliance oder dem Überlebenden Branch-Server festzulegen.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie die Einstellung Voicemail-Umleitung später ändern müssen, verwenden Sie dazu das Cmdlet " <STRONG>Satz-CsVoiceMailReRoutingConfiguration</STRONG> ". Ausführliche Informationen zu <STRONG>New-</STRONG> und CSVoiceMailReroutingConfiguration finden Sie in den Shell <STRONG>-</STRONG>Hilfethemen.

    
    </div>

3.  Legen Sie die Exchange-um-Teilnehmerzugriffsnummer fest, die dem Exchange um-Wählplan des Zweig Benutzers als die Exchange um-Teilnehmerzugriffsnummer in der Konfiguration der Voicemail-Umleitung auf der Survivable Branch-Appliance oder dem Survivable Branch-Server entspricht.
    
    <div>
    

    > [!NOTE]  
    > Konfigurieren Sie den Wählplan der Exchange um-Benutzer so, dass nur ein Wählplan für alle Verzweigungs Benutzer vorgesehen ist, die während eines WAN-Ausfalls Zugriff auf die Funktion "Voicemail erhalten" benötigen.

    
    </div>

**Nächster Schritt** für Survivor-Branch-Appliances oder Survivable Branch-Server: [Privatbenutzer auf einer Survivable Branch-Appliance oder einem Server in lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

