---
title: Planen von automatischen Telefonkonferenzen und Anrufwarteschleifen für Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
description: Erfahren Sie mehr über automatische Telefonkonferenzen und Anrufwarteschlangen und deren Verwendung, um Anrufern zu helfen, durch ein Menüsystem zu wechseln, um Personen oder Abteilungen in Ihrer Organisation zu erreichen.
ms.openlocfilehash: 2944f7b4add49b136d56620f41a2a1afb1a30a92
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460725"
---
# <a name="plan-for-teams-auto-attendants-and-call-queues"></a>Planen von automatischen Telefonkonferenzen und Anrufwarteschleifen für Teams

Mit automatischen Telefonkonferenzen können Sie Menüoptionen einrichten, um Anrufe basierend auf der Anrufereingabe weiterzurouten. Menüoptionen, z. B. "Für Vertrieb, drücken Sie 1.  Für Dienste drücken Sie 2", damit eine automatische Telefonkonferenz einer Organisation eine Reihe von Auswahlmöglichkeiten zur Verfügung stellt, die Anrufer schnell an ihr Ziel führen, ohne sich bei eingehenden Anrufen auf einen menschlichen Operator verlassen zu müssen.

Anrufwarteschlangen sind Wartebereiche für Anrufer. In Situationen, in denen Anrufer eine person mit einer bestimmten Spezialität (z. B. Vertrieb oder Dienstleistung) anstelle einer bestimmten Person erreichen müssen, können Sie Anrufer mithilfe von Anrufwarteschleifen mit der Gruppe von Agenten verbinden, die ihnen helfen können. Anrufer werden in den Halteraum gestellt, bis ein agent, der der Warteschlange zugewiesen ist, verfügbar ist, um ihren Anruf zu führen.

Wenn sie zusammen verwendet werden, können automatische Telefonanrufe und Anrufwarteschlangen Anrufer ganz einfach an die entsprechende Person oder Abteilung in Ihrer Organisation weiterzusenden.

## <a name="auto-attendants"></a>Automatische Telefonzentralen

Der Hauptzweck einer automatischen Telefonkonferenz besteht in der Direkten Anwahl eines Anrufers an eine geeignete Person oder Abteilung basierend auf der Eingabe des Anrufers zu den bereitgestellten Menüoptionen. Anrufer können an bestimmte Personen in Ihrer Organisation, an Anrufwarteschlangen, in denen sie warten, bis sie mit dem nächsten verfügbaren Mitarbeiter sprechen, oder an voicemail geleitet werden. Für Geschäftszeiten, Arbeitsstunden und Feiertage können unterschiedliche Anrufroutingoptionen angegeben werden.

Menüanforderungen können mithilfe von Text-zu-Sprache (systemgenerierte Eingabeaufforderungen) oder durch Hochladen einer aufgezeichneten Audiodatei erstellt werden. Die Spracherkennung akzeptiert Sprachbefehle für die freihändige Navigation, aber Anrufer können auch die Telefontaste verwenden, um in Menüs zu navigieren.

Jede automatische Attendant verfügt über eine bestimmte Sprache und Zeitzone. Wenn Sie Geschäfte in mehreren Sprachen oder in mehreren Teilen der Welt unternehmen, können Sie so viele verschiedene automatische Telefonkonferenzen erstellen, wie Sie benötigen, um Ihre Anrufer unterbringen zu können.

Für jede automatische Attendant können Sie einen Operator konfigurieren. Während Sie Operatoranrufe konfigurieren können, um zu einer Vielzahl von Zielen zu wechseln, ist das Operatorfeature so konzipiert, dass Anrufer mit einer bestimmten Person in Ihrer Organisation sprechen können, die ihnen helfen kann.

Automatische Telefon attendants can be configured to allow callers to search your organization's directory, either by name or by extension number. In einer automatischen Telefonwarte können Sie angeben, wer für die Verzeichnissuche verfügbar ist, indem Sie Benutzergruppen auswählen, die sie ein- oder ausschließen möchten. (Dies wird als *Wählbereich bezeichnet.)*

Anrufer können eine automatische Telefonkonferenz entweder über eine direkte Telefonnummer, sofern konfiguriert, oder durch Umleiten von einer anderen automatischen Telefonkonferenz oder einer Anrufwarteschleife erreichen.

## <a name="call-queues"></a>Anrufwarteschleifen

Eine Anrufwarteschlange entspricht einem Warteraum in einem physischen Gebäude. Anrufer warten im Halteraum, während Anrufe an die Agenten in der Warteschlange gesendet werden. Anrufwarteschlangen werden häufig für Vertriebs- und Dienstfunktionen verwendet. Anrufwarteschlangen können jedoch für alle Situationen verwendet werden, in denen die Anzahl der Anrufe Ihre interne Kapazität überschreitet, z. B. einen Empfangsisten in einer geschäftigen Einrichtung.

Anrufwarteschlangen ermöglichen ein bestimmtes Routing von Anrufen in Fällen, in denen die Gesamtanzahl der Anrufer in der Warteschlange oder die Wartezeit die von Ihnen angegebenen Grenzwerte überschreitet. Anrufe können an bestimmte Personen, Voicemails, andere Anrufwarteschlangen oder automatische Telefonkonferenzen gesendet werden.

Wie automatische Telefonwarteschlangen verfügen anrufwarteschlangen jeweils über eine Spracheinstellung. Sie können verschiedene Anrufwarteschlangen verwenden, wenn Sie Geschäfte in mehreren Sprachen unternehmen. Agents können Mitglieder von mehreren Warteschlangen sein, wenn sie mehrsprachig sind.

Für jede Anrufwarteschlange können Sie angeben, ob Agenten in der Warteschlange die Anrufannahme abmelden können und ob Anrufe basierend auf der Anwesenheitsanzeige in Teams an sie weitervermittelt werden sollen.

Sie können einer Anrufwarteschlange eine Telefonnummer zuweisen, aber Anrufwarteschlangen bieten keine separate Anrufrouting für Off-Hours und Feiertage. Sofern Ihre Anrufwarteschlange nicht rund um die Uhr besetzt ist, empfehlen wir, die Telefonnummer einer automatischen Telefonleitung zuzuordnen, die während der Geschäftszeiten an die Anrufwarteschlange umgeleitet wird.

## <a name="prerequisites"></a>Voraussetzungen

Zum Konfigurieren von automatischen Telefonkonferenzen und Anrufwarteschlangen benötigen Sie die folgenden Ressourcen:

- Ein Ressourcenkonto für jede automatische Telefonkonferenz und jede Anrufwarteschlange
- Kostenloses Telefonsystem – Lizenz für virtuelle Benutzer für jedes Ressourcenkonto
- Mindestens eine [Microsoft-Dienstnummer,](getting-service-phone-numbers.md)eine direkte Routingnummer oder eine Hybridnummer für jedes Ressourcenkonto, das direkt gewählt werden soll
 - Die Servicenummer kann eine gebührenfreie oder gebührenfreie Nummer sein.

Agenten, die Anrufe aus den Anrufwarteschlangen empfangen, müssen Enterprise-VoIP oder lokale Benutzer aktiviert sein. Wenn die Anrufwarteschlangen direkte Routingnummern verwenden, benötigen Die Mitarbeiter, die Anrufe anstellen oder übertragen müssen, außerdem:

- Eine online zugewiesene Sprachroutingrichtlinie, wenn die Anrufwarteschlange den Übertragungsmodus verwendet
- Eine Lizenz für Audiokonferenzen oder eine Online-Voiceroutingrichtlinie wird zugewiesen, wenn die Anrufwarteschlange den Konferenzmodus verwendet

Wenn Ihre Mitarbeiter die Microsoft Teams-App für Anrufwarteschlangenanrufe verwenden, müssen sie sich im TeamsOnly-Modus befinden.

Wenn Anrufe an eine externe Telefonnummer übertragen werden, muss das Ressourcenkonto, das die Übertragung (d. h. das der automatischen Telefonkonferenz oder Anrufwarteschlange zugeordnete Konto) über eine virtuelle Microsoft 365 Phone System-Benutzerlizenz und eine der folgenden Zugewiesenen verfügen:

- Lizenz [für einen Anrufplan](calling-plans-for-office-365.md)
- Eine [Online-Voiceroutingrichtlinie](manage-voice-routing-policies.md)

> [!NOTE]
> Direkte Routingdienstnummern für automatische Telefonkonferenzen und Anrufwarteschlangen werden nur für Microsoft Teams-Benutzer und Anrufermitarbeiter unterstützt.<br>
> Übertragungen zwischen Anrufplan-Trunks und Direct Routing-Trunks werden nicht unterstützt.<br>
> In einem Hybridszenario muss das Ressourcenkonto lokal erstellt werden. Weitere Informationen finden Sie unter [Planen von Cloudanrufwarteschlangen](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-queue).

## <a name="business-decisions"></a>Geschäftsentscheidungen

Bevor Sie Ihre automatischen Telefonkonferenzen und Anrufwarteschlangen einrichten, sollten Sie einige Entscheidungen treffen, wie Sie diese Features in Ihrem Unternehmen verwenden. Diese Entscheidungen bestimmen die Einstellungen, die Sie beim Konfigurieren ihrer automatischen Telefonkonferenzen und Anrufwarteschlangen auswählen.

Dokumentieren Sie Ihre Antworten auf diese Fragen, und geben Sie die Informationen an den Administrator weiter, der die Konfiguration vor sich hat.

- Welche Sprachen benötigen Sie? Wo sind diese Sprachen erforderlich – welche Abteilung oder Gruppe?
- Möchten Sie Spracheingaben von Anrufern oder nur Wähleingaben zulassen?
- Benötigen Sie separates Anrufrouting für Off-Hours oder Feiertage? Was sind die Stunden und Feiertage?
- Möchten Sie es Denkmitarbeitern in einer Anrufwarteschlange ermöglichen, anrufe nicht zu nehmen?
- Möchten Sie, dass Mitarbeiter in Ihren Anrufwarteschlangen oder Ihr Operator eine bestimmte Anrufer-ID haben, wenn sie sich auswählen?
- Möchten Sie das Parken und Abrufen von Anrufen [in](call-park-and-retrieve.md) Ihrer Organisation aktivieren, um Anrufabrufe zwischen Personen oder Abteilungen zu unterstützen?
- Möchten Sie für die Sprachanforderungen Ihre eigene Aufzeichnen oder die vom System generierte Stimme verwenden? (Die vom System generierte Sprachsteuerung ist einfach zu aktualisieren.)

## <a name="technical-decisions"></a>Technische Entscheidungen

Wenn Sie automatische Telefonkonferenzen und Anrufwarteschlangen verwenden, um Anrufer mit Personen in Ihrer Organisation zu verbinden, müssen Sie einige technische Entscheidungen treffen, bevor Sie mit der Konfiguration beginnen.

Agents können auf folgende Weise zu Anrufwarteschlangen hinzugefügt werden:

- Einzelne Benutzer
- Verteilerlisten
- Sicherheitsgruppen, einschließlich E-Mail-aktivierter Sicherheitsgruppen
- Microsoft 365-Gruppen oder Teams

Sie können bei Bedarf eine Kombination dieser Optionen für jede Warteschlange verwenden. Gruppen mit einer E-Mail-Adresse können für Voicemail verwendet werden. Die Verwendung von Teams bietet eine Reihe von Vorteilen, z. B. freigegebenen Dateispeicher und Chats zwischen Agents, ein allgemeines Postfach, in dem Voicemails empfangen werden können, und eine erweiterbare Plattform, die die Integration in Ihre Geschäftsanwendungen oder Power Apps umfassen kann.

Wir empfehlen, eine Strategie zum Hinzufügen von Anrufer zu Warteschlangen zu wählen, bevor Sie mit der Konfiguration beginnen.

Wenn Sie über eine automatische Telefonwarteschlange und eine Anrufwarteschlange verfügen und zu Teams migrieren, benötigen Sie einen Plan, um Ihre vorhandenen Telefonnummern an die neuen automatischen Telefonwarteschlangen und Anrufwarteschlangen zu übertragen. Möglicherweise müssen Sie einen [Portierungsauftrag erstellen,](phone-number-calling-plans/port-order-overview.md) um Ihre Nummern von einem anderen Anbieter zu verschieben. Es wird empfohlen, vorübergehend eine oder mehrere neue Telefonnummern zu erwerben und die automatische Telefonwarteschlange und die Anrufwarteschlange zu testen, bevor Sie sie über die aktuell in Betrieb bzw. im Dienst gespeicherten Nummern wechseln.

*Der Konferenzmodus* ist eine Option in Anrufwarteschlangen, die die Zeit zum Verbinden von Teams-VOIP-Anrufen und PSTN-Anrufen mit einem Agent erheblich reduziert. Damit der Konferenzmodus funktioniert, müssen die Telefonberater in der Anrufwarteschleife einen der folgenden Clients verwenden:

- Die neueste Version des Microsoft Teams-Desktopclients, der Android-App oder der iOS-App
  - Microsoft Teams Telefon, Version 1449/1.0.94.2020051601 oder höher
  
Legen Sie die Teams-Konten der Agents auf den Modus "Nur Teams" ein. Telefonberater, die diese Anforderungen nicht erfüllen, werden nicht in die Anrufweiterleitungsliste aufgenommen.

Es wird empfohlen, den Konferenzmodus für Ihre Anrufwarteschleifen zu aktivieren, wenn alle Ihre Telefonberater kompatible Clients verwenden.

## <a name="plan-your-call-routing-flow"></a>Planen des Anrufroutingflusses

Im Rahmen des Planungsprozesses wird empfohlen, das Anrufrouting für Ihre Organisation in einem Diagramm zu erstellen. Das Diagramm hilft Ihnen, das effizienteste Routing für Personen zu ermitteln, die sich bei Ihrer Organisation einschalten. Sie können das Diagramm auch verwenden, um die automatischen Telefonwarteschlangen und Anrufwarteschlangen zu ermitteln, die Sie erstellen müssen, sowie verwandte Anforderungen wie Servicenummern, Lizenzen und Ressourcenkonten.

Sehen wir uns an, wie automatische Telefonkonferenzen und Anrufwarteschlangen Anrufe routen.

Automatische Telefon attendants route all calls in one of the following ways:

- **Sofort umleiten** – Anrufe können direkt nach der Beantwortung oder nach einer ersten Begrüßung an eines der Anrufroutingziele (unten aufgeführt) umgeleitet werden.
- **Umleitung basierend auf Wähloptionen** – Anrufer können zur Auswahl zwischen Optionen geleitet werden, die den Nummern auf der Telefontaste 0-9 zugewiesen sind. Jeder Wähltaste kann ein Anrufroutingziel zugewiesen werden.
- **Personen** nach Name oder Erweiterung wählen – Anrufer können dazu geleitet werden, die Durchwahlnummer der Person zu wählen, die sie im Verzeichnis Ihrer Organisation erreichen möchten, oder indem sie den Namen der Person schreiben.
- **Trennen** : Eine automatische Telefonkonferenz kann den Anruf auflegen.

> [!NOTE]
> Eine einzelne automatische Telefon attendant kann nur eine einzelne "Dial by"-Methode unterstützen.  Damit Anrufer nach Name und Nummer wählen können, müssen Sie eine automatische Telefonkonferenz erstellen, die über eine Option für die Namenswahl und die andere für die Durchwahl verfügt.  Jede dieser Optionen wird an separate automatische Telefon telefonieren, die für diese Szenarien für "Nachwählen" konfiguriert sind.

Wenn Anrufe von einer automatischen Telefonleitung oder Anrufwarteschlange umgeleitet werden, können Sie aus den folgenden Anrufroutingzielen auswählen:

- **Person in der Organisation** – eine Person in Ihrer Organisation, die Sprachanrufe empfangen kann. Dies kann ein Onlinebenutzer oder ein Benutzer sein, der lokal mit Skype for Business Server gehostet wird.
- **Sprach-App** – eine andere automatische Telefonkonferenz oder Anrufwarteschlange. Wählen Sie das dem Ziel zugeordnete Ressourcenkonto aus.
- **Externe Telefonnummer –** beliebige Telefonnummer. (Siehe [technische Details zur externen Übertragung](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).
- **Voicemail** – das Sprachpostfach, das einer von Ihnen angegebenen Microsoft 365-Gruppe zugeordnet ist.
- **Operator** (nur automatische Attendant) – der für die automatische Attendant definierte Operator. Das Definieren eines Operators ist optional. Ein Operator kann eines der anderen Ziele in dieser Liste sein.

Automatische Telefonkonferenzen bieten separate Anrufroutingoptionen für Anrufe, die außerhalb der Geschäftszeiten und an Feiertagen empfangen werden. Das Routing von Anrufen nach Stunden ermöglicht alle oben aufgeführten Optionen, während das Routing von Feiertagsanrufen nur das Umleiten oder Trennen eines Anrufs ermöglicht, aber keine Optionen für die Wähltaste.

Anrufwarteschlangen setzen den Anrufer in den Halteraum, bis ein Agent, der der Warteschlange zugewiesen ist, für den Anruf verfügbar ist. Es gibt zwei Situationen, in denen ein Anrufer aus der Warteschlange geleitet werden kann:

- **Anrufüberlauf** : Wenn die Anzahl der Anrufe in der Warteschlange den von Ihnen festgelegten Grenzwert überschreitet, werden neue Anrufer aus der Warteschlange umgeleitet.
- **Anruftimeout:** Wenn ein Anrufer länger als die konfigurierte Timeouteinstellung in der Warteschlange war, wird er aus der Warteschlange umgeleitet.

Anrufe, die aus einer Warteschlange umgeleitet werden, können an alle oben aufgeführten Anrufroutingziele gesendet werden, mit Ausnahme eines Operators. (Anrufwarteschlangen verfügen nicht über Operatoren, Aber Sie können Anrufer an das gleiche Ziel umleiten wie einen Operator, den Sie für eine automatische Telefonkonferenz konfiguriert haben.)

Das folgende Beispiel zeigt ein Beispiel für das Anrufrouting mit automatischen Telefonkonferenzen und Anrufwarteschlangen.

![Diagramm des Anrufroutings mithilfe von automatischen Telefonkonferenzen und Anrufwarteschlangen](media/attendant-and-queue-call-routing.png)

Im obigen Beispiel:

- Die Nulltaste (0) leitet Anrufer an einen Operator um. Der Operator für diese automatische Attendant wurde als Person **in der Organisation konfiguriert.**
- Mit der -Taste (1) werden Anrufer an die Anrufwarteschlange des Vertriebs umgeleitet. Diese Anrufwarteschlange ist mit einem Team verbunden, das das Vertriebsteam enthält, das der Warteschlange zugewiesen ist.
- Die beiden Schlüssel (2) leiten Anrufer an die Supportanrufwarteschlange weiter. Diese Anrufwarteschlange ist mit einem Team verbunden, das das dem Team zugewiesene Supportteam enthält.
- Die Supportanrufwarteschlange verfügt über eine direkte Telefonnummer über eine dazwischenliegende automatische Telefonkonferenz. Wenn eine automatische Telefonleitung die Supportzeile beantwortet, können Sie die Zeiten und die Weiterleitung von Feiertagen trennen.
- Der drei (3)-Schlüssel leitet Benutzer zu einer anderen automatischen Telefonleitung für das Unternehmensverzeichnis um. Die automatische Telefonkonferenz im Unternehmensverzeichnis ermöglicht Anrufern, einzelne Personen in der Organisation anwählen, indem sie ihren Namen oder ihre Erweiterung wählen.

Es wird empfohlen, ein oder mehrere Diagramme zu erstellen, die dem oben genannten Diagramm ähneln, um das Anrufrouting zu zuordnungen. Stellen Sie sicher, dass Sie Folgendes in Ihr Diagramm oder die zugehörige Dokumentation mit einplanen:

- Welche automatischen Telefontelefone haben direkten Zugriff über Telefonnummern?
- Welche Anforderungen gelten für die Weiterleitung an die Feiertage und die Feiertage für die einzelnen automatischen Teilnehmer?
- Die Mitgliedschaft für jede Anrufwarteschlange. (Sie können Benutzer einzeln hinzufügen oder die Warteschlange verschiedenen Gruppentypen zuordnungen. Das Zuordnen einer Warteschlange zu einem Team bietet die vielseitigste Erfahrung.)

Hier sind einige bewährte Methoden für das Anrufrouting:

- Sehen Sie sich Ihr vorhandenes Anrufsystem an, und analysieren Sie die Typen und Häufigkeit eingehender Anrufe. Verwenden Sie diese Informationen, um Ihre automatische Telefonwarteschlange und die Anrufwarteschlange zu informieren.
- Setzen Sie die am häufigsten verfügbaren Optionen frühestens in das Menü, um Anrufe so schnell wie möglich weiter zu routen.
- Vermeiden Sie es, Servicenummern direkt mit Anrufwarteschlangen zu verbinden, es sei denn, die Warteschlangen sind rund um die Uhr verfügbar. Anrufwarteschlangen ermöglichen keine separate Anrufbehandlung für Arbeitsstunden oder Feiertage. Wenn Sie eine Warteschlange mit einer direkten Nummer haben möchten, weisen Sie die Nummer einer automatischen Attendant zu, die während der Geschäftszeiten automatisch an die Warteschlange umgeleitet wird.
- Wenn Sie zahlreiche Anrufe erhalten, die grundlegende Informationen zu Ihrem Unternehmen anfordern, z. B. Geschäftszeiten, Standort oder Websiteadresse, sollten Sie eine automatische Telefonwarte erstellen, um diese Fragen mit aufgezeichneten Nachrichten zu beantworten.
- Halten Sie die Liste der Menüelemente auf fünf oder weniger. Anrufer können probleme haben, sich mehr als fünf Optionen zu merken. Verwenden Sie geschachtelte automatische Telefonkonferenzen, wenn weitere Optionen zum ordnungsgemäßen Routen eines Anrufs erforderlich sind.
- Beschreiben Sie zuerst den Dienst, gefolgt von der Option zum Drücken (z. B. Bei Vertrieb drücken Sie 1) und nicht umgekehrt (z. B. Drücken Sie 1 für Vertrieb).
- Benutzerterminologie, die Ihre Anrufer verstehen, anstatt intern zu verwenden.
- Vermeiden Sie häufige Aktualisierungen beim Anrufrouting. Wenn Sie ihre Menüoptionen für eine automatische Telefonkonferenz in Zukunft ändern, rufen Sie diese in der Sprachanrufaufforderung für die ersten 30 Tage auf.

## <a name="getting-started"></a>Erste Schritte

Nachdem Sie die Planungsaufgaben in diesem Artikel abgeschlossen haben, führen Sie die folgenden Schritte aus, um Ihre automatischen Telefonwarteschlangen und Anrufwarteschlangen einrichten zu lassen:

1. Rufen Sie die Servicenummern ab, die Sie für die automatischen Telefonkonferenzen und Anrufwarteschlangen benötigen, auf die Sie barrierefrei sein möchten, indem Sie direkt von außerhalb Ihrer Organisation anrufen. Dies kann das [Übertragen von Nummern von einem anderen Anbieter oder](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) das Anfordern neuer [Servicenummern umfassen.](getting-service-phone-numbers.md)

2. Holen Sie [sich eine Lizenz für Telefonsystem – Virtueller Benutzer](teams-add-on-licensing/virtual-user.md) für jedes Ressourcenkonto, das Sie erstellen möchten. Diese Lizenzen sind kostenlos, daher empfehlen wir, ein paar zusätzliche Lizenzen für den Fall zu erhalten, dass Sie in Zukunft Änderungen an Ihren Ressourcenkonten vornehmen.

3. [Erstellen Sie ein Ressourcenkonto](manage-resource-accounts.md) für jede automatische Telefonkonferenz und Anrufwarteschlange, die Sie erstellen möchten. Weisen Sie jedem Konto eine Lizenz für das Telefonsystem – virtuellen Benutzer und optional eine Dienstnummer zu.

4. [Erstellen Sie die Feiertage,](set-up-holidays-in-teams.md) für die Sie ein separates Anrufrouting in Ihren automatischen Telefonkonferenzen wünschen.

5. Richten Sie optional [das Parken](call-park-and-retrieve.md) und Abrufen von Anrufen ein, wenn Sie dieses Feature verwenden möchten, um bei Anrufübertragungen zu helfen.

6. Erstellen Sie die Gruppen, die Sie verwenden möchten, um die Anrufer für die Anrufwarteschlangen zu enthalten.

7. Wenn Sie die Durchwahl zulassen möchten, stellen Sie sicher, dass Sie die Durchwahlnummer Ihrer Benutzer zu ihrem Azure Active Directory-Profil hinzugefügt haben.

Nachdem Sie die vorstehenden Schritte abgeschlossen haben, können Sie Ihre automatischen Telefonwarteschlangen und Anrufwarteschlangen erstellen. Da automatische Telefonkonferenzen und Anrufwarteschlangen Anrufe untereinander umleiten können, lesen Sie das von Ihnen erstellte Workflowdiagramm, um zu ermitteln, welche automatische Telefonleitung oder Anrufwarteschlange zuerst erstellt werden soll. Im beispiel im obigen Diagramm würden Sie die Warteschlangen für Vertriebs- und Supportanrufe erstellen, bevor Sie die automatische Contoso-Hauptwartestelle erstellen, da die automatische Hauptwartestelle Anrufer an die Vertriebs- und Supportanrufwarteschlangen weiterzuvermittelen muss.

In den folgenden Artikeln finden Sie Informationen zum Erstellen von automatischen Telefonkonferenzen und Anrufwarteschlangen:

- [Einrichten einer automatischen Attendant](create-a-phone-system-auto-attendant.md)
- [Erstellen einer Anrufwarteschlange](create-a-phone-system-call-queue.md)

## <a name="related-topics"></a>Verwandte Themen

[Planen von direktem Routing](direct-routing-plan.md)

[Verfügbarkeit von Audiokonferenzen und Anrufplänen nach Ländern und Regionen](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Erstellen einer Anrufwarteschlange – Lernprogramm für kleine Unternehmen](business-voice/create-a-phone-system-call-queue-smb.md)

[Einrichten einer automatischen Attendant – Lernprogramm für kleine Unternehmen](business-voice/create-a-phone-system-auto-attendant-smb.md)
