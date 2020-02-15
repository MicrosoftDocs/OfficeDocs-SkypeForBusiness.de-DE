---
title: 'Lync Server 2013: Konfigurieren von Voicemail-Escape'
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
ms.openlocfilehash: 131b36b87a3d930662cdd863dd4ebc1d0d69163e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-mail-escape-in-lync-server-2013"></a>Konfigurieren von Voicemail-Escapes in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-22_

Wenn ein Benutzer das gleichzeitige Klingeln für ein Mobiltelefon konfiguriert, werden Anrufer normalerweise an den persönlichen Voicemail-Dienst des Benutzers weitergeleitet, wenn das Mobiltelefon ausgeschaltet wird, wenn der Akku leer ist oder wenn sich das Mobiltelefon außerhalb des Empfangsbereichs befindet. Mit lync Server 2013 können sich Benutzer für geschäftsbezogene Anrufe entscheiden, die an das Voicemailsystem des Unternehmens weitergeleitet werden. Insbesondere kann ein Zeitgeber konfiguriert werden, und wenn der Anruf von der Voicemail des Carriers innerhalb des definierten Zeitbereichs beantwortet wird, trennt sich lync Server vom Voicemailsystem des Carriers (und der persönlichen Voicemail des Benutzers), während der verbleibende Benutzer Endpunkte im Unternehmenssystem Ringen weiter. Somit wird der Anrufer automatisch an das Voicemail-System des Unternehmens des Benutzers weitergeleitet.

Diese Konfiguration wird mithilfe des lync Server-Verwaltungsshell-Cmdlets, **festlegen-CsVoicePolicy**, auf VoIP-Richtlinienebene mit den folgenden Parametern ausgeführt.

<div>

## <a name="to-configure-voice-mail-escape"></a>So konfigurieren Sie die Voicemail-escapefunktion

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Geben Sie die folgenden Parameter für **Set-CsVoicePolicy** an:
    
      - **EnableVoicemailEscapeTimer** – Aktiviert oder deaktiviert den Escape-Timer.
    
      - **PSTNVoicemailEscapeTimer** – Gibt den Zeitüberschreitungswert in Millisekunden an. Der Standardwert lautet 1500 Millisekunden, und der Wert kan zwischen 0 und 8000 Millisekunden liegen.

</div>

<div>

## <a name="example"></a>Beispiel

    Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
    
    Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren von VoIP-Richtlinien und PSTN-Verwendungsdatensätzen zum Autorisieren von Anruffunktionen und-Berechtigungen in lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

