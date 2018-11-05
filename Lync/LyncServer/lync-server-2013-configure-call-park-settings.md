---
title: Konfigurieren von Einstellungen für das Parken von Anrufen in Lync Server 2013
TOCTitle: Konfigurieren von Einstellungen für das Parken von Anrufen in Lync Server 2013
ms:assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425886(v=OCS.15)
ms:contentKeyID: 49293740
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Einstellungen für das Parken von Anrufen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Wenn Sie nicht die Standardeinstellungen für die Parken von Anrufen verwenden möchten, können Sie sie anpassen. Bei der Anwendung zum Parken von Anrufen-Installation werden standardmäßig globale Einstellungen konfiguriert. Sie können die globalen Einstellungen ändern, und Sie können außerdem standortspezifische Einstellungen angeben. Verwenden Sie das Cmdlet **New-CsCpsConfiguration**, um neue standortspezifische Einstellungen zu erstellen. Verwenden Sie das Cmdlet **Set-CsCpsConfiguration**, um vorhandene Einstellungen zu ändern.


> [!NOTE]
> Es wird empfohlen, mindestens die Option <STRONG>OnTimeoutURI</STRONG> zu konfigurieren, um ein Fallbackziel anzugeben, das bei Auftreten einer Zeitüberschreitung für geparkte Anrufe und bei erfolglosen Rückrufversuchen verwendet wird.



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
<p>Der Wert muss im Format &quot;hh:mm:ss&quot; eingegeben werden, um die Stunden, Minuten und Sekunden anzugeben. Der Mindestwert beträgt 10 Sekunden, der Maximalwert liegt bei 10 Minuten. Der Standardwert lautet &quot;00:01:30&quot;.</p></td>
</tr>
<tr class="even">
<td><p><strong>EnableMusicOnHold</strong></p></td>
<td><p>Legt fest, ob der Anrufer eines geparkten Anrufs Wartemusik hört.</p>
<p>Gültige Werte sind &quot;True&quot; oder &quot;False&quot;. Der Standardwert lautet &quot;True&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxCallPickupAttempts</strong></p></td>
<td><p>Die Anzahl von Rückrufversuchen, die für einen geparkten Anruf bei dem Telefon erfolgt, an dem der Anruf entgegengenommen wurde, bevor der Anruf an den Fallback-URI (Uniform Resource Identifier) weitergeleitet wird, der für <strong>OnTimeoutURI</strong> angegeben ist. Der Standardwert ist 1.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnTimeoutURI</strong></p></td>
<td><p>Die SIP-Adresse des Benutzers oder der Reaktionsgruppe, an die ein nicht beantworteter geparkter Anruf geroutet wird, wenn <strong>MaxCallPickupAttempts</strong> überschritten wird.</p>
<p>Bei diesem Wert muss es sich um einen SIP-URI handeln, der mit &quot;sip:&quot; beginnt. Beispiel: sip:bob@contoso.com. In der Standardeinstellung ist keine Weiterleitungsadresse angegeben.</p></td>
</tr>
</tbody>
</table>


## So konfigurieren Sie Einstellungen für die Parken von Anrufen

1.  Melden Sie sich auf dem Computer, auf dem die Lync Server-Verwaltungsshell installiert ist, als Mitglied der Gruppe "RTCUniversalServerAdmins" oder mit den erforderlichen Benutzerrechten an, wie beschrieben unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie folgenden Befehl aus:
    
        New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
    

    > [!TIP]
    > Verwenden Sie das Cmdlet <STRONG>Get-CsSite</STRONG>, um den Standort zu ermitteln. Ausführliche Informationen finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell.

    
    Beispiel:
    
        New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com

## Siehe auch

#### Aufgaben

[Anpassen der Wartemusik für das Parken von Anrufen in Lync Server 2013](lync-server-2013-customize-call-park-music-on-hold.md)  

#### Weitere Ressourcen

[New-CsCpsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCpsConfiguration)  
[Set-CsCpsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCpsConfiguration)  
[Get-CsSite](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsSite)

