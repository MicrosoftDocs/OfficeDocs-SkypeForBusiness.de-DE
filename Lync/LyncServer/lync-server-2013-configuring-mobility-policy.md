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
ms.openlocfilehash: 82ca5fbd079f428edf48ef3f0c28bd3677a5acde
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-policy-in-lync-server-2013"></a>Konfigurieren von mobilitätsrichtlinien in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-13_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 bietet mobilitätsrichtlinien, die festlegen, wer Mobilitätsfunktionen nutzen, über Arbeit anrufen, VoIP (Voice over IP) oder Video verwenden kann und ob WLAN für VoIP oder Video erforderlich ist. Das Feature "Anruf über Arbeit" ermöglicht einem mobilen Benutzer das tätigen und annehmen von Anrufen auf einem Mobiltelefon mithilfe einer geschäftlichen Telefonnummer anstelle der Mobiltelefonnummer. Dieses Feature verhindert, dass die angerufene Person die Mobiltelefonnummer des Anrufers sieht und einem Benutzer die Möglichkeit gibt, ausgehende Gebühren zu vermeiden. Durch die Konfiguration von VoIP und Video können Benutzer VoIP-Anrufe und Videos empfangen und tätigen. Einstellungen für die WLAN-Nutzung definieren, ob das Gerät eines Benutzers ein WLAN-Netzwerk über ein Mobilfunknetz verwenden muss.

Standardmäßig sind Mobilität, Anruf über Arbeit und VoIP-und Videofunktionen aktiviert. Die Einstellungen, die WLAN für VoIP und Video erfordern, sind deaktiviert. Administratoren können durch Ausführen eines Cmdlets bestimmen, wer Zugriff auf diese Features hat. Sie können die Optionen global, nach Standort oder nach Benutzer deaktivieren.

Benutzer müssen die beiden folgenden Voraussetzungen erfüllen, um die Mobilitätsfeatures und das Feature "Geschäftlich anrufen" verwenden zu können:

  - Benutzer müssen für lync Server 2013 aktiviert sein.

  - Benutzer müssen für Enterprise-VoIP aktiviert sein.

  - Benutzern muss eine Mobilitätsrichtlinie zugewiesen sein, für die die Option **EnableMobility** auf TRUE gesetzt ist.

Zum Verwenden des Features Geschäftlich anrufen müssen Benutzer zudem die beiden folgenden Voraussetzungen erfüllen:

  - Benutzern muss eine VoIP-Richtlinie zugewiesen sein, für die die Option **Gleichzeitiges Klingeln von Telefonen aktivieren** aktiviert ist.

  - Benutzern muss eine Mobilitätsrichtlinie mit der Option **EnableOutsideVoice** und dem Wert "True" zugewiesen werden.

<div>


> [!NOTE]  
> Benutzer, die nicht für Enterprise-VoIP aktiviert sind, können mit ihren mobilen Geräten lync-VoIP-Anrufe (Voice over IP) durchführen oder an Konferenzen teilnehmen, indem Sie den Link klicken, um auf Ihren mobilen Geräten zu verbinden, wenn Sie diesen Benutzern die entsprechenden Optionen für die VoIP-Richtlinie zuweisen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-defining-your-mobility-requirements.md">Definieren Ihrer Mobilitätsanforderungen für lync Server 2013</A>.



</div>

Ausführliche Informationen zum Aktivieren von Benutzern für lync Server 2013 finden Sie unter [deaktivieren oder erneutes Aktivieren des Benutzerkontos für lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md). Ausführliche Informationen zum Aktivieren von Benutzern für Enterprise-VoIP finden Sie unter [Aktivieren von Benutzern für Enterprise-VoIP in lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md). Ausführliche Informationen zum Festlegen von VoIP-Richtlinienoptionen finden Sie unter [Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).

<div>

## <a name="to-modify-global-mobility-policy"></a>So ändern Sie die globale Mobilitätsrichtlinie

1.  Melden Sie sich an einem beliebigen Computer an, auf dem lync Server-Verwaltungsshell und OCSCore als Mitglied der CsAdministrator-Rolle installiert sind.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Deaktivieren Sie den Zugriff auf die Mobilität und Geschäftlich anrufen global. Geben Sie an der Befehlszeile Folgendes ein:
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > Sie können auch nur den Zugriff auf das Feature Geschäftlich anrufen deaktivieren, ohne den Zugriff auf die Mobilität zu deaktivieren. Es ist jedoch nicht möglich, den Zugriff auf die Mobilität deaktivieren, ohne auch den Zugriff auf Geschäftlich anrufen zu deaktivieren.

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a>So ändern Sie die Mobilitätsrichtlinie nach Standort

1.  Melden Sie sich an einem beliebigen Computer an, auf dem lync Server-Verwaltungsshell und OCSCore als Mitglied der CsAdministrator-Rolle installiert sind.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Erstellen Sie eine Richtlinie auf Standortebene, und schalten Sie VoIP und Video aus, und aktivieren Sie WLAN für IP-Audio und IP-Video nach Standort. Geben Sie in die Befehlszeile Folgendes ein:
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a>So ändern Sie die Mobilitätsrichtlinie nach Benutzer

1.  Melden Sie sich an einem beliebigen Computer an, auf dem lync Server-Verwaltungsshell und OCSCore als Mitglied der CsAdministrator-Rolle installiert sind.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Erstellen Sie Mobilitätsrichtlinien auf Benutzerebene, und deaktivieren Sie den Zugriff auf die Mobilität und Geschäftlich anrufen nach Benutzer. Geben Sie an der Befehlszeile Folgendes ein:
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    Sie können auch nur den Zugriff auf das Feature Geschäftlich anrufen deaktivieren, ohne den Zugriff auf die Mobilität zu deaktivieren. Es ist jedoch nicht möglich, den Zugriff auf die Mobilität deaktivieren, ohne auch den Zugriff auf Geschäftlich anrufen zu deaktivieren.
    
    Beispiel:
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Deaktivieren oder erneutes Aktivieren des Benutzerkontos für lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[Aktivieren von Benutzern für Enterprise-VoIP in lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)  
[Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


[Definieren der Mobilitätsanforderungen für lync Server 2013](lync-server-2013-defining-your-mobility-requirements.md)  


[New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)  
[Gruppe-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)  
[Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)  
[Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)  
[Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

