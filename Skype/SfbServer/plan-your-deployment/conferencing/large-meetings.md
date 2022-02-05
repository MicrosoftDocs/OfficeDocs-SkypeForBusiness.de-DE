---
title: Planen großer Besprechungen in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 21507e18-bd79-4019-9c3a-0867fccaa3b4
description: 'Zusammenfassung: Lesen Sie dieses Thema, um mehr über bewährte Methoden für die Implementierung und Verwaltung großer Besprechungen in Skype for Business Server zu erfahren.'
---

# <a name="plan-for-large-meetings-in-skype-for-business-server"></a>Planen großer Besprechungen in Skype for Business Server
 
**Zusammenfassung:** Lesen Sie dieses Thema, um mehr über bewährte Methoden für die Implementierung und Verwaltung großer Besprechungen in Skype for Business Server zu erfahren.
  
Die Größe von Besprechungen, die Skype for Business Server unterstützen können, hängt davon ab, ob Konferenzen in einem freigegebenen oder dedizierten Pool gehostet werden: von 250 Teilnehmern in einem freigegebenen Pool bis zu 1000 Teilnehmern in einem dedizierten Pool. 
  
> [!NOTE]
> Dieses Thema befasst sich mit bewährten Methoden für große Besprechungen, die von Skype for Business Server unterstützt werden. Wenn Ihre Organisation größere Besprechungsfunktionen benötigt, sollten Sie erwägen, eine Hybridumgebung zu implementieren, die Skype-Besprechung Broadcast nutzt, einen neuen Onlinedienst, der Teil Microsoft 365 und Office 365 ist. 

> [!NOTE]
> Skype-Besprechung Broadcast ermöglicht Benutzern das Hosten und Übertragen von Besprechungen an ein großes Onlinepublikum von bis zu 10.000 Teilnehmern. Die Verwendung von Skype-Besprechung Broadcast erfordert, dass Skype for Business Server bereits in einem Hybridsetup mit einer Produktions-Microsoft 365 oder Office 365 Organisation konfiguriert sind. Für alle Benutzer muss ein Onlinemandant als Voraussetzung eingerichtet sein. Wenn Sie an der Bereitstellung einer Hybridlösung interessiert sind, die Skype-Besprechung Broadcast nutzen kann, lesen Sie [was ist eine Skype-Besprechung Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) und [konfigurieren Sie Ihre lokale Bereitstellung für Skype-Besprechung Broadcast](../../deploy/configure-skype-meeting-broadcast.md). 
  
Große Besprechungen weisen in der Regel die folgenden Merkmale auf:
  
- Das Besprechungsformat ist eine 1:n-Präsentation.
    
- Ein oder mehrere Benutzer sind Referenten, und alle anderen Teilnehmer nehmen nur als Teilnehmer teil.
    
- PowerPoint Präsentationsfreigabe ist die Hauptaktivität für die Datenzusammenarbeit.
    
- Audio ist erforderlich, und video kann auch verwendet werden.
    
- Eine dedizierte Person, in der Regel der Besprechungsorganisator oder ein Assistent des Organisators, richtet die Besprechung weit im Voraus ein.
    
- Dedizierte Mitarbeiter (nicht die Referenten) führen die Besprechung aus, einschließlich der Herstellung einer Verbindung mit einer Onlinebesprechung, der Überprüfung, ob Audio-, Video- und Folienfreigaben funktionieren, Verwalten von Lobby- und Benutzerrollen, Stummschalten und Aufheben der Stummschaltung von Teilnehmern, Beantworten von Fragen und Verwalten von Aufzeichnungen, sofern zutreffend.
    
Wenn ein Benutzer eine Besprechung plant, erstellt Skype for Business Server einen Datensatz in der Konferenzdatenbank, der Konferenzdaten speichert, aber keine Hardwareressourcen für die geplante Besprechung im Voraus reserviert. Stattdessen verfügt Skype for Business Server über integrierte Lastenausgleichslogik, um Konferenzressourcen auf Front-End-Servern dynamisch zuzuweisen, sodass Lasten gleichmäßig auf alle Front-End-Server im Pool verteilt werden. Dadurch werden Hardwareressourcen effektiv bereitstellt und verwendet, es ist jedoch wichtig, dass Sie sehr große Besprechungen angemessen unterstützen. 
  
Wenn beispielsweise ein Skype for Business Server Pool in der Nähe seiner obersten Kapazität ausgeführt wird, kann jeder Front-End-Server ungefähr 125 Besprechungen mit durchschnittlicher Größe hosten. Das Hinzufügen einer weiteren kleinen Besprechung wäre kein Problem, aber das Hinzufügen einer Besprechung für 1000 Benutzer wäre ein Problem, da die Front-End-Server wahrscheinlich nicht in der Lage wären, eine so große Besprechung gleichzeitig mit den anderen 125 Besprechungen zu unterstützen.
  
Für die Unterstützung großer Besprechungen mit bis zu 1.000 Teilnehmern müssen Die Probleme im Zusammenhang mit dem gemeinsam genutzten Hardwaremodell und dem Reservierungsmodell behandelt werden. Im Allgemeinen müssen Sie einen dedizierten Pool planen und bewährte Methoden befolgen, wie in den folgenden Abschnitten beschrieben. 
  
## <a name="plan-for-a-dedicated-pool"></a>Planen eines dedizierten Pools

Wenn Ihre Organisation Besprechungen mit mehr als 250 Teilnehmern erfordert, müssen Sie einen dedizierten Pool planen, um die Last zu unterstützen. 
  
Um über genügend CPU- und Speicherressourcen für Besprechungen mit bis zu 1.000 Benutzern zu verfügen, sollten die hostenden Front-End-Server keine anderen Chat- und Anwesenheits- oder Enterprise-VoIP-Workloads hosten. Die Server sollten auch keine anderen Besprechungen hosten, unabhängig von der Größe der anderen Besprechungen. Um Besprechungen mit bis zu 1.000 Benutzern zu hosten, müssen Sie einen separaten Skype for Business Server Pool einrichten, der für das Hosten großer Besprechungen vorgesehen ist.
  
Ein Skype for Business Server Pool, der für das Hosten großer Besprechungen vorgesehen ist, sollte eine und nur eine Besprechung mit bis zu 1.000 Benutzern gleichzeitig hosten. Besprechungszeiten müssen daher im Voraus über einen Out-of-Band-Planungsprozess reserviert werden, um dedizierten Support von den Front-End-Servern sicherzustellen. Um mehrere große Besprechungen gleichzeitig zu unterstützen, sollten Sie mehrere dedizierte Pools für große Besprechungen einrichten.
  
Weitere Informationen zu Hardware- und Softwareanforderungen sowie zur Planung einer Topologie, die große Besprechungen unterstützt, finden Sie unter [Hardware- und Softwareanforderungen für Konferenzen in Skype for Business Server](hardware-and-software-requirements.md) und [Planen Ihrer Konferenztopologie für Skype for Business Server](conferencing-topology.md).
  
## <a name="implement-best-practices-for-large-meetings"></a>Implementieren bewährter Methoden für große Besprechungen

Nachdem Sie einen dedizierten Pool für große Besprechungen eingerichtet haben, können Sie Maßnahmen ergreifen, um sicherzustellen, dass im Pool gehostete große Besprechungen die beste Benutzererfahrung bieten. Die folgenden Abschnitte enthalten Richtlinien für die Verwaltung großer Besprechungen:
  
- Erstellen dedizierter Besprechungsorganisatoren
    
- Erstellen dedizierter Moderatoren
    
- Verwalten eines separaten Kalenders für große Besprechungen
    
- Implementieren eines Planungsprozesses für große Besprechungen
    
- Angeben der entsprechenden Planungsdetails
    
- Erstellen einer Konferenzrichtlinie für große Besprechungen
    
### <a name="create-dedicated-meeting-organizers"></a>Erstellen dedizierter Besprechungsorganisatoren

Um den Echtzeit-Kommunikationsdatenverkehr im großen Besprechungspool zu minimieren, empfiehlt Microsoft nicht, Benutzer zu hosten, die sich regelmäßig mit Skype for Business Clients anmelden und an Chat-, Anwesenheits-, Konferenz- und Sprachsitzungen teilnehmen. Führen Sie stattdessen eine der folgenden Aktionen aus:
  
- Erstellen eines oder mehrerer dedizierter Benutzerkonten nur zum Planen großer Besprechungen
    
- Verwalten der Benutzerkonten der Mitarbeiter, die für die Planung großer Besprechungen in einem großen Besprechungspool verantwortlich sind
    
### <a name="create-dedicated-moderators"></a>Erstellen dedizierter Moderatoren

Bei mehreren Hundert bis 1.000 Benutzern in einer Besprechung empfiehlt es sich, die Onlinesitzung einer großen Besprechung durch eine dedizierte Person zu moderieren. Diese dedizierte Person kann eine Stellvertretung des Besprechungsorganisators oder ein Mitglied des Supportpersonals für große Besprechungen der Organisation sein. Es ist wichtig, den dedizierten Besprechungsmoderator zum Zeitpunkt der Besprechungsplanung als Referenten hinzuzufügen, obwohl es möglich ist, einen Teilnehmer einer Onlinebesprechung zur Referentenrolle zu bewerben, während die Besprechung läuft.
  
Der Besprechungsmoderator kann alle Referentenfunktionen von Skype for Business Clients verwenden, um die große Besprechung zu verwalten. Zu diesen Funktionen gehören:
  
- Überwachen des Wartebereichs und Zulassen oder Ablehnen von Benutzern im Wartebereich
    
- Entfernen von Benutzern aus der Besprechung, die nicht an der Besprechung teilnehmen sollten
    
- Ändern von Besprechungszugriffstypen
    
- Ändern von Teilnehmerrollen
    
- Einladen zusätzlicher Teilnehmer während der Besprechung mit drag & drop-Funktionen, Telefonwählen oder E-Mails
    
- Stummschalten und Aufheben der Stummschaltung der Zielgruppe oder einzelner Benutzer
    
- Verwalten von Besprechungsinhalten, einschließlich Hochladen von Inhalten, Löschen von Inhalten und Wechseln aktiver Inhalte

    
### <a name="maintain-a-separate-calendar"></a>Verwalten eines separaten Kalenders

Für jeden großen Besprechungspool sollten Sie einen separaten Kalender mit großen Besprechungen verwalten, die in diesem Pool geplant sind. Sie können beispielsweise ein einzelnes Benutzerkonto im Pool für große Besprechungen verwalten und Outlook mit Exchange und Onlinebesprechungs-Add-Ins für Skype for Business verwenden, um einen separaten Kalender zu verwalten. Wenn Sie mehrere Benutzerkonten verwenden, um Supportmitarbeitern das Erstellen großer Besprechungen zu ermöglichen, können Sie einen separaten Kalender einrichten, in dem alle großen Besprechungen festgehalten werden, die von Supportmitarbeitern erstellt werden. 
  
Durch das Verwalten eines separaten Kalenders für Besprechungen vermeiden Sie Konflikte und stellen sicher, dass zu einem bestimmten Zeitpunkt immer jeweils nur eine große Besprechung stattfinden kann.
  
### <a name="implement-a-scheduling-process"></a>Implementieren eines Planungsprozesses

Da im dedizierten großen Besprechungspool jeweils nur eine große Besprechung unterstützt wird, sollten Sie einen umfangreichen Besprechungsplanungsprozess implementieren, um das Einrichten großer Besprechungen zu vereinfachen und Konflikte zu vermeiden. Diese Funktion wird nicht direkt von Skype for Business Server oder Skype for Business Clients bereitgestellt. Eine Möglichkeit, einen solchen Prozess zu implementieren, besteht darin, das Ticketsystem Ihres Supportteams zu verwenden, sofern verfügbar.
  
Zum Planen einer großen Besprechung müssen die folgenden Schritte ausgeführt werden:
  
- Der Besprechungsorganisator oder die Stellvertretung bestimmt die Uhrzeit, Dauer und Größe einer bevorstehenden Besprechung sowie die Liste der Referenten. Wenn die erwartete Besprechungsgröße 250 Benutzer überschreitet oder um eine optimale Benutzererfahrung für eine Besprechung mit weniger als 250 Benutzern sicherzustellen, sendet der Organisator oder die Stellvertretung eine Anforderung für eine große Besprechung.
    
- Die Planungsmitarbeiter überprüfen, ob das angeforderte Datum und die gewünschte Uhrzeit verfügbar sind. Da jeweils nur eine einzelne große Besprechung im dedizierten Pool unterstützt wird, müssen die Planungsmitarbeiter den Kalender für große Besprechungen überprüfen, um festzustellen, ob für das angeforderte Datum und die gewünschte Uhrzeit eine weitere Besprechung geplant ist. Wenn die angeforderte Zeit verfügbar ist, genehmigt der Mitarbeiter die Besprechungsanfrage.
    
- Wenn die Anforderung genehmigt wurde, verwendet das Planungsteam (unter Verwendung von Anmeldeinformationen im dedizierten Pool) das Onlinebesprechungs-Add-In für Skype for Business mit Outlook, um eine Besprechung im dedizierten Pool für große Besprechungen einzurichten. Die URL, die für die Teilnahme an der Besprechung verwendet werden soll, wird dem Antragsteller als Teil des Genehmigungshinweiss bereitgestellt.
    
- Der Besprechungsorganisator oder die Stellvertretung verwendet Outlook, um die bevorstehende Besprechung zu planen und die URL für die Teilnahme an der Besprechung zur Besprechungseinladung hinzuzufügen. Der Besprechungsorganisator oder die Stellvertretung gibt dann die eingeladenen Benutzer an und sendet die Besprechungseinladung.
    
### <a name="specify-appropriate-scheduling-details"></a>Angeben der entsprechenden Planungsdetails

Nach der Überprüfung, ob zum gewünschten Zeitpunkt keine andere Besprechung geplant ist, plant der große Supportmitarbeiter der Besprechung, der die Anforderung verarbeitet, die Besprechung im großen Besprechungspool. 
  
Um eine optimale Benutzererfahrung zu gewährleisten, ist es wichtig, die große Besprechung mit den richtigen Zugriffsebenen und Besprechungseinstellungen zu planen, die den Anforderungen des Besprechungsorganisators entsprechen. Berücksichtigen Sie die folgenden Planungseinstellungen, die in Skype for Business Besprechungsoptionen konfiguriert sind:
  
- Verwenden Sie einen neuen Besprechungsraum für jede große Besprechung, anstatt den dedizierten Besprechungsraum erneut zu verwenden. 
    
- Geben Sie die Zugriffsebene für die Besprechung wie folgt an:
    
  - Wenn sich mindestens ein eingeladener Benutzer außerhalb der Organisation befindet, legen Sie den **Besprechungszugriffstyp auf "Jeder" fest (keine Einschränkungen).** Dadurch vermeiden Sie, dass sie während der laufenden Besprechung einen möglicherweise großen Wartebereich verwalten müssen.
    
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
    
    Durch die explizite Verwaltung von Referenten können Sie die Referenten auf eine kleine Zahl beschränken, um eine effektive große Besprechung zu ermöglichen. Wenn die Mehrzahl der Besprechungsteilnehmer die Teilnehmerrolle hat, verringert dies die Wahrscheinlichkeit, dass Personen versehentlich die Kontrolle über die Präsentation übernehmen, eine PowerPoint Präsentation löschen, Referenten stumm schalten/die Stummschaltung aufheben und andere Unterbrechungen der Besprechung. 
    
- Aktivieren Sie die Option **Alle Teilnehmer stummschalten**, um sicherzustellen, dass nur Referenten Audioinhalte in die Besprechung übertragen können.
    
- Überprüfen Sie die **Videoeinstellung "Teilnehmer blockieren** ", um sicherzustellen, dass nur Referenten Videos in die Besprechung übertragen können.
    
### <a name="create-a-conferencing-policy"></a>Erstellen einer Konferenzrichtlinie

Erstellen Sie eine neue Konferenzrichtlinie speziell für große Besprechungen, und weisen Sie die Konferenzrichtlinie dann den Benutzern zu, die im dedizierten großen Besprechungspool verwaltet werden. Mithilfe der folgenden Einstellungen können Sie die Konferenzrichtlinie konfigurieren:
  
- Legen Sie die **MaxMeetingSize-Option** auf 1000 fest. (Der Standardwert ist 250.)
    
- Legen Sie die Option **AllowLargeMeetings** auf **True** fest. 
    
- Legen Sie die Option **EnableAppDesktopSharing** auf **Keine** fest.
    
- Legen Sie die Option **AllowUserToScheduleMeetingsWithAppSharing** auf **False** fest.
    
- Legen Sie die Option **AllowSharedNotes** auf **False** fest.
    
- Legen Sie die Option **AllowAnnotations** auf **False** fest.
    
- Legen Sie die Option **DisablePowerPointAnnotations** auf **True** fest.
    
- Legen Sie die Option **AllowMultiview** auf **False** fest.
    
- Legen Sie die Option **EnableMultiviewJoin** auf **False** fest.
    
> [!NOTE]
> Für die Unterstützung großer Besprechungen in Skype for Business Server muss die Einstellung **"AllowLargeMeetings**" auf "true" festgelegt sein. Wenn diese Einstellung auf "true" festgelegt ist, wird die Skype for Business Oberfläche für besonders große Besprechungen optimiert, wenn Benutzer an der Besprechung teilnehmen. Insbesondere zeigt Skype for Business in einer großen Besprechung nicht die anfängliche oder die Aktualisierung der vollständigen Besprechungsteilnehmerliste an, was ein Leistungsengpass sowohl für den Client als auch für Skype for Business Server ist. Stattdessen zeigen Skype for Business nur Informationen über den Benutzer und die Liste der Referenten der Besprechung an. Skype for Business zeigt weiterhin die Gesamtzahl der Teilnehmer an, die in den großen Besprechungen verfügbar sind.

Die **Einstellung "AllowLargeMeetings $true" bewirkt Folgendes** :

- Blendet die Teilnehmerliste aus. 

- Deaktiviert Fehler im Chatfenster.

- Deaktiviert Video mit mehreren Teilnehmern.

- Deaktiviert die Möglichkeit, einen Teilnehmer zum Referenten zu bewerben. Sie müssen vorausplanen und alle Referenten vor der Besprechung deklarieren.

- Deaktiviert die Möglichkeit, die Stummschaltung einzelner Teilnehmer aufzuheben.

- Deaktiviert die Möglichkeit, das Feature "Video-Blickpunkt sperren" auf Teilnehmer anzuwenden.

- PsTN-Einwahlbenutzer können sich nicht mit 6 stummschalten, da die persönliche virtuelle Unterstützung, die für DTMF-Befehle in aktiven großen Besprechungen verantwortlich ist, fehlt.

- Wenn der Referent/Organisator eine Besprechung plant, bei der jeder zuerst stummgeschaltet werden soll ("Alle stumm schalten"), werden PSTN-Benutzer während des Anrufs stummgeschaltet und können die Stummschaltung selbst nicht aufheben.

Mit Ausnahme der Einstellung **Maximale Besprechungsgröße** sind alle anderen hier angegeben Konferenzrichtlinieneinstellungen erforderlich, um die Konferenzfunktionen zu deaktivieren, die für große Besprechungen nicht erforderlich sind.
  
Darüber hinaus müssen Sie den dedizierten Pool für große Besprechungen konfigurieren, damit jeder Skype for Business Server Benutzer, der im Pool verwaltet wird und für die Verwaltung des Besprechungszeitplans verantwortlich ist, über die entsprechenden Berechtigungen verfügt. Gehen Sie hierzu wie folgt vor:
  
- Legen Sie die Option **Als Referenten festlegen** auf **Keine** fest. Normalerweise sind nur einige wenige Benutzer der gesamten Teilnehmer einer großen Besprechung Referenten, sodass die Teilnehmer nicht automatisch als Referenten für große Besprechungen zugelassen werden sollten. Die Referenten sollten stattdessen bei der geplanten Besprechung explizit festgelegt oder während der großen Besprechung explizit ernannt werden.
    
- Stellen Sie sicher, dass das Kontrollkästchen " **Konferenztyp zugewiesen" standardmäßig** nicht aktiviert ist. Mit dieser Einstellung wird gesteuert, ob das Onlinebesprechungs-Add-In für Skype for Business immer Konferenzen mithilfe der vom Organisator zugewiesenen Konferenz plant, was bedeutet, dass geplante Besprechungen die gleiche Teilnahme-URL und Audioinformationen aufweisen. In Szenarien für die Zusammenarbeit in kleinen Gruppen funktioniert ein solcher zugewiesener Konferenztyp gut, da jeder über eine eigene zugewiesene Konferenz verfügt und die url- und Audioinformationen für den konstanten Beitritt dazu beiträgt, die Teilnahme an Besprechungen zu beschleunigen. Im Szenario für große Besprechungen plant der Supportmitarbeiter für große Besprechungen die großen Besprechungen jedoch mithilfe eines einzigen Satzes von Benutzeranmeldeinformationen und stellt den Besprechungsanfragern dann Teilnahme-URLs und Audioinformationen bereit. In diesem Fall funktioniert die Verwendung einer anderen URL für die Teilnahme an jeder Besprechung besser.
    
- Stellen Sie sicher, dass das Kontrollkästchen **Anonyme Benutzer standardmäßig zulassen** nur aktiviert wird, wenn es erforderlich ist. Diese Einstellung wirkt sich auf den standardmäßigen Besprechungszugriffstyp aus, der vom Onlinebesprechungs-Add-In für Skype for Business geplant wird, wenn keine zugewiesene Konferenz verwendet wird. Die entsprechende Option für diese Einstellung hängt von den Anforderungen Ihrer Organisation ab. Wenn die meisten großen Besprechungen in Ihrer Organisation interne Besprechungen sind, sollte diese Option nicht ausgewählt werden. Wenn beim Großteil der großen Besprechungen externe Benutzer teilnehmen, sollte diese Option ausgewählt werden.
    
Weitere Informationen zum Erstellen einer Konferenzrichtlinie finden Sie unter [Verwalten von Konferenzrichtlinien in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).
  

