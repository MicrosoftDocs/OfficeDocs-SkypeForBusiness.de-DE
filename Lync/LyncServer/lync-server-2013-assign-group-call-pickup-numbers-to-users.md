---
title: Zuweisen von Nummern für die Gruppenanrufannahme an Benutzer
TOCTitle: Zuweisen von Nummern für die Gruppenanrufannahme an Benutzer
ms:assetid: b8e79275-8e7e-4799-b908-f34f61df22f0
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ945647(v=OCS.15)
ms:contentKeyID: 52056445
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zuweisen von Nummern für die Gruppenanrufannahme an Benutzer

 

_**Letztes Änderungsdatum des Themas:** 2013-01-30_

Nachdem Sie der Anrufparkorbit-Tabelle Gruppennummern für die Gruppenanrufannahme hinzugefügt haben, können Sie die Gruppen den Benutzern zuweisen. Verwenden Sie das SEFAUtil-Resource Kit-Tool (Secondary Extension Feature Activation), um Gruppen für die Anrufannahme den Benutzern zuzuweisen.


> [!NOTE]
> Weisen Sie in einer Hybridbereitstellung keine Gruppenanrufannahme-Gruppe zu Benutzern zu, die online verwaltet werden. Benutzer, die online verwaltet werden, können nicht an der Gruppenanrufannahme teilnehmen. Das heißt, ihre Anrufe können nicht von anderen Benutzern angenommen werden, und sie können nicht die Anrufe anderer Benutzer entgegennehmen.



## So weisen Sie eine Gruppenanrufannahme-Gruppe einem Benutzer zu

1.  Melden Sie sich mit Administratorrechten an dem Computer an, auf dem Sie das SEFAUtil-Tool installiert haben.

2.  Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Beispiel:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

## Siehe auch

#### Aufgaben

[Aktivieren der Gruppenanrufannahme für Benutzer](lync-server-2013-enable-group-call-pickup-for-users.md)  
[Deaktivieren der Gruppenanrufannahme für Benutzer](lync-server-2013-disable-group-call-pickup-for-users.md)

