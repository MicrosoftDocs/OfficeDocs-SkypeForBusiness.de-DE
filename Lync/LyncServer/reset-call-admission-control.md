---
title: Zurücksetzen der Anrufsteuerung
TOCTitle: Zurücksetzen der Anrufsteuerung
ms:assetid: 5873f56c-f3d6-4d73-beea-c9f37d5077f6
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688064(v=OCS.15)
ms:contentKeyID: 49890758
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zurücksetzen der Anrufsteuerung

 

_**Letztes Änderungsdatum des Themas:** 2012-10-11_

Wenn in einem Lync Server 2010Front-End-Pool eine Anrufsteuerung gehostet wird, müssen Sie das Hosting der Anrufsteuerung in einen Lync Server 2013-Pool verschieben, bevor Sie den Lync Server 2010Front-End-Pool entfernen können.

## So setzen Sie die Anrufsteuerung zurück

1.  Öffnen Sie die Topologie-Generator.

2.  Klicken Sie mit der rechten Maustaste auf den Standortknoten, und klicken Sie auf **Eigenschaften bearbeiten** .

3.  Vergewissern Sie sich, dass in der **Einstellung für Anrufsteuerung** die Option **Anrufsteuerung aktivieren** ausgewählt wurde.

4.  Wählen Sie unter **Front-End-Pool für die Anrufsteuerung (CAC)** den Lync Server 2013-Pool aus, in dem die Anrufsteuerung gehostet werden soll, und klicken Sie auf **OK** .

5.  Veröffentlichen Sie die Topologie.

