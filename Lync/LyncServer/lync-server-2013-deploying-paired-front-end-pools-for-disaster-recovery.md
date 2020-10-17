---
title: 'Lync Server 2013: Bereitstellen gekoppelter Front-End-Pools für die Notfallwiederherstellung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying paired Front End pools for disaster recovery
ms:assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204773(v=OCS.15)
ms:contentKeyID: 48183727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 309c8f7ac7da4e40f2b16e5d13015330b2d9b611
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514525"
---
# <a name="deploying-paired-front-end-pools-for-disaster-recovery-in-lync-server-2013"></a>Bereitstellen gekoppelter Front-End-Pools für die Notfallwiederherstellung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

Sie können die Notfall Wiederherstellungs Topologie mit gepaarten Front-End-Pools problemlos mithilfe des Topologie-Generators bereitstellen.

<div>

## <a name="to-deploy-a-pair-of-front-end-pools"></a>So stellen Sie ein Paar von Front-End-Pools bereit

1.  Wenn die Pools neu und noch nicht definiert sind, verwenden Sie den Topologie-Generator, um die Pools zu erstellen.

2.  Klicken Sie im Topologie-Generator mit der rechten Maustaste auf einen der beiden Pools, und klicken Sie dann auf **Eigenschaften bearbeiten**.

3.  Klicken Sie im linken Bereich auf **Flexibilität**, und wählen Sie dann im rechten Bereich **Zugeordneter Sicherungspool**aus.

4.  Wählen Sie im Feld unter **Zugeordneter Sicherungspool** den Pool aus, mit dem dieser Pool ein Paar bilden soll. Zur Auswahl stehen nur vorhandene Pools, die noch nicht mit einem anderen Pool ein Paar bilden.
    
    ![36080581-DB76-497d-bf9e-f02b39574d0e](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "36080581-DB76-497d-bf9e-f02b39574d0e")  

5.  Wählen Sie **Automatisches Failover und Failback für Sprachdienste** aus, und klicken Sie dann auf **OK**.
    
    Wenn Sie die Details zu diesem Pool anzeigen, erscheint der neu zugeordnete Pool jetzt im rechten Bereich unter **Flexibilität**.

6.  Verwenden Sie den Topologie-Generator, um die Topologie zu veröffentlichen.

7.  Wenn die beiden Pools noch nicht bereitgestellt wurden, führen Sie die Bereitstellung jetzt durch, um die Konfiguration abzuschließen. Sie können die letzten beiden Schritte in diesem Verfahren überspringen.
    
    Wenn die Pools jedoch bereits bereitgestellt waren, bevor Sie die Paarbeziehung definiert haben, müssen Sie die beiden folgenden abschließenden Schritte ausführen.

8.  Führen Sie auf jedem Front-End-Server in beiden Pools Folgendes aus:
    ```console
    <system drive>\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe 
    ```
    Hierdurch werden die anderen Dienste konfiguriert, die erforderlich sind, damit die Sicherung des Poolpaars korrekt funktioniert.

9.  Führen Sie an einer lync Server-Verwaltungsshell Eingabeaufforderung Folgendes aus:
    ```powershell
    Start-CsWindowsService -Name LYNCBACKUP
    ```
10. Verwenden Sie die folgenden Cmdlets, um zu erzwingen, dass die Benutzer- und Konferenzdaten beider Pools miteinander synchronisiert werden:
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
       ```
    
    Das Synchronisieren der Daten kann einige Zeit in Anspruch nehmen. Sie können die folgenden Cmdlets verwenden, um den Status zu prüfen. Stellen Sie sicher, dass sich der Status in beide Richtungen im stationären Zustand befindet.
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
       ```

<div class="">


> [!NOTE]  
> Die Option <STRONG>Automatisches Failover und Failback für VoIP</STRONG> und die zugehörigen Zeitintervalle im Topologie-Generator gelten nur für die Features der VoIP-Ausfallsicherheit, die in lync Server 2010 eingeführt wurden. Die Auswahl dieser Option bedeutet nicht, dass das in diesem Dokument beschriebene Pool Failover automatisch erfolgt. Für das Pool-Failover und das Failback muss ein Administrator immer manuell die Failover-und Failback-Cmdlets aufrufen.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

