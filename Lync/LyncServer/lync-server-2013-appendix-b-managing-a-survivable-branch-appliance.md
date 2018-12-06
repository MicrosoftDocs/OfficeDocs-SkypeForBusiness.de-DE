---
title: 'Lync Server 2013: Anhang B: Verwalten einer Survivable Branch Appliance'
TOCTitle: 'Anhang B: Verwalten einer Survivable Branch Appliance'
ms:assetid: 2ec9d505-6d39-491c-9524-8cf36866b855
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425797(v=OCS.15)
ms:contentKeyID: 49293561
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anhang B: Verwalten einer Survivable Branch Appliance in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-18_

In diesem Thema werden die Verfahren zum Verwalten einer Survivable Branch-Anwendung beschrieben. Insbesondere wird erläutert, wie Sie eine Survivable Branch-Anwendung ersetzen und umbenennen und wie Sie den Lync Server 2013-Front-End-Pool ändern, dem die Survivable Branch-Anwendung zugeordnet ist.

## So ersetzen Sie eine Survivable Branch Appliance

1.  Beenden Sie alle Lync Server 2013-Dienste auf der Survivable Branch-Anwendung. (Weitere Informationen finden Sie in der Herstellerdokumentation zur Survivable Branch-Anwendung.)

2.  (Empfohlen) Entfernen Sie die Survivable Branch-Anwendung aus der Domäne.

3.  Löschen Sie das Survivable Branch-Anwendung-Computerobjekt in Active Directory-Domänendienste, indem Sie die folgenden Schritte ausführen:
    
      - Melden Sie sich bei einem Mitgliedsserver als Mitglied der Gruppe "Organisations-Admins" an.
    
      - Klicken Sie nacheinander auf **Start** , **Verwaltungstools** und dann auf **Active Directory-Benutzer und -Computer** .
    
      - Klicken Sie mit der rechten Maustaste auf das Survivable Branch-Anwendung-Objekt, und klicken Sie auf **Löschen** .

4.  Fügen Sie das Survivable Branch-Anwendung-Computerobjekt erneut hinzu. (Siehe [Hinzufügen einer Survivable Branch Appliance zu Active Directory in Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).)

5.  Warten Sie die Active Directory-Replikation ab.

6.  Öffnen Sie die Lync Server-Verwaltungsshell, und geben Sie **Enable-CSTopology** ein.

7.  Verbinden Sie die neue Survivable Branch-Anwendung mit dem Netzwerk, und führen Sie die Schritte unter [Bereitstellen einer Survivable Branch Appliance oder eines Survivable Branch Servers mit Lync Server 2013 – Aufgaben am zentralen Standort](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) und [Bereitstellen einer Survivable Branch Appliance oder eines Survivable Branch Servers mit Lync Server 2013 – Aufgaben am Zweigstellenstandort](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md) aus.

## So benennen Sie eine Survivable Branch Appliance um

1.  Verschieben Sie die Benutzer an den zentralen Standort. Ausführliche Informationen finden Sie unter [Verschieben von Benutzern in einen anderen Pool](lync-server-2013-move-users-to-another-pool.md).

2.  Beenden Sie alle Lync Server 2013-Dienste auf der Survivable Branch-Anwendung. (Weitere Informationen finden Sie in der Herstellerdokumentation zur Survivable Branch-Anwendung.)

3.  Entfernen Sie die Survivable Branch-Anwendung aus der Topologie, indem Sie die folgenden Schritte ausführen:
    
      - Klicken Sie auf **Start** , **Alle Programme** , **Microsoft Lync Server** und anschließend auf **Lync Server-Topologie-Generator** .
    
      - Erweitern Sie in der Konsolenstruktur den Knoten **Zweigniederlassungen** , klicken Sie auf die Survivable Branch-Anwendung, und klicken Sie anschließend im Aktionsbereich auf **Löschen** .

4.  Entfernen Sie die Survivable Branch-Anwendung aus der Domäne.

5.  Löschen Sie das Survivable Branch-Anwendung-Computerobjekt in Active Directory, indem Sie die folgenden Schritte ausführen:
    
      - Melden Sie sich bei einem Domänencontroller als Mitglied der Gruppe "Organisations-Admins" an.
    
      - Klicken Sie nacheinander auf **Start** , **Verwaltungstools** und dann auf **Active Directory-Benutzer und -Computer** .
    
      - Klicken Sie mit der rechten Maustaste auf das Survivable Branch-Anwendung-Objekt, und klicken Sie auf **Löschen** .

6.  Setzen Sie die Survivable Branch-Anwendung auf die Werkseinstellungen zurück. (Informationen hierzu finden Sie in der Herstellerdokumentation zur Survivable Branch Appliance.)

7.  Führen Sie die Schritte unter [Bereitstellen einer Survivable Branch Appliance oder eines Survivable Branch Servers mit Lync Server 2013 – Aufgaben am zentralen Standort](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) und [Bereitstellen einer Survivable Branch Appliance oder eines Survivable Branch Servers mit Lync Server 2013 – Aufgaben am Zweigstellenstandort](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md) aus.

8.  Verschieben Sie die Benutzer auf die umbenannte Survivable Branch-Anwendung. Ausführliche Informationen finden Sie unter [Verschieben von Benutzern in einen anderen Pool](lync-server-2013-move-users-to-another-pool.md).

## So ändern Sie den der Survivable Branch Appliance zugeordneten Lync Server-Front-End-Pool

1.  Verschieben Sie die Benutzer von der Survivable Branch-Anwendung in den Lync Server-Front-End-Pool am zentralen Standort. Ausführliche Informationen finden Sie unter [Verschieben von Benutzern in einen anderen Pool](lync-server-2013-move-users-to-another-pool.md).

2.  Beenden Sie alle Lync Server-Dienste auf der Survivable Branch-Anwendung. (Weitere Informationen finden Sie in der Herstellerdokumentation zur Survivable Branch-Anwendung.)

3.  Aktualisieren Sie den der Survivable Branch-Anwendung zugeordneten Lync Server-Front-End-Pool, indem Sie die folgenden Schritte ausführen:
    
      - Klicken Sie auf **Start** , **Alle Programme** , **Microsoft Lync Server** und anschließend auf **Lync Server-Topologie-Generator** .
    
      - Erweitern Sie **Zweigniederlassungen** .
    
      - Klicken Sie mit der rechten Maustaste auf das zu ändernde Survivable Branch-Anwendung-Objekt, und klicken Sie dann auf **Eigenschaften bearbeiten** .
    
      - Wählen Sie unter **Flexibilität** den neuen Front-End-Pool aus, dem die Survivable Branch-Anwendung zugeordnet werden soll, und klicken Sie dann auf **Weiter** .
    
      - Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf die neue Survivable Branch-Anwendung, klicken Sie auf **Topologie** und anschließend auf **Veröffentlichen** .

4.  Starten Sie alle Lync Server-Dienste auf der Survivable Branch-Anwendung neu.

5.  Testen Sie die Survivable Branch-Anwendung. Ausführliche Informationen finden Sie unter [Verwalten von Benutzern in einer Survivable Branch Appliance oder auf einem Survivable Branch Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).

6.  Verschieben Sie die Benutzer vom Lync Server-Front-End-Pool am zentralen Standort auf die Survivable Branch-Anwendung.

