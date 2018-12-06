---
title: Erstellen von Netzwerkregionenverbindungen in Lync Server 2013
TOCTitle: Erstellen von Netzwerkregionenverbindungen in Lync Server 2013
ms:assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg413047(v=OCS.15)
ms:contentKeyID: 49295949
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen von Netzwerkregionenverbindungen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Regionen in einem Netzwerk sind über physische WAN-Verbindungen miteinander verbunden. Eine *Netzwerkregionenverbindung* erstellt eine Verbindung zwischen zwei Regionen, die für die Anrufsteuerung (Call Admission Control, CAC) konfiguriert sind, und legt die Bandbreiteneinschränkungen für den Audio- und Videodatenverkehr zwischen diesen Regionen fest.

Ausführliche Informationen zum Arbeiten mit Netzwerkregionenverbindungen finden Sie in der Lync Server-Verwaltungsshell-Dokumentation für die folgenden Cmdlets:

  - [New-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkRegionLink)

  - [Get-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkRegionLink)

  - [Set-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkRegionLink)

  - [Remove-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkRegionLink)

Die Beispieltopologie weist eine Verbindung zwischen den Regionen "North America" und "APAC" sowie zwischen den Regionen "EMEA" und "APAC" auf. Jede dieser Regionenverbindungen wird durch die WAN-Bandbreite beschränkt, wie beschrieben in der Tabelle "Bandbreiteninformationen zur Regionenverbindungen" im Abschnitt [Beispiel: Zusammenstellen der Anforderungen Ihrer Organisation für die Anrufsteuerung in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in der Planungsdokumentation.

## So erstellen Sie Netzwerkregionenverbindungen mithilfe der Lync Server-Verwaltungsshell

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet "New-CsNetworkRegionLink" aus, um die Regionenverbindungen zu erstellen und geeignete Bandbreitenrichtlinienprofile anzuwenden. Führen Sie beispielsweise den folgenden Befehl aus:
    
        New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link

       &nbsp;
    
        New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link

## So erstellen Sie Netzwerkregionenverbindungen mithilfe der Lync Server-Systemsteuerung

1.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3.  Klicken Sie auf die Navigationsschaltfläche **Regionenverbindung**.

4.  Klicken Sie auf **Neu**.

5.  Klicken Sie auf der Seite **Neue Netzwerkregionenverbindung** auf **Name**, und geben Sie einen Namen für die Netzwerkregionenverbindung ein.

6.  Klicken Sie auf **Netzwerkregion 1** und anschließend auf die Netzwerkregion in der Liste, für die eine Verbindung zu Netzwerkregion 2 erstellt werden soll.

7.  Klicken Sie auf **Netzwerkregion 2** und anschließend auf eine Netzwerkregion in der Liste, für die eine Verbindung zu Netzwerkregion 1 erstellt werden soll.

8.  Klicken Sie optional auf **Bandbreitenrichtlinie**, und wählen Sie das Bandbreitenrichtlinienprofil aus, das Sie auf die Netzwerkregionenverbindung anwenden möchten.
    

    > [!NOTE]
    > Wenden Sie nur dann eine Bandbreitenrichtlinie an, wenn die Netzwerkregionenverbindung eine Bandbreiteneinschränkung aufweist und Sie die Anrufsteuerung verwenden möchten, um den Mediendatenverkehr in dieser Verbindung zu steuern.



9.  Klicken Sie auf **Commit**.

10. Zum Abschließen der Erstellung von Netzwerkregionenverbindungen für Ihre Topologie wiederholen Sie die Schritte 4 bis 9 mit Einstellungen für weitere Regionen.

