---
title: Konferenzrichtlinie – Erstellen einer neuen oder Bearbeiten einer vorhandenen Konferenzrichtlinie
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ConfMeetingPolicyEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: ebd2f120-b57a-4c94-9509-20e098f4b0f4
ROBOTS: NOINDEX, NOFOLLOW
description: Eine Konferenzrichtlinie definiert die Features und Funktionen, die Benutzern während einer Konferenz zur Verfügung stehen (auch bekannt als Besprechung).
ms.openlocfilehash: a7e5e32d474a915c8c91bfe13fa13feffe98d064
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60837277"
---
# <a name="conferencing-policy-create-new-or-edit-existing"></a>Konferenzrichtlinie: Erstellen einer neuen oder Bearbeiten einer vorhandenen Konferenzrichtlinie

Eine Konferenzrichtlinie definiert die Features und Funktionen, die Benutzern während einer Konferenz zur Verfügung stehen (auch bekannt als Besprechung).

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste sind die Felder der Seite beschrieben.

- **Bereich** Gibt den Bereich der Konferenzrichtlinie an, die Sie erstellen oder ändern: global, Standort oder Benutzer.

- **Name** Jede Konferenzrichtlinie erfordert einen Namen. Globale und Standortkonferenzrichtlinien werden standardmäßig benannt, und der Name kann nicht geändert werden. Verwenden Sie für Benutzerkonferenzrichtlinien einen beschreibenden Namen, der den Benutzer oder die Benutzergruppe identifiziert.

    > [!NOTE]
    > Nachdem Sie die Konferenzrichtlinie gespeichert haben, kann der Name nicht mehr geändert werden.

- **Beschreibung** Dieses Feld ist optional. Verwenden Sie sie, um zusätzliche Details zur Konferenzrichtlinie bereitzustellen.

- **Organisatorrichtlinie** Die Einstellungen in diesem Abschnitt gelten für den Benutzer, der eine Konferenz organisiert. Wenn eine Einstellung ausgewählt ist, kann der Benutzer eine Konferenz organisieren, die das angegebene Merkmal aufweist. Wenn keine Einstellung ausgewählt ist, kann der Benutzer keine Konferenz mit dieser Eigenschaft organisieren. Diese Einstellungen bestimmen nicht, worauf der Benutzer als Teilnehmer an anderen Konferenzen zugreifen kann.

    Klicken Sie auf den Pfeil nach oben oder nach unten neben der Beschriftung, um den Abschnitt zu schließen oder zu öffnen.

- **Maximale Besprechungsgröße** die maximale Anzahl von Benutzern, die in einer Konferenz zulässig sind. Standardmäßig beträgt die maximale Konferenzgröße 250.

- **Teilnehmer dürfen anonyme Benutzer einladen** Aktivieren Sie dieses Kontrollkästchen, damit Benutzer anonyme Benutzer zu Konferenzen einladen können. Anonyme Benutzer sind Benutzer, die keine Anmeldeinformationen in den Active Directory-Domänendiensten Ihrer Organisation haben und daher nicht authentifiziert sind.

- **Aufzeichnung** Geben Sie an, ob Teilnehmer Konferenzen aufzeichnen können. Die Optionen sind **None** oder **Enable recording**.

- **Zulassen der Aufzeichnung von Verbundteilnehmern und anonymen Teilnehmern** Aktivieren Sie dieses Kontrollkästchen, um externen und nicht authentifizierten Teilnehmern das Aufzeichnen von Konferenzen zu ermöglichen.

- **Audio/Video** Geben Sie an, ob Teilnehmer Audio und Video verwenden können:

  - **Keine** Wählen Sie diese Option aus, um die Verwendung von Audio und Video zu verhindern.

  - **Ip-Audio aktivieren** Wählen Sie diese Option aus, um die Verwendung von Audio, aber nicht von Video zuzulassen.

  - **Ip-Audio/Video aktivieren** Wählen Sie diese Option aus, um Sowohl Audio als auch Video zuzulassen.

- **Aktivieren von PSTN-Einwahlkonferenzen** Wenn Sie Audio in **Audio/Video** aktiviert haben, aktivieren Sie dieses Kontrollkästchen, um Benutzern das Einwählen in Konferenzen über das Telefonfestnetz (Public Switched Telephone Network, PSTN) zu ermöglichen.

- **Anonymen Teilnehmern das Ausgehende gestatten** Aktivieren Sie dieses Kontrollkästchen, wenn Sie Benutzern das Einwählen in Konferenzen gestatten und nicht authentifizierten (anonymen) Benutzern die Teilnahme an einer Konferenz über ausgehende Telefonverbindungen gestatten möchten. Bei ausgehenden Telefonverbindungen ruft der Konferenzserver den Benutzer an, und der Benutzer nimmt das Gespräch an, um an der Konferenz teilzunehmen.

- **Teilnehmer, die nicht für Enterprise-VoIP aktiviert sind, dürfen ausgehende Anrufe wählen** Wenn Sie Audio in **Audio/Video** aktiviert haben, aktivieren Sie dieses Kontrollkästchen, um Benutzern, die nicht für Enterprise-VoIP aktiviert sind, die Teilnahme an einer Konferenz über ausgehende Telefonverbindungen zu ermöglichen. Bei ausgehenden Telefonverbindungen telefoniert der Konferenzserver den Benutzer, und der Benutzer antwortet dann auf das Telefon, um an der Konferenz teilzunehmen.

- **Zulassen mehrerer Videostreams** Wenn Sie Video in **Audio/Video** aktiviert haben, aktivieren Sie dieses Kontrollkästchen, um Benutzern das Organisieren von Konferenzen mit Dem Video "Katalogansicht" zu ermöglichen. Wenn dieses Kontrollkästchen aktiviert ist, können Benutzer mit dieser Einstellung Konferenzen organisieren, die mehrere Videostreams senden. Wenn dieses Kontrollkästchen nicht aktiviert ist, können Benutzer nur Konferenzen organisieren, die einen einzelnen Videostream senden.

    > [!NOTE]
    > Diese Option bestimmt den Typ des von der Konferenz unterstützten Videostreams. Es bestimmt nicht, ob Teilnehmer mehrere Videostreams empfangen können. Die Option **"Teilnehmer für die Teilnahme mit mehreren Videostreams** aktivieren" bestimmt, ob Teilnehmer mehrere Videostreams empfangen können.

- **Datenzusammenarbeit** Geben Sie an, ob die Konferenz die Datenzusammenarbeit zulässt. Die Optionen sind **"None"** oder **"Datenzusammenarbeit aktivieren".**

    Die folgenden Einstellungen gelten für die Datenzusammenarbeit:

  - **Partnerteilnehmern und anonymen Teilnehmern das Herunterladen von Inhalten gestatten** Wenn Sie die Datenzusammenarbeit zulassen, aktivieren Sie dieses Kontrollkästchen, um externen und nicht authentifizierten Benutzern das Herunterladen von Inhalten wie Folien oder Handzetteln aus einer Konferenz zu ermöglichen.

  - **Teilnehmer dürfen Dateien übertragen** Wenn Sie die Datenzusammenarbeit zulassen, aktivieren Sie dieses Kontrollkästchen, um Dateiübertragungen an alle Teilnehmer während einer Konferenz zuzulassen.

  - **Aktivieren von Anmerkungen** Wenn Sie die Datenzusammenarbeit zulassen, aktivieren Sie dieses Kontrollkästchen, um Teilnehmern das Erstellen von Anmerkungen auf dem Bildschirm zu Inhalten zu ermöglichen, die während der Konferenz freigegeben wurden.

  - **Aktivieren PowerPoint Anmerkungen** Wenn Sie Anmerkungen zulassen, aktivieren Sie dieses Kontrollkästchen, damit Teilnehmer Anmerkungen in PowerPoint Folien erstellen können, die während der Konferenz freigegeben wurden.

  - **Aktivieren von Umfragen** Wenn Sie die Datenzusammenarbeit zulassen, aktivieren Sie dieses Kontrollkästchen, damit Teilnehmer während einer Konferenz eine Umfrage abhalten können.

- **Anwendungsfreigabe** Geben Sie an, ob die Konferenz die Anwendungsfreigabe zulässt. Die Optionen sind **"Anwendungsfreigabe deaktivieren"** oder **"Anwendungsfreigabe aktivieren".**

    Die folgenden Einstellungen gelten für die Anwendungsfreigabe:

  - **Zulassen, dass Teilnehmer die Kontrolle übernehmen** Wenn Sie die Anwendungsfreigabe zulassen, aktivieren Sie dieses Kontrollkästchen, damit Teilnehmer die Kontrolle über Anwendungen oder Desktops übernehmen können, die während der Konferenz freigegeben werden.

  - **Zulassen, dass Partnerteilnehmer und anonyme Teilnehmer die Kontrolle übernehmen** Wenn Sie die Anwendungsfreigabe zulassen, aktivieren Sie dieses Kontrollkästchen, damit externe und nicht authentifizierte Teilnehmer die Kontrolle über Anwendungen oder Desktops übernehmen können, die während der Konferenz freigegeben werden.

- **Teilnehmerrichtlinie** Die Einstellungen in diesem Abschnitt gelten für Benutzer als Teilnehmer an einer Konferenz oder Sitzung mit zwei Teilnehmern. Da es sich bei den folgenden Einstellungen um Benutzereinstellungen handelt, kann ein Benutzer in einer Konferenz oder Sitzung mit zwei Teilnehmern andere Funktionen als ein anderer Benutzer in derselben Konferenz oder Sitzung mit zwei Teilnehmern haben.

    Klicken Sie auf den Pfeil nach oben oder nach unten neben der Beschriftung, um den Abschnitt zu schließen oder zu öffnen.

- Wählen Sie **"Anwendungs- und Desktopfreigabe aktivieren"** aus, um Benutzern das Freigeben von Anwendungen oder deren Desktop während der Teilnahme an einer Konferenz oder Sitzung mit zwei Teilnehmern zu ermöglichen. Wählen Sie **"Anwendungs- und Desktopfreigabe deaktivieren"** aus, um zu verhindern, dass Benutzer Anwendungen oder ihren Desktop freigeben, während sie an einer Konferenz oder Sitzung mit zwei Teilnehmern teilnehmen.

- **Aktivieren der Peer-to-Peer-Dateiübertragung** Aktivieren Sie dieses Kontrollkästchen, um Dateiübertragungen zwischen Personen (d. h. Dateiübertragungen, an denen nicht alle Teilnehmer beteiligt sind) während einer Konferenz oder Sitzung mit zwei Teilnehmern zuzulassen.

- **Aktivieren der Peer-to-Peer-Aufzeichnung** Aktivieren Sie dieses Kontrollkästchen, um Benutzern das Aufzeichnen von Sitzungen mit zwei Teilnehmern zu ermöglichen.

- **Teilnehmer können mit mehreren Videostreams teilnehmen** Aktivieren Sie dieses Kontrollkästchen, um Teilnehmern das Empfangen von Katalogansichtsvideos in Konferenzen zu ermöglichen, die dies zulassen. Wenn diese Option nicht ausgewählt ist, können teilnehmer nur einen einzelnen Videostream empfangen, unabhängig davon, was die Konferenz zulässt.

    > [!NOTE]
    > Der **Wert "Mehrere Videodatenströme zulassen"** bestimmt, ob eine Konferenz mehrere Videostreams zulässt.

Ausführliche Informationen zu den Konferenzfunktionen finden Sie unter [Overview of Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-conferencing) in der Planungsdokumentation. Ausführliche Informationen zur Verwendung von Konferenzrichtlinien finden Sie unter [Conferencing Policies](/previous-versions/office/lync-server-2013/lync-server-2013-conferencing-policies) in der Betriebsdokumentation.