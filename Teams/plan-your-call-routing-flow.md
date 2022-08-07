---
title: Planen des Anrufweiterleitungsflusses für Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
ms.custom:
- Phone System
description: Erfahren Sie, wie Sie Ihren Anrufweiterleitungsfluss für automatische Telefonzentralen und Anrufwarteschleifen in Microsoft Teams planen.
ms.openlocfilehash: c883d6e104d73bf4082f69128af141f489d7cf89
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270530"
---
# <a name="plan-your-call-routing-flow"></a>Planen des Anrufweiterleitungsflusses

Im Rahmen des Planungsprozesses wird empfohlen, das Anrufrouting für Ihre Organisation in einem Diagramm zu erarbeiten. Das Diagramm hilft dabei, das effizienteste Routing für Personen zu ermitteln, die sich in Ihre Organisation einschalten. Sie können das Diagramm auch verwenden, um die automatischen Telefonzentralen und Anrufwarteschleifen zu ermitteln, die Sie erstellen müssen, zusammen mit den zugehörigen Anforderungen wie Dienstnummern, Lizenzen und Ressourcenkonten.

Sehen wir uns an, wie automatische Telefonzentralen und Anrufwarteschleifen Anrufe weiterleiten.

Automatische Telefonzentralen leiten alle Anrufe auf eine der folgenden Arten weiter:

- **Umleitung sofort** – Anrufe können unmittelbar nach der Beantwortung oder nach einer ersten Begrüßung an eines der (unten aufgeführten) Anrufweiterleitungsziele umgeleitet werden.
- **Umleitung basierend auf Wähloptionen** – Anrufer können angeleitet werden, um zwischen den Optionen zu wählen, die den Nummern auf der Wähltastatur ihres Telefons zugewiesen sind, 0-9. Jeder Wähltaste kann ein Anrufroutingziel zugewiesen werden.
- **Wählen Sie Personen nach Name oder Durchwahl** . Anrufer können angewiesen werden, die Durchwahlnummer der Person zu wählen, die sie im Verzeichnis Ihrer Organisation erreichen möchten, oder indem Sie den Namen der Person schreiben.
- **Verbindung trennen** – eine automatische Telefonzentrale kann den Anruf auflegen.

> [!NOTE]
> Eine einzelne automatische Telefonzentrale kann nur eine einzelne "Dial by"-Methode unterstützen.  Damit Anrufer nach Name und Rufnummer wählen können, müssen Sie eine automatische Telefonzentrale erstellen, die über eine Option zum Wählen nach Namen und die andere für die Durchwahl verfügt.  Jede dieser Optionen wird zu separaten automatischen Telefonzentralen weitergeleitet, die für diese Szenarien mit "Wählhilfe" konfiguriert sind.

Wenn Anrufe von einer automatischen Telefonzentrale oder Anrufwarteschleife umgeleitet werden, können Sie aus den folgenden Anrufweiterleitungszielen wählen:

- **Person in der Organisation** – eine Person in Ihrer Organisation, die Sprachanrufe empfangen kann. Dies kann ein Onlinebenutzer oder ein Lokal gehosteter Benutzer sein, der mit Skype for Business Server gehostet wird.
- **VoIP-App** – eine andere automatische Telefonzentrale oder anrufwarteschleife. Wählen Sie das dem Ziel zugeordnete Ressourcenkonto aus.
- **Externe Telefonnummer** – beliebige Telefonnummer. Sehen Sie [sich die technischen Details zur externen Übertragung an](create-a-phone-system-auto-attendant.md?tabs=additional-resources).

- **Voicemail** – das VoIP-Postfach, das einer von Ihnen angegebenen Microsoft 365-Gruppe zugeordnet ist. Sie können auswählen, ob Voicemailtranskriptionen und die Option "Bitte hinterlasse eine Nachricht nach dem Ton" angezeigt werden sollen. Systemaufforderung.
- **Operator** (nur automatische Telefonzentrale) – der für die automatische Telefonzentrale definierte Operator. Das Definieren eines Operators ist optional. Ein Operator kann ein beliebiges der anderen Ziele in dieser Liste sein.

Automatische Telefonzentralen bieten separate Anrufweiterleitungsoptionen für Anrufe, die außerhalb der Geschäftszeiten und an Feiertagen eingehen.

Anrufwarteschleifen setzen den Anrufer in den Haltebereich, bis ein der Warteschleife zugewiesener Agent für den Anruf verfügbar ist. Es gibt zwei Situationen, in denen ein Anrufer aus der Warteschleife geleitet wird:

- **Anrufüberlauf** : Wenn die Anzahl der Anrufe in der Warteschleife den von Ihnen festgelegten Grenzwert überschreitet, werden neue Anrufer aus der Warteschleife umgeleitet.
- **Anruftimeout** : Wenn sich ein Anrufer länger als die konfigurierte Timeouteinstellung in der Warteschleife befunden hat, wird er aus der Warteschlange umgeleitet.

Anrufe, die aus einer Warteschleife umgeleitet werden, können an eines der oben aufgeführten Anrufweiterleitungsziele mit Ausnahme eines Operators gesendet werden. (Anrufwarteschleifen haben keine Operatoren, aber Sie können Anrufer an das gleiche Ziel umleiten wie ein Operator, den Sie für eine automatische Telefonzentrale konfiguriert haben.)

Das folgende Beispiel zeigt ein Beispiel für das Anrufrouting mithilfe von automatischen Telefonzentralen und Anrufwarteschleifen.

![Diagramm der Anrufweiterleitung mithilfe von automatischen Telefonzentralen und Anrufwarteschleifen.](media/attendant-and-queue-call-routing.png)

Im obigen Beispiel:

- Der Nullschlüssel (0) leitet Anrufer an einen Operator um. Der Operator für diese automatische Telefonzentrale wurde als **Person in der Organisation** konfiguriert.
- Mit dem einen (1) Schlüssel werden Anrufer an die Verkaufsanrufwarteschleife umgeleitet. Diese Anrufwarteschleife ist mit einem Team verbunden, das das der Warteschlange zugewiesene Vertriebsteam enthält.
- Die beiden (2) Schlüssel leiten Anrufer an die Supportanrufwarteschleife um. Diese Anrufwarteschleife ist mit einem Team verbunden, das das dem Team zugewiesene Supportteam enthält.
- Die Supportanrufwarteschleife verfügt über eine direkte Telefonnummer über eine dazwischenliegende automatische Telefonzentrale. Wenn eine automatische Telefonzentrale die Supportzeile beantwortet, können Sie die Abwesenheitsstunden und die Anrufweiterleitung für Feiertage trennen.
- Der drei (3) Schlüssel leitet Benutzer zu einer anderen automatischen Telefonzentrale für das Unternehmensverzeichnis um. Die automatische Telefonzentrale des Unternehmensverzeichnisses ermöglicht Es Anrufern, Einzelpersonen in der Organisation anzurufen, indem sie ihren Namen oder ihre Erweiterung wählen.

Es wird empfohlen, ein oder mehrere Diagramme zu erstellen, die dem oben genannten ähneln, um Ihre Anrufweiterleitung zuzuordnen. Achten Sie darauf, Folgendes in Ihr Diagramm oder die zugehörige Dokumentation einzuschließen:

- Welche automatischen Telefonzentralen haben direkten Zugriff über Telefonnummern?
- Was sind die Anforderungen an die Abwesenheits- und Feiertagsweiterleitung für jede automatische Telefonzentrale?
- Die Mitgliedschaft für jede Anrufwarteschleife. (Sie können Benutzer einzeln hinzufügen oder die Warteschlange verschiedenen Gruppentypen zuordnen. Das Zuordnen einer Warteschlange zu einem Team bietet die vielseitigste Erfahrung.)

Hier sind einige bewährte Methoden für die Anrufweiterleitung:

- Sehen Sie sich Ihr vorhandenes Anrufsystem an, und analysieren Sie die Arten und Häufigkeit eingehender Anrufe. Verwenden Sie diese Informationen, um Ihre automatische Telefonzentrale und die Struktur der Anrufwarteschleife zu informieren.
- Platzieren Sie die am häufigsten verwendeten Optionen frühestens in das Menü, um Anrufe so schnell wie möglich weiterzuleiten.
- Vermeiden Sie es, Servicenummern direkt mit Anrufwarteschleifen zu verbinden, es sei denn, die Warteschlangen sind 24/7 verfügbar. Anrufwarteschleifen ermöglichen keine separate Anrufbehandlung für Freie Stunden oder Feiertage. Wenn Sie eine Warteschlange mit einer direkten Nummer haben möchten, weisen Sie die Nummer einer automatischen Telefonzentrale zu, die während der Geschäftszeiten automatisch zur Warteschlange umleitet.
- Wenn Sie zahlreiche Anrufe erhalten, die grundlegende Informationen zu Ihrem Unternehmen anfordern, z. B. Geschäftszeiten, Standort oder Websiteadresse, sollten Sie erwägen, eine automatische Telefonzentrale zu erstellen, um diese Fragen mit aufgezeichneten Nachrichten zu beantworten.
- Behalten Sie die Liste der Menüelemente auf fünf oder weniger bei. Anrufer können Probleme haben, sich mehr als fünf Optionen zu merken. Verwenden Sie geschachtelte automatische Telefonzentralen, wenn weitere Optionen erforderlich sind, um einen Anruf ordnungsgemäß weiterzuleiten.
- Beschreiben Sie zuerst den Dienst, gefolgt von der Option zum Drücken (z. B. Für Vertrieb drücken Sie 1) und nicht umgekehrt (z. B. Drücken Sie 1 für Den Vertrieb).
- Benutzerterminologie, die Ihre Anrufer verstehen, anstatt zu verstehen, was Sie intern verwenden können.
- Vermeiden Sie häufige Updates für das Anrufrouting. Wenn Sie ihre Menüoptionen für eine automatische Telefonzentrale in Zukunft ändern, rufen Sie diese in den Sprachansagen für die ersten 30 Tage an.
