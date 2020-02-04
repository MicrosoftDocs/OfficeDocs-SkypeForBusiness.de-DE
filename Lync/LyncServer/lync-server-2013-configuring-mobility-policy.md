---
title: 'Lync Server 2013: Konfigurieren der Mobilitätsrichtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring mobility policy
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690018(v=OCS.15)
ms:contentKeyID: 48184204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39a7f0791def99e0b42a57b1f13aae88abbfafa4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763399"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-policy-in-lync-server-2013"></a>Konfigurieren der Mobilitätsrichtlinie in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-13_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 bietet mobilitätsrichtlinien, die bestimmen, wer Mobilitätsfunktionen nutzen, über Arbeit anrufen, VoIP (Voice over IP) oder Video verwenden kann und ob WLAN für VoIP oder Video erforderlich ist. Mit der Funktion Anruf über Arbeit kann ein Mobilfunknutzer Anrufe auf einem Mobiltelefon tätigen und empfangen, indem er eine geschäftliche Telefonnummer anstelle der Mobiltelefonnummer verwendet. Dieses Feature verhindert, dass der angerufene die Handynummer des Anrufers sieht und es einem Benutzer ermöglicht, ausgehende Gebühren zu vermeiden. Die Konfiguration von VoIP und Video ermöglicht es Benutzern, VoIP-Anrufe und Videos zu empfangen und zu führen. Einstellungen für die WLAN-Nutzung definieren, ob das Gerät eines Benutzers ein WLAN-Netzwerk über ein Mobilfunknetz verwenden muss.

Standardmäßig sind Mobilität, Anruf über die Arbeit und die VoIP-und Videofunktionen aktiviert. Die Einstellungen für WLAN für VoIP und Video sind deaktiviert. Administratoren können ermitteln, wer Zugriff auf diese Features hat, indem Sie ein Cmdlet ausführen. Sie können Optionen Global, nach Website oder nach Benutzer deaktivieren.

Um Mobilitätsfunktionen nutzen und über die Arbeit anrufen zu können, müssen die Benutzer die folgenden Voraussetzungen erfüllen:

  - Benutzer müssen für lync Server 2013 aktiviert sein.

  - Benutzer müssen für Enterprise-VoIP aktiviert sein.

  - Benutzern muss eine Mobilitätsrichtlinie zugewiesen werden, bei der die **EnableMobility** -Option auf "true" festgelegt ist.

Damit Benutzer den Anruf über die Arbeit nutzen können, müssen Sie die beiden folgenden zusätzlichen Voraussetzungen erfüllen:

  - Benutzern muss eine VoIP-Richtlinie zugewiesen sein, für die die Option **gleichzeitiges Anrufen von Telefonen aktivieren** aktiviert ist.

  - Benutzern muss eine Mobilitätsrichtlinie zugewiesen werden, bei der die **EnableOutsideVoice** -Option auf "true" festgelegt ist.

<div>


> [!NOTE]  
> Benutzer, die nicht für Enterprise-VoIP aktiviert sind, können Ihre mobilen Geräte verwenden, um lync zu lync-VoIP-Anrufen (Voice over IP) zu machen oder an Konferenzen teilzunehmen, indem Sie auf Ihren mobilen Geräten über den Link zum teilnehmen klicken, wenn Sie diesen Benutzern die entsprechenden Optionen für VoIP-Richtlinien zuweisen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-defining-your-mobility-requirements.md">Definieren Ihrer Mobilitätsanforderungen für lync Server 2013</A>.



</div>

Details zum Aktivieren von Benutzern für lync Server 2013 finden Sie unter [deaktivieren oder erneutes Aktivieren des Benutzerkontos für lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md). Details zum Aktivieren von Benutzern für Enterprise-VoIP finden Sie unter [Aktivieren von Benutzern für Enterprise-VoIP in lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md). Details zum Festlegen von VoIP-Richtlinienoptionen finden Sie unter [Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).

<div>

## <a name="to-modify-global-mobility-policy"></a>So ändern Sie die globale Mobilitätsrichtlinie

1.  Melden Sie sich bei einem beliebigen Computer an, auf dem die lync Server-Verwaltungsshell und OCSCore als Mitglied der CsAdministrator-Rolle installiert sind.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Deaktivieren Sie den Zugriff auf Mobilität, und rufen Sie über die Arbeit weltweit an. Geben Sie in der Befehlszeile Folgendes ein:
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > Sie können den Anruf über die Arbeit ausschalten, ohne den Zugriff auf Mobilität zu deaktivieren. Sie können die Mobilität jedoch nicht deaktivieren, ohne dass Sie den Anruf über die Arbeit abschalten.

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a>So ändern Sie die mobilitätsrichtlinien nach Website

1.  Melden Sie sich bei einem beliebigen Computer an, auf dem die lync Server-Verwaltungsshell und OCSCore als Mitglied der CsAdministrator-Rolle installiert sind.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Erstellen Sie eine Richtlinie auf Websiteebene, und deaktivieren Sie VoIP und Video, und aktivieren Sie WLAN für IP-Audio und für IP-Video nach Website anfordern. Geben Sie in der Befehlszeile Folgendes ein:
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a>So ändern Sie die mobilitätsrichtlinien nach Benutzern

1.  Melden Sie sich bei einem beliebigen Computer an, auf dem die lync Server-Verwaltungsshell und OCSCore als Mitglied der CsAdministrator-Rolle installiert sind.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Erstellen Sie mobilitätsrichtlinien auf Benutzerebene, deaktivieren Sie Mobilität, und rufen Sie Sie über die Arbeit des Benutzers an. Geben Sie in der Befehlszeile Folgendes ein:
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    Sie können den Anruf über die Arbeit ausschalten, ohne den Zugriff auf Mobilität zu deaktivieren. Sie können die Mobilität jedoch nicht deaktivieren, ohne dass Sie den Anruf über die Arbeit abschalten.
    
    Beispiel:
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Deaktivieren oder erneutes Aktivieren des Benutzerkontos für lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[Aktivieren von Benutzern für Enterprise-VoIP in lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)  
[Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


[Definieren der Mobilitätsanforderungen für Lync Server 2013](lync-server-2013-defining-your-mobility-requirements.md)  


[New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)  
[Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)  
[Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)  
[Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)  
[Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

