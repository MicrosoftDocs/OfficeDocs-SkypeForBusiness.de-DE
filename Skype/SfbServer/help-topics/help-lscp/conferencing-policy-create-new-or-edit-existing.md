---
title: Konferenzrichtlinie Erstellen neuer oder Bearbeiten vorhandener Konferenzrichtlinien
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ConfMeetingPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ebd2f120-b57a-4c94-9509-20e098f4b0f4
description: Eine Konferenzrichtlinie definiert die Features und Funktionen, die Benutzern während einer Konferenz zur Verfügung stehen (auch als Besprechung bekannt).
ms.openlocfilehash: 073019a46e2934f78ec0f20b8a7cb8e04c01bab9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121018"
---
# <a name="conferencing-policy-create-new-or-edit-existing"></a>Konferenzrichtlinie: Erstellen einer neuen oder Bearbeiten einer vorhandenen Konferenzrichtlinie

Eine Konferenzrichtlinie definiert die Features und Funktionen, die Benutzern während einer Konferenz zur Verfügung stehen (auch als Besprechung bekannt).

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste sind die Felder der Seite beschrieben.

- **Bereich** Gibt den Bereich der Konferenzrichtlinie an, die Sie erstellen oder ändern: global, website oder benutzer.

- **Name** Jede Konferenzrichtlinie erfordert einen Namen. Globale Konferenzrichtlinien und Websitekonferenzrichtlinien werden standardmäßig benannt, und der Name kann nicht geändert werden. Verwenden Sie für Benutzerkonferenzrichtlinien einen beschreibenden Namen, der den Benutzer oder die Benutzergruppe identifiziert.

    > [!NOTE]
    > Nachdem Sie die Konferenzrichtlinie gespeichert haben, kann der Name nicht geändert werden.

- **Beschreibung** Dieses Feld ist optional. Verwenden Sie sie, um zusätzliche Details zur Konferenzrichtlinie zur Verfügung zu stellen.

- **Organisatorrichtlinie** Die Einstellungen in diesem Abschnitt gelten für den Benutzer, der eine Konferenz organisiert. Wenn eine Einstellung ausgewählt ist, kann der Benutzer eine Konferenz mit dem angegebenen Merkmal organisieren. Wenn keine Einstellung ausgewählt ist, kann der Benutzer keine Konferenz mit diesem Merkmal organisieren. Diese Einstellungen bestimmen nicht, auf was der Benutzer als Teilnehmer an anderen Konferenzen Zugriff hat.

    Klicken Sie auf den Pfeil nach oben oder nach unten neben der Beschriftung, um den Abschnitt zu schließen oder zu öffnen.

- **Maximale Besprechungsgröße** die maximale Anzahl von Benutzern, die an einer Konferenz zulässig sind. Standardmäßig beträgt die maximale Konferenzgröße 250.

- **Zulassen, dass Teilnehmer anonyme Benutzer einladen** Aktivieren Sie dieses Kontrollkästchen, damit Benutzer anonyme Benutzer zu Konferenzen einladen können. Anonyme Benutzer sind Benutzer, die nicht über Anmeldeinformationen in den Active Directory-Domänendiensten Ihrer Organisation verfügen und daher nicht authentifiziert sind.

- **Aufzeichnung** Geben Sie an, ob Teilnehmer Konferenzen aufzeichnen können. Die Optionen sind **None** oder **Aufzeichnung aktivieren.**

- **Aufzeichnen von Verbundteilnehmern und anonymen Teilnehmern zulassen** Aktivieren Sie dieses Kontrollkästchen, um externen und nicht authentifizierten Teilnehmern das Aufzeichnen von Konferenzen zu ermöglichen.

- **Audio/Video** Geben Sie an, ob Teilnehmer Audio und Video verwenden können:

  - **Keine** Wählen Sie diese Option aus, um die Verwendung von Audio und Video zu verhindern.

  - **Aktivieren von IP-Audio** Wählen Sie diese Option aus, um die Verwendung von Audio, aber nicht Video zu ermöglichen.

  - **Aktivieren von IP-Audio/Video** Wählen Sie diese Option aus, um Audio und Video zu ermöglichen.

- **Aktivieren von PSTN-Einwahlkonferenzen** Wenn Sie Audio in **Audio/Video** aktiviert haben, aktivieren Sie dieses Kontrollkästchen, um Benutzern die Einwahl in Konferenzen über das Festnetz (Public Switched Telephone Network, PSTN) zu ermöglichen.

- **Zulassen, dass anonyme Teilnehmer sich auswählen** Aktivieren Sie dieses Kontrollkästchen, wenn Sie Benutzern die Einwahl in Konferenzen erlauben und nicht authentifizierten (anonymen) Benutzern die Teilnahme an einer Konferenz mithilfe von Wähltelefonie ermöglichen möchten. Bei ausgehenden Telefonverbindungen ruft der Konferenzserver den Benutzer an, und der Benutzer nimmt das Gespräch an, um an der Konferenz teilzunehmen.

- **Teilnehmer, die nicht für die Enterprise-VoIP aktiviert sind, zulassen** Wenn Sie Audio in **Audio/Video** aktiviert haben, aktivieren Sie dieses Kontrollkästchen, um Benutzern, die nicht für Enterprise-VoIP aktiviert sind, die Teilnahme an einer Konferenz mithilfe von Einwahltelefonie zu ermöglichen. Wenn der Benutzer über ein Einwahltelefon über den Konferenzserver telefoniert, antwortet der Benutzer dem Telefon, um an der Konferenz teil zu nehmen.

- **Zulassen mehrerer Videostreams** Wenn Sie Video in **Audio/Video** aktiviert haben, aktivieren Sie dieses Kontrollkästchen, um Benutzern das Organisieren von Konferenzen mit dem Video der Galerieansicht zu ermöglichen. Wenn dieses Kontrollkästchen aktiviert ist, können Benutzer mit dieser Einstellung Konferenzen organisieren, die mehrere Videostreams senden. Wenn dieses Kontrollkästchen nicht aktiviert ist, können Benutzer nur Konferenzen organisieren, die einen einzelnen Videostream senden.

    > [!NOTE]
    > Diese Option bestimmt den Typ des Videostreams, der von der Konferenz unterstützt wird. Es wird nicht bestimmt, ob Teilnehmer mehrere Videostreams empfangen können. Die **Option Teilnehmer für die Teilnahme an mehreren Videostreams** aktivieren bestimmt, ob Teilnehmer mehrere Videostreams empfangen können.

- **Datenzusammenarbeit** Geben Sie an, ob die Konferenz die Datenzusammenarbeit zulässt. Die Optionen sind **None** oder **Enable data collaboration**.

    Die folgenden Einstellungen gelten für die Datenzusammenarbeit:

  - **Zulassen, dass Verbundteilnehmer und anonyme Teilnehmer Inhalte herunterladen** Wenn Sie die Datenzusammenarbeit zulassen, aktivieren Sie dieses Kontrollkästchen, um externen und nicht authentifizierten Benutzern das Herunterladen von Inhalten wie Folien oder Handzetteln von einer Konferenz zu ermöglichen.

  - **Zulassen, dass Teilnehmer Dateien übertragen** Wenn Sie die Datenzusammenarbeit zulassen, aktivieren Sie dieses Kontrollkästchen, um Dateiübertragungen an alle Teilnehmer während einer Konferenz zu ermöglichen.

  - **Aktivieren von Anmerkungen** Wenn Sie die Datenzusammenarbeit zulassen, aktivieren Sie dieses Kontrollkästchen, um Teilnehmern das Erstellen von Anmerkungen auf dem Bildschirm zu Inhalten zu ermöglichen, die während der Konferenz freigegeben wurden.

  - **Aktivieren von PowerPoint-Anmerkungen** Wenn Sie Anmerkungen zulassen, aktivieren Sie dieses Kontrollkästchen, damit Teilnehmer Anmerkungen in während der Konferenz freigegebenen PowerPoint-Folien erstellen können.

  - **Aktivieren von Umfragen** Wenn Sie die Datenzusammenarbeit zulassen, aktivieren Sie dieses Kontrollkästchen, um Teilnehmern das Halten einer Umfrage während einer Konferenz zu ermöglichen.

- **Anwendungsfreigabe** Geben Sie an, ob die Konferenz die Anwendungsfreigabe zulässt. Die Optionen sind **Deaktivieren der Anwendungsfreigabe oder** Aktivieren der **Anwendungsfreigabe.**

    Die folgenden Einstellungen gelten für die Anwendungsfreigabe:

  - **Zulassen, dass Teilnehmer die Kontrolle übernehmen** Wenn Sie die Anwendungsfreigabe zulassen, aktivieren Sie dieses Kontrollkästchen, um Teilnehmern die Kontrolle über Anwendungen oder Desktops zu ermöglichen, die während der Konferenz freigegeben werden.

  - **Zulassen, dass Verbundteilnehmer und anonyme Teilnehmer die Kontrolle übernehmen** Wenn Sie die Anwendungsfreigabe zulassen, aktivieren Sie dieses Kontrollkästchen, um externen und nicht authentifizierten Teilnehmern die Kontrolle über Anwendungen oder Desktops zu ermöglichen, die während der Konferenz freigegeben werden.

- **Teilnehmerrichtlinie** Die Einstellungen in diesem Abschnitt gelten für Benutzer als Teilnehmer an einer Konferenz oder einer Sitzung mit zwei Teilnehmern. Da es sich bei den folgenden Einstellungen um Benutzereinstellungen handelt, kann ein Benutzer in einer Konferenz oder einer Sitzung mit zwei Parteien andere Funktionen haben als ein anderer Benutzer in derselben Konferenz- oder Zwei-Parteien-Sitzung.

    Klicken Sie auf den Pfeil nach oben oder nach unten neben der Beschriftung, um den Abschnitt zu schließen oder zu öffnen.

- Wählen **Sie Anwendungs- und Desktopfreigabe aktivieren** aus, damit Benutzer Anwendungen oder ihren Desktop freigeben können, während sie an einer Konferenz oder einer Sitzung mit zwei Parteien teilnehmen. Wählen **Sie Anwendungs- und Desktopfreigabe deaktivieren** aus, um zu verhindern, dass Benutzer Anwendungen oder ihren Desktop freigeben, während sie an einer Konferenz oder einer Sitzung mit zwei Parteien teilnehmen.

- **Aktivieren der Peer-zu-Peer-Dateiübertragung** Aktivieren Sie dieses Kontrollkästchen, um Dateiübertragungen zwischen Personen (d. h. Dateiübertragungen, die nicht alle Teilnehmer betreffen) während einer Konferenz oder einer Sitzung mit zwei Teilnehmern zu ermöglichen.

- **Aktivieren der Peer-zu-Peer-Aufzeichnung** Aktivieren Sie dieses Kontrollkästchen, damit Benutzer Sitzungen mit zwei Parteien aufzeichnen können.

- **Aktivieren der Teilnahme an mehreren Videostreams** Aktivieren Sie dieses Kontrollkästchen, um Teilnehmern den Empfang von Video in der Galerieansicht in Konferenzen zu ermöglichen, die dies zulassen. Wenn diese Option nicht ausgewählt ist, können Teilnehmer nur einen einzelnen Videostream erhalten, unabhängig davon, was die Konferenz zulässt.

    > [!NOTE]
    > Die **Option Mehrere Videostreams zulassen** bestimmt, ob eine Konferenz mehrere Videostreams zulässt.

Ausführliche Informationen zu den Konferenzfunktionen finden Sie unter [Overview of Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-conferencing) in der Planungsdokumentation. Ausführliche Informationen zur Verwendung von Konferenzrichtlinien finden Sie unter [Conferencing Policies](/previous-versions/office/lync-server-2013/lync-server-2013-conferencing-policies) in der Betriebsdokumentation.