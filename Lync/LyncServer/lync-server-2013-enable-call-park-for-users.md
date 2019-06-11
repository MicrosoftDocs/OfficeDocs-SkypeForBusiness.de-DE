---
title: 'Lync Server 2013: Aktivieren des Anruf Parks für Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Call Park for users
ms:assetid: 9430763f-3394-467c-9c6d-426bf761604e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398753(v=OCS.15)
ms:contentKeyID: 48184814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16538ba00571c429493a2bc0ce1ef14b0a331305
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-call-park-for-users-in-lync-server-2013"></a>Aktivieren des Anruf Parks für Benutzer in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-11_

Benutzer können keine Anrufe parken oder geparkte Anrufe abrufen, bis Sie in der VoIP-Richtlinie für den Anruf Park aktiviert sind.

<div>


> [!NOTE]  
> Standardmäßig ist der Parken von Anrufen für alle Benutzer deaktiviert.



</div>

Sie können das Parken von Anrufen im globalen Bereich oder auf dem Website Bereich oder dem Benutzerbereich aktivieren. Der Benutzerbereich hat Vorrang vor dem Website Bereich, und der Website Bereich hat Vorrang vor dem globalen Bereich. Wenn Sie über mehrere VoIP-Richtlinien verfügen, überprüfen Sie alle Richtlinien, um den Anruf Park zu aktivieren, und nicht nur die globale Richtlinie.

<div>

## <a name="to-use-lync-server-control-panel-to-enable-call-park-for-users"></a>So verwenden Sie die lync Server-Systemsteuerung zum Aktivieren des Anruf Parks für Benutzer

1.  Melden Sie sich als Mitglied der Gruppe **RTCUniversalServerAdmins** oder als Benutzer mit der Administratorrolle **CsVoiceAdministrator**, **CsServerAdministrator** oder **CsAdministrator** beim Computer an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.

4.  Klicken Sie auf die Registerkarte **VoIP-Richtlinie**.

5.  Doppelklicken Sie auf eine vorhandene VoIP-Richtlinie, um das Dialogfeld **VoIP-Richtlinie bearbeiten** zu öffnen.

6.  Wählen Sie unter **Anruffunktionen** die Option **Parken von Anrufen aktivieren** aus.

7.  Klicken Sie auf **OK**, um die VoIP-Richtlinie zu speichern.

</div>

<div>

## <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>So verwenden Sie Cmdlets zum Aktivieren des Anruf Parks für Benutzer

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe „RTCUniversalServerAdmins“ oder als Benutzer mit der administrativen Rolle „CsVoiceAdministrator“, „CsServerAdministrator“ oder „CsAdministrator“ an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie folgenden Befehl aus:
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    So können Sie beispielsweise den Anruf Park für die standardmäßige globale VoIP-Richtlinie aktivieren:
    
        Set-CsVoicePolicy -EnableCallPark $true

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

