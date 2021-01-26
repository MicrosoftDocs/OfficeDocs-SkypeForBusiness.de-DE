---
title: Planen automatischer Telefonkonferenzen und Anrufwarteschleifen in Teams
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
description: Hier erhalten Sie Informationen zu automatischen Telefonisten und Anrufwarteschleifen und erfahren, wie Sie Anrufer beim Wechseln durch ein Menüsystem unterstützen, um Personen oder Abteilungen in Ihrer Organisation zu erreichen.
ms.openlocfilehash: 9ba8ccf08793e352e225340aeab33d7b95204cd9
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918891"
---
# <a name="plan-for-teams-auto-attendants-and-call-queues"></a>Planen automatischer Telefonkonferenzen und Anrufwarteschleifen in Teams

Automatische Telefon attendants allow you to set menu options to route calls based on caller input. Menüoptionen, z. B. "Für den Vertrieb drücken Sie 1.  Bei "Dienste drücken 2" kann eine Organisation für eine automatische Telefongesellschaft eine Reihe von Auswahlmöglichkeiten bereitstellen, die Anrufer schnell an ihr Ziel leiten, ohne sich auf einen menschlichen Operator verlassen zu müssen, um eingehende Anrufe zu verarbeiten.

Anrufwarteschleifen sind Wartebereiche für Anrufer. In Situationen, in denen Anrufer eine bestimmte Person mit einer bestimmten Spezialität ( z. B. Vertrieb oder Service) statt einer bestimmten Person erreichen müssen, können Sie Anrufer mithilfe von Anrufwarteschleifen mit der Gruppe der Telefonisten verbinden, die ihnen helfen können. Anrufer werden so lange halten, bis ein Agent, der der Warteschlange zugewiesen ist, für den Anruf verfügbar ist.

Bei der gemeinsamen Verwendung können automatische Telefonisten und Anrufwarteschleifen Anrufer ganz einfach an die entsprechende Person oder Abteilung in Ihrer Organisation weiterzuentsprechen.

## <a name="auto-attendants"></a>Automatische Telefonzentralen

Der Hauptzweck einer automatischen Telefon attendant besteht in der Direkten Anwahl eines Anrufers an eine entsprechende Person oder Abteilung basierend auf der Eingabe des Anrufers zu den bereitgestellten Menüoptionen. Anrufer können an bestimmte Personen innerhalb Ihrer Organisation, an Anrufwarteschleifen, in denen sie mit dem nächsten verfügbaren Mitarbeiter sprechen, oder an Voicemail geleitet werden. Für Geschäftszeiten, Arbeitsstunden und Feiertage können verschiedene Anrufroutingoptionen festgelegt werden.

Menüanforderungen können mithilfe von Text-zu-Sprache (vom System generierte Eingabeaufforderungen) oder durch Hochladen einer aufgezeichneten Audiodatei erstellt werden. Die Spracherkennung akzeptiert Sprachbefehle für die Freisprechnavigation, aber auch Anrufer können über die Telefontaste in den Menüs navigieren.

Jede automatische Attendant verfügt über eine bestimmte Sprache und Zeitzone. Wenn Sie Geschäfte in mehreren Sprachen oder in mehreren Teilen der Welt machen, können Sie so viele unterschiedliche automatische Telefonkonferenzen erstellen, wie Sie für Ihre Anrufer benötigen.

Für jede automatische Attendant können Sie einen Operator konfigurieren. Sie können Die Anrufe von Netzbetreibern zwar so konfigurieren, dass sie an eine Vielzahl von Zielen gehen, aber die Funktion der Netzbetreiber soll es Anrufern ermöglichen, mit einer bestimmten Person in Ihrer Organisation zu sprechen, die ihnen helfen kann.

Automatische Telefonisten können so konfiguriert werden, dass Anrufer das Verzeichnis Ihrer Organisation durchsuchen können, entweder nach Name oder nach Durchwahlnummer. In einer automatischen Telefon attendant können Sie angeben, wer für die Verzeichnissuche verfügbar ist, indem Sie Benutzergruppen zum Ein- oder Ausschließen auswählen. (Dies wird als *Wählbereich bezeichnet.)*

Anrufer können eine automatische Telefon attendant entweder über eine direkte Telefonnummer, falls konfiguriert oder von einer anderen automatischen Telefonisten oder einer Anrufwarteschleife aus umgeleitet werden.

## <a name="call-queues"></a>Anrufwarteschleifen

Eine Anrufwarteschleife ist mit einem Warteraum in einem physischen Gebäude vergleichbar. Anrufer warten im Warteschleifen, während Anrufe an die Agents in der Warteschlange geroutet werden. Anrufwarteschleifen werden häufig für Vertriebs- und Dienstfunktionen verwendet. Anrufwarteschleifen können jedoch für alle Situationen verwendet werden, in denen die Anzahl der Anrufe Ihre interne Kapazität überschreitet, z. B. einen Empfangsisten in einer gebuchten Einrichtung.

Anrufwarteschleifen ermöglichen ein bestimmtes Routing von Anrufen in Fällen, in denen die Gesamtzahl der Anrufer in der Warteschlange oder die Wartezeit die von Ihnen festgelegten Grenzwerte überschreitet. Anrufe können an bestimmte Personen, Voicemail, andere Anrufwarteschleifen oder automatische Telefon telefonieren.

Wie bei automatischen Telefonkonferenzen verfügen Anrufwarteschleifen jeweils über eine Spracheinstellung. Sie können verschiedene Anrufwarteschleifen verwenden, wenn Sie in mehreren Sprachen geschäfte machen. Agents können Mitglieder von mehreren Warteschlangen sein, wenn sie mehrsprachiger Art sind.

Für jede Anrufwarteschleife können Sie angeben, ob Telefonisten in der Warteschlange die Anrufanrufe abmelden können und ob Anrufe basierend auf ihren Anwesenheitsanzeigen in Teams an sie weitervermittelt werden sollen.

Sie können einer Anrufwarteschleife eine Telefonnummer zuweisen, jedoch bieten Anrufwarteschleifen kein separates Anrufrouting für Arbeits- und Feiertage. Sofern Ihre Anrufwarteschleife nicht rund um die Uhr besetzt ist, empfehlen wir, die Telefonnummer einer automatischen Telefonwarteschlange zuzuordnen, die während der Geschäftszeiten an die Anrufwarteschleife umleitet.

## <a name="prerequisites"></a>Voraussetzungen

Zum Konfigurieren von automatischen Telefonkonferenzen und Anrufwarteschleifen benötigen Sie die folgenden Ressourcen:

- Ein Ressourcenkonto für jede automatische Telefon attendant und jede Anrufwarteschleife
- Ein kostenloses Telefonsystem – Virtuelle Benutzerlizenz für jedes Ressourcenkonto
- Mindestens eine [Microsoft-Dienstnummer,](getting-service-phone-numbers.md)eine direkte Routingnummer oder eine Hybridnummer für jedes Ressourcenkonto, das direkt anwählbar sein soll
 - Die Servicenummer kann eine gebührenpflichtige oder gebührenfreie Nummer sein.

Agents, die Anrufe aus den Anrufwarteschleifen erhalten, müssen Enterprise-VoIP oder lokale Benutzer aktiviert sein. Wenn in den Anrufwarteschleifen Direct Routing-Nummern verwendet werden, benötigen Telefonmitarbeiter außerdem:

- Eine Online-Voicerouting-Richtlinie, die zugewiesen wurde, wenn die Anrufwarteschlange den Übertragungsmodus verwendet
- Wenn die Anrufwarteschleife den Konferenzmodus verwendet, wird eine Lizenz für Audiokonferenzen oder eine Richtlinie für das Online-Voicerouting zugewiesen

Wenn Ihre Mitarbeiter die Microsoft Teams-App für Anrufe in der Anrufwarteschleife verwenden, müssen sie sich im TeamsOnly-Modus befinden.

Wenn Anrufe an eine externe Telefonnummer übertragen werden, muss das Ressourcenkonto, das die Übertragung (d. h. das der automatischen Telefonanlage oder Anrufwarteschleife zugeordnete Konto) über eine Telefonnummer und eine Lizenz für einen virtuellen Benutzer des Microsoft 365-Telefonsystems verfügen. Darüber hinaus:

- Weisen Sie für ein Ressourcenkonto mit einer Anrufplannummer eine [Anrufplanlizenz](calling-plans-for-office-365.md) zu.
- Weisen Sie für ein Ressourcenkonto mit einer Direct Routing-Nummer eine [Online-Voiceroutingrichtlinie zu.](manage-voice-routing-policies.md)

> [!NOTE]
> Direkte Routing-Servicenummern für automatische Telefonisten und Anrufwarteschleifen werden nur für Microsoft Teams-Benutzer und Nur-Telefonisten unterstützt.<br>
> Übertragungen zwischen Anrufplan- und Direct -Routing-Trunks werden nicht unterstützt.

## <a name="business-decisions"></a>Geschäftsentscheidungen

Bevor Sie Ihre automatischen Telefonkonferenzen und Anrufwarteschleifen einrichten, müssen Sie einige Entscheidungen zur Verwendung dieser Features in Ihrem Unternehmen treffen. Diese Entscheidungen bestimmen die Einstellungen, die Sie beim Konfigurieren Ihrer automatischen Telefonkonferenzen und Anrufwarteschleifen auswählen.

Dokumentieren Sie Ihre Antworten auf diese Fragen, und stellen Sie die Informationen für den Administrator zur Konfiguration zur Verfügung.

- Welche Sprachen benötigen Sie? Wo sind diese Sprachen erforderlich – welche Abteilung oder Gruppe?
- Möchten Sie Spracheingaben von Anrufern oder nur Wähleingaben zulassen?
- Benötigen Sie separate Anrufrouting für Arbeits- oder Feiertage? Wie sieht es mit Stunden und Feiertagen aus?
- Möchten Sie zulassen, dass Agenten in einer Anrufwarteschleife die Anrufanrufe nicht mehr verwenden?
- Möchten Sie, dass Telefonieren in Ihren Anrufwarteschleifen oder ihrem Netzbetreiber eine bestimmte Anrufer-ID hat, wenn sie anrufen?
- Möchten Sie das [Parken](call-park-and-retrieve.md) und Abrufen von Anrufen in Ihrer Organisation aktivieren, um die Übergabe von Anrufen zwischen Personen oder Abteilungen zu unterstützen?
- Möchten Sie für die Sprachanrufe ihre eigene Stimme aufzeichnen oder die vom System generierte Stimme verwenden? (Die vom System generierte Stimme ist einfach zu aktualisieren.)

## <a name="technical-decisions"></a>Technische Entscheidungen

Wenn Sie automatische Telefonisten und Anrufwarteschleifen verwenden, um Anrufer mit Personen in Ihrer Organisation zu verbinden, müssen Sie einige technische Entscheidungen treffen, bevor Sie mit der Konfiguration beginnen.

Agents können Anrufwarteschleifen auf folgende Weise hinzugefügt werden:

- Einzelne Benutzer
- Verteilerlisten
- Sicherheitsgruppen, einschließlich E-Mail-aktivierter Sicherheitsgruppen
- Microsoft 365-Gruppen oder Teams

Sie können bei Bedarf eine Kombination dieser Optionen für jede Warteschlange verwenden. Gruppen mit einer E-Mail-Adresse können für Voicemail verwendet werden. Die Verwendung von Teams bietet eine Reihe von Vorteilen, einschließlich freigegebener Dateispeicherung und Chats zwischen Agents, einem gemeinsamen Postfach, in dem Voicemails empfangen werden können, und eine erweiterbare Plattform, die Integration in Ihre Geschäftsanwendungen oder Power Apps umfassen kann.

Es wird empfohlen, eine Strategie zum Hinzufügen von Telefonanrufmitarbeitern zu Warteschlangen zu wählen, bevor Sie mit der Konfiguration beginnen.

Wenn Sie über eine vorhandene automatische Telefonant- und Anrufwarteschleifeninfrastruktur verfügen und zu Teams migrieren, benötigen Sie einen Plan, um Ihre vorhandenen Telefonnummern an die neuen automatischen Telefonisten und Anrufwarteschleifen zu übertragen. Möglicherweise müssen Sie einen [Portierungsauftrag erstellen,](phone-number-calling-plans/port-order-overview.md) um Ihre Nummern von einem anderen Anbieter zu verschieben. Es wird empfohlen, vorübergehend eine oder mehrere neue Telefonnummern zu erwerben und die automatische Telefonwarteschlange und die Anrufwarteschleifenflüsse zu testen, bevor Sie diese Nummern über die Nummern umschalten, die Aktuell in Service sind.

*Der Konferenzmodus* ist eine Option in Anrufwarteschleifen, die die Zeit, die zum Verbinden von Teams-VOIP- und -PSTN-Anrufen mit einem Agent benötigt wird, erheblich reduziert. Damit der Konferenzmodus funktioniert, müssen die Telefonmitarbeiter in der Anrufwarteschleife einen der folgenden Clients verwenden:

- Die neueste Version des Microsoft Teams-Desktopclients, der Android-App oder der iOS-App
  - Microsoft Teams Phone, Version 1449/1.0.94.2020051601 oder höher
  
Legen Sie die Teams-Konten von Agents auf den Modus "Nur Für Teams" festgelegt. Agents, die die Anforderungen nicht erfüllen, sind nicht in der Anrufroutingliste enthalten.

Es wird empfohlen, den Konferenzmodus für Ihre Anrufwarteschleifen zu aktivieren, wenn ihre Agents alle kompatible Clients verwenden.

> [!NOTE]
> "Beschäftigt" wird vom Konferenzmodus nicht unterstützt. Agents bei Anrufen, die keine Anrufwarteschleifenanrufe sind, wird möglicherweise weiterhin ein Anrufwarteschleifenanruf präsentiert, wenn das anwesenheitsbasierte Routing nicht aktiviert ist.

## <a name="plan-your-call-routing-flow"></a>Planen des Anrufroutingflusses

Im Rahmen des Planungsprozesses empfiehlt es sich, das Anrufrouting für Ihre Organisation in einem Diagramm zu erstellen. Das Diagramm hilft Ihnen dabei, das effizienteste Routing für Anrufer in Ihrer Organisation zu ermitteln. Sie können das Diagramm auch verwenden, um die automatischen Telefonkonferenzen und Anrufwarteschleifen, die Sie erstellen müssen, sowie zugehörige Anforderungen wie Servicenummern, Lizenzen und Ressourcenkonten zu ermitteln.

Sehen wir uns an, wie automatische Telefonkonferenzen und Anrufwarteschleifen Anrufe routen.

Automatische Telefon attendants route all calls in one of the following ways:

- **Sofort umleiten** : Anrufe können unmittelbar nach dem Beantworten oder nach einer ersten Begrüßung an eines der (unten aufgeführten) Anrufroutingziele umgeleitet werden.
- **Umleiten basierend auf Wähloptionen** – Anrufer können umgeleitet werden, um zwischen den Optionen zu wählen, die den Nummern auf der Wähltastatur des Telefons (0-9) zugewiesen sind. Jeder Wähltasten kann ein Anrufroutingziel zugewiesen werden.
- **Personen** nach Name oder Durchwahl anrufen – Anrufer können zur Durchwahlnummer der Person, die sie im Verzeichnis Ihrer Organisation erreichen möchten, oder durch Eingeben des Namens der Person geleitet werden.
- **Trennen** – Eine automatische Telefonkonferenz kann den Anruf auflegen.

> [!NOTE]
> Eine einzelne automatische Telefon attendant kann nur eine einzelne "Dial by"-Methode unterstützen.  Damit Anrufer nach Name und Nummer wählen können, müssen Sie eine automatische Telefon attendant erstellen, die eine Option für die Namensanwahl und die andere für die Durchwahl bietet.  Jede dieser Optionen führt die Route zu separaten automatischen Telefonanten, die für diese Szenarien für "Einwählen" konfiguriert sind.

Wenn Anrufe von einer automatischen Telefonkonferenz oder Anrufwarteschleife umgeleitet werden, können Sie unter den folgenden Anrufroutingzielen wählen:

- **Person in der Organisation** – eine Person in Ihrer Organisation, die Sprachanrufe empfangen kann. Dies kann ein Onlinebenutzer oder ein Lokal mit Skype for Business Server gehosteter Benutzer sein.
- **Sprach-App** – eine andere automatische Telefonkonferenz oder eine Anrufwarteschleife. Wählen Sie das Ressourcenkonto aus, das dem Ziel zugeordnet ist.
- **Externe Telefonnummer –** beliebige Telefonnummer. (Siehe [technische Details zur externen Übertragung).](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)
- **Voicemail –** das Sprachpostfach, das einer von Ihnen angegebenen Microsoft 365-Gruppe zugeordnet ist.
- **Operator** (nur automatische Attendant) – der für die automatische Attendant definierte Operator. Das Definieren eines Operators ist optional. Ein Operator kann eines der anderen Ziele in dieser Liste sein.

Automatische Telefon attendants offer separate call routing options for calls received outside of business hours and on holidays. Das Routing nach Stunden ermöglicht alle oben aufgeführten Optionen, während das Routing von Feiertagen nur das Umleiten oder Trennen eines Anrufs, aber keine Optionen für die Wählta nicht zulässt.

Anrufwarteschleifen halten den Anrufer so lange, bis ein Der Warteschleife zugewiesener Agent für den Anruf zur Verfügung steht. Es gibt zwei Situationen, in denen ein Anrufer aus der Warteschlange geleitet werden kann:

- **Anrufüberlauf** – Wenn die Anzahl der Anrufe in der Warteschlange das von Ihnen festgelegte Limit überschreitet, werden neue Anrufer aus der Warteschlange umgeleitet.
- **Anruftimeout** : Wenn ein Anrufer länger als die konfigurierte Timeouteinstellung in der Warteschlange war, wird er aus der Warteschlange umgeleitet.

Anrufe, die aus einer Warteschlange umgeleitet werden, können an alle oben aufgeführten Anrufroutingziele mit Ausnahme eines Anbieters gesendet werden. (Anrufwarteschleifen haben keine Operatoren, aber Sie können Anrufer an das gleiche Ziel umleiten wie einen Operator, den Sie für eine automatische Telefonkonferenz konfiguriert haben.)

Das folgende Beispiel zeigt ein Beispiel für die Anrufrouting mithilfe von automatischen Telefonkonferenzen und Anrufwarteschleifen.

![Diagramm der Anrufrouting mithilfe von automatischen Telefonkonferenzen und Anrufwarteschleifen](media/attendant-and-queue-call-routing.png)

Im vorstehenden Beispiel:

- Die Nulltaste (0) leitet Anrufer an einen Operator weiter. Der Operator für diese automatische Attendant wurde als Person **in der Organisation konfiguriert.**
- Der eine (1) Schlüssel leitet Anrufer an die Anrufwarteschleife weiter. Diese Anrufwarteschleife ist mit einem Team verbunden, das das der Warteschlange zugewiesene Vertriebsteam enthält.
- Die beiden Schlüssel leiten Anrufer an die Supportanrufwarteschleife weiter. Diese Anrufwarteschleife ist mit einem Team verbunden, das das dem Team zugewiesene Supportteam enthält.
- Die Supportanrufwarteschlange verfügt über eine direkte Telefonnummer über eine zusätzliche automatische Telefonkonferenz. Wenn eine automatische Telefonleitung die Supportleitung beantwortet, sind getrennte Arbeitsstunden und Weiterleitung von Festanrufen möglich.
- Der drei (3) Schlüssel leitet Benutzer zu einer anderen automatischen Telefongesellschaft für das Unternehmensverzeichnis weiter. Die automatische Telefonkonferenz des Unternehmensverzeichnisses ermöglicht Anrufern, einzelne Personen in der Organisation durch Wählen ihres Namens oder ihrer Durchwahl anwählen.

Es wird empfohlen, ein oder mehrere Diagramme zu erstellen, die dem oben genannten Diagramm ähneln, um die Anrufrouting zu planen. Achten Sie darauf, dass Sie Folgendes in Ihr Diagramm oder die zugehörige Dokumentation mit auf den Weg geben:

- Auf welche automatischen Telefon attendants kann direkt über Telefonnummern zugegriffen werden?
- Welche Anforderungen gelten für die Weiterleitung von Arbeitsstunden und Feiertagen für die einzelnen automatischen Attendants?
- Die Mitgliedschaft für jede Anrufwarteschleife. (Sie können Benutzer einzeln hinzufügen oder die Warteschlange verschiedenen Gruppenarten zuordnungen. Das Zuordnen einer Warteschlange zu einem Team bietet die vielseitigste Erfahrung.)

Hier sind einige bewährte Methoden für die Anrufrouting:

- Sehen Sie sich Ihr vorhandenes Anrufsystem an, und analysieren Sie die Typen und die Häufigkeit eingehender Anrufe. Verwenden Sie diese Informationen, um Ihre automatische Telefon attendant und die Struktur der Anrufwarteschleife zu informieren.
- Legen Sie die am häufigsten angezeigten Optionen frühestens im Menü ab, um Anrufe so schnell wie möglich weiter zu routen.
- Vermeiden Sie es, Leistungsnummern direkt mit Anrufwarteschleifen zu verbinden, es sei denn, die Warteschlangen sind rund um die Uhr verfügbar. Anrufwarteschleifen ermöglichen keine separate Anrufbehandlung für Arbeitsstunden oder Feiertage. Wenn Sie eine Warteschlange mit einer direkten Nummer haben möchten, weisen Sie die Nummer einer automatischen Attendant zu, die während der Geschäftszeiten automatisch zur Warteschlange umgeleitet wird.
- Wenn Sie zahlreiche Anrufe erhalten, die grundlegende Informationen zu Ihrem Unternehmen anfordern, z. B. Geschäftszeiten, Ort oder Websiteadresse, sollten Sie erwägen, eine automatische Telefongesellschaft zu erstellen, die diese Fragen mit aufgezeichneten Nachrichten beantwortet.
- Halten Sie die Liste der Menüelemente auf fünf oder weniger. Anrufer können Probleme haben, sich mehr als fünf Optionen zu merken. Verwenden Sie geschachtelte automatische Telefonisten, wenn weitere Optionen zum ordnungsgemäßen Routen eines Anrufs erforderlich sind.
- Beschreiben Sie zuerst den Dienst, gefolgt von der Option zum Drücken (z. B. bei "Sales press 1") und nicht umgekehrt (z. B. Drücken Sie "1" für "Vertrieb".
- Die Benutzerterminologie, die Ihre Anrufer verstehen, anstatt was Sie intern verwenden können.
- Vermeiden Sie häufige Aktualisierungen beim Anrufrouting. Wenn Sie ihre Menüoptionen für eine automatische Telefon attendant in Zukunft ändern, rufen Sie diese in den Sprachanrufaufforderungen für die ersten 30 Tage auf.

## <a name="getting-started"></a>Erste Schritte

Nachdem Sie die Planungsaufgaben in diesem Artikel abgeschlossen haben, führen Sie die folgenden Schritte aus, um Ihre automatischen Telefonkonferenzen und Anrufwarteschleifen eingerichtet zu lassen:

1. Rufen Sie die Servicenummern ab, die Sie für die automatischen Telefonkonferenzen und Anrufwarteschleifen benötigen, auf die Sie durch direkte Anrufe von außerhalb Ihrer Organisation zugriffen möchten. Dazu kann das [Übertragen von Nummern von einem anderen Anbieter](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) oder das Anfordern neuer [Servicenummern gehören.](getting-service-phone-numbers.md)

2. Holen Sie [sich eine Telefonsystem- virtuelle Benutzerlizenz](teams-add-on-licensing/virtual-user.md) für jedes Ressourcenkonto, das Sie erstellen möchten. Da diese Lizenzen kostenlos sind, empfehlen wir Ihnen, für den Fall, dass Sie in Zukunft Änderungen an Ihren Ressourcenkonten vornehmen möchten, ein paar zusätzliche Lizenzen zu erhalten.

3. [Erstellen Sie ein Ressourcenkonto](manage-resource-accounts.md) für jede automatische Telefonwarteschlange und Anrufwarteschleife, die Sie erstellen möchten. Weisen Sie jedem Konto eine Telefonsystem- virtuelle Benutzerlizenz und optional eine Servicenummer zu.

4. [Erstellen Sie die Feiertage,](set-up-holidays-in-teams.md) für die Sie separates Anrufrouting in Ihren automatischen Telefonkonferenzen wünschen.

5. Richten Sie optional [das Parken](call-park-and-retrieve.md) und Abrufen von Anrufen ein, wenn Sie dieses Feature zur Unterstützung bei Anrufübertragungen verwenden möchten.

6. Erstellen Sie die Gruppen, die Sie für die Telefonanrufmitarbeiter für die Anrufwarteschleifen verwenden möchten.

7. Wenn Sie die Durchwahl per Durchwahl zulassen möchten, stellen Sie sicher, dass Sie die Durchwahlnummer Ihrer Benutzer zu ihrem Azure Active Directory-Profil hinzugefügt haben.

Nachdem Sie die vorstehenden Schritte abgeschlossen haben, können Sie Ihre automatischen Telefonkonferenzen und Anrufwarteschleifen erstellen. Da automatische Telefonkonferenzen und Anrufwarteschleifen Anrufe aufeinander umleiten können, können Sie in dem von Ihnen erstellten Workflowdiagramm ermitteln, welche automatische Telefon attendant oder Anrufwarteschleife zuerst erstellt werden soll. Im Beispiel im vorstehenden Diagramm würden Sie die Vertriebs- und Supportanrufwarteschleifen erstellen, bevor Sie die automatische Hauptkonferenz von Contoso erstellen, da die automatische Haupt telefonisten die Anrufer an die Vertriebs- und Supportanrufwarteschleifen umschalten muss.

In den folgenden Artikeln finden Sie Informationen zum Erstellen von automatischen Telefonkonferenzen und Anrufwarteschleifen:

- [Einrichten einer automatischen Attendant](create-a-phone-system-auto-attendant.md)
- [Erstellen einer Anrufwarteschlange](create-a-phone-system-call-queue.md)

## <a name="related-topics"></a>Verwandte Themen

[Planen von direktem Routing](direct-routing-plan.md)

[Verfügbarkeit von Audiokonferenzen und Anrufplänen nach Ländern und Regionen](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Erstellen einer Anrufwarteschleife – Lernprogramm für kleine Unternehmen](business-voice/create-a-phone-system-call-queue-smb.md)

[Einrichten einer automatischen Attendant – Lernprogramm für kleine Unternehmen](business-voice/create-a-phone-system-auto-attendant-smb.md)