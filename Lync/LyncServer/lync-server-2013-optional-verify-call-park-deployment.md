---
title: 'Lync Server 2013: (Optional) Überprüfen der Bereitstellung der Funktion zum Parken von Anrufen'
TOCTitle: (Optional) Überprüfen der Bereitstellung der Funktion zum Parken von Anrufen
ms:assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg413076(v=OCS.15)
ms:contentKeyID: 49296004
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# (Optional) Überprüfen der Bereitstellung der Funktion zum Parken von Anrufen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-11_

Nach dem Installieren und Konfigurieren der Anwendung zum Parken von Anrufen müssen Sie die Konfiguration überprüfen, um sicherzustellen, dass das Parken und Entgegennehmen von Anrufen wie erwartet funktioniert. Überprüfen Sie mindestens Folgendes:

  - Rufen Sie einen Benutzer an, bei dem das Parken von Anrufen aktiviert ist, und bitten Sie ihn oder sie, den Anruf zu parken.
    

    > [!NOTE]
    > Wenn Sie Parken von Anrufen kurz vor dem Testen in der VoIP-Richtlinie aktiviert haben, muss dieser Benutzer sich von Lync Server abmelden und dann wieder anmelden, damit die Option zum Parken von Anrufen in der Liste zur Anrufweiterleitung angezeigt wird.



  - Wählen Sie die Orbitnummer, um den Anruf entgegenzunehmen.

  - Parken Sie einen weiteren Anruf, lassen Sie Zeitspanne für die Zeitüberschreitung verstreichen, und nehmen Sie den Rückruf nicht entgegen. Überprüfen Sie, ob der Anruf, bei dem eine Zeitüberschreitung aufgetreten ist, ordnungsgemäß an das für **OnTimeoutURI** angegebene Fallbackziel weitergeleitet wurde.

