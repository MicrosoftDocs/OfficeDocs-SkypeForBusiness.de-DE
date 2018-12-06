---
title: Autorisieren einer Verbindung zum Office Communications Server 2007 R2-Edgeserver
TOCTitle: Autorisieren einer Verbindung zum Office Communications Server 2007 R2-Edgeserver
ms:assetid: 14f6798a-28d6-4b3d-8734-942192e1bbf5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204702(v=OCS.15)
ms:contentKeyID: 49293270
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Autorisieren einer Verbindung zum Office Communications Server 2007 R2-Edgeserver

 

_**Letztes Änderungsdatum des Themas:** 2012-09-28_

Sie müssen die Liste der internen Server, die für die Verbindung mit dem Office Communications Server 2007 R2-Edgeserver autorisiert sind, für jeden Lync Server 2013-Front-End-Server oder Standard Edition-Server in Ihrem Pilotpool aktualisieren. Ohne diese Aktualisierungen sind keine Audio/Video (A/V)-Konferenzen für Benutzer möglich, die den Edgeserver der Vorversion verwenden.

## So autorisieren Sie die Verbindung mit dem Office Communications Server 2007 R2-Edgeserver

1.  Öffnen Sie auf dem Office Communications Server 2007 R2-Edgeserver in der Gruppe **Verwaltungstools** das Snap-In **Computerverwaltung** .

2.  Erweitern Sie in der Konsolenstruktur die Option **Dienste und Anwendungen** .

3.  Klicken Sie mit der rechten Maustaste auf **Office Communications Server 2007 R2**, und klicken Sie dann auf **Eigenschaften** .

4.  Klicken Sie auf die Registerkarte **Intern** .

5.  Klicken Sie unter **Server hinzufügen** auf **Hinzufügen** .

6.  Geben Sie im Dialogfeld **Office Communications Server hinzufügen** die entsprechenden Informationen ein:
    
      - Geben Sie den vollqualifizierten Domänennamen (FQDN) jedes Lync Server 2013-Front-End-Servers oder Standard Edition-Servers und Lync Server 2013-Pools an.
    
      - Geben Sie den FQDN des Lync Server 2013-Directors an, wenn Sie eine statische Route im Pool konfiguriert haben, in der der nächste Hopcomputer durch den FQDN angegeben ist.

7.  Nachdem Sie für jeden Lync Server 2013, Front-End-Server, Standard Edition-Server, Pool und Director einen Eintrag hinzugefügt haben, klicken Sie auf **Anwenden** und dann auf **OK** , um die Eigenschaften-Seite zu schließen.

