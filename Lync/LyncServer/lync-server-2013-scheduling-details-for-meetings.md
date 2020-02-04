---
title: 'Lync Server 2013: Planen von Details für Besprechungen'
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
ms.openlocfilehash: a4a0f85e93588e725e825fee22a8c2e95b74095b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scheduling-details-for-meetings-in-lync-server-2013"></a>Planen von Details für Besprechungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-04_

Nachdem sichergestellt wurde, dass zum angefragten Zeitpunkt keine weitere Besprechung anberaumt ist, planen die zuständigen Supportmitarbeiter die Besprechung im Pool für große Besprechungen ein. Verwenden Sie das Online Besprechungs-Add-in für lync, das mit dem lync Server 2013-Client installiert ist, um diese Aufgabe mithilfe der Anmeldeinformationen eines für lync Server aktivierten Benutzers im dedizierten groß Besprechungs Pool auszuführen.

Um die bestmögliche Benutzerfreundlichkeit zu erzielen, ist es wichtig, die große Besprechung mit den richtigen Zugriffsebenen und Besprechungseinstellungen zu planen, die den Bedürfnissen des Besprechungsorganisators entsprechen. Wir empfehlen die folgenden Planungseinstellungen, die in den lync-Besprechungsoptionen konfiguriert sind:

  - Verwenden Sie einen neuen Besprechungsraum für jede große Besprechung, anstatt den dedizierten Besprechungsraum erneut zu verwenden.

  - Geben Sie die Zugriffsebene für die Besprechung wie folgt an:
    
      - Wenn mindestens eine Einladung außerhalb der Organisation ist, setzen Sie den Besprechungs Zugriffstyp auf " **jeder" (keine Einschränkungen**. Dadurch vermeiden Sie, dass Sie während der laufenden Besprechung einen möglicherweise großen Wartebereich verwalten müssen.
    
      - Wenn die Besprechung nur intern ist, legen Sie den Zugriffstyp für die Besprechung auf **Jeder innerhalb meiner Organisation** fest.
        
        <div>
        

        > [!NOTE]  
        > Vermeiden Sie die Festlegung des Besprechungszugriffs Typs für Personen, die <STRONG>ich aus meinem Unternehmen einlade</STRONG> , denn wenn Sie diese Einstellung verwenden, müssen Organisatoren alle Benutzer-e-Mail-Adressen zur Liste der eingeladenen hinzufügen, und Sie können keine Verteilergruppe einladen.<BR>Vermeiden Sie es, den Besprechungs Zugriffstyp <STRONG>nur auf ich, den Organisator der Besprechung</STRONG> , festzulegen, da für diese Einstellung erforderlich ist, dass jeder Besprechungsteilnehmer, einschließlich Referenten, zur Besprechungs Laufzeit in die Lobby gestellt wird. Die Person, die für die Ausführung der umfangreichen Besprechung verantwortlich ist, muss die Lobby Liste ständig überwachen und neue Benutzer in der Lobby aufnehmen.

        
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
    > Indem Sie Referenten explizit verwalten, können Sie die Anzahl der Referenten steuern, sodass Sie die Referenten auf eine klein genug Zahl begrenzen können, um eine effektive große Besprechung zu ermöglichen. Wenn die Mehrheit der Besprechungsteilnehmer über die Rolle "Teilnehmer" verfügt, kann dadurch die Wahrscheinlichkeit verringert werden, dass Personen versehentlich die Steuerung der Präsentation übernehmen, eine PowerPoint-Präsentation löschen, Referenten stumm schalten/stumm schalten und andere Unterbrechungen der Besprechung durchführen.

    
    </div>

  - Aktivieren Sie die Option **Alle Teilnehmer stummschalten**, um sicherzustellen, dass nur Referenten Audioinhalte in die Besprechung übertragen können.

  - Aktivieren Sie die Option **Video von Teilnehmern blockieren**, um sicherzustellen, dass nur Referenten Videoinhalte in die Besprechung übertragen können.

Die folgende Abbildung zeigt die empfohlenen Einstellungen für das Online Besprechungs-Add-in für lync.

![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")

</div>

<span> </span>

</div>

</div>

</div>

