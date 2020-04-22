---
title: Planen großer Besprechungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 21507e18-bd79-4019-9c3a-0867fccaa3b4
description: 'Zusammenfassung: in diesem Thema finden Sie Informationen zu bewährten Methoden für die Implementierung und Verwaltung von großen Besprechungen in Skype for Business Server.'
ms.openlocfilehash: 18b0f036e49996564aa68735300f4e677ce5b1cb
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780234"
---
# <a name="plan-for-large-meetings-in-skype-for-business-server"></a>Planen großer Besprechungen in Skype for Business Server
 
**Zusammenfassung:** In diesem Thema erfahren Sie mehr über bewährte Methoden für die Implementierung und Verwaltung von großen Besprechungen in Skype for Business Server.
  
Die Größe der Besprechungen, die Skype for Business Server unterstützenkann, hängt davon ab, ob Konferenzen in einem freigegebenen oder dedizierten Pool gehostet werden: von 250 Teilnehmern in einem gemeinsamen Pool bis zu 1000 Teilnehmern in einem dedizierten Pool. 
  
> [!NOTE]
> In diesem Thema werden die bewährten Methoden für umfangreiche Besprechungen behandelt, die von Skype for Business Server unterstützt werden. Wenn Ihre Organisation größere Besprechungsfunktionen erfordert, sollten Sie die Implementierung einer Hybridumgebung in Betracht ziehen, die Skype-Live Konferenz, einen neuen Onlinedienst, der Teil Office 365 ist, nutzt. 

> [!NOTE]
> Skype-Live Konferenz ermöglicht Benutzern das Hosten und übertragen von Besprechungen mit großen Online-Zielgruppen von bis zu 10.000 Teilnehmern. Die Verwendung von Skype-Live Konferenz erfordert, dass Skype for Business Server bereits in einem Hybrid-Setup mit einer Produktions Office 365 Organisation konfiguriert werden. Für alle Benutzer muss ein Online Mandant als Voraussetzung eingerichtet sein. Wenn Sie an der Bereitstellung einer Hybridlösung interessiert sind, die die Vorteile von Skype-Live Konferenz nutzen kann, lesen Sie [Was ist eine Skype-Live Konferenz?](https://go.microsoft.com/fwlink/?LinkId=617071) und [Konfigurieren Sie Ihre lokale Bereitstellung für Skype](../../deploy/configure-skype-meeting-broadcast.md)-Live Konferenz. 
  
Große Besprechungen weisen normalerweise die folgenden Merkmale auf:
  
- Das Besprechungs Format ist eine 1: n-Präsentation.
    
- Ein oder mehrere Benutzer sind Referenten, und alle anderen Personen sind nur als Teilnehmer beteiligt.
    
- PowerPoint-Präsentations Freigabe ist die Hauptaktivität der Datenzusammenarbeit.
    
- Audio ist erforderlich, und Video kann auch verwendet werden.
    
- Eine dedizierte Person, in der Regel der Besprechungsorganisator oder ein Assistent des Organisators, richtet die Besprechung weitgehend im Voraus ein.
    
- Dedizierte Mitarbeiter (nicht die Referenten) führen die Besprechung aus, einschließlich der Verbindung mit einer Onlinebesprechung, der Überprüfung, ob Audio-, Video-und Folien Freigaben ausgeführt werden, die Verwaltung von Lobby-und Benutzerrollen, das stumm schalten und das stumm schalten von Teilnehmern, das nehmen von Fragen und das Verwalten von Aufzeichnungen, je nach Bedarf.
    
Wenn ein Benutzer eine Besprechung plant, erstellt Skype for Business Server einen Datensatz in der Konferenzdatenbank, in dem Konferenzdaten gespeichert werden, reserviert jedoch keine Hardwareressourcen für die geplante Besprechung im voraus. Stattdessen verfügt Skype for Business Server über integrierte Lastenausgleichs Logik zum dynamischen Zuordnen von Konferenzressourcen auf Front-End-Servern auf eine Weise, die Lasten gleichmäßig auf alle Front-End-Server im Pool verteilt. Dadurch werden Hardwareressourcen effektiv bereitgestellt und verwendet, aber es ist wichtig, dass Sie die Unterstützung sehr großer Besprechungen entsprechend planen. 
  
Wenn beispielsweise ein Skype for Business Server-Pool knapp an seiner Spitzenkapazität liegt, kann jeder Front-End-Server ungefähr 125 Besprechungen mit durchschnittlicher Größe hosten. Das Hinzufügen einer weiteren kleinen Besprechung wäre kein Problem, aber das Hinzufügen einer Besprechung für 1000 Benutzer würde ein Problem sein, da die Front-End-Server eine solche große Besprechung möglicherweise nicht gleichzeitig mit den anderen 125-Besprechungen unterstützen können.
  
Die Unterstützung großer Besprechungen mit bis zu 1000 Teilnehmern erfordert die Behebung der Probleme im Zusammenhang mit dem freigegebenen Hardwaremodell und dem nicht Reservierungs Modell. Im Allgemeinen müssen Sie einen dedizierten Pool planen und bewährte Methoden wie in den folgenden Abschnitten beschrieben befolgen. 
  
## <a name="plan-for-a-dedicated-pool"></a>Planen eines dedizierten Pools

Wenn Ihre Organisation Besprechungen mit mehr als 250 Teilnehmern erfordert, müssen Sie einen dedizierten Pool zur Unterstützung der Last planen. 
  
Um über ausreichende CPU-und Arbeitsspeicherressourcen für Besprechungen mit bis zu 1000 Benutzern verfügen zu können, sollten die hostenden Front-End-Server keine anderen Chatnachrichten und Anwesenheits-oder Enterprise-VoIP-Arbeitslasten hosten. Die Server sollten auch keine anderen Besprechungen hosten, unabhängig von der Größe der anderen Besprechungen. Um Besprechungen mit bis zu 1000 Benutzern zu hosten, müssen Sie einen separaten Skype for Business Server Pool einrichten, der für das Hosten großer Besprechungen dediziert ist.
  
Ein Skype for Business Server Pool, der für das Hosten großer Besprechungen vorgesehen ist, sollte nur eine Besprechung mit bis zu 1000 Benutzern gleichzeitig hosten, sodass Besprechungszeiten vorab über einen Out-of-Band-Planungsprozess reserviert werden müssen, um den dedizierten Support von den Front-End-Servern sicherzustellen. Um mehr als eine große Besprechung gleichzeitig zu unterstützen, sollten Sie mehrere dedizierte große Besprechungs Pools einrichten.
  
Weitere Informationen zu Hardware-und Softwareanforderungen sowie zur Planung einer Topologie, die große Besprechungen unterstützt, finden Sie unter [Hardware-und Softwareanforderungen für Konferenzen in Skype for Business Server](hardware-and-software-requirements.md) und [Planen Ihrer Konferenz Topologie für Skype for Business Server](conferencing-topology.md).
  
## <a name="implement-best-practices-for-large-meetings"></a>Implementieren bewährter Methoden für große Besprechungen

Nachdem Sie einen dedizierten Pool für große Besprechungen eingerichtet haben, können Sie Schritte Unternehmen, um sicherzustellen, dass große Besprechungen, die im Pool gehostet werden, die beste Benutzerfreundlichkeit bieten. Die folgenden Abschnitte enthalten Richtlinien für die Verwaltung großer Besprechungen:
  
- Erstellen dedizierter Besprechungsorganisatoren
    
- Erstellen dedizierter Moderatoren
    
- Verwalten eines separaten Kalenders für große Besprechungen
    
- Implementieren eines Planungsprozesses für große Besprechungen
    
- Angeben der entsprechenden Planungsdetails
    
- Erstellen einer konferenzrichtlinie für große Besprechungen
    
### <a name="create-dedicated-meeting-organizers"></a>Erstellen dedizierter Besprechungsorganisatoren

Um den Echt Zeit Kommunikations Datenverkehr im großen Besprechungs Pool zu minimieren, empfiehlt Microsoft nicht das Hosten von Benutzern, die sich regelmäßig mit Skype for Business-Clients anmelden und an Chat-, Anwesenheits-, Konferenz-und sprach Sitzungen teilnehmen. Führen Sie stattdessen einen der folgenden Schritte aus:
  
- Erstellen eines oder mehrerer dedizierter Benutzerkonten nur für die Planung großer Besprechungen
    
- Home die Benutzerkonten der Mitarbeiter, die für die Planung großer Besprechungen in einem großen Besprechungs Pool zuständig sind
    
### <a name="create-dedicated-moderators"></a>Erstellen dedizierter Moderatoren

Bei mehreren hundert bis tausend Benutzern in einer Besprechung empfiehlt es sich, dass eine dedizierte Person die Onlinesitzung einer großen Besprechung moderiert. Diese dedizierte Person kann eine Stellvertretung des Besprechungsorganisators oder ein Mitglied des Teams für die Großkunden Unterstützung für Besprechungen sein. Es ist wichtig, dass der dedizierte Besprechungs Moderator zum Zeitpunkt der geplanten Besprechung als Referent hinzugefügt wird, obwohl es möglich ist, einen Online-Besprechungsteilnehmer zur Referenten Rolle zu fördern, während die Besprechung ausgeführt wird.
  
Der Besprechungs Moderator kann alle Referenten Funktionen Skype for Business Clients zum Verwalten der großen Besprechung verwenden. Diese Funktionen umfassen Folgendes:
  
- Überwachen der Lobby und zulassen oder ablehnen von Benutzern in der Lobby
    
- Entfernen von Benutzern aus der Besprechung, die nicht in der Besprechung sein sollten
    
- Ändern von Besprechungszugriffs Typen
    
- Ändern von Teilnehmerrollen
    
- Einladen zusätzlicher Teilnehmer während der Besprechung per Drag & Drop-Funktion, Telefonanruf oder e-Mail
    
- Stumm schalten und stumm schalten der Zielgruppe oder einzelner Benutzer
    
- Verwalten von Besprechungsinhalten, einschließlich Hochladen von Inhalten, Löschen von Inhalten und wechseln von aktivem Inhalt

    
### <a name="maintain-a-separate-calendar"></a>Verwalten eines separaten Kalenders

Für jeden großen Besprechungs Pool sollten Sie einen separaten Kalender mit großen Besprechungen aufrecht erhalten, die in diesem Pool geplant sind. Sie können beispielsweise ein einzelnes Benutzerkonto im großen Besprechungs Pool verwenden und Outlook mit Exchange und Online-Besprechungs-Add-in verwenden, um Skype for Business einen separaten Kalender zu verwalten. Wenn Sie mehrere Benutzerkonten verwenden, um Supportmitarbeitern das Erstellen großer Besprechungen zu ermöglichen, können Sie einen separaten Kalender einrichten, in dem alle großen Besprechungen festgehalten werden, die von Supportmitarbeitern erstellt werden. 
  
Durch das Verwalten eines separaten Kalenders für Besprechungen vermeiden Sie Konflikte und stellen sicher, dass zu einem bestimmten Zeitpunkt immer jeweils nur eine große Besprechung stattfinden kann.
  
### <a name="implement-a-scheduling-process"></a>Implementieren eines Planungsprozesses

Da nur eine große Besprechung gleichzeitig im dedizierten großen Besprechungs Pool unterstützt wird, sollten Sie einen umfangreichen Besprechungs Planungsprozess implementieren, um das Einrichten großer Besprechungen zu vereinfachen und Konflikte zu verhindern. Diese Funktion wird nicht direkt von Skype for Business Server-oder Skype for Business-Clients bereitgestellt. Eine Möglichkeit zum Implementieren eines solchen Prozesses besteht darin, das Ticket System des Support Teams Ihres Unternehmens zu verwenden, sofern verfügbar.
  
Zum Planen einer großen Besprechung müssen Sie die folgenden Schritte ausführen:
  
- Der Besprechungsorganisator oder die Stellvertretung bestimmt neben der Liste der Referenten die Zeit, die Dauer und die Größe einer bevorstehenden Besprechung. Wenn die erwartete Besprechungsgröße 250 Benutzer überschreitet oder die beste Benutzerfreundlichkeit für eine Besprechung mit weniger als 250 Benutzern sichergestellt wird, sendet der Organisator oder der Stellvertreter eine Anforderung für eine große Besprechung.
    
- Die Mitarbeiter der Zeitplanung prüfen, ob das angeforderte Datum und die angeforderte Uhrzeit verfügbar sind. Da wir nur eine einzelne große Besprechung im dedizierten Pool gleichzeitig unterstützen, muss das Planungs Personal den großen Besprechungs Kalender überprüfen, um zu bestimmen, ob eine andere Besprechung für das angeforderte Datum und die angeforderte Uhrzeit geplant ist. Wenn die angeforderte Zeit zur Verfügung steht, genehmigt das Personal die Besprechungsanfrage.
    
- Wenn die Anforderung genehmigt wird, verwendet das Planungs Personal (mithilfe von Anmeldeinformationen im dedizierten Pool) das Online Besprechungs-Add-in für Skype for Business mit Outlook, um eine Besprechung im dedizierten großen Besprechungs Pool einzurichten. Die URL, die für die Teilnahme an der Besprechung verwendet werden soll, wird dem anfordernden im Rahmen der Genehmigungsbenachrichtigung zur Verfügung gestellt.
    
- Der Besprechungsorganisator oder die Stellvertretung verwendet Outlook, um die bevorstehende Besprechung zu planen, wobei die URL für die Teilnahme an der Besprechung der Besprechungseinladung hinzugefügt wird. Der Besprechungsorganisator oder die Stellvertretung gibt dann die Benutzer an, die eingeladen werden sollen, und sendet die Besprechungseinladung aus.
    
### <a name="specify-appropriate-scheduling-details"></a>Angeben der entsprechenden Planungsdetails

Nachdem Sie überprüft haben, um sicherzustellen, dass keine andere Besprechung zum gewünschten Zeitpunkt geplant ist, plant der große Besprechungs Mitarbeiter, der die Anforderung verarbeitet, die Besprechung im großen Besprechungs Pool. 
  
Um eine optimale Benutzerfreundlichkeit sicherzustellen, ist es wichtig, die große Besprechung mit den richtigen Zugriffsebenen und Besprechungseinstellungen zu planen, die den Anforderungen des Besprechungsorganisators entsprechen. Die folgenden Planungseinstellungen sollten in Skype for Business-Besprechungsoptionen konfiguriert werden:
  
- Verwenden Sie einen neuen Besprechungsraum für jede große Besprechung, anstatt den dedizierten Besprechungsraum erneut zu verwenden. 
    
- Geben Sie die Zugriffsebene für die Besprechung wie folgt an:
    
  - Wenn sich mindestens eine Einladung außerhalb der Organisation befindet, legen Sie den Besprechungs Zugriffstyp auf " **anyone" (keine Einschränkungen)** fest. Dadurch vermeiden Sie, dass sie während der laufenden Besprechung einen möglicherweise großen Wartebereich verwalten müssen.
    
  - Wenn die Besprechung nur intern ist, legen Sie den Zugriffstyp für die Besprechung auf **Jeder innerhalb meiner Organisation** fest.
    
    > [!NOTE]
    > Vermeiden Sie es, den Zugriffstyp für die Besprechung auf **Von mir eingeladene Personen in meinem Unternehmen** festzulegen. Wenn Sie diese Einstellung verwenden, müssen Besprechungsorganisatoren die E-Mail-Adressen aller Benutzer zur Eingeladenenliste hinzufügen, und Sie können keine Verteilergruppe einladen. Vermeiden Sie es, den Zugriffstyp für die Besprechung auf **Nur ich, der Besprechungsorganisator** festzulegen, da diese Einstellung erfordert, dass jeder Besprechungsteilnehmer, auch die Referenten, zur Laufzeit der Besprechung zum Wartebereich hinzugefügt werden muss. Der Verantwortliche für die Durchführung der großen Besprechung muss dann ständig die Wartebereichsliste überwachen und neue Benutzer im Wartebereich zur Besprechung zulassen.
  
- Wenn Sie die Option **Anrufer erhalten direkten Zugang** aktivieren, können Benutzer, die sich per Telefon einwählen, automatisch der Besprechung beitreten.
    
- Laden Sie folgende Benutzer explizit ein:
    
  - Besprechungsorganisator und Delegat (anfordernde Person)
    
  - Die von der eine Besprechung anfordernden Person vorgelegte Liste mit Referenten
    
    > [!NOTE]
    > Wenn der Zugriffstyp der Besprechung auf **Von mir ausgewählte Personen** festgelegt ist, müssen Sie jeden Teilnehmer einer großen Besprechung explizit als eingeladenen Benutzer hinzufügen. 
  
- Verwalten Sie die Referenten explizit, anstatt die Referenten-Option auf einen der Werte für automatische Hochstufung festzulegen. Stellen Sie sicher, dass folgende Benutzer als Referenten hinzugefügt werden:
    
  - Besprechungsorganisator und Delegat (anfordernde Person)
    
  - Die von eine große Besprechung anfordernden Personen vorgelegte Liste mit Referenten
    
    Durch die explizite Verwaltung von Referenten können Sie Moderatoren auf eine klein genug Zahl beschränken, um eine effektive große Besprechung zu ermöglichen. Wenn die Mehrheit der Besprechungsteilnehmer über die Rolle "Teilnehmer" verfügt, kann dies dazu führen, dass Personen versehentlich die Steuerung der Präsentation übernehmen, eine PowerPoint-Präsentation löschen, Referenten stumm schalten/stumm schalten und andere Unterbrechungen der Besprechung auftreten. 
    
- Aktivieren Sie die Option **Alle Teilnehmer stummschalten**, um sicherzustellen, dass nur Referenten Audioinhalte in die Besprechung übertragen können.
    
- Überprüfen Sie die Videoeinstellung für die **Teilnehmer blockieren** , um sicherzustellen, dass nur Referenten Video in die Besprechung übertragen können.
    
### <a name="create-a-conferencing-policy"></a>Erstellen einer konferenzrichtlinie

Erstellen Sie eine neue konferenzrichtlinie speziell für große Besprechungen, und weisen Sie die konferenzrichtlinie den Benutzern zu, die im dedizierten großen Besprechungs Pool verwaltet werden. Mithilfe der folgenden Einstellungen können Sie die Konferenzrichtlinie konfigurieren:
  
- Legen Sie die **MaxMeetingSize** -Option auf 1000 fest. (Der Standardwert ist 250.)
    
- Legen Sie die Option **AllowLargeMeetings** auf **True** fest. 
    
- Legen Sie die Option **EnableAppDesktopSharing** auf **Keine** fest.
    
- Legen Sie die Option **AllowUserToScheduleMeetingsWithAppSharing** auf **False** fest.
    
- Legen Sie die Option **AllowSharedNotes** auf **False** fest.
    
- Legen Sie die Option **AllowAnnotations** auf **False** fest.
    
- Legen Sie die Option **DisablePowerPointAnnotations** auf **True** fest.
    
- Legen Sie die Option **AllowMultiview** auf **False** fest.
    
- Legen Sie die Option **EnableMultiviewJoin** auf **False** fest.
    
> [!NOTE]
> Unterstützung für große Besprechungen in Skype for Business Server erfordert, dass die **AllowLargeMeetings** -Einstellung auf true festgelegt ist. Wenn diese Einstellung auf "true" festgelegt ist, wird die Skype for Business Erfahrung für extra große Besprechungen optimiert, wenn Benutzer an der Besprechung teilnehmen. Insbesondere wird in einer großen Besprechung Skype for Business nicht das erste oder das Update der vollständigen Besprechungsteilnehmer Liste angezeigt, ein Leistungsengpass sowohl für den Client als auch für Skype for Business Server. Stattdessen werden in Skype for Business nur Informationen über den Benutzer und die Liste der Referenten der Besprechung angezeigt. In Skype for Business wird weiterhin die Gesamtzahl der Teilnehmer angezeigt, die in den großen Besprechungen verfügbar sind.

Die Einstellung **AllowLargeMeetings $true** bewirkt Folgendes:

- Blendet die Teilnehmerliste aus. 

- Deaktiviert Fehler im Chatfenster.

- Deaktiviert Video mit mehreren Teilnehmern.

- Deaktiviert die Fähigkeit, einen Teilnehmer für Referenten zu bewerben. Sie müssen vorausschauend planen und alle Referenten vor der Besprechung deklarieren.

- Deaktiviert die Möglichkeit zum Aufheben der Stummschaltung für einzelne Teilnehmer.

- Deaktiviert die Möglichkeit, das Feature "Video Spotlight sperren" auf Teilnehmer anzuwenden.

- PSTN-Einwahlbenutzer können die Stummschaltung selbst nicht mit 6 aufheben, da die persönliche virtuelle Unterstützung, die für DTMF-Befehle in aktiven großen Besprechungen zuständig ist, fehlt.

- Wenn der Referent/Organisator eine Besprechung plant, in der jeder zuerst stumm geschaltet werden soll ("alle stumm schalten"), werden PSTN-Benutzer während des Anrufs stumm geschaltet und können die Stummschaltung selbst nicht wieder aufheben.

Mit Ausnahme der Einstellung **Maximale Besprechungsgröße** sind alle anderen hier angegeben Konferenzrichtlinieneinstellungen erforderlich, um die Konferenzfunktionen zu deaktivieren, die für große Besprechungen nicht erforderlich sind.
  
Darüber hinaus müssen Sie den dedizierten großen Besprechungs Pool so konfigurieren, dass jeder Skype for Business Server Benutzer, der im Pool verwaltet wird und für die Verwaltung des Besprechungs Zeitplans zuständig ist, über die entsprechenden Berechtigungen verfügt. Gehen Sie hierzu wie folgt vor:
  
- Legen Sie die Option **Als Referenten festlegen** auf **Keine** fest. Normalerweise sind nur einige wenige Benutzer der gesamten Teilnehmer einer großen Besprechung Referenten, sodass die Teilnehmer nicht automatisch als Referenten für große Besprechungen zugelassen werden sollten. Die Referenten sollten stattdessen bei der geplanten Besprechung explizit festgelegt oder während der großen Besprechung explizit ernannt werden.
    
- Stellen Sie sicher, dass das Kontrollkästchen **zugewiesener Konferenztyp Standard** mäßig nicht aktiviert ist. Mit dieser Einstellung wird gesteuert, ob das Online Besprechungs-Add-in für Skype for Business Konferenzen immer mit der zugewiesenen Konferenz des Organisators plant, was bedeutet, dass geplante Besprechungen über dieselbe Join-URL und Audioinformationen verfügen. In Szenarien für die Zusammenarbeit in kleinen Gruppen funktioniert der zugewiesene Konferenztyp gut, da jeder über eine eigene zugewiesene Konferenz verfügt, und die URL und die Audioinformationen für den konstanten Beitritt helfen, eine schnellere Besprechungsteilnahme zu ermöglichen. Im Szenario mit großen Besprechungen werden die großen Besprechungen jedoch mithilfe eines einzigen Satzes von Benutzeranmeldeinformationen geplant, und dann werden den Besprechungs anfordernden Join-URLs und Audioinformationen zur Verfügung gestellt. In diesem Fall funktioniert die Verwendung einer anderen URL für die Teilnahme an jeder Besprechung besser.
    
- Stellen Sie sicher, dass das Kontrollkästchen **Anonyme Benutzer standardmäßig zulassen** nur aktiviert wird, wenn es erforderlich ist. Diese Einstellung wirkt sich auf den standardmäßigen Besprechungs Zugriffstyp aus, der vom Online Besprechungs-Add-in für Skype for Business geplant wird, wenn keine zugewiesene Konferenz verwendet wird. Die entsprechende Option für diese Einstellung hängt von den Anforderungen Ihrer Organisation ab. Wenn die meisten großen Besprechungen in Ihrer Organisation interne Besprechungen sind, sollte diese Option nicht ausgewählt werden. Wenn beim Großteil der großen Besprechungen externe Benutzer teilnehmen, sollte diese Option ausgewählt werden.
    
Weitere Informationen zum Erstellen einer konferenzrichtlinie finden Sie unter [Manage Conferencing Policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).
  

