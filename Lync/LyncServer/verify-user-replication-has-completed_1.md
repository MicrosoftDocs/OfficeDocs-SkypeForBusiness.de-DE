---
title: Sicherstellen, dass die Benutzerreplikation abgeschlossen ist
TOCTitle: Sicherstellen, dass die Benutzerreplikation abgeschlossen ist
ms:assetid: 199dc9de-b555-468f-a42a-9e92ea6c9053
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204712(v=OCS.15)
ms:contentKeyID: 49293321
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Sicherstellen, dass die Benutzerreplikation abgeschlossen ist

 

_**Letztes Änderungsdatum des Themas:** 2012-09-28_

Wenn Sie das Cmdlet **Move-CsLegacyUser** ausführen, tritt möglicherweise ein Fehler auf, wenn die Benutzerinformationen nicht vollständig zwischen AD DS (Active Directory Domain Services) Lync Server 2013-Datenbank synchronisiert sind, da die erste Replikation nicht vollständig abgeschlossen wurde. Die Dauer der erfolgreichen ersten Synchronisierung durch den Lync Server 2013-Benutzerreplikationsdienst hängt von der Anzahl der Domänencontroller ab, die in der Active Directory-Gesamtstruktur enthalten sind und als Host für den Lync Server 2013-Pool dienen. Der erste Synchronisierungsvorgang des Lync Server 2013-Benutzerreplikationsdienstes beginnt, wenn der Lync Server 2013 zum ersten Mal gestartet wird. Danach wird die Synchronisierungshäufigkeit durch das Benutzerreplikationsintervall bestimmt. Führen Sie die folgenden Schritte aus, um zu überprüfen, ob die Benutzerreplikation erfolgreich abgeschlossen wurde, bevor Sie das Cmdlet **Move-CsLegacyUser** ausführen.

## So überprüfen Sie, dass die Benutzerreplikation abgeschlossen wurde

1.  Klicken Sie auf dem Lync Server 2013-Front-End-Server auf das **Startmenü** und dann auf **Ausführen** .

2.  Geben Sie **eventvwr.exe** ein, und klicken Sie dann auf **OK** .

3.  Klicken Sie in der Ereignisanzeige auf **Anwendungs- und Dienstprotokolle** , um die Ansicht zu erweitern, und wählen Sie dann Lync Server aus.

4.  Klicken Sie im Bereich **Aktion** auf **Aktuelles Protokoll filtern** .

5.  Klicken Sie in der Liste **Ereignisquellen** auf **LS User Replicator** .

6.  Geben Sie unter **\<All Event IDs\>** den Wert **30024** ein, und klicken Sie dann auf **OK** .

7.  Suchen Sie in der gefilterten Ereignisliste auf der Registerkarte **Allgemein** nach einem Eintrag, der besagt, dass die Benutzerreplikation erfolgreich abgeschlossen wurde.

