---
title: 'Lync Server 2013: Konfigurieren der Voicemail-Escape-Konfiguration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice mail escape
ms:assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688157(v=OCS.15)
ms:contentKeyID: 49733761
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c32d3bbc39d8f18e30153193c1e722db1ec9d50e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734435"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-mail-escape-in-lync-server-2013"></a>Konfigurieren von Voicemail-Escape in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

Wenn ein Benutzer das gleichzeitige Klingeln auf einem Mobiltelefon konfiguriert, wird ein Anrufer in der Regel an die persönliche Voicemail des Benutzers weitergeleitet, wenn das Mobiltelefon ausgeschaltet ist, der Akku nicht mehr zur verweilen oder außerhalb des gültigen Bereichs liegt. Mit lync Server 2013 können Benutzer entscheiden, dass unternehmensbezogene Anrufe an das Voicemailsystem des Unternehmens weitergeleitet werden. Insbesondere kann ein Zeitgeber konfiguriert werden, und wenn der Anruf von der Voicemail des Netzbetreibers innerhalb des definierten Zeitraums beantwortet wird, wird die Verbindung zwischen lync Server und dem Voicemailsystem des Netzbetreibers (und der persönlichen Voicemail des Benutzers) getrennt, während der verbleibende Benutzer Endpunkte im Unternehmenssystem Klingeln weiterhin. Auf diese Weise wird der Anrufer automatisch an die Firmen-Voicemail des Benutzers weitergeleitet.

Diese Konfiguration wird mit dem Cmdlet "lync Server-Verwaltungsshell", " **Satz-CsVoicePolicy**", auf der VoIP-Richtlinienebene mit den folgenden Parametern ausgeführt.

<div>

## <a name="to-configure-voice-mail-escape"></a>So konfigurieren Sie Voicemail Escape

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Geben Sie die folgenden Parameter für **Set-CsVoicePolicy** an:
    
      - **EnableVoicemailEscapeTimer**: Aktiviert oder deaktiviert den Escape-Timer.
    
      - **PSTNVoicemailEscapeTimer**: Gibt den Timeoutwert in Millisekunden an. Der Standardwert lautet 1500 Millisekunden und der Wert kann zwischen 0 und 8000 Millisekunden liegen.

</div>

<div>

## <a name="example"></a>Beispiel

    Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
    
    Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren von VoIP-Richtlinien und PSTN-Verwendungsdatensätzen zum Autorisieren von Anruffunktionen und -berechtigungen in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

