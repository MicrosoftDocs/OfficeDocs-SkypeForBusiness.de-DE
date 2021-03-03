---
title: Planen großer Besprechungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 21507e18-bd79-4019-9c3a-0867fccaa3b4
description: 'Zusammenfassung: In diesem Thema erfahren Sie mehr über bewährte Methoden für die Implementierung und Verwaltung großer Besprechungen in Skype for Business Server.'
ms.openlocfilehash: 8e982f08b1ff65ac6a4ea6f47a15e57f1eded163
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813975"
---
# <a name="plan-for-large-meetings-in-skype-for-business-server"></a>Planen großer Besprechungen in Skype for Business Server
 
**Zusammenfassung:** In diesem Thema erfahren Sie mehr über bewährte Methoden für die Implementierung und Verwaltung großer Besprechungen in Skype for Business Server.
  
Die Größe von Besprechungen, die Skype for Business Server unterstützen kann, hängt davon ab, ob Konferenzen in einem freigegebenen oder dedizierten Pool gehostet werden: von 250 Teilnehmern in einem freigegebenen Pool bis zu 1.000 Teilnehmern in einem dedizierten Pool. 
  
> [!NOTE]
> Dieser Schwerpunkt liegt auf bewährten Methoden für große Besprechungen, die von Skype for Business Server unterstützt werden. Wenn Ihre Organisation größere Besprechungsfunktionen benötigt, sollten Sie die Implementierung einer Hybridumgebung in Betracht ziehen, die die Vorteile von Skype Meeting Broadcast nutzt, einem neuen Onlinedienst, der Bestandteil von Microsoft 365 und Office 365 ist. 

> [!NOTE]
> Skype Meeting Broadcast ermöglicht Benutzern das Hosten und Übertragen von Besprechungen an ein großes Onlinepublikum mit bis zu 10.000 Teilnehmern. Für die Verwendung von Skype Meeting Broadcast muss Skype for Business Server bereits in einer Hybrideinrichtung mit einer Microsoft 365- oder Office 365-Produktionsorganisation konfiguriert sein. Für alle Benutzer muss ein Online mandant als Voraussetzung eingerichtet sein. Wenn Sie an der Bereitstellung einer Hybridlösung interessiert sind, die die Vorteile von Skype Meeting Broadcast nutzen kann, lesen Sie "Was ist [eine Skype-Liveübertragung?"](https://go.microsoft.com/fwlink/?LinkId=617071) und konfigurieren Sie Ihre lokale Bereitstellung für [Skype Meeting Broadcast.](../../deploy/configure-skype-meeting-broadcast.md) 
  
Große Besprechungen haben in der Regel die folgenden Merkmale:
  
- Das Besprechungsformat ist eine 1:n-Präsentation.
    
- Ein oder einige wenige Benutzer sind Moderatoren, und alle anderen benutzer nehmen nur als Teilnehmer teil.
    
- Die Hauptaktivität für die Datenzusammenarbeit ist die PowerPoint-Präsentationsfreigabe.
    
- Audio ist erforderlich, und video kann auch verwendet werden.
    
- Eine dedizierte Person, in der Regel entweder der Besprechungsorganisator oder ein Assistent des Organisators, richtet die Besprechung bereits im Voraus ein.
    
- Dedizierte Mitarbeiter (nicht die Moderatoren) nehmen die Besprechung vor. Dazu gehören das Herstellen einer Verbindung mit einer Onlinebe besprechung, das Überprüfen der Audio-, Video- und Folienfreigabe, das Verwalten von Lobby- und Benutzerrollen, das Stummschalten und Das Stummschalten von Teilnehmern, das Beantworten von Fragen und das Verwalten von Aufzeichnungen, falls angemessen.
    
Wenn ein Benutzer eine Besprechung plant, erstellt Skype for Business Server einen Datensatz in der Konferenzdatenbank, in der Konferenzdaten gespeichert werden, aber keine Hardwareressourcen für die geplante Besprechung im Voraus reserviert werden. Stattdessen verfügt Skype for Business Server über integrierte Lastenausgleichslogik, um Konferenzressourcen dynamisch auf Front-End-Servern so zuzuordnen, dass die Lasten gleichmäßig auf alle Front-End-Server im Pool verteilt werden. Dadurch werden effektiv Hardwareressourcen zur Verfügung stellen und verwendet. Es ist jedoch wichtig, dass Sie sehr große Besprechungen entsprechend unterstützen. 
  
Wenn beispielsweise ein Skype for Business Server-Pool in der Nähe seiner Topkapazität ausgeführt wird, kann jeder Front-End-Server etwa 125 Besprechungen mit durchschnittlicher Größe hosten. Das Hinzufügen einer weiteren kleinen Besprechung wäre kein Problem, aber das Hinzufügen einer Besprechung für 1000 Benutzer wäre ein Problem, da die Front-End-Server wahrscheinlich nicht gleichzeitig mit den anderen 125 Besprechungen eine so große Besprechung unterstützen können.
  
Für die Unterstützung großer Besprechungen mit bis zu 1.000 Teilnehmern müssen die Probleme im Zusammenhang mit dem gemeinsam genutzten Hardwaremodell und dem Reservierungsmodell angesprochen werden. Im Allgemeinen müssen Sie einen dedizierten Pool planen und bewährte Methoden befolgen, wie in den folgenden Abschnitten beschrieben. 
  
## <a name="plan-for-a-dedicated-pool"></a>Planen eines dedizierten Pools

Wenn Ihre Organisation Besprechungen mit mehr als 250 Teilnehmern erfordert, müssen Sie einen dedizierten Pool zur Unterstützung der Last planen. 
  
Um über ausreichende CPU- und Arbeitsspeicherressourcen für Besprechungen mit bis zu 1000 Benutzern zu verfügen, sollten die hostende Front-End-Server keine anderen Chat- und Anwesenheits- oder Enterprise-VoIP hosten. Die Server sollten auch keine anderen Besprechungen hosten, unabhängig von der Größe der anderen Besprechungen. Zum Hosten von Besprechungen mit bis zu 1.000 Benutzern müssen Sie einen separaten Skype for Business Server-Pool einrichten, der für das Hosten großer Besprechungen eingerichtet ist.
  
Ein Skype for Business Server-Pool, der für das Hosten großer Besprechungen reserviert ist, sollte eine und nur eine Besprechung mit bis zu 1.000 Benutzern gleichzeitig hosten, sodass Besprechungszeiten im Voraus über einen Out-of-Band-Planungsprozess reserviert werden müssen, um dedizierte Unterstützung von den Front-End-Servern sicherzustellen. Um mehrere große Besprechungen gleichzeitig zu unterstützen, sollten Sie mehrere dedizierte große Besprechungspools einrichten.
  
Weitere Informationen zu Hardware- und Softwareanforderungen sowie zum Planen einer Topologie, die große Besprechungen unterstützt, finden Sie unter [Hardware-](hardware-and-software-requirements.md) und Softwareanforderungen für Konferenzen in Skype for Business Server und Planen Ihrer Konferenztopologie für Skype for [Business Server.](conferencing-topology.md)
  
## <a name="implement-best-practices-for-large-meetings"></a>Implementieren bewährter Methoden für große Besprechungen

Nachdem Sie einen dedizierten Pool für große Besprechungen eingerichtet haben, können Sie Maßnahmen ergreifen, um sicherzustellen, dass große, im Pool gehostete Besprechungen die beste Benutzererfahrung bieten. Die folgenden Abschnitte enthalten Richtlinien für die Verwaltung großer Besprechungen:
  
- Erstellen dedizierter Besprechungsorganisatoren
    
- Erstellen dedizierter Moderatoren
    
- Verwalten eines separaten Kalenders für große Besprechungen
    
- Implementieren eines Planungsvorgangs für große Besprechungen
    
- Angeben geeigneter Planungsdetails
    
- Erstellen einer Konferenzrichtlinie für große Besprechungen
    
### <a name="create-dedicated-meeting-organizers"></a>Erstellen dedizierter Besprechungsorganisatoren

Um den Datenverkehr der Echtzeitkommunikation im großen Besprechungspool zu minimieren, empfiehlt Microsoft nicht, Benutzer zu hosten, die sich regelmäßig mit Skype for Business-Clients anmelden und an Chat-, Anwesenheits-, Konferenz- und Sprachsitzungen teilnehmen. Gehen Sie stattdessen wie folgt vor:
  
- Erstellen eines oder mehrere dedizierter Benutzerkonten nur zum Planen großer Besprechungen
    
- Verwalten der Benutzerkonten der Mitarbeiter, die für die Planung großer Besprechungen in einem großen Besprechungspool verantwortlich sind
    
### <a name="create-dedicated-moderators"></a>Erstellen dedizierter Moderatoren

Bei mehreren Hundert bis 1000 Benutzern in einer Besprechung ist es eine bewährte Methode, eine dedizierte Person die Onlinesitzung einer großen Besprechung zu moderieren. Diese dedizierte Person kann eine Stellvertretung des Besprechungsorganisators oder ein Mitglied des Supportpersonals für große Besprechungen der Organisation sein. Es ist wichtig, den dedizierten Besprechungsmoderator zu dem Zeitpunkt, zu dem die Besprechung geplant ist, als Moderator hinzuzufügen, obwohl es möglich ist, einen Online-Besprechungsteilnehmer während der Besprechung in die Rolle des Moderators zu übernehmen.
  
Der Besprechungsmoderator kann alle Moderatorfunktionen von Skype for Business-Clients verwenden, um die große Besprechung zu verwalten. Zu diesen Funktionen gehören:
  
- Überwachen der Lobby und Zugeben oder Ablehnen von Benutzern in der Lobby
    
- Entfernen von Benutzern aus der Besprechung, die nicht an der Besprechung teil sein sollten
    
- Ändern der Zugriffstypen für Besprechungen
    
- Ändern von Teilnehmerrollen
    
- Einladen zusätzlicher Teilnehmer während der Besprechung mit Drag and Drop-Funktion, Telefonanruf oder E-Mail
    
- Stummschalten und Stummschalten der Benutzer oder einzelner Benutzer
    
- Verwalten von Besprechungsinhalten, einschließlich hochladen von Inhalten, Löschen von Inhalten und Wechseln aktiver Inhalte

    
### <a name="maintain-a-separate-calendar"></a>Verwalten eines separaten Kalenders

Für jeden großen Besprechungspool sollten Sie einen separaten Kalender mit großen Besprechungen verwalten, die in diesem Pool geplant sind. Sie können beispielsweise ein einzelnes Benutzerkonto im großen Besprechungspool verwalten und Outlook mit Exchange und Online-Besprechungs-Add-In für Skype for Business verwenden, um einen separaten Kalender zu verwalten. Wenn Sie mehrere Benutzerkonten verwenden, um Supportmitarbeitern das Erstellen großer Besprechungen zu ermöglichen, können Sie einen separaten Kalender einrichten, in dem alle großen Besprechungen festgehalten werden, die von Supportmitarbeitern erstellt werden. 
  
Durch das Verwalten eines separaten Kalenders für Besprechungen vermeiden Sie Konflikte und stellen sicher, dass zu einem bestimmten Zeitpunkt immer jeweils nur eine große Besprechung stattfinden kann.
  
### <a name="implement-a-scheduling-process"></a>Implementieren eines Planungsprozesses

Da im dedizierten großen Besprechungspool immer nur eine große Besprechung unterstützt wird, sollten Sie einen großen Besprechungsplanungsprozess implementieren, um das Einrichten großer Besprechungen zu erleichtern und Konflikte zu vermeiden. Diese Funktion wird nicht direkt von Skype for Business Server- oder Skype for Business-Clients bereitgestellt. Eine Möglichkeit zum Implementieren eines solchen Prozesses besteht in der Verwendung des Ticketsystem des Supportteams Ihrer Organisation, sofern verfügbar.
  
Das Planen einer großen Besprechung umfasst die Durchführung der folgenden Schritte:
  
- Der Besprechungsorganisator oder die Stellvertretung bestimmt die Uhrzeit, Dauer und Größe einer anstehenden Besprechung sowie die Liste der Organisator. Wenn die erwartete Besprechungsgröße 250 Benutzer überschreitet oder um eine optimale Benutzererfahrung für eine Besprechung mit weniger als 250 Benutzern sicherzustellen, sendet der Organisator oder die Stellvertretung eine Anforderung für eine große Besprechung.
    
- Die Planungsmitarbeiter überprüfen, ob das angeforderte Datum und die angeforderte Uhrzeit verfügbar sind. Da wir immer nur eine einzige große Besprechung im dedizierten Pool gleichzeitig unterstützen, müssen die Planungsmitarbeiter den Kalender für große Besprechungen überprüfen, um festzustellen, ob für den angeforderten Termin und die angeforderte Uhrzeit eine weitere Besprechung geplant ist. Wenn die angeforderte Zeit verfügbar ist, genehmigt der Mitarbeiter die Besprechungsanfrage.
    
- Wenn die Anforderung genehmigt wird, verwendet das Planungspersonal (unter Verwendung von Anmeldeinformationen im dedizierten Pool) das Onlinebesprechungs-Add-In für Skype for Business mit Outlook, um eine Besprechung im dedizierten großen Besprechungspool zu einrichten. Die URL, die für die Teilnahme an der Besprechung verwendet werden soll, wird dem Anfordernde im Rahmen des Genehmigungshinweises bereitgestellt.
    
- Der Besprechungsorganisator oder die Stellvertretung verwendet Outlook, um die anstehende Besprechung zu planen, und fügt die URL für die Teilnahme an der Besprechung der Besprechungseinladung hinzu. Der Besprechungsorganisator oder die Stellvertretung gibt dann die zu eingeladenen Benutzer an und sendet die Besprechungseinladung.
    
### <a name="specify-appropriate-scheduling-details"></a>Angeben geeigneter Planungsdetails

Nachdem sichergestellt wurde, dass zum angeforderten Zeitpunkt keine andere Besprechung geplant ist, plant das große Besprechungssupportteam, das die Anfrage verarbeitet, die Besprechung im großen Besprechungspool. 
  
Um eine optimale Benutzererfahrung zu gewährleisten, ist es wichtig, die große Besprechung mit den richtigen Zugriffsebenen und Besprechungseinstellungen zu planen, die den Anforderungen des Besprechungsorganisators entsprechen. Berücksichtigen Sie die folgenden Planungseinstellungen, die in den Skype for Business -Besprechungsoptionen konfiguriert sind:
  
- Verwenden Sie einen neuen Besprechungsraum für jede große Besprechung, anstatt den dedizierten Besprechungsraum erneut zu verwenden. 
    
- Geben Sie die Zugriffsebene für die Besprechung wie folgt an:
    
  - Wenn sich mindestens ein eingeladener Benutzer außerhalb der Organisation befindet, legen Sie den Zugriffstyp für die Besprechung auf **"Jeder" (keine Einschränkungen) festgelegt.** Dadurch vermeiden Sie, dass sie während der laufenden Besprechung einen möglicherweise großen Wartebereich verwalten müssen.
    
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
    
    Durch die explizite Verwaltung von Moderatoren können Sie die Moderatoren auf eine kleine Zahl beschränken, um eine effektive große Besprechung zu ermöglichen. Wenn die Mehrzahl der Besprechungsteilnehmer die Rolle des Teilnehmers hat, verringert sich die Wahrscheinlichkeit, dass Benutzer versehentlich die Kontrolle über die Präsentation übernehmen, eine PowerPoint-Präsentation löschen, Sprecher stummschalten/stummschalten und andere Unterbrechungen der Besprechung. 
    
- Aktivieren Sie die Option **Alle Teilnehmer stummschalten**, um sicherzustellen, dass nur Referenten Audioinhalte in die Besprechung übertragen können.
    
- Überprüfen Sie **die Videoeinstellung "Teilnehmer blockieren",** um sicherzustellen, dass nur Moderatoren Video in die Besprechung übertragen können.
    
### <a name="create-a-conferencing-policy"></a>Erstellen einer Konferenzrichtlinie

Erstellen Sie eine neue Konferenzrichtlinie speziell für große Besprechungen, und weisen Sie die Konferenzrichtlinie dann den Benutzern zu, die im dedizierten großen Besprechungspool zu hause sind. Mithilfe der folgenden Einstellungen können Sie die Konferenzrichtlinie konfigurieren:
  
- Legen Sie **die Option "MaxMeetingSize"** auf 1000. (Der Standardwert ist 250.)
    
- Legen Sie die Option **AllowLargeMeetings** auf **True** fest. 
    
- Legen Sie die Option **EnableAppDesktopSharing** auf **Keine** fest.
    
- Legen Sie die Option **AllowUserToScheduleMeetingsWithAppSharing** auf **False** fest.
    
- Legen Sie die Option **AllowSharedNotes** auf **False** fest.
    
- Legen Sie die Option **AllowAnnotations** auf **False** fest.
    
- Legen Sie die Option **DisablePowerPointAnnotations** auf **True** fest.
    
- Legen Sie die Option **AllowMultiview** auf **False** fest.
    
- Legen Sie die Option **EnableMultiviewJoin** auf **False** fest.
    
> [!NOTE]
> Für die Unterstützung großer Besprechungen in Skype for Business Server muss die Einstellung **"AllowLargeMeetings"** auf "true" festgelegt sein. Wenn diese Einstellung auf "true" festgelegt ist, wird die Skype for Business-Umgebung für besonders große Besprechungen optimiert, wenn Benutzer an der Besprechung teilnehmen. Insbesondere zeigt Skype for Business bei einer großen Besprechung nicht die Erste oder Aktualisierung der vollständigen Besprechungsteilnehmerliste an, was ein Leistungsengpässe für den Client und Skype for Business Server ist. Stattdessen zeigt Skype for Business nur Informationen über den Benutzer und die Liste der Moderatoren der Besprechung an. Skype for Business zeigt weiterhin die Gesamtzahl der verfügbaren Teilnehmer an den großen Besprechungen an.

Die **Einstellung "AllowLargeMeetings$true** bewirkt Folgendes:

- Blendet die Teilnehmerliste aus. 

- Deaktiviert Fehler im Fenster für Automatische Benachrichtigungen.

- Deaktiviert Video mit mehreren Parteien.

- Deaktiviert die Möglichkeit, einen Teilnehmer zum Presenter zu machen. Sie müssen vorausplanen und alle Moderatoren vor der Besprechung deklarieren.

- Deaktiviert die Möglichkeit zum Deaktivieren der Stummschaltung einzelner Teilnehmer.

- Deaktiviert die Möglichkeit, das Feature "Video-Blickpunkt sperren" auf Teilnehmer anzuwenden.

- PstN-Einwahlbenutzer können die Stummschaltung mithilfe von 6 nicht selbst aufändern, da die persönliche virtuelle Unterstützung, die für die DtmF-Befehle in aktiven großen Besprechungen zuständig ist, fehlt.

- Wenn der Organisator/der Organisator eine Besprechung plant, bei der alle Zuerst stummgeschaltet werden sollen ("Alle stummschalten"), werden #A0 während des Anrufs stummgeschaltet und können die Stummschaltung nicht selbst aufändern.

Mit Ausnahme der Einstellung **Maximale Besprechungsgröße** sind alle anderen hier angegeben Konferenzrichtlinieneinstellungen erforderlich, um die Konferenzfunktionen zu deaktivieren, die für große Besprechungen nicht erforderlich sind.
  
Darüber hinaus müssen Sie den dedizierten großen Besprechungspool so konfigurieren, dass jeder Skype for Business Server-Benutzer, der im Pool verwaltet wird und für die Verwaltung des Besprechungszeitplans verantwortlich ist, über die entsprechenden Berechtigungen verfügt. Gehen Sie hierzu wie folgt vor:
  
- Legen Sie die Option **Als Referenten festlegen** auf **Keine** fest. Normalerweise sind nur einige wenige Benutzer der gesamten Teilnehmer einer großen Besprechung Referenten, sodass die Teilnehmer nicht automatisch als Referenten für große Besprechungen zugelassen werden sollten. Die Referenten sollten stattdessen bei der geplanten Besprechung explizit festgelegt oder während der großen Besprechung explizit ernannt werden.
    
- Stellen Sie sicher, dass das **standardmäßige** Kontrollkästchen "Zugewiesener Konferenztyp" nicht aktiviert ist. Diese Einstellung steuert, ob das Onlinebesprechungs-Add-In für Skype for Business Konferenzen immer mithilfe der vom Organisator zugewiesenen Konferenz plant, was bedeutet, dass geplante Besprechungen dieselbe Teilnahme-URL und dieselben Audioinformationen haben. In Szenarien für die Zusammenarbeit in kleinen Gruppen funktioniert dies gut, da jeder über eine eigene konferenz zugewiesene Konferenz verfügt, und die konstante Teilnahme-URL und Audioinformationen helfen, den schnelleren Besprechungs beitritt zu erleichtern. Im Szenario für große Besprechungen planen die Supportmitarbeiter für große Besprechungen jedoch große Besprechungen mit einem einzigen Satz von Benutzeranmeldeinformationen und stellen den Besprechungsanfragern dann URLs und Audioinformationen zur Teilnahme zur Verfügung. In diesem Fall funktioniert die Verwendung einer anderen URL für die Teilnahme an jeder Besprechung besser.
    
- Stellen Sie sicher, dass das Kontrollkästchen **Anonyme Benutzer standardmäßig zulassen** nur aktiviert wird, wenn es erforderlich ist. Diese Einstellung wirkt sich auf den standardmäßigen Besprechungszugriffstyp aus, der vom Online-Besprechungs-Add-In für Skype for Business geplant wird, wenn keine zugewiesene Konferenz verwendet wird. Die entsprechende Option für diese Einstellung hängt von den Anforderungen Ihrer Organisation ab. Wenn die meisten großen Besprechungen in Ihrer Organisation interne Besprechungen sind, sollte diese Option nicht ausgewählt werden. Wenn beim Großteil der großen Besprechungen externe Benutzer teilnehmen, sollte diese Option ausgewählt werden.
    
Weitere Informationen zum Erstellen einer Konferenzrichtlinie finden Sie unter "Verwalten von [Konferenzrichtlinien in Skype for Business Server".](../../manage/conferencing/conferencing-policies.md)
  

