---
title: Planungsdetails
TOCTitle: Planungsdetails
ms:assetid: 39ca6fff-2c15-4347-9f1f-6c8687a39a49
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204823(v=OCS.15)
ms:contentKeyID: 49293715
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planungsdetails

 

_**Letztes Änderungsdatum des Themas:** 2012-10-04_

Die Mitarbeiter, die die große Besprechung unterstützen und die Anfrage verwalten, stellen zunächst sicher, dass zur angeforderten Zeit keine andere Besprechung geplant ist, und sie planen anschließend die Besprechung im Pool für große Besprechungen. Verwenden Sie zur Durchführung dieser Aufgabe das Onlinebesprechungs-Add-In für Lync, das mit dem Lync Server 2013-Client installiert wird. Verwenden Sie die Anmeldeinformationen eines Benutzers, der auf dem Lync Server im dedizierten Pool für große Besprechungen aktiviert ist.

Um die bestmögliche Benutzerfreundlichkeit zu erzielen, ist es wichtig, die große Besprechung mit den richtigen Zugriffsebenen und Besprechungseinstellungen zu planen, die den Bedürfnissen des Besprechungsorganisators entsprechen. Es wird empfohlen, die folgenden Planungseinstellungen zu verwenden, die in den Lync-Besprechungsoptionen konfiguriert werden können:

  - Verwenden Sie einen neuen Besprechungsraum für jede große Besprechung, anstatt den dedizierten Besprechungsraum erneut zu verwenden.

  - Geben Sie die Zugriffsebene für die Besprechung wie folgt an:
    
      - Wenn mindestens ein eingeladener Benutzer nicht zur Organisation gehört, legen Sie den Zugriffstyp für die Besprechung auf **Alle Personen (keine Einschränkungen)** fest. Dadurch vermeiden Sie, dass sie während der laufenden Besprechung einen möglicherweise großen Wartebereich verwalten müssen.
    
      - Wenn die Besprechung nur intern ist, legen Sie den Zugriffstyp für die Besprechung auf **Jeder innerhalb meiner Organisation** fest.
        

        > [!NOTE]
        > Vermeiden Sie es, den Zugriffstyp für die Besprechung auf <STRONG>Von mir eingeladene Personen in meinem Unternehmen</STRONG> festzulegen. Wenn Sie diese Einstellung verwenden, müssen Besprechungsorganisatoren die E-Mail-Adressen aller Benutzer zur Eingeladenenliste hinzufügen, und Sie können keine Verteilergruppe einladen.<BR>Vermeiden Sie es, den Zugriffstyp für die Besprechung auf <STRONG>Nur ich, der Besprechungsorganisator</STRONG> festzulegen, da diese Einstellung erfordert, dass jeder Besprechungsteilnehmer, auch die Referenten, zur Laufzeit der Besprechung zum Wartebereich hinzugefügt werden muss. Der Verantwortliche für die Durchführung der großen Besprechung muss dann ständig die Wartebereichsliste überwachen und neue Benutzer im Wartebereich zur Besprechung zulassen.



  - Wenn Sie die Option **Anrufer erhalten direkten Zugang** aktivieren, können Benutzer, die sich per Telefon einwählen, automatisch der Besprechung beitreten.

  - Laden Sie folgende Benutzer explizit ein:
    
      - Besprechungsorganisator und Delegat (anfordernde Person)
    
      - Die von der eine Besprechung anfordernden Person vorgelegte Liste mit Referenten
    

    > [!NOTE]
    > Wenn der Zugriffstyp der Besprechung auf <STRONG>Von mir ausgewählte Personen</STRONG> festgelegt ist, müssen Sie jeden Teilnehmer einer großen Besprechung explizit als eingeladenen Benutzer hinzufügen.



  - Verwalten Sie die Referenten explizit, anstatt die Referenten-Option auf einen der Werte für automatische Hochstufung festzulegen. Stellen Sie sicher, dass folgende Benutzer als Referenten hinzugefügt werden:
    
      - Besprechungsorganisator und Delegat (anfordernde Person)
    
      - Die von eine große Besprechung anfordernden Personen vorgelegte Liste mit Referenten
    

    > [!NOTE]
    > Indem Sie die Referenten explizit verwalten, können Sie ihre Anzahl steuern und auf eine so kleine Zahl begrenzen, dass eine effektive große Besprechung möglich ist. Wenn die Mehrheit der Besprechungsteilnehmer nur eine Teilnehmerrolle hat, verringert sich die Wahrscheinlichkeit, dass Personen versehentlich die Steuerung der Präsentation übernehmen, eine PowerPoint-Präsentation löschen, Referenten stummschalten bzw. die Stummschaltung aufheben oder die Besprechung auf andere Weise stören.



  - Aktivieren Sie die Option **Alle Teilnehmer stummschalten**, um sicherzustellen, dass nur Referenten Audioinhalte in die Besprechung übertragen können.

  - Aktivieren Sie die Option **Video von Teilnehmern blockieren**, um sicherzustellen, dass nur Referenten Videoinhalte in die Besprechung übertragen können.

Die folgende Abbildung zeigt die empfohlenen Einstellungen für das Onlinebesprechungs-Add-In für Lync.

![Optionen für Konferenzbesprechung](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "Optionen für Konferenzbesprechung")

