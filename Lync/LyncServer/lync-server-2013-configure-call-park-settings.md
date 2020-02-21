---
title: 'Lync Server 2013: Konfigurieren der Einstellungen für das Parken von Anrufen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Call Park settings
ms:assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425886(v=OCS.15)
ms:contentKeyID: 48183922
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b99bc06f22490013dd14dc8527bd3eb88938380
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-call-park-settings-in-lync-server-2013"></a>Konfigurieren von Einstellungen für das Parken von Anrufen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Wenn Sie die Standardeinstellungen für das Parken von Anrufen nicht verwenden möchten, können Sie Sie anpassen. Bei der Installation des Anwendung zum Parken von Anrufen werden standardmäßig globale Einstellungen konfiguriert. Sie können die globalen Einstellungen ändern, und Sie können außerdem standortspezifische Einstellungen angeben. Verwenden Sie das Cmdlet **New-CsCpsConfiguration**, um neue standortspezifische Einstellungen zu erstellen. Verwenden Sie das Cmdlet **Set-CsCpsConfiguration**, um vorhandene Einstellungen zu ändern.

<div>


> [!NOTE]  
> Es wird empfohlen, mindestens die Option <STRONG>OnTimeoutURI</STRONG> zu konfigurieren, um ein Fallbackziel anzugeben, das bei Auftreten einer Zeitüberschreitung für geparkte Anrufe und bei erfolglosen Rückrufversuchen verwendet wird.



</div>

Verwenden Sie das Cmdlet **New-CsCpsConfiguration** oder das Cmdlet **Set-CsCpsConfiguration**, um beliebige der folgenden Einstellungen zu konfigurieren:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Option</th>
<th>Festlegung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>CallPickupTimeoutThreshold</strong></p></td>
<td><p>Die Zeitspanne, die nach dem Parken eines Anrufs verstreicht, bis das Telefon zurückgerufen wird, an dem der Anruf entgegengenommen wurde.</p>
<p>Der Wert muss im Format "hh:mm:ss" eingegeben werden, um die Stunden, Minuten und Sekunden anzugeben. Der Mindestwert beträgt 10 Sekunden, der Maximalwert liegt bei 10 Minuten. Der Standardwert lautet "00:01:30".</p></td>
</tr>
<tr class="even">
<td><p><strong>"Enablemusiconhold"</strong></p></td>
<td><p>Legt fest, ob der Anrufer eines geparkten Anrufs Wartemusik hört.</p>
<p>Gültige Werte sind "True" oder "False". Der Standardwert lautet "True".</p></td>
</tr>
<tr class="odd">
<td><p><strong>"Maxcallpickupattempts"</strong></p></td>
<td><p>Die Anzahl von Rückrufversuchen, die für einen geparkten Anruf bei dem Telefon erfolgt, an dem der Anruf entgegengenommen wurde, bevor der Anruf an den Fallback-URI (Uniform Resource Identifier) weitergeleitet wird, der für <strong>OnTimeoutURI</strong> angegeben ist. Der Standardwert ist 1.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnTimeoutURI</strong></p></td>
<td><p>Die SIP-Adresse des Benutzers oder der Reaktionsgruppe, an die ein nicht beantworteter geparkter Anruf geroutet wird, wenn <strong>MaxCallPickupAttempts</strong> überschritten wird.</p>
<p>Bei diesem Wert muss es sich um einen SIP-URI handeln, der mit "sip:" beginnt. Beispiel: sip:bob@contoso.com. In der Standardeinstellung ist keine Weiterleitungsadresse angegeben.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-call-park-settings"></a>So konfigurieren Sie Einstellungen für das Parken von Anrufen

1.  Melden Sie sich an dem Computer an, auf dem lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md)beschrieben.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Ausführen
    
        New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
    
    <div>
    

    > [!TIP]  
    > Verwenden Sie das Cmdlet <STRONG>Get-CsSite</STRONG>, um den Standort zu ermitteln. Ausführliche Informationen finden Sie unter lync Server-Verwaltungsshell Dokumentation.

    
    </div>
    
    Beispiel:
    
        New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Anpassen der Wartemusik für das Parken von Anrufen in lync Server 2013](lync-server-2013-customize-call-park-music-on-hold.md)  


[New-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCpsConfiguration)  
[Gruppe-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCpsConfiguration)  
[Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

