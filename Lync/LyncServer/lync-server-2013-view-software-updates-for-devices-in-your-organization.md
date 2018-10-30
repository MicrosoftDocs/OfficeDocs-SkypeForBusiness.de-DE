---
title: Anzeigen von Softwareupdates für Geräte in Lync Server 2013
TOCTitle: Anzeigen von Softwareupdates für Geräte in Lync Server 2013
ms:assetid: d2cca12b-ed43-4e1f-90ab-d14bca8b482c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182592(v=OCS.15)
ms:contentKeyID: 49295496
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anzeigen von Softwareupdates für Geräte in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

In Lync Server 2013 verwenden Sie den Geräteaktualisierungswebdienst zum Anzeigen und Verwalten von Softwareupdates für die Geräte in Ihrer Organisation. Diese Updates stehen in Form von CAB-Dateien auf der Microsoft-Supportwebsite zur Verfügung: [http://go.microsoft.com/fwlink/?linkid=204091\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=204091%26clcid=0x407). Nach dem Download der CAB-Datei führen Sie das **Import-CSdeviceUpdate**-Cmdlet aus, um die Geräteupdateregeln aus der CAB-Datei zu importieren. Ausführliche Informationen zum **Import-CSdeviceUpdate**-Cmdlet finden Sie unter [Import-CsDeviceUpdate](https://docs.microsoft.com/en-us/powershell/module/skype/Import-CsDeviceUpdate) in der Lync Server-Verwaltungsshell-Dokumentation.


> [!TIP]
> Bevor Sie ein neues Update in Ihrer Organisation bereitstellen, sollten Sie seine ordnungsgemäße Funktion auf einem Testgerät überprüfen.



## So zeigen Sie Softwareupdates für UC-Geräte an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Laden Sie die CAB-Datei von der Microsoft-Supportwebsite unter [http://go.microsoft.com/fwlink/?linkid=204091\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=204091%26clcid=0x407) in ein Verzeichnis auf einem Lync Server 2013-Computer herunter (Beispiel: **C:\\Updates\\UCUpdates.cab**).

3.  Importieren Sie die Geräteupdateregeln aus der Datei C:\\Updates\\UCUpdates.cab, indem Sie eines der folgenden Cmdlets ausführen:
    
      - Wenn sich die CAB-Datei auf demselben Computer befindet wie der Dienst, der aktualisiert werden soll (service:Redmond-websvc-2), führen Sie das folgende Cmdlet aus:
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - Wenn sich die CAB-Datei auf einem anderen Computer befindet als der Dienst, der aktualisiert werden soll (service:Redmond-websvc-3), führen Sie das folgende Cmdlet aus:
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

5.  Klicken Sie in der linken Navigationsleiste auf **Clients** und dann auf **Geräteupdate**.

6.  Klicken Sie auf der Seite **Geräteupdate** auf ein Update in der Liste, und führen Sie eine der folgenden Aktionen aus:
    
      - **Abbrechen eines ausstehenden Updates.** Klicken Sie auf das Menü **Aktion** und anschließend auf **Ausstehende Updates abbrechen**, um die Bereitstellung des ausgewählten Updates auf den Geräten in Ihrer Organisation zu verhindern.
    
      - **Genehmigen eines Updates.** Klicken Sie auf das Menü **Aktion** und anschließend auf **Genehmigen**, um die Bereitstellung des ausgewählten Updates auf den Geräten in Ihrer Organisation zuzulassen.
    
      - **Wiederherstellen eines Updates.** Klicken Sie auf das Menü **Aktion** und anschließend auf **Wiederherstellen**, um die Bereitstellung eines zuvor genehmigten Updates auf den Geräten in Ihrer Organisation zuzulassen.

## Siehe auch

#### Weitere Ressourcen

[Verwalten von Geräten, Telefonen und Clientanwendungen in Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)

