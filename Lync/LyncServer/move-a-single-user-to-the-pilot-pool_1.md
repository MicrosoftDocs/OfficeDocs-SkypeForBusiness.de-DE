---
title: Verschieben eines einzelnen Benutzers zum Pilotpool
TOCTitle: Verschieben eines einzelnen Benutzers zum Pilotpool
ms:assetid: 80d5b365-f153-4c61-a148-f9e18ce6e027
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688109(v=OCS.15)
ms:contentKeyID: 49890814
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verschieben eines einzelnen Benutzers zum Pilotpool

 

_**Letztes Änderungsdatum des Themas:** 2012-09-28_

Sie können einen Benutzer aus Ihrem Office Communications Server 2007 R2-Pool in Ihren Lync Server 2013-Pilotpool verschieben, indem Sie die Systemsteuerung für Lync Server 2013 oder die Verwaltungsshell für Lync Server 2013 verwenden. Im nachfolgenden Beispiel ist in der Spalte "Registrierungspool" **\<Office Communications Server\>** der Office Communications Server 2007 R2-Pool, und alle sechs Benutzer sind mit diesem Pool verbunden. Verwenden Sie die folgenden Verfahren, um einen Benutzer in Ihren Lync Server 2013-Pool zu verschieben, und zwar mithilfe der Systemsteuerung für Lync Server 2013 und der Lync Server-Verwaltungsshell.

![Suche nach OCS-Benutzern in Lync Server-Systemsteuerung](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Suche nach OCS-Benutzern in Lync Server-Systemsteuerung")

## So verschieben Sie einen Benutzer mithilfe von Systemsteuerung für Lync Server 2013

1.  Melden Sie sich über ein Konto, das Mitglied der Gruppe "RTCUniversalServerAdmins" oder der Administratorrolle "CsAdministrator" oder "CsUserAdministrator" ist, am Front-End-Server an.

2.  Öffnen Sie die Lync Server-Systemsteuerung.

3.  Klicken Sie auf **Benutzer**.

4.  Klicken Sie auf der Registerkarte **Benutzersuche** auf die Schaltfläche **Suchen**.

5.  Klicken Sie dann auf **Filter hinzufügen**.

6.  Erstellen Sie einen Filter, in dem der **Office Communications Server-Benutzer** gleich **True** ist.

7.  Klicken Sie auf **Suchen**, um nach Legacybenutzern von Office Communications Server 2007 R2 zu suchen.
    
    ![Suche nach OCS-Benutzern in Lync Server-Systemsteuerung](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Suche nach OCS-Benutzern in Lync Server-Systemsteuerung")  

8.  Wählen Sie einen Benutzer aus, den Sie in den Lync Server 2013-Pool verschieben möchten. In diesem Beispiel verschieben wir den Benutzer Sara Davis.

9.  Wählen Sie im Menü **AktionAusgewählte Benutzer in Pool verschieben**.

10. Wählen Sie in der Dropdownliste den Lync Server 2013-Pool aus.

11. Klicken Sie auf **Aktion** und dann auf **Ausgewählte Benutzer in Pool verschieben**. Klicken Sie anschließend auf **OK**.
    
    ![Zielpool in Dialogfeld zum Verschieben von Benutzern festlegen](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "Zielpool in Dialogfeld zum Verschieben von Benutzern festlegen")  

12. Stellen Sie sicher, dass die Spalte **Registrierungspool** für den Benutzer nun den Lync Server 2013-Pool enthält. Ist dies der Fall, wurde der Benutzer erfolgreich verschoben.

## So verschieben Sie einen Benutzer mithilfe von Verwaltungsshell für Lync Server 2013

1.  Öffnen Sie die Lync Server-Verwaltungsshell.

2.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Move-CsLegacyUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  Geben Sie anschließend an der Befehlszeile Folgendes ein:
    
        Get-CsUser -Identity "David Pelton"

4.  Die **RegistrarPool** -Identität zeigt jetzt auf den Lync Server 2013-Pool. Das Vorhandensein dieser Identität zeigt an, dass der Benutzer erfolgreich verschoben worden ist.
    
    ![Ausgabe von Get-CsUser-Cmdlet mit Filter Identity](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Ausgabe von Get-CsUser-Cmdlet mit Filter Identity")  
    

    > [!NOTE]
    > Ausführliche Informationen zum <STRONG>Get-CsUser</STRONG> -Cmdlet erhalten Sie, indem Sie folgenden Befehl ausführen: <STRONG>Get-Help Get-CsUser -Detailed</STRONG>


