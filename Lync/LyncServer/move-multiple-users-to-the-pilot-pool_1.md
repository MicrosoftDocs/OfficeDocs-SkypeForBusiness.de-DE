---
title: Verschieben von mehreren Benutzern in den Pilotpool
TOCTitle: Verschieben von mehreren Benutzern in den Pilotpool
ms:assetid: 9492797f-2a26-4773-8ad2-97cb53fa68fc
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688143(v=OCS.15)
ms:contentKeyID: 49890848
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verschieben von mehreren Benutzern in den Pilotpool

 

_**Letztes Änderungsdatum des Themas:** 2012-10-02_

Sie können mehrere Benutzer aus Ihrem Office Communications Server 2007 R2-Pool in Ihren Lync Server 2013-Pilotpool verschieben, indem Sie die Systemsteuerung für Lync Server 2013 oder die Verwaltungsshell für Lync Server 2013 nutzen.

## So verschieben Sie mehrere Benutzer mit der Systemsteuerung für Lync Server 2013

1.  Öffnen Sie die **Lync Server-Systemsteuerung** .

2.  Klicken Sie auf der Registerkarte **Benutzersuche** auf die Schaltfläche **Suchen**.

3.  Klicken Sie dann auf **Filter hinzufügen**.

4.  Erstellen Sie einen Filter, in dem der **Office Communications Server-Benutzer** gleich **True** ist.

5.  Klicken Sie auf **Suchen**, um nach Legacybenutzern von Office Communications Server 2007 R2 zu suchen.

6.  Wählen Sie zwei Benutzer aus, die Sie in den Lync Server 2013-Pool verschieben möchten. In diesem Beispiel werden wir die Benutzer Chen Yang und Claus Hansen verschieben.
    
    ![Nach Suche nach OCS-Benutzern angezeigte Benutzerliste](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "Nach Suche nach OCS-Benutzern angezeigte Benutzerliste")  

7.  Wählen Sie im Menü **Aktion** die Option **Ausgewählte Benutzer in Pool verschieben** aus.

8.  Wählen Sie in der Dropdownliste den Lync Server 2013-Pool aus.

9.  Klicken Sie auf **Aktion** und dann auf **Ausgewählte Benutzer in Pool verschieben** . Klicken Sie auf "OK".
    
    ![Benutzer verschieben, Zielregistrierungspool (Dialogfeld)](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Benutzer verschieben, Zielregistrierungspool (Dialogfeld)")  

10. Stellen Sie sicher, dass die Spalte **Registrierungspool** für die Benutzer jetzt den Lync Server 2013-Pool enthält. Dies weist darauf hin, dass die Benutzer erfolgreich verschoben wurden.

## So verschieben Sie mehrere Benutzer mit der Verwaltungsshell für Lync Server 2013

1.  Öffnen Sie die Verwaltungsshell für Lync Server 2013.

2.  Geben Sie an der Befehlszeile folgenden Befehl ein, wobei Sie **User1** und **User2** durch die betreffenden Benutzernamen, die Sie verschieben möchten, und **pool\_FQDN** durch den Namen des Zielpools ersetzen. In diesem Beispiel verschieben wir die Benutzer Hao Chen und Katie Jordan.
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsLegacyUser -Target "pool_FQDN"
    
    ![Beispiel-Cmdlet zum Verschieben eines Legacybenutzers](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "Beispiel-Cmdlet zum Verschieben eines Legacybenutzers")  

3.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Get-CsUser -Identity "User1"

4.  Die **Registrierungspool** -Identität sollte jetzt auf den Pool zeigen, den Sie im vorherigen Schritt als **pool\_FQDN** angegeben haben. Das Vorhandensein dieser Identität bestätigt, dass die Benutzer erfolgreich verschoben wurden. Wiederholen Sie den Schritt, um zu prüfen, ob **User2** verschoben wurde.
    
    ![Ausgabe von PowerShell-Cmdlet Get-UsUser -Identity](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Ausgabe von PowerShell-Cmdlet Get-UsUser -Identity")  

## So verschieben Sie alle Benutzer gleichzeitig mit der Verwaltungsshell für Lync Server 2013

In diesem Beispiel befinden sich alle Benutzer im Office Communications Server 2007 R2-Pool (pool01.contoso.net). Mit der Verwaltungsshell für Lync Server 2013 werden wir alle Benutzer gleichzeitig in den Lync Server 2013-Pool (pool02.contoso.net) verschieben.

1.  Öffnen Sie die **Verwaltungsshell für Lync Server 2013**.

2.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Get-CsUser -OnOfficeCommunicationServer | Move-CsLegacyUser -Target "pool_FQDN"
    
    ![Beispiel-Cmdlet zum Verschieben aller Legacybenutzer in einem Pool](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "Beispiel-Cmdlet zum Verschieben aller Legacybenutzer in einem Pool")  

3.  Führen Sie dann für einen der Pilotbenutzer **Get-CsUser** aus.
    
        Get-CsUser -Identity "Hao Chen"

4.  Die **Registrierungspool** -Identität zeigt nun für alle Benutzer auf den Pool, den Sie im vorherigen Schritt als "pool\_FQDN" angegeben haben. Das Vorhandensein dieser Identität bestätigt, dass der Benutzer erfolgreich verschoben wurde.

5.  Darüber hinaus können wir die Benutzerliste in der Systemsteuerung für Lync Server 2013 anzeigen und prüfen, ob der Wert des Registrierungspools jetzt auf den Lync Server 2013-Pool zeigt.
    
    ![Lync Server 2013-Systemsteuerung mit Benutzerliste](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013-Systemsteuerung mit Benutzerliste")

