---
title: Aktivieren der Gruppenanrufannahme für Benutzer
TOCTitle: Aktivieren der Gruppenanrufannahme für Benutzer
ms:assetid: 20ec5f41-6ba2-4156-82ed-b91d05b62a6d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ945620(v=OCS.15)
ms:contentKeyID: 52056301
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren der Gruppenanrufannahme für Benutzer

 

_**Letztes Änderungsdatum des Themas:** 2013-01-30_

Aktivieren Sie die Gruppenanrufannahme für Benutzer mithilfe des SEFAUtil-Resource Kit-Tools. Damit Benutzer die Gruppenanrufannahme nutzen können, muss ihnen in der Orbittabelle für das Parken von Anrufen eine Gruppennummer vom Typ "GroupPickup" zugewiesen sein. Die Zuweisung einer Nummer für die Anrufannahmegruppe und die Aktivierung der Gruppenanrufannahme erfolgen gleichzeitig durch das Verwenden des Parameters "/enablegrouppickup", wenn Sie "SEFAUtil.exe" ausführen.

## So aktivieren Sie die Gruppenanrufannahme für einen Benutzer

1.  Melden Sie sich mit Administratorrechten an dem Computer an, auf dem Sie das SEFAUtil-Tool installiert haben.

2.  Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Beispiel:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

## Siehe auch

#### Aufgaben

[Zuweisen von Nummern für die Gruppenanrufannahme an Benutzer](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[Deaktivieren der Gruppenanrufannahme für Benutzer](lync-server-2013-disable-group-call-pickup-for-users.md)

