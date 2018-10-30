---
title: Deaktivieren der Gruppenanrufannahme für Benutzer
TOCTitle: Deaktivieren der Gruppenanrufannahme für Benutzer
ms:assetid: 91b06f9e-2840-45a2-bbb3-6a29179b9a9f
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ945638(v=OCS.15)
ms:contentKeyID: 52056387
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Deaktivieren der Gruppenanrufannahme für Benutzer

 

_**Letztes Änderungsdatum des Themas:** 2013-01-30_

Verwenden Sie das folgende Verfahren, um die Gruppenanrufannahme für einen Benutzer zu deaktivieren.


> [!NOTE]
> Wenn Sie die Gruppenanrufannahme für einen Benutzer deaktivieren, wird die Nummer für die Anrufannahmegruppe verworfen, die dem Benutzer zugewiesen war. Wenn Sie die Gruppenanrufannahme für diesen Benutzer erneut aktivieren möchten, müssen Sie auch die Nummer für die Anrufannahmegruppe erneut mithilfe des Parameters "/enablegrouppickup" zuweisen.



## So deaktivieren Sie die Gruppenanrufannahme für einen Benutzer

1.  Melden Sie sich mit Administratorrechten an dem Computer an, auf dem Sie das SEFAUtil-Tool installiert haben.

2.  Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    Beispiel:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

## Siehe auch

#### Aufgaben

[Zuweisen von Nummern für die Gruppenanrufannahme an Benutzer](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[Aktivieren der Gruppenanrufannahme für Benutzer](lync-server-2013-enable-group-call-pickup-for-users.md)

