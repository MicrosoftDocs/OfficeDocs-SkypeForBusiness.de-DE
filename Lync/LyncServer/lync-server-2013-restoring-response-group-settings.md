---
title: Wiederherstellen der Reaktionsgruppeneinstellungen
TOCTitle: Wiederherstellen der Reaktionsgruppeneinstellungen
ms:assetid: 4f8e1949-925d-4538-be1d-9ac7c06b2aca
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh202174(v=OCS.15)
ms:contentKeyID: 52056334
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Wiederherstellen der Reaktionsgruppeneinstellungen

 

_**Letztes Änderungsdatum des Themas:** 2013-02-18_

Wenn Sie die Reaktionsgruppenanwendung bereitgestellt haben und einen Back-End-Server oder einen Standard Edition-Server wiederherstellen müssen, müssen Sie auch die Konfigurationseinstellungen der Reaktionsgruppe wiederherstellen.

## So stellen Sie die Konfigurationseinstellungen für die Reaktionsgruppe wieder her

1.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<pool FQDN>" -OverwriteOwner -FileName "<path and file name of the backed up file at $Backup>"
    
    Beispiel:
    
        Import-CsRgsConfiguration -Destination "service: ApplicationServer:pool01.contoso.com" -OverwriteOwner -FileName "C:\RgsConfiguration.zip"

