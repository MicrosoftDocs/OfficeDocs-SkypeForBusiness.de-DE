---
title: 'Lync Server 2013: Bereitstellen von Front-End-Poolpaaren für die Notfallwiederherstellung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying paired Front End pools for disaster recovery
ms:assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204773(v=OCS.15)
ms:contentKeyID: 48183727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78c0d6b266f6401c9ba48bfe38ee54b7b4281717
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832528"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-paired-front-end-pools-for-disaster-recovery-in-lync-server-2013"></a>Bereitstellen von Front-End-Poolpaaren für die Notfallwiederherstellung in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Sie können die Disaster Recovery-Topologie von gekoppelten Front-End-Pools auf einfache Weise mithilfe von Topology Builder bereitstellen.

<div>

## <a name="to-deploy-a-pair-of-front-end-pools"></a>So stellen Sie ein Front-End-Poolpaar bereit

1.  Wenn die Pools neu sind und noch nicht definiert sind, verwenden Sie den Topologie-Generator zum Erstellen der Pools.

2.  Klicken Sie im Topologie-Generator mit der rechten Maustaste auf einen der beiden Pools, und klicken Sie dann auf **Eigenschaften bearbeiten**.

3.  Klicken Sie im linken Bereich auf **Flexibilität**, und wählen Sie dann im rechten Bereich die Option **Zugeordneter Sicherungspool** aus.

4.  Wählen Sie im Feld unter **Zugeordneter Sicherungspool** den Pool aus, mit dem dieser Pool ein Paar bilden soll. Zur Auswahl stehen nur vorhandene Pools, die noch nicht mit einem anderen Pool ein Paar bilden.
    
    ![36080581-DB76-497d-bf9e-f02b39574d0e] (images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "36080581-DB76-497d-bf9e-f02b39574d0e")  

5.  Wählen Sie **Automatisches Failover und Failback für Sprachdienste** aus, und klicken Sie dann auf **OK**.
    
    Wenn Sie die Details zu diesem Pool anzeigen, erscheint der zugeordnete Pool jetzt im rechten Bereich unter **Flexibilität**. 

6.  Verwenden Sie den Topologie-Generator zum Veröffentlichen der Topologie.

7.  Wenn die beiden Pools noch nicht bereitgestellt wurden, führen Sie die Bereitstellung jetzt durch, um die Konfiguration abzuschließen. Die letzten beiden Schritte in diesem Verfahren können Sie überspringen.
    
    Wenn die Pools jedoch bereits bereitgestellt waren, bevor Sie die Paarbeziehung definiert haben, müssen Sie die beiden folgenden abschließenden Schritte ausführen.

8.  Führen Sie auf jedem Front-End-Server in beiden Pools Folgendes aus:
    
        <system drive>\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe 
    
    Hierdurch werden die anderen Dienste konfiguriert, die erforderlich sind, damit die Sicherung des Poolpaars korrekt funktioniert.

9.  Führen Sie an einer Eingabeaufforderung der lync Server-Verwaltungsshell die folgenden Aktionen aus:
    
        Start-CsWindowsService -Name LYNCBACKUP

10. Verwenden Sie die folgenden Cmdlets, um zu erzwingen, dass die Benutzer- und Konferenzdaten beider Pools miteinander synchronisiert werden:
    
       ```
        Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
       ```
    
       ```
        Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
       ```
    
    Das Synchronisieren der Daten kann einige Zeit in Anspruch nehmen. Sie können die folgenden Cmdlets verwenden, um den Status zu überprüfen. Stellen Sie sicher, dass der Status für beide Richtungen stabil ist.
    
       ```
        Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
       ```
    
       ```
        Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
       ```

<div class="">


> [!NOTE]  
> Die Option <STRONG>Automatisches Failover und Failback für VoIP</STRONG> und die zugehörigen Zeitintervalle im Topologie-Generator gelten nur für die Features der VoIP-Resilienz, die in lync Server 2010 eingeführt wurden. Wenn Sie diese Option auswählen, bedeutet dies nicht, dass das in diesem Dokument beschriebene Pool-Failover automatisch erfolgt. Für Pool-Failover und Failback muss ein Administrator immer manuell die Failover-und Failback-Cmdlets aufrufen.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

