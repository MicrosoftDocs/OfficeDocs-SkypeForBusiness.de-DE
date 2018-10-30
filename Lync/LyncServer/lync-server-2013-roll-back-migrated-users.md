---
title: 'Lync Server 2013: Zurücksetzen von migrierten Benutzern'
TOCTitle: Zurücksetzen von migrierten Benutzern
ms:assetid: bfabaf0b-9a42-4057-b729-a7ab9eee8c72
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205224(v=OCS.15)
ms:contentKeyID: 49295272
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zurücksetzen von migrierten Benutzern in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-07_

Wenn Sie ein Rollback für den einheitlichen Kontaktspeicher ausführen müssen, sollten Sie für die Kontakte nur ein Rollback ausführen, wenn Sie den Benutzer zurück nach Exchange 2010 oder Lync Server 2010 verschieben. Für das Rollback deaktivieren Sie die Richtlinien für den Benutzer, und führen Sie dann das **Invoke-CsUcsRollback**-Cmdlet aus. Es genügt nicht, nur **Invoke-CsUcsRollback** ausführen, um ein permanentes Rollback sicherzustellen, da die Migration des einheitlichen Kontaktspeichers erneut gestartet wird, falls die Richtlinien nicht deaktiviert sind. Angenommen, für einen Benutzer wird ein Rollback ausgeführt, da für Exchange 2013 ein Rollback auf Exchange 2010 ausgeführt wird, und anschließend wird das Postfach des Benutzers nach Exchange 2013 verschoben. In diesem Fall wird die Migration des einheitlichen Kontaktspeichers sieben Tage nach dem Rollback erneut gestartet, vorausgesetzt der einheitliche Kontaktspeicher ist weiterhin in den Benutzerdiensterichtlinien für den Benutzer aktiviert.


> [!IMPORTANT]
> Mit dem <STRONG>Move-CsUser</STRONG>-Cmdlet wird in den folgenden Situationen automatisch ein Rollback für den Kontaktspeicher des Endbenutzers von Exchange 2013 auf Lync Server 2013 ausgeführt: 
> <UL>
> <LI>
> <P>Wenn Benutzer von Lync Server 2013 nach Lync Server 2010 verschoben werden.</P>
> <LI>
> <P>Wenn Benutzer standortübergreifend migriert werden. Beispielsweise, wenn ein Benutzer von Skype for Business Online nach einer lokalen Lync Server 2013-Instanz verschoben wird, oder umgekehrt.</P></LI></UL>




> [!IMPORTANT]
> Durch das Importieren der Daten eines einheitlichen Kontaktspeichers aus einer Sicherungsdatenbank können Daten des einheitlichen Kontaktspeichers und Benutzerdaten beschädigt werden, falls der einheitliche Kontaktspeichermodus zwischen dem Export und dem Import geändert wurde. Beispiel: 
> <UL>
> <LI>
> <P>Wenn Sie Kontaktlisten exportieren, bevor die Kontakte der Benutzer zu Exchange 2013 migriert werden, und dann nach der Migration dieselben Daten importieren, werden die Daten des einheitlichen Kontaktspeichers und die Kontaktlisten beschädigt.</P>
> <LI>
> <P>Wenn Sie Benutzerdaten exportieren, nachdem Sie Benutzer zu Exchange 2013 migriert haben, ein Rollback für die Migration ausführen und dann aus irgendeinem Grund die Daten nach der Migration importieren, werden die Daten des einheitlichen Kontaktspeichers und die Kontaktlisten beschädigt.</P></LI></UL>




> [!IMPORTANT]
> Bevor sie ein Exchange-Postfach von Exchange 2013 nach Exchange 2010 verschieben, muss der Exchange-Administrator sicherstellen, dass der Lync Server-Administrator zuvor ein Rollback für die Lync Server-Benutzerkontakte von Exchange 2013 auf Lync Server ausgeführt hat. Informationen zum Ausführen eines Rollbacks für Kontakte des einheitlichen Kontaktspeichers auf Lync Server finden Sie im Verfahren "So führen Sie ein Rollback für Kontakte des einheitlichen Kontaktspeichers von Exchange 2013 auf Lync Server 2013 aus" weiter unten in diesem Abschnitt.



Im folgenden Verfahren wird beschrieben, wie Sie ein Rollback für Benutzerkontakte ausführen. Wenn Sie das **Move-CsUser**-Cmdlet zum Verschieben von Benutzern zwischen Lync Server 2013 und Lync Server 2010 verwenden, können Sie diese Schritte überspringen, da für den einheitlichen Kontaktspeicher vom **Move-CsUser**-Cmdlet automatisch ein Rollback ausgeführt wird, wenn Benutzer von Lync Server 2013 nach Lync Server 2010 verschoben werden. Mit **Move-CsUser** werden Richtlinien für den einheitlichen Kontaktspeicher nicht deaktiviert, weshalb die Migration zum einheitlichen Kontaktspeicher erneut ausgeführt wird, falls der Benutzer zurück zu Lync Server 2013 verschoben wird.

## So führen Sie ein Rollback für Benutzerkontakte von Lync Server 2013 auf Lync Server 2010 aus

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Deaktivieren Sie den einheitlichen Kontaktspeicher für die Benutzer, für die ein Rollback ausgeführt werden soll, damit sie nach dem Rollback nicht erneut migriert werden. (Führen Sie diesen Schritt nur aus, wenn Sie sicherstellen möchten, dass die Benutzer in Zukunft nicht erneut migriert werden.) Geben Sie an der Befehlszeile Folgendes ein, um den einheitlichen Kontaktspeicher für einzelne Benutzer zu deaktivieren:
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    Beispiel:
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  Führen Sie vor dem Verschieben eines Benutzers von Lync Server 2013 nach Lync Server 2010 ein Rollback für die Buddy-Liste für die angegebenen Benutzer in Lync Server aus.
    

    > [!IMPORTANT]
    > Wenn dieser Schritt ausgelassen wird, geht die Buddy-Liste verloren.



4.  Führen Sie ein Rollback für die angegebenen Benutzer aus. Geben Sie an der Befehlszeile Folgendes ein:
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    Beispiel:
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    

    > [!IMPORTANT]
    > Es wird davon abgeraten, mit der Option -Force das Rollback zu erzwingen. Falls Sie diese Option verwenden, gehen die Kontakte der Benutzer verloren.



## So führen Sie ein Rollback für Kontakte des einheitlichen Kontaktspeichers von Exchange 2013 auf Lync Server 2013 aus

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Deaktivieren Sie den einheitlichen Kontaktspeicher für die Benutzer, für die ein Rollback ausgeführt werden soll, damit sie nach dem Rollback nicht erneut migriert werden. Geben Sie an der Befehlszeile Folgendes ein, um den einheitlichen Kontaktspeicher für einzelne Benutzer zu deaktivieren:
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    Beispiel:
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  Führen Sie ein Rollback für die angegebenen Benutzer aus. Geben Sie an der Befehlszeile Folgendes ein:
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    Beispiel:
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    

    > [!IMPORTANT]
    > Sie müssen zuerst ein Rollback für den Lync Server-Benutzer ausführen und anschließend das Exchange 2013-Postfach verschieben. Für den Exchange-Administrator ist das Ausführen eines Rollbacks für Exchange gesperrt, bis das Lync Server-Rollback abgeschlossen ist. Es wird davon abgeraten, mit der Option -Force das Rollback zu erzwingen. Falls Sie diese Option verwenden, gehen die Kontakte der Benutzer verloren.



4.  Nachdem Sie ein Rollback für den Benutzer auf Lync Server ausgeführt haben, kann der Exchange-Administrator ein Rollback für den Exchange-Benutzer von Exchange 2013 auf Exchange 2010 ausführen.

