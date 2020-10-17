---
title: 'Lync Server 2013: Planen von Details für Besprechungen'
description: 'Lync Server 2013: Planen von Details für Besprechungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scheduling details
ms:assetid: 39ca6fff-2c15-4347-9f1f-6c8687a39a49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204823(v=OCS.15)
ms:contentKeyID: 48183910
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef7a6907aedbc880731b3fb474c9294c1c111b80
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561981"
---
# <a name="scheduling-details-for-meetings-in-lync-server-2013"></a>Planungsdetails für Besprechungen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-04_

Nachdem Sie überprüft haben, um sicherzustellen, dass keine andere Besprechung zum gewünschten Zeitpunkt geplant ist, plant der große Besprechungs Mitarbeiter, der die Anforderung verarbeitet, die Besprechung im großen Besprechungs Pool. Verwenden Sie das Online-Besprechungs-Add-in für lync, das mit dem lync Server 2013-Client installiert ist, um diese Aufgabe auszuführen, wobei die Anmeldeinformationen eines Benutzers verwendet werden, der für lync Server im dedizierten großen Besprechungs Pool aktiviert ist.

Um die bestmögliche Benutzerfreundlichkeit zu erzielen, ist es wichtig, die große Besprechung mit den richtigen Zugriffsebenen und Besprechungseinstellungen zu planen, die den Bedürfnissen des Besprechungsorganisators entsprechen. Wir empfehlen die folgenden Planungseinstellungen, die in lync-Besprechungsoptionen konfiguriert sind:

  - Verwenden Sie einen neuen Besprechungsraum für jede große Besprechung, anstatt den dedizierten Besprechungsraum erneut zu verwenden.

  - Geben Sie die Zugriffsebene für die Besprechung wie folgt an:
    
      - Wenn mindestens ein eingeladener Benutzer nicht zur Organisation gehört, legen Sie den Zugriffstyp für die Besprechung auf **Alle Personen (keine Einschränkungen)** fest. Dadurch vermeiden Sie, dass sie während der laufenden Besprechung einen möglicherweise großen Wartebereich verwalten müssen.
    
      - Wenn die Besprechung nur intern ist, legen Sie den Zugriffstyp für die Besprechung auf **Jeder innerhalb meiner Organisation** fest.
        
        <div>
        

        > [!NOTE]  
        > Vermeiden Sie es, den Zugriffstyp für die Besprechung auf <STRONG>Von mir eingeladene Personen in meinem Unternehmen</STRONG> festzulegen. Wenn Sie diese Einstellung verwenden, müssen Besprechungsorganisatoren die E-Mail-Adressen aller Benutzer zur Eingeladenenliste hinzufügen, und Sie können keine Verteilergruppe einladen.<BR>Vermeiden Sie es, den Zugriffstyp für die Besprechung auf <STRONG>Nur ich, der Besprechungsorganisator</STRONG> festzulegen, da diese Einstellung erfordert, dass jeder Besprechungsteilnehmer, auch die Referenten, zur Laufzeit der Besprechung zum Wartebereich hinzugefügt werden muss. Der Verantwortliche für die Durchführung der großen Besprechung muss dann ständig die Wartebereichsliste überwachen und neue Benutzer im Wartebereich zur Besprechung zulassen.

        
        </div>

  - Wenn Sie die Option **Anrufer erhalten direkten Zugang** aktivieren, können Benutzer, die sich per Telefon einwählen, automatisch der Besprechung beitreten.

  - Laden Sie folgende Benutzer explizit ein:
    
      - Besprechungsorganisator und Delegat (anfordernde Person)
    
      - Die von der eine Besprechung anfordernden Person vorgelegte Liste mit Referenten
    
    <div>
    

    > [!NOTE]  
    > Wenn der Zugriffstyp der Besprechung auf <STRONG>Von mir ausgewählte Personen</STRONG> festgelegt ist, müssen Sie jeden Teilnehmer einer großen Besprechung explizit als eingeladenen Benutzer hinzufügen.

    
    </div>

  - Verwalten Sie die Referenten explizit, anstatt die Referenten-Option auf einen der Werte für automatische Hochstufung festzulegen. Stellen Sie sicher, dass folgende Benutzer als Referenten hinzugefügt werden:
    
      - Besprechungsorganisator und Delegat (anfordernde Person)
    
      - Die von eine große Besprechung anfordernden Personen vorgelegte Liste mit Referenten
    
    <div>
    

    > [!NOTE]  
    > Indem Sie die Referenten explizit verwalten, können Sie ihre Anzahl steuern und auf eine so kleine Zahl begrenzen, dass eine effektive große Besprechung möglich ist. Wenn die Mehrheit der Besprechungsteilnehmer nur eine Teilnehmerrolle hat, verringert sich die Wahrscheinlichkeit, dass Personen versehentlich die Steuerung der Präsentation übernehmen, eine PowerPoint-Präsentation löschen, Referenten stummschalten bzw. die Stummschaltung aufheben oder die Besprechung auf andere Weise stören.

    
    </div>

  - Aktivieren Sie die Option **Alle Teilnehmer stummschalten**, um sicherzustellen, dass nur Referenten Audioinhalte in die Besprechung übertragen können.

  - Aktivieren Sie die Option **Video von Teilnehmern blockieren**, um sicherzustellen, dass nur Referenten Videoinhalte in die Besprechung übertragen können.

In der folgenden Abbildung sind die empfohlenen Einstellungen für das Online-Besprechungs-Add-in für lync dargestellt.

![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")

</div>

<span> </span>

</div>

</div>

</div>

