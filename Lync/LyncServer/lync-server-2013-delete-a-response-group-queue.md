---
title: Löschen einer Warteschleife für Reaktionsgruppen
TOCTitle: Löschen einer Warteschleife für Reaktionsgruppen
ms:assetid: 67c7a489-8c5f-4c6b-9387-9d4c11d43695
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg521008(v=OCS.15)
ms:contentKeyID: 49294260
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Löschen einer Warteschleife für Reaktionsgruppen

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Gehen Sie nach einer der folgenden Methoden vor, um eine Warteschleife zu löschen.

## So löschen Sie eine Warteschleife mithilfe der Lync Server-Systemsteuerung

1.  Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Reaktionsgruppen** und dann auf **Warteschleife**.

4.  Geben Sie im Suchfeld Teile oder den vollständigen Namen der Warteschleife ein, die Sie löschen möchten.

5.  Klicken Sie in der Warteschleifenliste auf die gewünschte Warteschleife, klicken Sie auf **Bearbeiten** und dann auf **Löschen**.

6.  Klicken Sie auf **OK**.

## So löschen Sie eine Warteschlange mithilfe von Cmdlets

1.  Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie an der Befehlszeile den folgenden Befehl aus:
    
        Get-CsRgsQueue -Identity <Application Server service> -Name "<name of queue>" | Remove-CsRgsQueue
    
    Beispiel:
    
        Get-CsRgsQueue -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsQueue

