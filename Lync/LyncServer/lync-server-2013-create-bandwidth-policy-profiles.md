---
title: Erstellen von Bandbreitenrichtlinienprofilen in Lync Server 2013
TOCTitle: Erstellen von Bandbreitenrichtlinienprofilen in Lync Server 2013
ms:assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412785(v=OCS.15)
ms:contentKeyID: 49295008
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen von Bandbreitenrichtlinienprofilen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

*Bandbreitenrichtlinien* definieren Einschränkungen zur Bandbreitenauslastung für in Echtzeit übertragene Audio- und Videodaten. Bandbreitenrichtlinien werden auf *Bandbreitenrichtlinienprofile* angewendet, die zur Anrufsteuerung auf mehrere Netzwerkstandorte angewendet werden können.

Anleitungen zu den Bandbreiteneinschränkungen, die Sie in Ihrer Bereitstellung der Anrufsteuerung festlegen sollten, finden Sie unter [Definieren der Anforderungen Ihrer Organisation für die Anrufsteuerung in Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md) in der Planungsdokumentation.

Ausführliche Informationen zum Arbeiten mit Bandbreitenrichtlinien und Richtlinienprofilen finden Sie in der Lync Server-Verwaltungsshell-Dokumentation für die folgenden Cmdlets:

  - [New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)

  - [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

  - [Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)

  - [Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)

Die im folgenden Verfahren erstellten Beispielrichtlinien legen Einschränkungen für den Audiodatenverkehr insgesamt, einzelne Audiositzungen, den Videodatenverkehr insgesamt und einzelne Videositzungen fest. Das Bandbreitenrichtlinienprofil "5Mb\_Link" legt beispielsweise folgende Einschränkungen fest:

  - Grenzwert für Audio: 2.000 KBit/s

  - Grenzwert für Audiositzung: 200 KBit/s

  - Grenzwert für Video: 1.400 KBit/s

  - Grenzwert für Videositzung: 700 KBit/s


> [!NOTE]
> Der Mindestgrenzwert für Audiositzungen ist 40&nbsp;KBit/s. Der Mindestgrenzwert für Videositzungen ist 100&nbsp;KBit/s.



## So erstellen Sie Bandbreitenrichtlinienprofile mithilfe der Verwaltungsshell

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie für jedes Bandbreitenrichtlinienprofil, das Sie erstellen möchten, das Cmdlet "New-CsNetworkBandwidthPolicyProfile" aus. Führen Sie beispielsweise den folgenden Befehl aus:
    
        New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400  -VideoBWSessionLimit 700

       &nbsp;
    
        New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700

       &nbsp;
    
        New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700

       &nbsp;
    
        New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700

## So erstellen Sie Bandbreitenrichtlinienprofile mithilfe der Lync Server-Systemsteuerung

1.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3.  Klicken Sie auf die Navigationsschaltfläche **Richtlinienprofil**.

4.  Klicken Sie auf **Neu**.

5.  Klicken Sie auf der Seite **Neues Richtlinienprofil** auf **Name**, und geben Sie einen Namen für das Bandbreitenrichtlinienprofil ein.

6.  Klicken Sie auf **Audiolimit**, und geben Sie die Höchstzahl an KBit/s ein, die für alle Audiositzungen insgesamt zulässig sein soll.

7.  Klicken Sie auf **Grenzwert für Audiositzung**, und geben Sie die Höchstzahl an KBit/s ein, die für jede einzelne Audiositzung zulässig sein soll.

8.  Klicken Sie auf **Videolimit**, und geben Sie die Höchstzahl an KBit/s ein, die für alle Videositzungen insgesamt zulässig sein soll.

9.  Klicken Sie auf **Grenzwert für Videositzung**, und geben Sie die Höchstzahl an KBit/s ein, die für jede einzelne Videositzung zulässig sein soll.

10. Klicken Sie optional auf **Beschreibung**, und geben Sie zusätzliche Informationen zur Beschreibung dieses Bandbreitenrichtlinienprofils ein.

11. Klicken Sie auf **Commit**.

12. Wiederholen Sie die Schritte 4 bis 11 mit Einstellungen für andere Bandbreitenrichtlinienprofile, um die Erstellung von Bandbreitenrichtlinienprofilen für Ihre Topologie abzuschließen.

