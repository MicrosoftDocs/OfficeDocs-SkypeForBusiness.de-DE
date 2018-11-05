---
title: Problembehandlung für das Lync VDI-Plug-In
TOCTitle: Problembehandlung für das Lync VDI-Plug-In
ms:assetid: 183c9449-b907-409c-b5ed-b02af3bd93ee
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204713(v=OCS.15)
ms:contentKeyID: 49293307
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Problembehandlung für das Lync VDI-Plug-In

 

_**Letztes Änderungsdatum des Themas:** 2012-10-10_

## Behebung von Problemen beim Installieren des Lync-VDI-Plug-In auf einem Thin-Client

Wenn beim Installieren des VDI-Plug-Ins auf einem Thin-Client Probleme auftreten, überprüfen Sie Folgendes:

  - Stellen Sie sicher, dass im Ordner, den Sie in den Systemvariablen "TEMP" und "TMP" angegeben haben, ausreichend Speicherplatz vorhanden ist

  - Stellen Sie sicher, dass der Schreibschutz deaktiviert ist. Entsprechende Anweisungen finden Sie Dokumentation des Geräteherstellers.

## Behebung von Problemen bei der Paarung

Wenn die Paarung des VDI-Plug-Ins fehlschlägt, wird das Paarungssymbol unten rechts als rotes “X” angezeigt:

![Lync VDI-Symbol mit erfolgreicher Koppelung](images/JJ204713.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync VDI-Symbol mit erfolgreicher Koppelung")

Im Folgenden finden Sie mögliche Gründe für Fehler und Korrekturmaßnahmen.

  - **Der Benutzer hat bei der Anmeldung falsche Anmeldeinformationen eingegeben.**
    
    Der Benutzer sollte sich von Lync abmelden und mit den richtigen Anmeldeinformationen erneut anmelden. Das Paarungsdialogfeld wird erneut angezeigt und gibt an, ob die Paarung erfolgreich war.

  - **Eine andere Instanz des Remotedesktop-Clients wird bereits ausgeführt**
    
    Benutzer, die in Windows die Remotedesktopverbindung verwenden, gehen folgendermaßen vor:
    
    1.  Starten Sie den Task-Manager: Drücken Sie **Alt+Strg+Entf**, und klicken Sie dann auf **Task-Manager starten**.
    
    2.  Klicken Sie auf die Registerkarte **Prozesse**, und suchen Sie in der Liste nach allen Prozessen mit dem Namen **mstsc.exe**.
    
    3.  Markieren Sie alle **mstsc.exe**-Prozesse, und klicken Sie dann auf **Prozess beenden**.
    
    4.  Starten Sie eine neue Remotedesktopsitzung, und versuchen Sie erneut, eine Verbindung herzustellen.

  - **Die erforderlichen Dateien wurden nicht ordnungsgemäß installiert.**
    
    Nach der Installation des Plug-Ins auf dem lokalen Computer sollten die folgenden Dateien in "C:\\Program Files\\Microsoft Office\\Office15" (bzw. im entsprechenden Laufwerkbuchstaben) vorhanden sein:
    
      - LyncVdiPlugin.dll
    
      - UcVdi.dll
    
    Wenn Probleme mit der VDI-Paarung auftreten, stellen Sie sicher, dass diese Dateien auf dem lokalen Computer vorhanden sind.

  - **Der Lync-Client wird auf dem lokalen Computer ausgeführt.**
    
    Zur Verwendung des Lync-VDI-Plug-Ins darf kein Lync-Client auf dem lokalen Computer ausgeführt werden, andernfalls schlägt die Paarung fehl. als bewährte Methode sollte der Benutzer keinen Lync-Client auf dem lokalen Computer installieren.

