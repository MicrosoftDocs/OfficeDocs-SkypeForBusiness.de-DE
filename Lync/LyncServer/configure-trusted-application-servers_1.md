---
title: Konfigurieren von vertrauenswürdigen Anwendungsservern
TOCTitle: Konfigurieren von vertrauenswürdigen Anwendungsservern
ms:assetid: 47a9e72e-566c-4c23-bec2-760a3098a974
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204865(v=OCS.15)
ms:contentKeyID: 49293879
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von vertrauenswürdigen Anwendungsservern

 

_**Letztes Änderungsdatum des Themas:** 2012-10-04_

Wenn Sie in einer gemischten Umgebung einen neuen vertrauenswürdigen Anwendungsserver nach dem Zusammenführen der Office Communications Server-Vorversionstopologie mit Lync Server 2013 erstellen und einen neuen vertrauenswürdigen Anwendungsserver mithilfe des Topologie-Generators definieren, müssen Sie den nächsten Hoppool als Lync Server 2013-Pool festlegen. In einer zusammengeführten Umgebung werden sowohl der Office Communications Server-Pool der Vorversion als auch der Lync Server 2013-Pool in der Dropdownliste angezeigt. Die Auswahl des Pools der Vorversion wird *nicht* unterstützt.

## So wählen Sie beim Erstellen eines vertrauenswürdigen Anwendungsservers Lync Server 2013 als nächsten Hop aus

1.  Öffnen Sie eine bestehende Topologie im Topologie-Generator.

2.  Klicken Sie im linken Bereich mit der rechten Maustaste auf **Vertrauenswürdige Anwendungsserver** , und klicken Sie anschließend auf **Neuer Pool für vertrauenswürdige Anwendungen** .

3.  Geben Sie den **Pool-FQDN** des vertrauenswürdigen Anwendungspools ein, und legen Sie fest, ob es sich um eine Topologie mit einem einzelnen oder mehreren Servern handelt.

4.  Klicken Sie auf **Weiter** .

5.  Wählen Sie auf der Seite **Nächsten Hop auswählen** den Lync Server 2013 Front-End-Pool aus der Liste aus.
    
    ![Neuen vertrauenswürdigen Anwendungspool definieren (Dialogfeld)](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Neuen vertrauenswürdigen Anwendungspool definieren (Dialogfeld)")  

6.  Klicken Sie auf **Fertig stellen** .

7.  Wählen Sie den obersten Knoten **Lync Server** aus, und wählen Sie im Bereich **Aktionen** die Aktion **Veröffentlichen** aus.

8.  Vergewissern Sie sich, dass der **Pool für vertrauenswürdige Anwendungen** erfolgreich erstellt wurde und mit dem richtigen Front-End-Pool verknüpft ist.

