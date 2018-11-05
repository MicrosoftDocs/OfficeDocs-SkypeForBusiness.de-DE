---
title: Aktivieren der Anrufsteuerung in Lync Server 2013
TOCTitle: Aktivieren der Anrufsteuerung in Lync Server 2013
ms:assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398642(v=OCS.15)
ms:contentKeyID: 49294560
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren der Anrufsteuerung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Nachdem Sie die Ihre Netzwerkeinstellungen für die Bereitstellung der Anrufsteuerung konfiguriert haben, müssen Sie die Anrufsteuerung aktivieren, um die Bandbreitenrichtlinien anzuwenden.

Ausführliche Informationen finden Sie in der Lync Server-Verwaltungsshell-Dokumentation zu den folgenden Cmdlets:

  - [Get-CsNetworkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkConfiguration)

  - [Set-CsNetworkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkConfiguration)

  - [Remove-CsNetworkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkConfiguration)

## So aktivieren Sie die Anrufsteuerung mithilfe der Verwaltungsshell

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet "Set-CsNetworkConfiguration" aus, um die Anrufsteuerung in Ihrem Netzwerk zu aktivieren. Führen Sie beispielsweise den folgenden Befehl aus:
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
    
    Wenn Sie die Anrufsteuerung in Ihrem Netzwerk deaktivieren möchten, führen Sie folgenden Befehl aus:
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0

## So aktivieren Sie die Anrufsteuerung mithilfe der Lync Server-Systemsteuerung

1.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3.  Klicken Sie auf die Navigationsschaltfläche **Global**.

4.  Klicken Sie in der Liste auf **Global**, und wählen Sie anschließend im Menü **Bearbeiten** die Option **Details anzeigen**.

5.  Aktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **Anrufsteuerung aktivieren**.
    

    > [!NOTE]
    > Wenn Sie die Anrufsteuerung innerhalb Ihrer Bereitstellung deaktivieren möchten, deaktivieren Sie dieses Kontrollkästchen.



6.  Klicken Sie auf **Commit**.

