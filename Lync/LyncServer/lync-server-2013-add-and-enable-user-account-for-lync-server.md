---
title: Hinzufügen und Aktivieren eines Benutzerkontos für Lync Server
TOCTitle: Hinzufügen und Aktivieren eines Benutzerkontos für Lync Server
ms:assetid: 1edd1c1c-307d-450b-abea-33aaf56bdf13
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg520961(v=OCS.15)
ms:contentKeyID: 49293382
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Hinzufügen und Aktivieren eines Benutzerkontos für Lync Server

 

_**Letztes Änderungsdatum des Themas:** 2012-11-02_

Nach dem Aktivieren eines Benutzerkontos in "Active Directory-Benutzer und -Computer" können Sie mithilfe der Lync Server-Systemsteuerung neue Lync Server 2013-Benutzerkonten erstellen und hinzufügen, indem Sie Lync Server einen Active Directory-Benutzer hinzufügen.

## So fügen Sie einen neuen Lync Server-Benutzer hinzu und aktivieren ihn

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4.  Klicken Sie auf **Benutzer aktivieren**.

5.  Klicken Sie im Dialogfeld **Neuer Lync Server-Benutzer** auf **Hinzufügen**.

6.  Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Namen, Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), Benutzerprinzipalnamen, die E-Mail-Adresse oder die Telefonnummer des gewünschten Active Directory-Benutzerkontos ein, und klicken Sie dann auf **Suchen**.

7.  Wählen Sie in der Tabelle das Konto aus, das Sie Lync Server hinzufügen möchten, und klicken Sie dann auf **OK**.

8.  Weisen Sie den Benutzer einem Pool zu, geben Sie zusätzliche Informationen an, und weisen Sie dem gewünschten Benutzer die Richtlinien zu. Klicken Sie anschließend auf **Aktivieren**.

## Siehe auch

#### Aufgaben

[Aktivieren oder Reaktivieren von Benutzerkonten für Lync Server](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[Entfernen eines Benutzerkontos aus Lync Server](lync-server-2013-remove-a-user-account-from-lync-server.md)  

#### Weitere Ressourcen

[Aktivieren und Deaktivieren von Benutzern für Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

