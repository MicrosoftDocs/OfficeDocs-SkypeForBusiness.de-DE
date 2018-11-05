---
title: 'Lync Server 2013: Ausführen eines Failbacks für einen Pool'
TOCTitle: Ausführen eines Failbacks für einen Pool
ms:assetid: 6232b644-ef57-4c9c-abec-14ff8ffc9fe7
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204945(v=OCS.15)
ms:contentKeyID: 49294192
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ausführen eines Failbacks für einen Pool in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Nachdem der ausgefallene Pool (d. h. Pool1 im vorliegenden Beispiel) wieder online ist, müssen Sie die folgenden Schritte ausführen, um Ihre Bereitstellung wieder in den normalen Betriebszustand zurückzuversetzen.

Beachten Sie, dass der Failback-Prozess einige Zeit in Anspruch nehmen kann. So würde zum Beispiel ein Pool mit 20.000 Benutzern bis zu 60 Minuten benötigen.

1.  Führen Sie für die Benutzer, die ursprünglich in Pool1 untergebracht waren und auf Pool2 verlegt wurden, ein Failback mit dem folgenden Cmdlet durch:
    
        Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

Weitere Schritte sind nicht erforderlich. Wenn Sie für den zentraler Verwaltungsserver das Failback ausgeführt haben, können Sie ihn in Pool2 belassen.

