---
title: Konfigurieren von Netzwerkstandortverknüpfungen
TOCTitle: Konfigurieren von Netzwerkstandortverknüpfungen
ms:assetid: 7e9147ae-e727-46c8-8c1a-6c13201f09be
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg521023(v=OCS.15)
ms:contentKeyID: 49294538
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Netzwerkstandortverknüpfungen

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Innerhalb einer Anrufsteuerungskonfiguration können Sie standortübergreifende Netzwerkrichtlinien zur Definition von Bandbreiteneinschränkungen zwischen Standorten erstellen, die direkt verbunden sind. Wenn Netzwerkstandorte eine direkte Verbindung teilen, können Bandbreiteneinschränkungen für Audio- und Videoverbindungen zwischen diesen zwei Standorten definiert werden. Die Lync Server-Systemsteuerung kann nicht zum Konfigurieren von Netzwerkstandortrichtlinien verwendet werden. Diese Aufgaben können ausschließlich mithilfe der Cmdlets aus der Lync Server-Verwaltungsshell ausgeführt werden. Eine Netzwerkstandortverknüpfung (auch als standortübergreifende Netzwerkrichtlinie bezeichnet) kann über die Lync Server-Verwaltungsshell erstellt, geändert und entfernt werden.

## So erstellen Sie eine Netzwerkstandortverknüpfung

1.  Melden Sie sich auf dem Computer, auf dem die Lync Server-Verwaltungsshell installiert ist, als Mitglied der Gruppe "RTCUniversalServerAdmins" oder mit den erforderlichen Benutzerrechten an, wie beschrieben unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Geben Sie an der Eingabeaufforderung den folgenden Befehl ein, und verwenden Sie dabei die für Ihre Konfiguration gültigen Werte:
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    In diesem Beispiel wird die neue Netzwerkstandortverknüpfung "Reno\_Portland" erstellt, über die Bandbreiteneinschränkungen zwischen den Netzwerkstandorten "Reno" und "Portland" festgelegt werden. Die Netzwerkstandorte und das Bandbreitenrichtlinienprofil müssen bereits vorhanden sein, bevor Sie diesen Befehl ausführen.

Eine ausführliche Beschreibung der Parameter finden Sie unter [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkInterSitePolicy) in der Lync Server-Verwaltungsshell-Dokumentation. Zum Abrufen einer Liste der Bandbreitenrichtlinienprofile, die auf die Netzwerkstandortverknüpfung angewendet werden können, verwenden Sie das Cmdlet **Get-CsNetworkBandwidthPolicyProfile**. Ausführliche Informationen finden Sie unter [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) in der Lync Server-Verwaltungsshell-Dokumentation.

## So ändern Sie eine Netzwerkstandortverknüpfung

1.  Melden Sie sich auf dem Computer, auf dem die Lync Server-Verwaltungsshell installiert ist, als Mitglied der Gruppe "RTCUniversalServerAdmins" oder mit den erforderlichen Benutzerrechten an, wie beschrieben unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Verwenden Sie das Cmdlet **Set-CsNetworkInterSitePolicy**, um die Eigenschaften einer Netzwerkstandortverknüpfung zu ändern. Sie können entweder einen oder beide verbundenen Standorte ändern, und Sie können das der Verknüpfung zugeordnete Bandbreitenrichtlinienprofil bearbeiten. Das folgende Beispiel zeigt, wie das Bandbreitenrichtlinienprofil der Standortverknüpfung "Reno\_Portland" geändert wird:
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

Eine ausführliche Beschreibung der Parameter finden Sie unter [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkInterSitePolicy) in der Lync Server-Verwaltungsshell-Dokumentation.

## So löschen Sie eine Netzwerkstandortverknüpfung

1.  Melden Sie sich auf dem Computer, auf dem die Lync Server-Verwaltungsshell installiert ist, als Mitglied der Gruppe "RTCUniversalServerAdmins" oder mit den erforderlichen Benutzerrechten an, wie beschrieben unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Verwenden Sie das Cmdlet **Remove-CsNetworkInterSitePolicy**, um eine Netzwerkstandortverknüpfung zu löschen. Im folgenden Beispiel wird die Netzwerkstandortverknüpfung "Reno\_Portland" gelöscht:
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

Eine ausführliche Beschreibung der Parameter finden Sie unter [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkInterSitePolicy) in der Lync Server-Verwaltungsshell-Dokumentation.

## Siehe auch

#### Konzepte

[Cmdlets für die Anrufsteuerung](https://docs.microsoft.com/en-us/powershell/module/skype/)  

#### Weitere Ressourcen

[New-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

