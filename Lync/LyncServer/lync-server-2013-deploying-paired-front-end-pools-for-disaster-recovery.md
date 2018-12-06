---
title: 'Lync Server 2013: Bereitstellen von Front-End-Poolpaaren für die Notfallwiederherstellung'
TOCTitle: Bereitstellen von Front-End-Poolpaaren für die Notfallwiederherstellung
ms:assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204773(v=OCS.15)
ms:contentKeyID: 49293550
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellen von Front-End-Poolpaaren für die Notfallwiederherstellung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Sie können die Notfallwiederherstellungstopologie eines Paars von Front-End-Pools mit dem Topologie-Generator auf einfache Weise bereitstellen.

## So stellen Sie ein Paar von Front-End-Pools bereit

1.  Verwenden Sie Topologie-Generator zum Erstellen der Pools, wenn die Pools neu und noch nicht definiert sind.

2.  Klicken Sie im Topologie-Generator mit der rechten Maustaste auf einen der beiden Pools, und klicken Sie dann auf **Eigenschaften bearbeiten** .

3.  Klicken Sie im linken Bereich auf **Flexibilität** , und wählen Sie dann im rechten Bereich **Zugeordneter Sicherungspool** aus.

4.  Wählen Sie im Feld unter **Zugeordneter Sicherungspool** den Pool aus, mit dem dieser Pool ein Paar bilden soll. Zur Auswahl stehen nur vorhandene Pools, die noch nicht mit einem anderen Pool ein Paar bilden.
    
    ![Ausfallsicherheit (Dialogfeld)](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "Ausfallsicherheit (Dialogfeld)")  

5.  Wählen Sie **Automatisches Failover und Failback für Sprachdienste** aus, und klicken Sie dann auf **OK** .
    
    Wenn Sie die Details zu diesem Pool anzeigen, erscheint der neu zugeordnete Pool jetzt im rechten Bereich unter **Flexibilität** .

6.  Verwenden Sie den Topologie-Generator, um die Topologie zu veröffentlichen.

7.  Wenn die beiden Pools noch nicht bereitgestellt wurden, führen Sie die Bereitstellung jetzt durch, um die Konfiguration abzuschließen. Sie können die letzten beiden Schritte in diesem Verfahren überspringen.
    
    Wenn die Pools jedoch bereits bereitgestellt waren, bevor Sie die Paarbeziehung definiert haben, müssen Sie die beiden folgenden abschließenden Schritte ausführen.

8.  Führen Sie auf jedem Front-End-Server in beiden Pools Folgendes aus:
    
        <system drive>\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe 
    
    Hierdurch werden die anderen Dienste konfiguriert, die erforderlich sind, damit die Sicherung des Poolpaars korrekt funktioniert.

9.  Führen Sie an einer Lync Server-Verwaltungsshell-Eingabeaufforderung folgenden Befehl aus:
    
        Start-CsWindowsService -Name LYNCBACKUP

10. Verwenden Sie die folgenden Cmdlets, um zu erzwingen, dass die Benutzer- und Konferenzdaten beider Pools miteinander synchronisiert werden:
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>

       &nbsp;
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    
    Das Synchronisieren der Daten kann einige Zeit in Anspruch nehmen. Sie können die folgenden Cmdlets verwenden, um den Status zu prüfen. Stellen Sie sicher, dass der Status für beide Richtungen stabil ist.
    
        Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>

       &nbsp;
    
        Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>


> [!NOTE]
> Die Option <STRONG>Automatisches Failover und Failback für Sprachdienste</STRONG> und die zugehörigen Zeitintervalle in Topologie-Generator gelten nur für die Sprachflexibilitätsfeatures, die in Lync Server 2010 eingeführt wurden. Die Auswahl dieser Option bewirkt nicht, dass das in diesem Dokument erörterte Poolfailover automatisch erfolgt. Um ein Poolfailover oder -failback durchzuführen, muss ein Administrator das Failover- bzw. Failback-Cmdlets immer manuell aufrufen.


