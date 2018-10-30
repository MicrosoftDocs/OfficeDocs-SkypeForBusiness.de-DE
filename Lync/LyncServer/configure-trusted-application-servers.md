---
title: Konfigurieren von vertrauenswürdigen Anwendungsservern
TOCTitle: Konfigurieren von vertrauenswürdigen Anwendungsservern
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204735(v=OCS.15)
ms:contentKeyID: 49293399
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von vertrauenswürdigen Anwendungsservern

 

_**Letztes Änderungsdatum des Themas:** 2014-11-05_

Wenn Sie in einer gemischten Umgebung einen neuen vertrauenswürdigen Anwendungsserver erstellen, müssen Sie einen Lync Server 2013-Pool als nächsten Hoppool festlegen. In einer gemischten Umgebung werden sowohl der Lync Server 2010-Pool der Vorgängerversion und der Lync Server 2013-Pool in der Dropdownliste angezeigt. Die Auswahl des Pools der Vorversion wird nicht unterstützt.

**Wählen Sie beim Erstellen eines vertrauenswürdigen Anwendungsservers Lync Server 2013 als nächsten Hoppool aus.**

1.  Öffnen Sie den Topologie-Generator.

2.  Klicken Sie im linken Bereich mit der rechten Maustaste auf **Vertrauenswürdige Anwendungsserver** , und klicken Sie anschließend auf **Neuer Pool für vertrauenswürdige Anwendungen** .

3.  Geben Sie den **Pool-FQDN** des Pools vertrauenswürdiger Anwendungen ein. Geben Sie an, ob der Pool einen einzelnen oder mehrere Server enthalten soll.

4.  Klicken Sie auf **Weiter** .

5.  Wählen Sie auf der Seite **Nächsten Hop auswählen** den Lync Server 2013 Front-End-Pool aus der Liste aus.

6.  Klicken Sie auf **Fertig stellen** .

7.  Wählen Sie den obersten Knoten **Lync Server** aus, und wählen Sie dann im Menü **Aktionen** die Option **Veröffentlichen** aus.
    
    Überprüfen Sie, dass der **vertrauenswürdige Anwendungspool** erfolgreich erstellt und dem richtigen Front-End-Pool zugeordnet worden ist.

