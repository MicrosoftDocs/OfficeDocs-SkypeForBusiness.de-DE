---
title: Verschieben von Lync Server 2010-Konferenzverzeichnissen zu Lync Server 2013
TOCTitle: Verschieben von Konferenzverzeichnissen
ms:assetid: 659867e0-ce91-4a95-9787-b1c1566460a8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn727126(v=OCS.15)
ms:contentKeyID: 62388540
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verschieben von Konferenzverzeichnissen

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Vor der Außerbetriebnahme eines Pools müssen Sie für jedes Konferenzverzeichnis im Lync Server 2010-Pool das folgende Verfahren durchführen.

## So verschieben Sie ein Konferenzverzeichnis nach Lync Server 2013

1.  Öffnen Sie die Lync Server-Verwaltungsshell.

2.  Führen Sie die folgenden Befehle aus, um die Identität der Konferenzverzeichnisse in Ihrer Organisation zu beziehen:
    
        Get-CsConferenceDirectory
    
    Der vorige Befehl gibt alle Konferenzverzeichnisse in Ihrer Organisation zurück. Deswegen empfiehlt es sich, die Ergebnisse auf den Pool zu beschränken, der außer Betrieb genommen werden soll. Wenn Sie z. B. den Pool mit dem vollqualifizierten Domänennamen (FQDN) "pool01.contoso.net" außer Betrieb nehmen möchten, können Sie die Ergebnisse mit dem folgenden Befehl auf die Konferenzverzeichnisse aus diesem Pool beschränken:
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    Dieser Befehl gibt nur die Konferenzverzeichnisse zurück, bei denen die ServiceID-Eigenschaft den FQDN "pool01.contoso.net" enthält.

3.  Führen Sie zum Verschieben von Konferenzverzeichnissen folgenden Befehl für jedes Konferenzverzeichnis in dem Pool aus:
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    Nutzen Sie z. B. den folgenden Befehl, um Verzeichnis 3 zu verschieben, und geben Sie einen Lync Server 2013-Pool als Zielpool an:
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
    
    Wenn Sie alle Konferenzverzeichnisse in einem Pool verschieben möchten, dann verwenden Sie einen Befehl, der so ähnlich aufgebaut ist wie der folgende:
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"

Eine detaillierte, schrittweise Anleitung zur Außerbetriebnahme von Lync 2010-Pools finden Sie in folgendem Dokument "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles" (steht unter [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227) zum Download zur Verfügung).

Beim Verschieben von Konferenzverzeichnissen könnten Sie die folgende Fehlermeldung erhalten:

    WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
    WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
    Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
    This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.

Dieser Fehler tritt in der Regel auf, wenn die Active Directory-Berechtigungen für die Lync Server-Verwaltungsshell aktualisiert werden müssen, damit ein bestimmter Vorgang abgeschlossen werden kann. Schließen Sie die aktuelle Instanz der Management Shell, öffnen Sie eine neue Instanz und geben Sie den Befehl zum Verschieben der Konferenzereignisse erneut ein.

