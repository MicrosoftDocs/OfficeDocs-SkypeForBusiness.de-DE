---
title: 'Lync Server 2013: Konfigurieren eines vorhandenen zentralen Verwaltungsservers'
TOCTitle: Konfigurieren eines vorhandenen zentralen Verwaltungsservers
ms:assetid: d715b24a-1256-4a7c-a5ef-1cee41d6b733
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205315(v=OCS.15)
ms:contentKeyID: 49295554
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren eines vorhandenen zentralen Verwaltungsservers in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Wenn Sie einen zentraler Verwaltungsserver aus einer vorhandenen Lync Server 2013-Bereitstellung wiederverwenden, müssen Sie das im Folgenden beschriebene Verfahren ausführen, um sicherzustellen, dass die Lync Server-Systemsteuerung und Windows PowerShell ordnungsgemäß ausgeführt werden.

## So konfigurieren Sie einen vorhanden zentraler Verwaltungsserver

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Verwenden Sie das **Update-CsAdminRole**-Cmdlet, um die auf dem zentraler Verwaltungsserver gespeicherten rollenbasierten Zugriffssteuerungsrollen zu aktualisieren.
    

    > [!NOTE]
    > Es wird keine Ausgabe erwartet, außer es tritt ein Fehler auf.


