---
title: 'Lync Server 2013: Anhang A: Verwenden von Cmdlets zur Bereitstellung einer Survivable Branch Appliance'
TOCTitle: 'Anhang A: Verwenden von Cmdlets zur Bereitstellung einer Survivable Branch Appliance'
ms:assetid: 796a26cf-7ec9-453b-8757-6153a6dd86c5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398598(v=OCS.15)
ms:contentKeyID: 49294481
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anhang A: Verwenden von Cmdlets zur Bereitstellung einer Survivable Branch Appliance in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-07_

In diesem Thema wird beschrieben, wie Sie eine Survivable Branch-Anwendung mithilfe von Lync Server-Verwaltungsshell bereitstellen. Führen Sie dieses Verfahren am zentralen Standort aus.

## So stellen Sie eine Survivable Branch-Anwendung remote bereit

1.  Führen Sie die Schritte in [Hinzufügen von Zweigstellenstandorten zur Topologie in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md) aus, um einen neuen Zweigstellenstandort hinzuzufügen.

2.  Fügen Sie den Zweigstellenstandort zur Domäne hinzu.

3.  Fügen Sie die Gruppe "RTCUniversalSBATechnicians" zur lokalen Administratorgruppe hinzu.

4.  Starten Sie den Server neu, und melden Sie sich als Mitglied der Gruppe "RTCUniversalSBATechnicians" an.

5.  Geben Sie in der Lync Server-Verwaltungsshell die folgenden Befehle ein, und ersetzen Sie die Platzhalter dabei durch die richtigen Informationen für Ihre Organisation:
    
        Export-CsConfiguration -FileName C:\CSConfig.zip
        Import-CsConfiguration -LocalStore -FileName C:\CSConfig.zip -Verbose
        Enable-CSReplica -Verbose
        Enable-CsComputer -Verbose
        Request-CsCertificate -New -Type default -CA <YourCA> -Verbose
        Set-CsCertificate -Type Default -Thumbprint <YourCertThumbprint>
        Start-cswindowsservice -verbose

