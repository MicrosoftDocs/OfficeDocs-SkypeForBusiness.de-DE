---
title: Verschieben eines einzelnen Benutzers in den Pilotpool
TOCTitle: Verschieben eines einzelnen Benutzers in den Pilotpool
ms:assetid: e9de81a8-40dd-4446-81e7-a2b810eaea50
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205401(v=OCS.15)
ms:contentKeyID: 49295777
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verschieben eines einzelnen Benutzers in den Pilotpool

 

_**Letztes Änderungsdatum des Themas:** 2012-09-26_

Mithilfe der Systemsteuerung für Lync Server 2013 oder der Verwaltungsshell für Lync Server 2013 können Sie einen Benutzer vom Lync Server 2010-Pool in den Lync Server 2013-Pilotpool verschieben. Im folgenden Beispiel ist **pool01.contoso.net** in der Spalte für den Registrierungspool der Lync Server 2010-Pool, und alle sechs Benutzer sind mit diesem Pool verbunden. Verwenden Sie die folgenden Verfahren, um einen Benutzer mithilfe der Systemsteuerung für Lync Server 2013 und der Lync Server-Verwaltungsshell in den Lync Server 2013-Pool zu verschieben.

## So verschieben Sie einen Benutzer mithilfe von Systemsteuerung für Lync Server 2013

**Liste der Benutzer in der Lync Server 2013-Systemsteuerung**

![Lync Server-Systemsteuerung – Benutzer verschieben (Dialogfeld)](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync Server-Systemsteuerung – Benutzer verschieben (Dialogfeld)")

1.  Melden Sie sich über ein Konto, das Mitglied der Gruppe „RTCUniversalServerAdmins“ oder der Administratorrolle „CsAdministrator“ oder „CsUserAdministrator“ ist, am Front-End-Server an.

2.  Öffnen Sie die **Lync Server-Systemsteuerung**.

3.  Klicken Sie auf **Benutzer** und anschließend auf **Suchen**.

4.  Wählen Sie einen Benutzer aus, den Sie in den Lync Server 2013-Pool verschieben möchten. In diesem Beispiel verschieben wir den Benutzer Sara Davis.

5.  Wählen Sie im Menü **Aktion** die Option **Ausgewählte Benutzer in Pool verschieben** aus.

6.  Wählen Sie in der Dropdownliste den Lync Server 2013-Pool aus.

7.  Klicken Sie auf **Aktion** und dann auf **Ausgewählte Benutzer in Pool verschieben**. Klicken Sie anschließend auf **OK**.
    
    ![Benutzer verschieben, Zielregistrierungspool (Dialogfeld)](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Benutzer verschieben, Zielregistrierungspool (Dialogfeld)")  

8.  Stellen Sie sicher, dass die Spalte **Registrierungspool** für den Benutzer jetzt den Lync Server 2013-Pool enthält. Dies weist darauf hin, dass der Benutzer erfolgreich verschoben worden ist.

## So verschieben Sie einen Benutzer mithilfe der Verwaltungsshell für Lync Server 2013

1.  Öffnen Sie die Lync Server-Verwaltungsshell.

2.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  Geben Sie anschließend an der Befehlszeile Folgendes ein:
    
        Get-CsUser -Identity "David Pelton"

4.  Die **RegistrarPool** -Identität zeigt jetzt auf den Lync Server 2013-Pool. Das Vorhandensein dieser Identität zeigt an, dass der Benutzer erfolgreich verschoben worden ist.
    
    ![Ausgabe von Get-CsUser-Cmdlet mit Filter Identity](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Ausgabe von Get-CsUser-Cmdlet mit Filter Identity")  
    

    > [!NOTE]
    > Ausführliche Informationen zum Cmdlet <STRONG>Get-CsUser</STRONG> erhalten Sie, indem Sie folgenden Befehl ausführen: <STRONG>Get-Help Get-CsUser -Detailed</STRONG>.


