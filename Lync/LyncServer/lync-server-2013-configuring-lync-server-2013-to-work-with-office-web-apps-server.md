---
title: Konfigurieren von Lync Server 2013 für die Verwendung mit Office Web Apps Server
TOCTitle: Konfigurieren von Lync Server 2013 für die Verwendung mit Office Web Apps Server
ms:assetid: 6231e519-9010-4ff9-b5a6-b5859c2b3e11
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204944(v=OCS.15)
ms:contentKeyID: 49294191
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Lync Server 2013 für die Verwendung mit Office Web Apps Server

 

_**Letztes Änderungsdatum des Themas:** 2013-04-22_

Damit Sie Lync Server 2013 für die Verwendung des Office Web Apps-Servers konfigurieren können, muss der Office Web Apps-Server bereitgestellt und konfiguriert sein. Ausführliche Informationen über die Installation und Konfiguration eines einzelnen Office Web Apps-Servers oder einer Office Web Apps-Serverfarm für Hochverfügbarkeitszwecke finden Sie im **Handbuch zur Bereitstellung von Office Web Apps-Server und Office Web Apps**.

Nachdem der Office Web Apps-Server erfolgreich installiert und Ihre Web-Farm ordnungsgemäß konfiguriert wurde, müssen Sie Lync Server für die Kommunikation mit dem neuen Server konfigurieren, indem Sie die Office Web Apps-Server-Such-URL zu Ihrer Lync Server-Topologie hinzufügen. Gehen Sie dazu wie folgt vor:

1.  Klicken Sie auf **Start**, **Alle Programme**, **Microsoft Lync Server 2013** und anschließend auf **Lync Server-Topologie-Generator**.

2.  Wählen Sie im Dialogfeld **Topologie-Generator** die Option **Topologie aus einer vorhandenen Bereitstellung herunterladen** aus, und klicken Sie dann auf **OK**.

3.  Geben Sie im Dialogfeld **Topologie speichern unter** einen Namen für Ihr Topologiedokument (z. B. **PreWebAppsServerTopology**) in **Dateiname** ein, und klicken Sie dann auf **Speichern**. Diese Topologie kann später wieder abgerufen und neu veröffentlicht werden, falls es zu Problemen kommt.

4.  Erweitern Sie im Topologie-Generator den Eintrag **Lync Server 2013**, erweitern Sie den Namen Ihres Standorts, erweitern Sie **Front-End-Pools der Enterprise Edition**, klicken Sie mit der rechten Maustaste auf den Namen eines Ihrer Pools, und klicken Sie dann auf **Eigenschaften bearbeiten**.

5.  Suchen Sie im Dialogfeld **Eigenschaften bearbeiten** auf der Registerkarte **Allgemein** die Überschrift **Office Web Apps-Server zuordnen**, und klicken Sie dann auf **Neu** (oder wählen Sie in der Dropdownliste einen vorhandenen Office Web Apps-Server aus).

6.  Geben Sie im Dialogfeld **Neuen Office Web Apps-Server definieren** den vollqualifizierten Domänennamen (FQDN) Ihres Office Web Apps-Servercomputers im Feld **FQDN von Office Web Apps-Server** ein. Anschließend sollte im Feld **Office Web Apps-Server-Such-URL** automatisch die Such-URL Ihres Office Web Apps-Servers stehen.
    
    Wenn der Office Web Apps-Server lokal installiert ist und sich in der gleichen Netzwerkzone wie Lync Server 2013 befindet, sollte die Option **Office Web Apps-Server ist in einem externen Netzwerk (d. h. Umkreis/Internet) bereitgestellt** nicht aktiviert werden.
    
    Wenn der Office Web Apps-Server außerhalb Ihrer internen Firewall bereitgestellt ist, aktivieren Sie die Option **Office Web Apps-Server ist in einem externen Netzwerk (d. h. Umkreis/Internet) bereitgestellt**.

7.  Klicken Sie im Dialogfeld **Neuen Office Web Apps-Server definieren** auf **OK**, und klicken Sie dann auf **OK** im Dialogfeld **Eigenschaften bearbeiten**. Die Office Web Apps-Such-URL wird dann unter den Zuordnungen des Pools aufgeführt.

Sie müssen diese Schritte für jeden Pool wiederholen, der Ihrem Office Web Apps-Server zugeordnet werden soll.

Nachdem Sie die Such-URL zur Topologie hinzugefügt haben, müssen Sie die aktualisierte Topologie veröffentlichen. Gehen Sie dazu im Topologie-Generator wie folgt vor:

1.  Klicken Sie auf **Aktion**, und klicken Sie dann auf **Topologie veröffentlichen**.

2.  Klicken Sie im Assistenten zum Veröffentlichen der Topologie auf der Seite **Topologie veröffentlichen** auf **Weiter**.

3.  Klicken Sie auf der Seite **Assistent für die Veröffentlichung abgeschlossen** auf **Fertig stellen**.

4.  Schließen Sie den Topologie-Generator.

