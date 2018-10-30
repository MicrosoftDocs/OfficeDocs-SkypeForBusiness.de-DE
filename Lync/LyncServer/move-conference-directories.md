---
title: Verschieben von Konferenzverzeichnissen
TOCTitle: Verschieben von Konferenzverzeichnissen
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204994(v=OCS.15)
ms:contentKeyID: 49294374
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verschieben von Konferenzverzeichnissen

 

_**Letztes Änderungsdatum des Themas:** 2012-10-04_

Vor der Außerbetriebnahme eines Pools müssen Sie für jedes Konferenzverzeichnis im Office Communications Server 2007 R2-Pool das folgende Verfahren durchführen.

## So verschieben Sie ein Konferenzverzeichnis in Lync Server 2013

1.  Öffnen Sie die Lync Server-Verwaltungsshell.

2.  Führen Sie die folgenden Befehle aus, um die Identität der Konferenzverzeichnisse in Ihrer Organisation zu beziehen:
    
        Get-CsConferenceDirectory
    
    Dieses Cmdlet gibt alle Konferenzverzeichnisse in der Organisation zurück. Deshalb empfiehlt es sich u. U., die Ergebnisse auf den Pool zu beschränken, den Sie außer Betrieb nehmen möchten. Beispiel: Sie möchten einen Pool mit dem vollqualifizierten Domänennamen (FQDN) **pool01.contoso.net** außer Betrieb nehmen:
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    Dieses Cmdlet gibt alle Konferenzverzeichnisse zurück, deren Dienst-ID den FQDN **pool01.contoso.net** enthält.

3.  Führen Sie zum Verschieben von Konferenzverzeichnissen folgenden Befehl für jedes Konferenzverzeichnis in dem Pool aus:
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    Beispiel:
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net


> [!NOTE]
> Möglicherweise tritt ein Fehler auf (siehe unten), der dadurch verursacht wird, dass die Lync Server-Verwaltungsshell einen aktualisierten Berechtigungssatz von Active Directory benötigt. Sie können den Fehler beheben, indem Sie das aktuelle Fenster schließen, eine neue Lync Server-Verwaltungsshell öffnen und den Befehl erneut ausführen.



![Move-CsConferenceDirectory-Fehlerausgabe](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Move-CsConferenceDirectory-Fehlerausgabe")

