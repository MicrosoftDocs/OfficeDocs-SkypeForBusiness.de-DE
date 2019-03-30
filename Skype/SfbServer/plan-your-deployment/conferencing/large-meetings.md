---
title: Planen von großen Besprechungen in Skype für Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 21507e18-bd79-4019-9c3a-0867fccaa3b4
description: 'Zusammenfassung: Lesen Sie dieses Thema, um Informationen zu bewährten Methoden für das Implementieren und Verwalten von großen Besprechungen in Skype für Business Server erhalten.'
ms.openlocfilehash: 4ef45f5393e389a3c6a1246041d058d1e0b387f1
ms.sourcegitcommit: 89b866a3c383555f6f89dc77bebd74cddf9e40fb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2019
ms.locfileid: "31003874"
---
# <a name="plan-for-large-meetings-in-skype-for-business-server"></a>Planen von großen Besprechungen in Skype für Business Server
 
**Zusammenfassung:** Lesen Sie in diesem Thema, um Informationen zu bewährten Methoden für das Implementieren und Verwalten von großen Besprechungen in Skype für Business Server erhalten.
  
Die Größe von Besprechungen, die unterstützt Skype für Business Server, hängt davon ab, ob Konferenzen in einem Pool gemeinsam genutzte oder dedizierte gehostet wird: an einer beliebigen Stelle aus 250 Teilnehmer in einem freigegebenen Pool 1000 Teilnehmern in einem dedizierten Pool. 
  
> [!NOTE]
> In diesem Thema konzentriert sich auf best Practices für große Besprechungen von Skype für Business Server unterstützt. Wenn Ihre Organisation größere Besprechung Funktionen erforderlich sind, sollten Sie erwägen, implementieren eine hybridumgebung, die eine neue Onlinedienst Skype Besprechung übertragen nutzt, die Teil von Office 365 ist. 

> [!NOTE]
> Skype-Livekonferenz ermöglicht Benutzern, Besprechungen von bis zu 10.000 Teilnehmern zu hosten und an ein ebenso großes Online-Publikum zu übertragen. Für die Nutzung von Skype-Livekonferenz muss Skype for Business Server bereits in einer Hybridumgebung mit einem Office 365-Produktionsmandanten konfiguriert sein. Als Grundvoraussetzung muss bei allen Benutzern ein Online-Mandant eingerichtet sein. Wenn Sie die Bereitstellung einer hybridlösung, die Skype Besprechung übertragen nutzen können, finden Sie unter interessiert sind [Was ist eine Skype Besprechung übertragen?](https://go.microsoft.com/fwlink/?LinkId=617071) und [Konfigurieren der lokalen Bereitstellung für Skype Besprechung übertragen werden](../../deploy/configure-skype-meeting-broadcast.md). 
  
Große Besprechungen weisen in der Regel folgende Merkmale auf:
  
- Das Besprechungsformat entspricht einem 1:n-Format.
    
- Ein oder wenige Benutzer fungieren als Referenten, und alle anderen Benutzer sind Teilnehmer.
    
- Die Freigabe von PowerPoint-Präsentationen stellt die Hauptaktivität hinsichtlich der Datenzusammenarbeit dar.
    
- Die Übertragung von Audiosignalen ist erforderlich, Videobilder können ebenfalls übertragen werden.
    
- Eine bestimmte Person, bei der es sich meist um den Organisator der Besprechung oder um einen Assistenten handelt, richtet die Besprechung rechtzeitig im Voraus ein.
    
- Spezielle Mitarbeiter (nicht die Referenten) führen durch die Besprechung, kümmern sich um das Herstellen von Verbindungen zu Onlinebesprechungen, stellen sicher, dass das Teilen von Audio-, Video- und Folieninhalten funktioniert, verwalten den Wartebereich und die Benutzerrollen, schalten Teilnehmer stumm bzw. heben deren Stummschaltung auf, nehmen Fragen entgegen und verwalten Aufzeichnungen nach Bedarf.
    
Wenn ein Benutzer eine Besprechung plant, erstellt Skype für Business Server einen Datensatz in der Datenbank für Konferenzen, die Konferenzdaten speichert, jedoch wird keine Hardwareressourcen für die geplante Besprechung im Voraus reserviert. Stattdessen verfügt Skype für Business Server integrierten Lastenausgleich Logik zum dynamisch Konferenzressourcen auf Front-End-Servern in einer Weise zuordnen, die Lasten gleichmäßig über alle Front-End-Servern im Pool verteilt. Dies effektiv bereitgestellt wird und Hardwareressourcen verwendet, aber es ist wichtig, dass Sie entsprechend sehr große Besprechungen unterstützen möchten. 
  
Beispielsweise einen Skype für Business Serverpool ungefähr in der oberen Kapazität ausgeführt wird, möglicherweise jedem Front-End-Server ungefähr 125 durchschnittlichen Größe Besprechungen hosten. Hinzufügen einer anderen kleine Besprechung wäre sich nicht auf ein Problem, aber eine Besprechung für 1.000 Benutzer hinzufügen wäre ein Problem, da wäre wahrscheinlich keine große Besprechung zur selben Zeit als die anderen 125 Konferenzen unterstützen die Front-End-Server.
  
Die Unterstützung großer Besprechungen mit bis zu 1.000 Teilnehmern macht es erforderlich, dass auch Probleme im Zusammenhang mit dem Hardwarefreigabemodell und dem Verzicht auf reservierte Ressourcen behandelt werden. Im Allgemeinen müssen Sie für einen dedizierten Pool planen, und befolgen bewährte Methoden, wie in den folgenden Abschnitten beschrieben. 
  
## <a name="plan-for-a-dedicated-pool"></a>Planung für einen dedizierten Pool

Wenn in Ihrem Unternehmen Besprechungen mit mehr als 250 Teilnehmer erforderlich sind, brauchen Sie einen Plan für einen dedizierten Pool, damit diese Lasten unterstützt werden können. 
  
Um ausreichende Speicherressourcen sowie die erforderliche CPU-Leistung für Besprechungen mit bis zu 1.000 Teilnehmern bereitstellen zu können, sollten auf dem Front-End-Server, der als Host fungiert, keine anderen Sofortnachrichten-, Anwesenheits- oder Enterprise-VoIP-Arbeitslasten verarbeitet werden. Auch auf das Hosten anderer Besprechungen durch die Server sollte unabhängig von ihrer Größe verzichtet werden. Um Besprechungen von bis zu hosten müssen Sie 1.000 Benutzer, eine separate Skype für Business Serverpool einrichten, der für das Hosten von großer Besprechungen vorgesehen ist.
  
Einen Skype für Business Server-Pool, der für das Hosten von großer Besprechungen vorgesehen ist, sollte eine hosten und nur eine Besprechung von bis zu 1000 Benutzern gleichzeitig, also Besprechungszeiten müssen im Voraus über einen außerhalb des Band scheduling-Prozess auf dedizierten Support zu gewährleisten reserviert werden aus der Front-End-Servern. Zur Unterstützung der mehr als eine großer Besprechung zur selben Zeit sollten Sie mehrere Pools mit dedizierten großen Besprechung einrichten.
  
Weitere Informationen zu Hardware- und softwareanforderungen und planen eine Topologie für große Besprechungen unterstützt, finden Sie unter [Hardware and Software Requirements for Conferencing in Skype für Business Server](hardware-and-software-requirements.md) und [Planen Ihrer konferenztopologie für Skype für Business Server](conferencing-topology.md).
  
## <a name="implement-best-practices-for-large-meetings"></a>Einführung von Best Practices für große Besprechungen

Nach dem Einrichten eines dedizierten Pools für große Besprechungen können Sie Schritte unternehmen, um sicherzustellen, dass die in diesem Pool gehosteten großen Besprechungen die beste Benutzererfahrung bieten. Die folgenden Abschnitte enthalten Richtlinien zum Verwalten großer Besprechungen:
  
- Anlegen von dedizierten Besprechungsorganisatoren
    
- Anlegen von dedizierten Moderatoren
    
- Pflege eines separaten Kalenders zur Verwaltung von großen Besprechungen
    
- Implementieren eines Planungsprozesses für große Besprechungen
    
- Definieren von angemessenen Planungsdetails
    
- Erstellen einer Konferenzrichtlinie für große Besprechungen
    
### <a name="create-dedicated-meeting-organizers"></a>Anlegen von dedizierten Besprechungsorganisatoren

Um die Echtzeitkommunikation Datenverkehr im Pool große Besprechung zu minimieren, ist es nicht empfehlenswert, das Hosten von Benutzern, die regelmäßig mit Skype für Business-Clients anmelden und Sofortnachrichten (IM), Anwesenheitsinformationen, Konferenzen und VoIP-Sitzungen teilnehmen. Gehen Sie stattdessen wie folgt vor:
  
- Erstellen Sie ein oder mehrere dedizierte Benutzerkonten nur für die Planung großer Besprechungen
    
- Verwalten Sie die Benutzerkonten der Mitarbeiter, die für die Planung großer Besprechungen zuständig sind, in einem großen Besprechungspool
    
### <a name="create-dedicated-moderators"></a>Anlegen von dedizierten Moderatoren

Mit mehreren Benutzern zu einer hunderttausend in einer Besprechung ist es ratsam, eine dedizierte Person Moderate der online-Sitzung einer großen Besprechung haben. Diese dedizierten Person kann einen Delegaten vom Organisator Besprechung oder ein Mitglied der Organisation Unterstützung für große Besprechungen Mitarbeiter sein. Es ist wichtig, Moderator dedizierten Besprechung als Referent an der Position, die die Besprechung geplant ist, hinzufügen, obwohl es möglich ist, einen online-Besprechungsteilnehmer zum Referenten fördern, während die Besprechung ausgeführt wird.
  
Der Moderator Besprechung kann alle Referenten Funktionen von Skype für Business-Clients verwenden, um große Besprechung verwalten. Hierzu zählen folgende Funktionen:
  
- Überwachen des Wartebereichs und Zulassen bzw. Ablehnen von Benutzern im Wartebereich
    
- Entfernen von Benutzern, die nicht an der Besprechung teilnehmen sollten
    
- Ändern der Besprechungszugriffstypen
    
- Ändern der Teilnehmerrollen
    
- Einladen zusätzlicher Teilnehmer während der Besprechung mithilfe von Drag & drop-Funktionalität, Telefonanruf oder e-Mail
    
- Stummschalten und Aufheben der Stummschaltung für die Zielgruppe oder für einzelne Benutzer
    
- Verwalten der Besprechungsinhalte, einschließlich Hochladen von Inhalten, Löschen von Inhalten und Auswählen der aktiven Inhalte

    
### <a name="maintain-a-separate-calendar"></a>Pflege eines separaten Kalenders

Für jeden Pool für große Besprechungen sollte ein eigener Kalender verwaltet werden, in dem die großen Besprechungen verzeichnet sind, die in diesem Pool geplant sind. Beispielsweise können Sie ein einzelnes Benutzerkonto auf der großen besprechungspool (privat) und Verwenden von Outlook mit Exchange und Onlinebesprechungs-Add-in für Skype für Unternehmen zum Verwalten eines separaten Kalenders. Wenn Sie mehrere Benutzerkonten verwenden, um Supportmitarbeitern das Erstellen großer Besprechungen zu ermöglichen, können Sie einen separaten Kalender einrichten, in dem alle großen Besprechungen festgehalten werden, die von Supportmitarbeitern erstellt werden. 
  
Durch das Verwalten eines separaten Kalenders für Besprechungen vermeiden Sie Konflikte und stellen sicher, dass zu einem bestimmten Zeitpunkt immer jeweils nur eine große Besprechung stattfinden kann.
  
### <a name="implement-a-scheduling-process"></a>Implementieren eines Planungsprozesses

Da nur eine große Besprechung zu einem Zeitpunkt im Pool dedizierten großen Besprechung unterstützt wird, sollten Sie eine große Besprechung scheduling-Prozess zum Einrichten von großen Besprechungen zu vereinfachen und verhindern von Konflikten implementieren. Diese Funktion wird nicht direkt von Skype für Business Server oder Skype für Business-Clients bereitgestellt. Eine Möglichkeit, einen solchen Prozess implementieren ist die Verwendung des Supportteam Ihrer Organisation zur System, falls verfügbar.
  
Die Planung einer großen Besprechung umfasst die folgenden Schritte:
  
- Der Besprechungsorganisator oder die delegierte Person bestimmt den Zeitpunkt, die Dauer und den Umfang einer anstehenden Besprechung sowie die Liste der Referenten. Falls der erwartete Besprechungsumfang 250 Benutzer überschreitet, oder um die optimale Funktionalität für eine Besprechung mit weniger als 250 Benutzern sicherzustellen, reicht der Organisator oder die delegierte Person einen Antrag für eine große Besprechung ein.
    
- Die Planungsmitarbeiter überprüfen, ob der angeforderte Termin verfügbar ist. Da jeweils immer nur eine einzige große Besprechung im Pool unterstützt wird, müssen die Planungsmitarbeiter anhand des Kalenders für große Besprechungen feststellen, ob für den angeforderten Termin bereits eine andere Besprechung geplant ist. Falls der angeforderte Termin verfügbar ist, wird die Besprechungsanfrage genehmigt.
    
- Wenn die Anforderung genehmigt wird, verwendet zum Einrichten einer Besprechung auf den dedizierten großen besprechungspool scheduling Mitarbeiter (Anmeldeinformationen auf dem dedizierten Pool) Onlinebesprechungs-Add-in für Skype für Unternehmen mit Outlook. Die URL für die Teilnahme an der Besprechung wird dem Antragsteller im Rahmen des Genehmigungshinweises bereitgestellt.
    
- Der Besprechungsorganisator oder die delegierte Person plant mithilfe von Outlook die anstehende Besprechung und fügt die URL für die Teilnahme an der Besprechung der Besprechungseinladung hinzu. Der Besprechungsorganisator oder die delegierte Person legt dann die Benutzer fest, die eingeladen werden sollen, und versendet die Besprechungseinladung.
    
### <a name="specify-appropriate-scheduling-details"></a>Definieren von angemessenen Planungsdetails

Nachdem sichergestellt wurde, dass zum angefragten Zeitpunkt keine weitere Besprechung anberaumt ist, planen die zuständigen Supportmitarbeiter die Besprechung im Pool für große Besprechungen ein. 
  
Um die beste benutzerumgebung zu gewährleisten, ist es wichtig, Planen Sie die große Besprechung mit den richtigen Zugriffsebenen und besprechungseinstellungen, die der Besprechungsorganisator Anforderungen geeignet sind. Berücksichtigen Sie die folgenden scheduling Einstellungen in Skype für Business Besprechungsoptionen konfiguriert:
  
- Verwenden Sie einen neuen Besprechungsraum für jede große Besprechung, anstatt den dedizierten Besprechungsraum erneut zu verwenden. 
    
- Geben Sie die Zugriffsebene für die Besprechung wie folgt an:
    
  - Wenn mindestens ein eingeladener Benutzer nicht zur Organisation gehört, legen Sie den Zugriffstyp für die Besprechung auf **Alle Personen (keine Einschränkungen)** fest. Dadurch vermeiden Sie, dass Sie während der laufenden Besprechung einen möglicherweise großen Wartebereich verwalten müssen.
    
  - Wenn die Besprechung nur intern ist, legen Sie den Zugriffstyp für die Besprechung auf **Jeder innerhalb meiner Organisation** fest.
    
    > [!NOTE]
    > Vermeiden Sie die Besprechung festlegen Zugriffstyp an **Personen, die ich in meinem Unternehmen einladen** , da Wenn Sie diese Einstellung verwenden, Organisatoren müssen alle Benutzer e-Mail-Adressen der Liste eingeladenen Benutzer hinzufügen, und Sie keine Verteilergruppe einladen. Vermeiden Sie die Einstellung die Besprechung Zugriffstyp **Privat** , Organisator der Besprechung, da diese Einstellung erfordert, dass jeder Besprechungsteilnehmer, einschließlich des Referenten, in den Wartebereich für eine Besprechung zur Laufzeit eingefügt werden muss. Verantwortlichen für die Ausführung der großen Besprechung muss dann ständig der Lobby Teilnehmerliste einer überwachen und neue Benutzer, die in der Lobby sind zulassen.
  
- Wenn Sie die Option **Anrufer erhalten direkten Zugang** aktivieren, können Benutzer, die sich per Telefon einwählen, automatisch der Besprechung beitreten.
    
- Laden Sie folgende Benutzer explizit ein:
    
  - Besprechungsorganisator und Delegat (anfordernde Person)
    
  - Die von der eine Besprechung anfordernden Person vorgelegte Liste mit Referenten
    
    > [!NOTE]
    > Wenn der Zugriffstyp der Besprechung auf **Von mir ausgewählte Personen** festgelegt ist, müssen Sie jeden Teilnehmer einer großen Besprechung explizit als eingeladenen Benutzer hinzufügen. 
  
- Verwalten Sie die Referenten explizit, anstatt die Referenten-Option auf einen der Werte für automatische Hochstufung festzulegen. Stellen Sie sicher, dass folgende Benutzer als Referenten hinzugefügt werden:
    
  - Besprechungsorganisator und Delegat (anfordernde Person)
    
  - Die von eine große Besprechung anfordernden Personen vorgelegte Liste mit Referenten
    
    Indem Sie die Referenten explizit verwalten, können Sie ihre Anzahl steuern und so weit begrenzen, dass eine effektive große Besprechung möglich ist. Wenn die Mehrheit der Besprechungsteilnehmer nur eine Teilnehmerrolle hat, verringert sich die Wahrscheinlichkeit, dass Personen versehentlich die Steuerung der Präsentation übernehmen, eine PowerPoint-Präsentation löschen, Referenten stummschalten bzw. die Stummschaltung aufheben oder die Besprechung auf andere Weise stören. 
    
- Aktivieren Sie die Option **Alle Teilnehmer stummschalten**, um sicherzustellen, dass nur Referenten Audioinhalte in die Besprechung übertragen können.
    
- Überprüfen Sie das **Video von Teilnehmern blockieren** festlegen, um sicherzustellen, dass nur Referenten Video in der Besprechung übertragen können.
    
### <a name="create-a-conferencing-policy"></a>Erstellen einer Konferenzrichtlinie

Erstellen Sie eine neue Konferenzrichtlinie speziell für große Besprechungen und weisen Sie sie anschließend den Benutzern zu, die auf den dedizierten großen Besprechungspools gehostet werden. Mithilfe der folgenden Einstellungen können Sie die Konferenzrichtlinie konfigurieren:
  
- Legen Sie die Option **MaxMeetingSize** auf 1000 ein. (Der Standardwert ist 250.)
    
- Legen Sie die Option **AllowLargeMeetings** auf **True** fest. 
    
- Legen Sie die Option **EnableAppDesktopSharing** auf **None** fest.
    
- Legen Sie die Option **AllowUserToScheduleMeetingsWithAppSharing** auf **False** fest.
    
- Legen Sie die Option **AllowSharedNotes** auf **False** fest.
    
- Legen Sie die Option **AllowAnnotations** auf **False** fest.
    
- Legen Sie die Option **DisablePowerPointAnnotations** auf **True** fest.
    
- Legen Sie die Option **AllowMultiview** auf **False** fest.
    
- Legen Sie die Option **EnableMultiviewJoin** auf **False** fest.
    
> [!NOTE]
> Unterstützung für große Besprechungen in Skype for Business Server erfordert, dass die Einstellung **AllowLargeMeetings** auf true festgelegt. Wenn diese Einstellung auf true festgelegt ist, der Skype Business wünschen festgelegt ist wird von sehr großen Besprechungen optimiert werden, wenn Benutzer an der Besprechung teilzunehmen. Insbesondere wird Skype für Unternehmen in eine große Besprechung, nicht angezeigt, die Initial oder Aktualisierung der der vollständige Besprechung Teilnehmerliste, die einen Leistungsengpass für den Client und Skype für Business Server ist. Skype für Unternehmen werden stattdessen nur Informationen zu den Benutzer und die Liste mit Referenten der Besprechung angezeigt. Skype für Unternehmen wird weiterhin die Gesamtzahl der Teilnehmer in großen Besprechungen verfügbar angezeigt.

Die Einstellung - AllowLargeMeetings $true bewirkt, dass die folgenden: · Blendet aus der Teilnehmerliste der Teilnehmer einer. · Fehler in das Sofortnachrichtenfenster deaktiviert.
· Video mit mehreren Teilnehmern deaktiviert.
· Deaktiviert die Möglichkeit, einen Teilnehmer zum Referenten zu fördern. Sie müssen im Voraus planen und alle Referenten vor der Besprechung zu deklarieren.
· Deaktiviert die Möglichkeit, einzelne Teilnehmer stummschaltung aufheben.
· Deaktiviert die Möglichkeit, das Feature Sperre Video Spotlight auf Teilnehmer anzuwenden.
· Öffentliche TELEFONE einwählen und Benutzer können sich über die stummschaltung aufheben keine * 6, da Befehle persönlichen virtuellen Unterstützung verantwortlich für DTMF aktiven große Besprechungen ist nicht vorhanden.
· Wenn der Referent/Organisator eine Besprechung plant, in dem jeder zuerst stummgeschaltet werden soll ("Stummschalten alle"), PSTN-Benutzer wird in der gesamten den Anruf stumm geschaltet werden und werden nicht stummschaltung nicht selbst aufheben.

Mit Ausnahme der Einstellung **Maximale Besprechungsgröße** sind alle anderen hier angegeben Konferenzrichtlinieneinstellungen erforderlich, um die Konferenzfunktionen, die für große Besprechungen nicht erforderlich sind, zu deaktivieren.
  
Darüber hinaus müssen Sie den dedizierten großen besprechungspool konfigurieren, sodass jede Skype für Business Server-Benutzer, der im Pool verwalteten und für die Verwaltung des Zeitplans für die Besprechung verantwortlich ist die entsprechenden Berechtigungen verfügt. Gehen Sie hierzu wie folgt vor:
  
- Legen Sie die Option **Als Referenten festlegen** auf **Keine** fest. Normalerweise sind nur einige wenige Benutzer der gesamten Teilnehmer einer großen Besprechung Referenten, sodass die Teilnehmer nicht automatisch als Referenten für große Besprechungen zugelassen werden sollten. Die Referenten sollten stattdessen bei der geplanten Besprechung explizit festgelegt oder während der großen Besprechung explizit ernannt werden.
    
- Stellen Sie sicher, dass das Kontrollkästchen **Konferenztyp standardmäßig zugewiesen** nicht ausgewählt ist. Dieser Einstellung wird gesteuert, ob das Onlinebesprechungs-Add-in für Skype für Unternehmen immer Konferenzen mit der Organisator plant Konferenz zugewiesen, haben, d. h., die geplante Besprechungen, die dieselbe Join-URL und Zugriffsinformationen enthalten. In Szenarien für die Zusammenarbeit kleine Gruppe zugewiesen müssen wie Konferenz Typ Works gut, da jeder die eigene Person Konferenz zugewiesen hat, und die Konstante Join-URL und die Audioinformationen trägt dazu bei, um schneller Besprechung beitreten zu vereinfachen. Jedoch im Szenario mit große Besprechung, die Unterstützung für große Besprechungen Mitarbeiter plant, die mit einem einzigen Satz von Anmeldeinformationen des Benutzers großen Besprechungen, und anschließend fügen Sie URLs und Audioinformationen der Besprechung anfordernden Personen. In diesem Fall funktioniert mit einer anderen URL zur Teilnahme an jede Besprechung besser.
    
- Stellen Sie sicher, dass das Kontrollkästchen **Anonyme Benutzer standardmäßig zulassen** nur aktiviert wird, wenn es erforderlich ist. Diese Einstellung wirkt sich auf die Standardeinstellungen für den Zugriffstyp durch das Onlinebesprechungs-Add-in für Skype für Unternehmen geplant wird, wenn Sie keine zugewiesene Konferenz verwenden. Die geeignete Option für diese Einstellung hängt von der Anforderungen Ihrer Organisation ab. Wenn die meisten großen Besprechungen in Ihrer Organisation interne Besprechungen sind, sollte diese Option nicht ausgewählt werden. Wenn beim Großteil der großen Besprechungen externe Benutzer teilnehmen, sollte diese Option ausgewählt werden.
    
Weitere Informationen zum Erstellen einer konferenzrichtlinie finden Sie unter [Manage Conferencing Policies in Skype für Business Server](../../manage/conferencing/conferencing-policies.md).
  

