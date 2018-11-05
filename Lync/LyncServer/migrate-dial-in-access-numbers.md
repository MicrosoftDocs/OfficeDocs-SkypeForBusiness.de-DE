---
title: Migrieren von Einwahlnummern für Einwahlkonferenzen
TOCTitle: Migrieren von Einwahlnummern für Einwahlkonferenzen
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49890972
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrieren von Einwahlnummern für Einwahlkonferenzen

 

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Für die Migration von Einwahlnummern von Lync Server 2010 zu Lync Server 2013 müssen Sie das **Move-CsApplicationEndpoint**-Cmdlet ausführen, um die Kontaktobjekte zu migrieren. Während der Koexistenz von Lync Server 2010 und Lync Server 2013 verhalten sich wie in diesem Abschnitt beschrieben in Lync Server 2013 erstellte Einwahlnummern ähnlich wie die in Lync Server 2010 erstellten Einwahlnummern.

Einwahlnummern, die Sie in Lync Server 2010 erstellt, aber nach Lync Server 2013 verschoben haben, oder die Sie in Lync Server 2013 vor, während oder nach der Migration erstellt haben, weisen folgende Merkmale auf:

  - Sie werden nicht in Office Communications Server 2007 R2-Besprechungseinladungen und auf der Einwahlnummernseite angezeigt.

  - Sie werden in Lync Server 2010-Besprechungseinladungen und auf der Einwahlnummernseite angezeigt.

  - Sie werden in Lync Server 2013-Besprechungseinladungen und auf der Einwahlnummernseite angezeigt.

  - Sie können nicht im Verwaltungstool von Office Communications Server 2007 R2 angezeigt oder geändert werden.

  - Sie können in der Lync Server 2010-Systemsteuerung und in der Lync Server 2010-Verwaltungsshell angezeigt und geändert werden.

  - Sie können in der Lync Server 2013-Systemsteuerung und in der Lync Server 2013-Verwaltungsshell angezeigt und geändert werden.

  - Sie können innerhalb des Bereichs durch Verwendung des Set-CsDialinConferencingAccessNumber -Cmdlets mit dem Priority -Parameter neu sequenziert werden.

Sie müssen die Migration von Einwahlnummern abschließen, die auf einen Lync Server 2010-Pool verweisen, bevor Sie den Lync Server 2010-Pool außer Betrieb nehmen. Wenn Sie die Migration von Einwahlnummern nicht wie im folgenden Verfahren beschrieben abschließen, schlagen eingehende Anrufe an die Einwahlnummern fehl.


> [!IMPORTANT]
> Sie müssen dieses Verfahren vor der Außerbetriebnahme des Lync Server 2010-Pools ausführen.




> [!NOTE]
> Es wird empfohlen, das Verschieben von Einwahlnummern zu einem Zeitpunkt mit möglichst geringer Netzwerkauslastung vorzunehmen, für den Fall, dass es zu einem kurzen Dienstausfall kommt.



**So identifizieren und verschieben Sie Einwahlnummern**

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Zum Verschieben aller Einwahlnummern in einen auf Lync Server 2013 gehosteten Pool, führen Sie an der Befehlszeile folgenden Befehl aus:
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  Öffnen Sie die Lync Server-Systemsteuerung.

4.  Klicken Sie in der linken Navigationsleiste auf **Konferenz**.

5.  Klicken Sie auf die Registerkarte **Einwahlnummer**.

6.  Überprüfen Sie, dass keine Einwahlnummern für den Lync Server 2010-Pool zurückbleiben, aus dem Sie migrieren.
    

    > [!NOTE]
    > Wenn alle Einwahlnummern auf den Lync Server 2013-Pool verweisen, können Sie den Lync Server 2010-Pool außer Betrieb nehmen.



**Überprüfen der Migration der Einwahlnummern mithilfe der Lync Server-Systemsteuerung**

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle **CsUserAdministrator** oder **CsAdministrator** zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie die Lync Server-Systemsteuerung.

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenz**.

4.  Klicken Sie auf die Registerkarte **Einwahlnummer**.

5.  Überprüfen Sie, ob alle Einwahlnummern zu dem auf Lync Server 2013 gehosteten Pool migriert wurden.

**Überprüfen der Migration der Einwahlnummern mithilfe der Lync Server-Verwaltungsshell**

1.  Öffnen Sie die Lync Server-Verwaltungsshell.

2.  Um alle migrierten Einwahlnummern für Konferenzen zurückzugeben, führen Sie an der Befehlszeile folgenden Befehl aus:
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  Überprüfen Sie, ob alle Einwahlnummern zu dem auf Lync Server 2013 gehosteten Pool migriert wurden.

