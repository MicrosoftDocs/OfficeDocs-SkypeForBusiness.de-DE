---
title: 'Lync Server 2013: Verwenden von Cmdlets zum Rückgängigmachen der Gesamtstrukturvorbereitung'
TOCTitle: Verwenden von Cmdlets zum Rückgängigmachen der Gesamtstrukturvorbereitung
ms:assetid: f48c7eb3-ccb0-48e6-ac79-ab7c7062b9d3
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg413024(v=OCS.15)
ms:contentKeyID: 49295907
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwenden von Cmdlets zum Rückgängigmachen der Gesamtstrukturvorbereitung für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-06-19_

Verwenden Sie das Cmdlet **Disable-CsAdForest**, um die Gesamtstrukturvorbereitung rückgängig zu machen.

> [!CAUTION]  
> Wenn Sie das Cmdlet <strong>Disable-CsAdForest</strong> in einer Umgebung ausführen, in der auch eine frühere Version von Lync Server bereitgestellt ist, werden die globalen Einstellungen für diese Version ebenfalls gelöscht.


## So machen Sie mithilfe von Cmdlets die Gesamtstrukturvorbereitung rückgängig

1.  Melden Sie sich bei einem Domänencomputer als Mitglied der Gruppe "Domänen-Admins" in der Stammdomäne der Gesamtstruktur an.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie folgenden Befehl aus:
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    Beispiel:
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    Der Parameter "Force" gibt an, ob die Ausführung des Tasks erzwungen wird. Wenn dieser Parameter nicht vorhanden ist, wird der Befehl nicht ausgeführt, auch wenn eine Domäne in der Gesamtstruktur noch für Lync Server 2013 vorbereitet ist. Wurde der Parameter "Force" angegeben, wird der Vorgang unabhängig vom Status der anderen Domänen in der Gesamtstruktur fortgesetzt.
    
    Wenn Sie den Parameter "GroupDomain" nicht angeben, wird standardmäßig die lokale Domäne verwendet.

## Siehe auch

#### Aufgaben

[Ausführen der Gesamtstrukturvorbereitung für Lync Server 2013](lync-server-2013-running-forest-preparation.md)  

#### Weitere Ressourcen

[Vorbereiten der Gesamtstruktur für Lync Server 2013](lync-server-2013-preparing-the-forest.md)

