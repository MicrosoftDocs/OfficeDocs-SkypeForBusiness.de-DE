---
title: Planen großer Besprechungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 21507e18-bd79-4019-9c3a-0867fccaa3b4
description: 'Zusammenfassung: Lesen Sie dieses Thema, um Informationen zu bewährten Methoden für das Implementieren und Verwalten von umfangreichen Besprechungen in Skype for Business Server zu erhalten.'
ms.openlocfilehash: 136896a45be36508af419d84bc5bd684c9d8a429
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "34696043"
---
# <a name="plan-for-large-meetings-in-skype-for-business-server"></a>Planen großer Besprechungen in Skype for Business Server
 
**Zusammenfassung:** In diesem Thema finden Sie Informationen zu bewährten Methoden zum Implementieren und Verwalten von umfangreichen Besprechungen in Skype for Business Server.
  
Die Größe von Besprechungen, die von Skype for Business Server unterstützt werden können, hängt davon ab, ob Konferenzen in einem freigegebenen oder dedizierten Pool gehostet werden: von 250 Teilnehmern an einem freigegebenen Pool bis zu 1000 Teilnehmern an einem dedizierten Pool. 
  
> [!NOTE]
> In diesem Thema werden bewährte Methoden für umfangreiche Besprechungen behandelt, die von Skype for Business Server unterstützt werden. Wenn in Ihrer Organisation größere Besprechungsfunktionen erforderlich sind, sollten Sie eine Hybridumgebung implementieren, die Skype-Live Konferenz, einen neuen Onlinedienst, der Teil von Office 365 ist, nutzt. 

> [!NOTE]
> Skype-Livekonferenz ermöglicht Benutzern, Besprechungen von bis zu 10.000 Teilnehmern zu hosten und an ein ebenso großes Online-Publikum zu übertragen. Für die Nutzung von Skype-Livekonferenz muss Skype for Business Server bereits in einer Hybridumgebung mit einem Office 365-Produktionsmandanten konfiguriert sein. Als Grundvoraussetzung muss bei allen Benutzern ein Online-Mandant eingerichtet sein. Wenn Sie an der Bereitstellung einer Hybridlösung interessiert sind, die die Vorteile von Skype-Live Konferenz nutzen kann, lesen Sie [Was ist eine Skype-Live Konferenz?](https://go.microsoft.com/fwlink/?LinkId=617071) und [Konfigurieren Sie Ihre lokale Bereitstellung für Skype](../../deploy/configure-skype-meeting-broadcast.md)-Live Konferenz. 
  
Große Besprechungen weisen in der Regel folgende Merkmale auf:
  
- Das Besprechungsformat entspricht einem 1:n-Format.
    
- Ein oder wenige Benutzer fungieren als Referenten, und alle anderen Benutzer sind Teilnehmer.
    
- Die Freigabe von PowerPoint-Präsentationen stellt die Hauptaktivität hinsichtlich der Datenzusammenarbeit dar.
    
- Die Übertragung von Audiosignalen ist erforderlich, Videobilder können ebenfalls übertragen werden.
    
- Eine bestimmte Person, bei der es sich meist um den Organisator der Besprechung oder um einen Assistenten handelt, richtet die Besprechung rechtzeitig im Voraus ein.
    
- Spezielle Mitarbeiter (nicht die Referenten) führen durch die Besprechung, kümmern sich um das Herstellen von Verbindungen zu Onlinebesprechungen, stellen sicher, dass das Teilen von Audio-, Video- und Folieninhalten funktioniert, verwalten den Wartebereich und die Benutzerrollen, schalten Teilnehmer stumm bzw. heben deren Stummschaltung auf, nehmen Fragen entgegen und verwalten Aufzeichnungen nach Bedarf.
    
Wenn ein Benutzer eine Besprechung plant, erstellt Skype for Business Server einen Eintrag in der Konferenzdatenbank, in dem Konferenzdaten gespeichert werden, reserviert aber keine Hardwareressourcen für die geplante Besprechung im voraus. Stattdessen verfügt Skype for Business Server über integrierte Load-Balancing-Logik, um Konferenzressourcen auf Front-End-Servern so dynamisch zuzuteilen, dass Lasten gleichmäßig über alle Front-End-Server im Pool verteilt werden. Diese Bestimmungen und Verwendung von Hardwareressourcen sind zwar effektiv, doch ist es wichtig, dass Sie die Unterstützung sehr großer Besprechungen entsprechend planen. 
  
Wenn beispielsweise ein Skype for Business-Serverpool nahezu an seiner obersten Kapazität ausgeführt wird, kann jeder Front-End-Server ungefähr 125-Besprechungen mit durchschnittlicher Größe hosten. Das Hinzufügen einer weiteren kleinen Besprechung wäre kein Problem, doch das Hinzufügen einer Besprechung für 1000-Benutzer wäre ein Problem, da die Front-End-Server wahrscheinlich nicht in der Lage sind, eine so große Besprechung zur gleichen Zeit wie die anderen 125-Besprechungen zu unterstützen.
  
Die Unterstützung großer Besprechungen mit bis zu 1.000 Teilnehmern macht es erforderlich, dass auch Probleme im Zusammenhang mit dem Hardwarefreigabemodell und dem Verzicht auf reservierte Ressourcen behandelt werden. Im Allgemeinen müssen Sie einen dedizierten Pool planen und bewährte Methoden wie in den folgenden Abschnitten beschrieben befolgen. 
  
## <a name="plan-for-a-dedicated-pool"></a>Planung für einen dedizierten Pool

Wenn in Ihrem Unternehmen Besprechungen mit mehr als 250 Teilnehmer erforderlich sind, brauchen Sie einen Plan für einen dedizierten Pool, damit diese Lasten unterstützt werden können. 
  
Um ausreichende Speicherressourcen sowie die erforderliche CPU-Leistung für Besprechungen mit bis zu 1.000 Teilnehmern bereitstellen zu können, sollten auf dem Front-End-Server, der als Host fungiert, keine anderen Sofortnachrichten-, Anwesenheits- oder Enterprise-VoIP-Arbeitslasten verarbeitet werden. Auch auf das Hosten anderer Besprechungen durch die Server sollte unabhängig von ihrer Größe verzichtet werden. Wenn Sie Besprechungen mit bis zu 1000 Benutzern hosten möchten, müssen Sie einen separaten Skype for Business-Server Pool einrichten, der für das Hosten großer Besprechungen dediziert ist.
  
Ein Skype for Business-Server Pool, der für das Hosten von umfangreichen Besprechungen dediziert ist, sollte nur eine Besprechung mit bis zu 1000 Benutzern gleichzeitig hosten, sodass Besprechungszeiten im Voraus über einen Out-of-Band-Planungsprozess reserviert werden müssen, um eine dedizierte Unterstützung durch die Front-End-Server. Wenn Sie mehr als eine große Besprechung gleichzeitig unterstützen möchten, sollten Sie mehrere dedizierte groß-Besprechungs Pools einrichten.
  
Weitere Informationen zu den Hardware-und Softwareanforderungen sowie zum Planen einer Topologie, die umfangreiche Besprechungen unterstützt, finden Sie unter [Hardware-und Softwareanforderungen für Konferenzen in Skype for Business Server](hardware-and-software-requirements.md) und [Planen der Konferenz Topologie für Skype for Business Server](conferencing-topology.md).
  
## <a name="implement-best-practices-for-large-meetings"></a>Einführung von Best Practices für große Besprechungen

Nach dem Einrichten eines dedizierten Pools für große Besprechungen können Sie Schritte unternehmen, um sicherzustellen, dass die in diesem Pool gehosteten großen Besprechungen die beste Benutzererfahrung bieten. Die folgenden Abschnitte enthalten Richtlinien zum Verwalten großer Besprechungen:
  
- Anlegen von dedizierten Besprechungsorganisatoren
    
- Anlegen von dedizierten Moderatoren
    
- Pflege eines separaten Kalenders zur Verwaltung von großen Besprechungen
    
- Implementieren eines Planungsprozesses für große Besprechungen
    
- Definieren von angemessenen Planungsdetails
    
- Erstellen einer Konferenzrichtlinie für große Besprechungen
    
### <a name="create-dedicated-meeting-organizers"></a>Anlegen von dedizierten Besprechungsorganisatoren

Zum Minimieren des Echt Zeit Datenverkehrs im großzügigen Besprechungs Pool empfiehlt Microsoft nicht das Hosten von Benutzern, die sich regelmäßig mit Skype for Business-Clients anmelden und an Instant Messaging (im), Anwesenheits-, Konferenz-und sprach Sitzungen teilnehmen. Gehen Sie stattdessen wie folgt vor:
  
- Erstellen Sie ein oder mehrere dedizierte Benutzerkonten nur für die Planung großer Besprechungen
    
- Verwalten Sie die Benutzerkonten der Mitarbeiter, die für die Planung großer Besprechungen zuständig sind, in einem großen Besprechungspool
    
### <a name="create-dedicated-moderators"></a>Anlegen von dedizierten Moderatoren

Mit mehreren hundert bis tausend Benutzern in einer Besprechung empfiehlt es sich, eine dedizierte Person für die Onlinesitzung einer umfangreichen Besprechung zu moderieren. Diese dedizierte Person kann eine Stellvertretung des Besprechungsorganisators oder ein Mitglied des Support Teams für groß Besprechungen der Organisation sein. Es ist wichtig, dass der dedizierte Besprechungs Moderator zu dem Zeitpunkt, zu dem die Besprechung geplant ist, als Referent hinzugefügt wird, obwohl es möglich ist, einen Onlinebesprechungsteilnehmer zur Referenten Rolle zu bewerben, während die Besprechung gerade ausgeführt wird.
  
Der Moderator der Besprechung kann alle Referenten Funktionen von Skype for Business-Clients verwenden, um die große Besprechung zu verwalten. Hierzu zählen folgende Funktionen:
  
- Überwachen des Wartebereichs und Zulassen bzw. Ablehnen von Benutzern im Wartebereich
    
- Entfernen von Benutzern, die nicht an der Besprechung teilnehmen sollten
    
- Ändern der Besprechungszugriffstypen
    
- Ändern der Teilnehmerrollen
    
- Einladen weiterer Teilnehmer während der Besprechung mithilfe der Drag & Drop-Funktion, Telefonwahl oder e-Mail
    
- Stummschalten und Aufheben der Stummschaltung für die Zielgruppe oder für einzelne Benutzer
    
- Verwalten der Besprechungsinhalte, einschließlich Hochladen von Inhalten, Löschen von Inhalten und Auswählen der aktiven Inhalte

    
### <a name="maintain-a-separate-calendar"></a>Pflege eines separaten Kalenders

Für jeden Pool für große Besprechungen sollte ein eigener Kalender verwaltet werden, in dem die großen Besprechungen verzeichnet sind, die in diesem Pool geplant sind. So können Sie beispielsweise ein einzelnes Benutzerkonto im großzügigen Besprechungs Pool einrichten und Outlook mit dem Exchange-und Online Besprechungs-Add-in für Skype for Business verwenden, um einen separaten Kalender zu verwalten. Wenn Sie mehrere Benutzerkonten verwenden, um Supportmitarbeitern das Erstellen großer Besprechungen zu ermöglichen, können Sie einen separaten Kalender einrichten, in dem alle großen Besprechungen festgehalten werden, die von Supportmitarbeitern erstellt werden. 
  
Durch das Verwalten eines separaten Kalenders für Besprechungen vermeiden Sie Konflikte und stellen sicher, dass zu einem bestimmten Zeitpunkt immer jeweils nur eine große Besprechung stattfinden kann.
  
### <a name="implement-a-scheduling-process"></a>Implementieren eines Planungsprozesses

Da im dedizierten, umfangreichen Besprechungs Pool nur jeweils eine große Besprechung unterstützt wird, sollten Sie einen umfangreichen Besprechungs Planungsprozess implementieren, um das Einrichten großer Besprechungen zu vereinfachen und Konflikte zu vermeiden. Diese Funktion wird nicht direkt von Skype for Business Server oder Skype for Business-Clients bereitgestellt. Eine Möglichkeit zur Implementierung eines solchen Prozesses besteht darin, das Ticketing-System Ihres Unternehmens zu verwenden, sofern verfügbar.
  
Die Planung einer großen Besprechung umfasst die folgenden Schritte:
  
- Der Besprechungsorganisator oder die delegierte Person bestimmt den Zeitpunkt, die Dauer und den Umfang einer anstehenden Besprechung sowie die Liste der Referenten. Falls der erwartete Besprechungsumfang 250 Benutzer überschreitet, oder um die optimale Funktionalität für eine Besprechung mit weniger als 250 Benutzern sicherzustellen, reicht der Organisator oder die delegierte Person einen Antrag für eine große Besprechung ein.
    
- Die Planungsmitarbeiter überprüfen, ob der angeforderte Termin verfügbar ist. Da jeweils immer nur eine einzige große Besprechung im Pool unterstützt wird, müssen die Planungsmitarbeiter anhand des Kalenders für große Besprechungen feststellen, ob für den angeforderten Termin bereits eine andere Besprechung geplant ist. Falls der angeforderte Termin verfügbar ist, wird die Besprechungsanfrage genehmigt.
    
- Wenn die Anforderung genehmigt wurde, verwendet das Planungs Personal (mithilfe von Anmeldeinformationen im dedizierten Pool) das Online Besprechungs-Add-in für Skype for Business mit Outlook, um eine Besprechung im dedizierten groß Besprechungs Pool einzurichten. Die URL für die Teilnahme an der Besprechung wird dem Antragsteller im Rahmen des Genehmigungshinweises bereitgestellt.
    
- Der Besprechungsorganisator oder die delegierte Person plant mithilfe von Outlook die anstehende Besprechung und fügt die URL für die Teilnahme an der Besprechung der Besprechungseinladung hinzu. Der Besprechungsorganisator oder die delegierte Person legt dann die Benutzer fest, die eingeladen werden sollen, und versendet die Besprechungseinladung.
    
### <a name="specify-appropriate-scheduling-details"></a>Definieren von angemessenen Planungsdetails

Nachdem sichergestellt wurde, dass zum angefragten Zeitpunkt keine weitere Besprechung anberaumt ist, planen die zuständigen Supportmitarbeiter die Besprechung im Pool für große Besprechungen ein. 
  
Um eine optimale Benutzererfahrung zu gewährleisten, ist es wichtig, die große Besprechung mit den richtigen Zugriffsebenen und Besprechungseinstellungen zu planen, die den Anforderungen des Besprechungsorganisators entsprechen. Bedenken Sie die folgenden Planungseinstellungen, die in den Skype for Business-Besprechungsoptionen konfiguriert sind:
  
- Verwenden Sie einen neuen Besprechungsraum für jede große Besprechung, anstatt den dedizierten Besprechungsraum erneut zu verwenden. 
    
- Geben Sie die Zugriffsebene für die Besprechung wie folgt an:
    
  - Wenn mindestens ein eingeladener Benutzer nicht zur Organisation gehört, legen Sie den Zugriffstyp für die Besprechung auf **Alle Personen (keine Einschränkungen)** fest. Dadurch vermeiden Sie, dass Sie während der laufenden Besprechung einen möglicherweise großen Wartebereich verwalten müssen.
    
  - Wenn die Besprechung nur intern ist, legen Sie den Zugriffstyp für die Besprechung auf **Jeder innerhalb meiner Organisation** fest.
    
    > [!NOTE]
    > Vermeiden Sie die Festlegung des Besprechungszugriffs Typs für Personen, die **ich aus meinem Unternehmen einlade** , denn wenn Sie diese Einstellung verwenden, müssen Organisatoren alle Benutzer-e-Mail-Adressen zur Liste der eingeladenen hinzufügen, und Sie können keine Verteilergruppe einladen. Vermeiden Sie es, den Besprechungs Zugriffstyp **nur auf ich, den Organisator der Besprechung** , festzulegen, da für diese Einstellung erforderlich ist, dass jeder Besprechungsteilnehmer, einschließlich Referenten, zur Besprechungs Laufzeit in die Lobby gestellt wird. Die Person, die für die Ausführung der umfangreichen Besprechung verantwortlich ist, muss die Lobby Liste ständig überwachen und neue Benutzer in der Lobby aufnehmen.
  
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
    
- Überprüfen Sie die Videoeinstellungen der **Teilnehmer blockieren** , um sicherzustellen, dass nur Referenten Video in die Besprechung übertragen können.
    
### <a name="create-a-conferencing-policy"></a>Erstellen einer Konferenzrichtlinie

Erstellen Sie eine neue Konferenzrichtlinie speziell für große Besprechungen und weisen Sie sie anschließend den Benutzern zu, die auf den dedizierten großen Besprechungspools gehostet werden. Mithilfe der folgenden Einstellungen können Sie die Konferenzrichtlinie konfigurieren:
  
- Setzen Sie die Option **MaxMeetingSize** auf 1000. (Der Standardwert ist 250.)
    
- Legen Sie die Option **AllowLargeMeetings** auf **True** fest. 
    
- Legen Sie die Option **EnableAppDesktopSharing** auf **None** fest.
    
- Legen Sie die Option **AllowUserToScheduleMeetingsWithAppSharing** auf **False** fest.
    
- Legen Sie die Option **AllowSharedNotes** auf **False** fest.
    
- Legen Sie die Option **AllowAnnotations** auf **False** fest.
    
- Legen Sie die Option **DisablePowerPointAnnotations** auf **True** fest.
    
- Legen Sie die Option **AllowMultiview** auf **False** fest.
    
- Legen Sie die Option **EnableMultiviewJoin** auf **False** fest.
    
> [!NOTE]
> Die Unterstützung für große Besprechungen in Skype for Business Server setzt voraus, dass die **AllowLargeMeetings** -Einstellung auf "true" festgelegt ist. Wenn diese Einstellung auf "true" festgelegt ist, wird die Skype for Business-Benutzeroberfläche für besonders große Besprechungen optimiert, wenn Benutzer an der Besprechung teilnehmen. Insbesondere in einer umfangreichen Besprechung wird in Skype for Business nicht das erste oder das Update der vollständigen Besprechungsteilnehmer Liste angezeigt, was ein Leistungsengpass für den Client und den Skype for Business-Server darstellt. Stattdessen werden in Skype for Business nur Informationen über den Benutzer und die Liste der Referenten der Besprechung angezeigt. Skype for Business zeigt weiterhin die Gesamtzahl der Teilnehmer an, die in den umfangreichen Besprechungen zur Verfügung stehen.

Die **AllowLargeMeetings $true** -Einstellung bewirkt Folgendes:

- Blendet die Teilnehmerliste aus. 

- Deaktiviert Fehler im Chatfenster.

- Deaktiviert Video mit mehreren Teilnehmern.

- Deaktiviert die Möglichkeit zum Heraufstufen eines Teilnehmers zum Referenten. Sie müssen voraus planen und alle Referenten vor der Besprechung deklarieren.

- Deaktiviert die Möglichkeit zum Aufheben der Stummschaltung einzelner Teilnehmer.

- Deaktiviert die Möglichkeit, das Feature "Video Spotlight sperren" auf Teilnehmer anzuwenden.

- Das PSTN-einwählen in den Benutzern kann die Stummschaltung selbst nicht mithilfe von 6 aufheben, da die persönliche virtuelle Unterstützung, die für DTMF-Befehle in aktiven groß Besprechungen zuständig ist, nicht vorhanden ist.

- Wenn der Referent/Organisator eine Besprechung plant, in der jeder zuerst stumm geschaltet werden soll ("alle stumm schalten"), werden PSTN-Benutzer während des gesamten Anrufs stumm geschaltet und können die Stummschaltung selbst nicht aufheben.

Mit Ausnahme der Einstellung **Maximale Besprechungsgröße** sind alle anderen hier angegeben Konferenzrichtlinieneinstellungen erforderlich, um die Konferenzfunktionen, die für große Besprechungen nicht erforderlich sind, zu deaktivieren.
  
Darüber hinaus müssen Sie den dedizierten Pool für große Besprechungen so konfigurieren, dass jeder Skype for Business Server-Benutzer, der sich im Pool befindet und für die Verwaltung des Besprechungs Zeitplans verantwortlich ist, über die entsprechenden Berechtigungen verfügt. Gehen Sie hierzu wie folgt vor:
  
- Legen Sie die Option **Als Referenten festlegen** auf **Keine** fest. Normalerweise sind nur einige wenige Benutzer der gesamten Teilnehmer einer großen Besprechung Referenten, sodass die Teilnehmer nicht automatisch als Referenten für große Besprechungen zugelassen werden sollten. Die Referenten sollten stattdessen bei der geplanten Besprechung explizit festgelegt oder während der großen Besprechung explizit ernannt werden.
    
- Stellen Sie sicher, dass das Kontrollkästchen **zugewiesene Konferenztyp Standard** mäßig nicht aktiviert ist. Mit dieser Einstellung wird gesteuert, ob das Online Besprechungs-Add-in für Skype for Business immer Konferenzen mit der zugewiesenen Konferenz des Organisators plant, was bedeutet, dass geplante Besprechungen über die gleiche URL und Audioinformationen für die Teilnahme verfügen. In Szenarien für die Zusammenarbeit in kleinen Gruppen funktioniert der zugewiesene Konferenztyp gut, weil jeder eine eigene, individuell zugewiesene Konferenz hat, und die URL-und Audioinformationen für die dauerhafte Teilnahme helfen, eine schnellere Besprechung zu ermöglichen. Im Szenario mit großer Besprechung plant der große Besprechungs Support die umfangreichen Besprechungen jedoch mit einem einzigen Satz von Benutzeranmeldeinformationen und stellt dann den Besprechungs anfordernden Teilnehmer-URLs und Audioinformationen zur Verfügung. In diesem Fall funktioniert die Verwendung einer anderen URL für die Teilnahme an jeder Besprechung besser.
    
- Stellen Sie sicher, dass das Kontrollkästchen **Anonyme Benutzer standardmäßig zulassen** nur aktiviert wird, wenn es erforderlich ist. Diese Einstellung wirkt sich auf den standardmäßigen Besprechungs Zugriffstyp aus, der vom Online Besprechungs-Add-in für Skype for Business geplant wird, wenn keine zugewiesene Konferenz verwendet wird. Die geeignete Option für diese Einstellung hängt von den Anforderungen Ihrer Organisation ab. Wenn die meisten großen Besprechungen in Ihrer Organisation interne Besprechungen sind, sollte diese Option nicht ausgewählt werden. Wenn beim Großteil der großen Besprechungen externe Benutzer teilnehmen, sollte diese Option ausgewählt werden.
    
Weitere Informationen zum Erstellen einer konferenzrichtlinie finden Sie unter [Verwalten von Konferenzrichtlinien in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).
  

