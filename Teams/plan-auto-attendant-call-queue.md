---
title: Planen von automatischen Telefonzentralen und Anrufwarteschlangen für Teams
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
description: Erfahren Sie mehr über automatische Telefonzentralen und Anrufwarteschlangen und wie Sie Sie verwenden können, um Anrufern zu helfen, durch ein Menü System zu navigieren, um Personen oder Abteilungen in Ihrer Organisation zu erreichen.
ms.openlocfilehash: 3e1a7fe6b5f059236e0fafd64dbf87b7cebbeecf
ms.sourcegitcommit: 22e2f51abf879b34701064839d0e410758b6a3dd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48209991"
---
# <a name="plan-for-teams-auto-attendants-and-call-queues"></a>Planen von automatischen Telefonzentralen und Anrufwarteschlangen für Teams

Mit automatischen Telefonzentralen können Sie Menü Optionen einrichten, um Anrufe basierend auf der Eingabe durch Anrufer weiterzuleiten. Menü Optionen ("für Verkäufe drücken Sie 1.  Für Services drücken Sie 2 ") für eine automatische Telefonzentrale: eine Organisation bietet eine Reihe von Entscheidungen, die Anrufer schnell ans Ziel führen, ohne sich auf einen menschlichen Netzbetreiber zu verlassen, der eingehende Anrufe übernimmt.


Anrufwarteschlangen sind Wartebereiche für Anrufer. In Situationen, in denen Anrufer jemanden mit einer bestimmten Spezialität – wie Vertrieb oder Service – und nicht mit einer bestimmten Person erreichen müssen, können Sie Anrufwarteschlangen verwenden, um Anrufer mit der Gruppe von Agents zu verbinden, die Sie unterstützen können. Anrufer werden in Wartestellung gesetzt, bis ein der Warteschlange zugeordneter Agent verfügbar ist, um den Anruf anzunehmen.

In Verbindung mit automatischen Telefonzentralen und Anrufwarteschlangen können Anrufer problemlos an die entsprechende Person oder Abteilung in Ihrer Organisation weitergeleitet werden.

## <a name="auto-attendants"></a>Automatische Telefonzentralen

Der primäre Zweck einer automatischen Telefonzentrale besteht darin, einen Anrufer an eine geeignete Person oder Abteilung zu leiten, die auf der Eingabe des Anrufers zu den bereitgestellten Menü Optionen basiert. Anrufer können an bestimmte Personen innerhalb Ihres Unternehmens weitergeleitet werden, um Warteschlangen anzurufen, in denen Sie warten, um mit dem nächsten verfügbaren Agenten oder Voicemail zu sprechen. Unterschiedliche Anrufweiterleitungsoptionen können für Geschäftszeiten, außerhalb von Stunden und Feiertage angegeben werden.

Menüansagen können mithilfe von Text-zu-Sprache (vom System generierte Eingabeaufforderungen) oder durch Hochladen einer aufgezeichneten Audiodatei erstellt werden. Spracherkennung akzeptiert Sprachbefehle für die Freisprech Navigation, aber auch Anrufer können über die Tastatur des Telefons in Menüs navigieren.

Jede automatische Telefonzentrale hat eine bestimmte Sprache und Zeitzone. Wenn Sie in mehreren Sprachen oder in mehreren Teilen der Welt Geschäfte tätigen, können Sie so viele verschiedene automatische Telefonzentralen erstellen, wie Sie benötigen, um Ihre Anrufer aufnehmen zu können.

Für jede automatische Telefonzentrale können Sie einen Operator konfigurieren. Zwar können Sie die Operator Aufrufe so konfigurieren, dass Sie zu einer Vielzahl von Zielen wechseln, doch das Feature "Operator" dient dazu, Anrufern zu ermöglichen, mit einer bestimmten Person in Ihrer Organisation zu sprechen, die Ihnen helfen kann.

Automatische Telefonzentralen können so konfiguriert werden, dass Anrufer das Verzeichnis Ihrer Organisation durchsuchen können, entweder nach Namen oder nach Durchwahlnummer. In einer automatischen Telefonzentrale können Sie festlegen, wer für die Verzeichnissuche verfügbar ist, indem Sie Gruppen von Benutzern zum einschließen oder ausschließen auswählen. (Dies wird als *Wählbereich*bezeichnet.)

Anrufer können eine automatische Telefonzentrale erreichen, entweder durch direkte Rufnummer, wenn Sie konfiguriert ist, oder indem Sie von einer anderen automatischen Telefonzentrale oder einer Anrufwarteschlange umgeleitet werden.

## <a name="call-queues"></a>Anrufwarteschleifen

Eine Anrufwarteschlange entspricht einem Wartebereich in einem physikalischen Gebäude. Anrufer warten auf Wartezeiten, während Anrufe an die Agents in der Warteschlange weitergeleitet werden, sobald diese verfügbar sind. Anrufwarteschlangen werden in der Regel für Vertriebs-und Servicefunktionen verwendet, können aber für jede Situation verwendet werden, in der die Anzahl der Anrufe Ihre interne Kapazität überschreitet, beispielsweise ein Rezeptionist in einer geschäftigen Einrichtung.

Anrufwarteschlangen ermöglichen spezifisches Routing von Anrufen in Fällen, in denen die Gesamtzahl der Anrufer in der Warteschlange oder die Wartezeit die von Ihnen festgelegten Grenzwerte überschreitet. Anrufe können an bestimmte Personen, Voicemail, andere Anrufwarteschlangen oder automatische Telefonzentralen weitergeleitet werden.

Wie bei automatischen Telefonzentralen verfügen Anrufwarteschlangen jeweils über eine Spracheinstellung. Sie können unterschiedliche Anrufwarteschlangen verwenden, wenn Sie in mehreren Sprachen tätig sind. Agents können Mitglieder von mehr als einer Warteschlange sein, wenn Sie mehrsprachig sind.

Sie können für jede Anrufwarteschlange angeben, ob sich die Agents in der Warteschlange für das annehmen von Anrufen entscheiden können und ob Anrufe auf Grundlage ihrer Anwesenheitsanzeige in Teams weitergeleitet werden sollen.

Sie können einer Anrufwarteschlange eine Telefonnummer zuweisen, jedoch bieten Anrufwarteschlangen keine separaten Anrufweiterleitung außerhalb von Stunden und Feiertagen. Sofern ihre Anrufwarteschlange nicht mit 24/7 besetzt ist, empfehlen wir, die Telefonnummer einer automatischen Telefonzentrale zuzuweisen, die während der Geschäftszeiten zur Anrufwarteschlange umgeleitet wird.

## <a name="prerequisites"></a>Voraussetzungen

Zum Konfigurieren von automatischen Telefonzentralen und Anrufwarteschlangen benötigen Sie Folgendes:

- Ein Ressourcenkonto für jede automatische Telefonzentrale und jede Anrufwarteschlange
- Eine ﻿kostenlose Telefonanlage – virtuelle Benutzerlizenz für jedes Ressourcenkonto
- Eine Dienstnummer für jede automatische Telefonzentrale oder Anrufwarteschlange, die direkt gewählt werden soll
- Einen Anrufplan für jede Person, die Anruf Warteschlangen Anrufe empfangen wird

> [!NOTE]
> Direct Routing-Dienstnummern für die automatische Telefonzentrale und die Anrufwarteschlangen werden nur für Microsoft Teams-Benutzer und Anruf-Agents unterstützt.

## <a name="business-decisions"></a>Geschäftliche Entscheidungen

Bevor Sie Ihre automatischen Telefonzentralen und Anrufwarteschlangen einrichten, sollten Sie sich mit einigen Entscheidungen über die Verwendung dieser Funktionen in Ihrem Unternehmen befassen. Diese Entscheidungen bestimmen die Einstellungen, die Sie auswählen, wenn Sie Ihre automatischen Telefonzentralen und Anrufwarteschlangen konfigurieren.

Dokumentieren Sie Ihre Antworten auf diese Fragen, und geben Sie die Informationen ein, die der Administrator für die Konfiguration vornimmt.

- Welche Sprachen benötigen Sie? Wo sind diese Sprachen erforderlich – welche Abteilung oder Gruppe?
- Möchten Sie Spracheingaben von Anrufern oder nur Wähl Eingaben zulassen?
- Benötigen Sie ein separates Anrufrouting außerhalb von Stunden oder an Feiertagen? Was sind die Stunden und Feiertage?
- Möchten Sie den Agents in einer Anrufwarteschlange erlauben, Anrufe abzulehnen?
- Möchten Sie, dass die Agents in ihren Anrufwarteschlangen oder Ihr Netzbetreiber eine bestimmte Rufnummernanzeige haben, wenn Sie sich auswählen? 
- Möchten Sie das [Parken und Abrufen von Anrufen](call-park-and-retrieve.md) in Ihrer Organisation aktivieren, um die Anrufübergabe zwischen Personen oder Abteilungen zu unterstützen?
- Möchten Sie für die Spracheingabe Aufforderungen ihre eigene aufzeichnen oder die vom System generierte Stimme verwenden? (Die vom System generierte Sprache ist sehr einfach zu aktualisieren.)

## <a name="technical-decisions"></a>Technische Entscheidungen

Wenn Sie automatische Telefonzentralen und Anrufwarteschlangen verwenden, um Anrufer mit Personen in Ihrer Organisation zu verbinden, gibt es einige technische Entscheidungen, die Sie treffen müssen, bevor Sie mit der Konfiguration beginnen.

Agents können den Anrufwarteschlangen folgendermaßen hinzugefügt werden:

- Einzelne Benutzer
- Verteilerlisten
- Sicherheitsgruppen, einschließlich e-Mail-aktivierter Sicherheitsgruppen
- Microsoft 365-Gruppen oder-Teams

Sie können bei Bedarf eine Kombination dieser Optionen für jede Warteschlange verwenden. Gruppen mit einer e-Mail-Adresse können für Voicemail verwendet werden. Die Verwendung von Teams bietet eine Reihe von Vorteilen, wie freigegebene Dateispeicherung und Chats zwischen Agents, ein gemeinsames Postfach, in dem Sprachnachrichten empfangen werden können, und eine erweiterbare Plattform, die die Integration in Ihre Geschäftsanwendungen oder Power apps einbeziehen kann.

Es wird empfohlen, eine Strategie für das Hinzufügen von Anruf-Agents zu Warteschlangen zu wählen, bevor Sie mit der Konfiguration beginnen.

Wenn Sie über eine vorhandene automatische Telefonzentrale und eine Anruf Warteschlangeninfrastruktur verfügen und zu Teams migrieren, benötigen Sie einen Plan, mit dem Sie Ihre vorhandenen Telefonnummern an die neuen automatischen Telefonzentralen und Anrufwarteschlangen übertragen können. Möglicherweise müssen Sie eine [Portierungs Reihenfolge](phone-number-calling-plans/port-order-overview.md) erstellen, um Ihre Nummern von einem anderen Anbieter zu verschieben. Wir empfehlen, dass Sie vorübergehend eine oder mehrere neue Telefonnummern erwerben und Ihre automatische Telefonzentrale und die Anruf Warteschlangen Ströme testen, bevor Sie Sie über die derzeit in Dienst befindlichen Nummern umschalten.

Der *Konferenzmodus* ist eine Option in Anrufwarteschlangen, die die Zeitdauer für die Verbindung von VoIP-Anrufen und PSTN-anrufen mit einem Agenten erheblich verkürzt. Damit der Konferenzmodus funktioniert, müssen die Agents in der Anrufwarteschlange einen der folgenden Clients verwenden:

  - Die neueste Version des Microsoft Teams-Desktop Clients, der Android-App oder der IOS-App
  - Microsoft Teams Phone Version 1449/1.0.94.2020051601 oder höher
  
Die Konten von Agenten Teams müssen auf "nur für Teams" eingestellt sein. Agents, die die Anforderungen nicht erfüllen, werden nicht in die Anruf Weiterleitungsliste aufgenommen.

Es wird empfohlen, den Konferenzmodus für Ihre Anrufwarteschlangen zu aktivieren, wenn Ihre Agents alle kompatible Clients verwenden.

> [!NOTE]
> Busy on Busy wird vom Konferenzmodus nicht unterstützt. Agents in Warteschlangen anrufen, die keine Anrufwarteschlange sind, werden möglicherweise weiterhin mit einem Anruf Warteschlangen Anruf angezeigt, wenn Anwesenheits basiertes Routing nicht aktiviert ist.

## <a name="plan-your-call-routing-flow"></a>Planen des Anruf Weiterleitungs Flusses

Im Rahmen des Planungsprozesses empfehlen wir, das Anrufrouting für Ihre Organisation in einem Diagramm zu erarbeiten. Auf diese Weise können Sie das effizienteste Routing für Personen ermitteln, die sich in Ihre Organisation einwählen. Sie können das Diagramm auch verwenden, um die automatischen Telefonzentralen und Anrufwarteschlangen zu ermitteln, die Sie erstellen müssen, sowie verwandte Anforderungen wie Dienstnummern, Lizenzen und Ressourcenkonten.

Sehen wir uns an, wie automatische Telefonzentralen und Anrufwarteschlangen Anrufe weiterleiten.

Automatische Telefonzentralen leiten alle Anrufe auf eine der folgenden Arten:

- **Sofort Umleitung** – Anrufe können an eines der Anruf Weiterleitungs Ziele (nachstehend aufgeführt) unmittelbar nach der Beantwortung oder nach einer anfänglichen Begrüßung umgeleitet werden.
- **Umleitung auf der Grundlage von Wähloptionen** – Anrufer können an die Wahl zwischen Optionen weitergeleitet werden, die den Nummern auf der Telefontastatur des Telefons zugeordnet sind, 0-9. Jeder Wähltaste kann ein Anrufrouting-Ziel zugewiesen werden.
- **Wenn Sie Personen nach Namen oder Durchwahl** Nummern anrufen, können Sie die Durchwahlnummer der Person wählen, die Sie im Verzeichnis Ihrer Organisation erreichen möchten, oder indem Sie den Namen der Person buchstabieren.
- **Trennen** – eine automatische Telefonzentrale kann den Anruf auflegen.

> [!NOTE]
> Eine einzelne automatische Telefonzentrale kann nur eine einzelne "Dial by"-Methode unterstützen.  Damit Anrufer über den Namen und die Nummer wählen können, müssen Sie eine automatische Telefonzentrale erstellen, die eine Option für "Dial by Name" und die andere für "Durchwahl" hat.  Jede dieser Optionen wird zu separaten automatischen attenants weitergeleitet, die für diese "Wähl-Szenarien" konfiguriert sind. 

Wenn Anrufe von einer automatischen Telefonzentrale weitergeleitet werden, können Sie aus den folgenden Anruf Weiterleitungs Zielen auswählen:

- **Person in der Organisation** – eine Person in Ihrer Organisation, die Sprachanrufe empfangen kann. Hierbei kann es sich um einen Online Benutzer oder einen lokal gehosteten Benutzer mit Skype for Business Server handeln.
- **Sprach-App** – eine andere automatische Telefonzentrale oder eine Anrufwarteschlange. Wählen Sie das dem Ziel zugeordnete Ressourcenkonto aus.
- **Externe Telefonnummer** – eine beliebige Telefonnummer. (Siehe [technische Informationen zur externen Übertragung](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).
- **Voicemail** – das Voicemail-Postfach, das einer von Ihnen angegebenen Microsoft 365-Gruppe zugeordnet ist.
- **Operator** – der für die automatische Telefonzentrale definierte Operator. Das Definieren eines Operators ist optional. Ein Operator kann eines der anderen Ziele in dieser Liste sein.

Automatische Telefonzentralen bieten getrennte Anrufweiterleitungsoptionen für eingehende Anrufe außerhalb der Geschäftszeiten und an Feiertagen. Nach Stunden-Anrufweiterleitung können alle oben aufgeführten Optionen ausgeführt werden, während das Urlaubs Anrufrouting nur das Umleiten oder Trennen eines Anrufs, aber keine Wähltasten Optionen ermöglicht.

Anrufwarteschlangen setzen den Anrufer in Wartestellung, bis ein der Warteschlange zugeordneter Agent verfügbar ist, um seinen Anruf zu führen. Es gibt zwei Situationen, in denen ein Aufrufer aus der Warteschlange heraus verwiesen werden kann:

- **Anruf Überlauf** : Wenn die Anzahl der Anrufe in der Warteschlange den von Ihnen festgelegten Grenzwert überschreitet, werden neue Anrufer aus der Warteschlange umgeleitet.
- **Anruf Timeout** – wenn ein Anrufer länger als die konfigurierte Timeouteinstellung in der Warteschlange war, werden Sie aus der Warteschlange umgeleitet.

Anrufe, die aus einer Warteschlange umgeleitet werden, können an alle oben aufgeführten Anruf Weiterleitungs Ziele mit Ausnahme eines Operators gesendet werden. (Anrufwarteschlangen verfügen nicht über Operatoren, aber Sie können Anrufer an denselben Zielort wie einen Operator umleiten, den Sie für eine automatische Telefonzentrale konfiguriert haben.)

Das folgende Beispiel zeigt ein Beispiel für das Anrufrouting mit automatischen Telefonzentralen und Anrufwarteschlangen.

![](media/attendant-and-queue-call-routing.png)

Im obigen Beispiel:
- Mit der NULL-Taste (0) werden die Aufrufer an einen Operator umgeleitet. Der Operator für diese automatische Telefonzentrale wurde als **Person in der Organisation**konfiguriert.
- Mit einem (1)-Schlüssel werden die Anrufer in die Warteschlange für den Verkaufs Anruf umgeleitet. Diese Anrufwarteschlange ist mit einem Team verbunden, das das der Warteschlange zugewiesene Vertriebsteam enthält.
- Die zwei (2)-Taste leitet Anrufer an die Support-Anrufwarteschlange weiter. Diese Anrufwarteschlange ist mit einem Team verbunden, das das dem Team zugewiesene Support Team enthält.
- Die Support-Anrufwarteschlange hat eine direkte Telefonnummer über eine dazwischenliegende automatische Telefonzentrale. Wenn Sie eine automatische Telefonzentrale annehmen, können Sie mit der Support Zeile getrennte Stunden und Urlaubs Anrufrouting abgleichen.
- Mit dem drei (3)-Schlüssel werden Benutzer an eine andere automatische Telefonzentrale für das Unternehmensverzeichnis umgeleitet. Mit der automatischen Telefonzentrale des Unternehmens können Anrufer Personen in der Organisation anrufen, indem Sie den Namen oder die Durchwahl wählen.

Wir empfehlen, ein oder mehrere Diagramme ähnlich wie oben zu erstellen, um das Anrufrouting zu kartieren. Stellen Sie sicher, dass Sie Folgendes in Ihr Diagramm oder die zugehörige Dokumentation einbeziehen:

- Welche automatischen Telefonzentralen über Telefonnummern direkt zugreifen können
- Was sind die Arbeitszeiten und Urlaubs Routing Anforderungen für jede automatische Telefonzentrale?
- Die Mitgliedschaft für jede Anrufwarteschlange. (Sie können Benutzer einzeln hinzufügen oder die Warteschlange verschiedenen Arten von Gruppen zuordnen. Das Zuordnen einer Warteschlange zu einem Team bietet die vielseitigste Erfahrung.)

Nachfolgend finden Sie einige bewährte Methoden für die Anrufweiterleitung:

- Sehen Sie sich das vorhandene Anruf System an, und analysieren Sie die Art und Häufigkeit der eingehenden Anrufe. Verwenden Sie diese Informationen, um Ihre automatische Telefonzentrale und die Anruf Warteschlangen Struktur zu informieren.
- Stellen Sie die am häufigsten verwendeten Optionen frühestens im Menü so ein, dass Anrufe so schnell wie möglich weitergeleitet werden.
- Vermeiden Sie das direkte Verbinden von Dienstnummern mit Anrufwarteschlangen, es sei denn, die Warteschlangen sind 24/7 verfügbar. Anrufwarteschlangen erlauben keine getrennte Anrufbehandlung außerhalb von Stunden oder an Feiertagen. Wenn Sie eine Warteschlange mit einer direkten Nummer haben möchten, weisen Sie die Nummer einer automatischen Telefonzentrale zu, die während der Geschäftszeiten automatisch zur Warteschlange weitergeleitet wird.
- Wenn Sie viele Anrufe erhalten, die grundlegende Informationen zu Ihrem Unternehmen anfordern, beispielsweise Geschäftszeiten, Standort oder Websiteadresse, sollten Sie eine automatische Telefonzentrale erstellen, um diese Fragen mit aufgezeichneten Nachrichten zu beantworten.
- Halten Sie die Liste der Menüelemente auf fünf oder weniger. Anrufer können Probleme haben, sich an mehr als fünf Optionen zu erinnern. Verwenden Sie geschachtelte automatische Telefonzentralen, wenn mehr Optionen für eine ordnungsgemäße Weiterleitung eines Anrufs erforderlich sind.
- Beschreiben Sie zuerst den Dienst, gefolgt von der Option zum Drücken (zum Beispiel: für Verkäufe drücken Sie 1) und nicht umgekehrt (zB. Drücken Sie 1 für Sales). 
- Benutzer Terminologie Ihre Anrufer verstehen nicht, was Sie intern verwenden können.
- Vermeiden Sie häufige Updates für das Anrufrouting. Wenn Sie Ihre Menü Optionen für eine automatische Telefonzentrale in Zukunft ändern, können Sie diese in den ersten 30 Tagen in den Sprachansagen anrufen.

## <a name="resource-accounts-and-phone-numbers"></a>Ressourcenkonten und Telefonnummern

Teams verwendet *[Ressourcenkonten](manage-resource-accounts.md)* , um automatische Telefonzentralen zu verbinden und Warteschlangen anzurufen und Ihnen auf Wunsch Telefonnummern zuzuweisen.

- Für jede Anrufwarteschlange und für die automatische Telefonzentrale ist mindestens ein Ressourcenkonto erforderlich.
- Für jedes Ressourcenkonto ist eine ﻿kostenlose Telefonanlage (Virtual User License) erforderlich.
- Einem Ressourcenkonto kann optional eine oder mehrere Servicenummern zugewiesen werden. (So werden Telefonnummern automatischen Telefonzentralen und Anrufwarteschlangen zugewiesen.)

Sie können einem Ressourcenkonto eine [Microsoft-Dienstnummer](getting-service-phone-numbers.md), eine direkte Routingnummer oder eine Hybrid Nummer zuweisen.

Sie können entweder gebührenpflichtige oder gebührenfreie Servicenummern nutzen. Sie können keine Benutzer Telefonnummern für automatische Telefonzentralen oder Anrufwarteschlangen verwenden.

## <a name="getting-started"></a>Erste Schritte

Nachdem Sie die Planungsaufgaben in diesem Artikel abgeschlossen haben, führen Sie die folgenden Schritte aus, um Ihre automatischen Telefonzentralen und Anrufwarteschlangen einzurichten:

1. Rufen Sie die Dienstnummern ab, die Sie für die automatischen Telefonzentralen benötigen, und rufen Sie Warteschlangen auf, auf die Sie über direkte Wählverbindungen von außerhalb Ihrer Organisation aus zugreifen möchten. Dies kann die [Übertragung von Nummern von einem anderen Anbieter](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) oder das [anfordern neuer Dienstnummern](getting-service-phone-numbers.md)sein.

2. Besorgen Sie sich eine [Telefonanlage – eine virtuelle Benutzerlizenz](teams-add-on-licensing/virtual-user.md) für jedes Ressourcenkonto, das Sie erstellen möchten. Da diese Lizenzen kostenlos sind, empfehlen wir Ihnen, ein paar Extras zu erhalten, falls Sie sich entscheiden, in Zukunft Änderungen an Ihren Ressourcenkonten vorzunehmen.

3. [Erstellen Sie ein Ressourcenkonto](manage-resource-accounts.md) für jede automatische Telefonzentrale und Anrufwarteschlange, die Sie erstellen möchten. Weisen Sie jedem Konto eine Telefonanlage zu – virtuelle Benutzerlizenz und optional eine Dienstnummer.

4. [Erstellen Sie die Feiertage](set-up-holidays-in-teams.md) , für die Sie in ihren automatischen Telefonzentralen ein separates Anrufrouting durchführen möchten.

5. Optional können Sie das [Parken und Abrufen von Anrufen einrichten](call-park-and-retrieve.md) , wenn Sie dieses Feature für die Anrufübertragung verwenden möchten.

6. Erstellen Sie die Gruppen, die Sie verwenden möchten, um die Anruf-Agents für die Anrufwarteschlangen zu enthalten.

7. Wenn Sie beabsichtigen, Dial-by-Erweiterung zuzulassen, stellen Sie sicher, dass Sie die Durchwahlnummer Ihrer Benutzer Ihrem Azure Active Directory-Profil hinzugefügt haben.

Nachdem Sie die obigen Schritte ausgeführt haben, können Sie Ihre automatischen Telefonzentralen erstellen und Warteschlangen anrufen. Da automatische Telefonzentralen und Anrufwarteschlangen Anrufe umleiten können, verweisen Sie auf das von Ihnen erstellte Workflowdiagramm, um zu ermitteln, welche automatische Telefonzentrale oder Anrufwarteschlange zuerst erstellt werden soll. In dem Beispiel oben in der obigen Abbildung würden Sie die Warteschlangen für Sales-und Support-Anrufe erstellen, bevor Sie die Haupt automatische Contoso-Telefonzentrale erstellen, weil die Haupt automatische Telefonzentrale Anrufer an die Warteschlangen für Sales-und Support-Anrufe weiterleiten muss.

Informationen zum Erstellen von automatischen Telefonzentralen und Anrufwarteschlangen finden Sie in den folgenden Artikeln:

- [Einrichten einer automatischen Telefonzentrale](create-a-phone-system-auto-attendant.md)
- [Erstellen einer Anrufwarteschlange](create-a-phone-system-call-queue.md)

## <a name="related-topics"></a>Verwandte Themen

[Planen von direktem Routing](direct-routing-plan.md)

[Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Beispiel für Kleinunternehmen – Einrichten einer automatischen Telefonzentrale](/microsoftteams/tutorial-org-aa)
