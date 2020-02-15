---
title: 'Lync Server 2013: Aktivieren des Anruf Parks für Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Call Park for users
ms:assetid: 9430763f-3394-467c-9c6d-426bf761604e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398753(v=OCS.15)
ms:contentKeyID: 48184814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8d739c9987c0a17c29997fad8ac47b2d886fbea
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033804"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-call-park-for-users-in-lync-server-2013"></a>Parken von Anrufen für Benutzer in lync Server 2013 aktivieren

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-11_

Benutzer können Anrufe nicht Parken oder geparkte Anrufe abrufen, bis Sie in der VoIP-Richtlinie für das Parken von Anrufen aktiviert sind.

<div>


> [!NOTE]  
> Standardmäßig ist das Parken von Anrufen für alle Benutzer deaktiviert.



</div>

Sie können das Parken von Anrufen auf globaler Ebene oder auf Websiteebene oder Benutzerebene aktivieren. Der Benutzerbereich hat Vorrang vor dem Website Bereich, und der Website Bereich hat Vorrang vor dem globalen Bereich. Wenn Sie über mehrere VoIP-Richtlinien verfügen, überprüfen Sie alle Richtlinien, um das Parken von Anrufen zu aktivieren, und nicht nur die globale Richtlinie.

<div>

## <a name="to-use-lync-server-control-panel-to-enable-call-park-for-users"></a>So verwenden Sie lync Server-Systemsteuerung zum Aktivieren des Anruf Parks für Benutzer

1.  Melden Sie sich als Mitglied der Gruppe **RTCUniversalServerAdmins** oder als Benutzer mit der Administratorrolle **CsVoiceAdministrator**, **CsServerAdministrator** oder **CsAdministrator** beim Computer an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.

4.  Klicken Sie auf die Registerkarte **VoIP-Richtlinie**.

5.  Doppelklicken Sie auf eine vorhandene VoIP-Richtlinie, um das Dialogfeld **VoIP-Richtlinie bearbeiten** zu öffnen.

6.  Wählen Sie unter **Anruffunktionen** die Option **Parken von Anrufen aktivieren** aus.

7.  Klicken Sie auf **OK**, um die VoIP-Richtlinie zu speichern.

</div>

<div>

## <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>So verwenden Sie Cmdlets zum Aktivieren des Anruf Parks für Benutzer

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der administrativen Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Ausführen
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    Wenn Sie beispielsweise das Parken von Anrufen für die standardmäßige globale VoIP-Richtlinie aktivieren möchten:
    
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

