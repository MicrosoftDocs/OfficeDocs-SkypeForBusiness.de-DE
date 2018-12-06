---
title: Aktivieren der Gruppenanrufannahme für Benutzer und Zuweisen einer Gruppennummer
TOCTitle: Aktivieren der Gruppenanrufannahme für Benutzer und Zuweisen einer Gruppennummer
ms:assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ945650(v=OCS.15)
ms:contentKeyID: 52056452
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren der Gruppenanrufannahme für Benutzer und Zuweisen einer Gruppennummer

 

_**Letztes Änderungsdatum des Themas:** 2013-01-30_

Nachdem Sie der Anrufparkorbit-Tabelle Gruppennummern für die Gruppenanrufannahme hinzugefügt haben, weisen Sie die Gruppennummern den Benutzern zu und aktivieren die Gruppenanrufannahme für diese Benutzer. Verwenden Sie das SEFAUtil-Resource Kit-Tool (Secondary Extension Feature Activation), um Gruppenmitglieder zuzuweisen und die Gruppenanrufannahme zu aktivieren.


> [!NOTE]
> Weisen Sie in einer Hybridbereitstellung keine Gruppenanrufannahme-Gruppe zu Benutzern zu, die online verwaltet werden. Benutzer, die online verwaltet werden, können nicht an der Gruppenanrufannahme teilnehmen. Das heißt, ihre Anrufe können nicht von anderen Benutzern angenommen werden, und sie können nicht die Anrufe anderer Benutzer entgegennehmen.



## So weisen Sie eine Gruppennummer zu und aktivieren die Gruppenanrufannahme für einen Benutzer

1.  Melden Sie sich mit Administratorrechten an dem Computer an, auf dem Sie das SEFAUtil-Tool installiert haben.

2.  Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Mit diesem Befehl können Sie beispielsweise einem Benutzer die Gruppennummer 199 zuweisen:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 

## Siehe auch

#### Aufgaben

[Deaktivieren der Gruppenanrufannahme für Benutzer](lync-server-2013-disable-group-call-pickup-for-users.md)

