---
title: 'Konferenzrichtlinie: Erstellen einer neuen oder Bearbeiten einer vorhandenen Konferenzrichtlinie'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ConfMeetingPolicyEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: ebd2f120-b57a-4c94-9509-20e098f4b0f4
ROBOTS: NOINDEX, NOFOLLOW
description: Eine Konferenzrichtlinie definiert die Funktionen und Funktionen, die Benutzer während einer Konferenz (auch als Besprechung bekannt) zur Verfügung haben.
ms.openlocfilehash: 97b022771f0077239475137496c222748b6ef828
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824885"
---
# <a name="conferencing-policy-create-new-or-edit-existing"></a>Konferenzrichtlinie: Erstellen einer neuen oder Bearbeiten einer vorhandenen Konferenzrichtlinie

Eine Konferenzrichtlinie definiert die Funktionen und Funktionen, die Benutzer während einer Konferenz (auch als Besprechung bekannt) zur Verfügung haben.

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste sind die Felder der Seite beschrieben.

- **Bereich** Gibt den Bereich der Konferenzrichtlinie an, die Sie erstellen oder ändern: global, Standort oder Benutzer.

- **Name** Jede Konferenzrichtlinie erfordert einen Namen. Globale Konferenzrichtlinien und Standortkonferenzrichtlinien werden standardmäßig benannt, und der Name kann nicht geändert werden. Verwenden Sie für Benutzerkonferenzrichtlinien einen beschreibenden Namen, der den Benutzer oder die Benutzergruppe identifiziert.

    > [!NOTE]
    > Nachdem Sie die Konferenzrichtlinie gespeichert haben, kann der Name nicht mehr geändert werden.

- **Beschreibung** Dieses Feld ist optional. Verwenden Sie diese, um zusätzliche Details zur Konferenzrichtlinie zur Verfügung zu stellen.

- **Organisatorrichtlinie** Die Einstellungen in diesem Abschnitt gelten für den Benutzer, der eine Konferenz organisiert. Wenn eine Einstellung ausgewählt ist, kann der Benutzer eine Konferenz mit dem angegebenen Merkmal organisieren. Wenn keine Einstellung ausgewählt ist, kann der Benutzer keine Konferenz mit diesem Merkmal organisieren. Diese Einstellungen bestimmen nicht, auf was der Benutzer als Teilnehmer an anderen Konferenzen Zugriff hat.

    Klicken Sie auf den Nach-oben- oder Abwärtspfeil neben der Beschriftung, um den Abschnitt zu schließen oder zu öffnen.

- **Maximale Besprechungsgröße** die maximale Anzahl von Benutzern, die für eine Konferenz zulässig sind. Standardmäßig beträgt die maximale Konferenzgröße 250.

- **Teilnehmer dürfen anonyme Benutzer einladen** Aktivieren Sie dieses Kontrollkästchen, damit Benutzer anonyme Benutzer zu Konferenzen einladen können. Anonyme Benutzer sind Benutzer, die nicht über Anmeldeinformationen in den Active Directory-Domänendiensten Ihrer Organisation verfügen und daher nicht authentifiziert sind.

- **Aufzeichnung** Geben Sie an, ob Teilnehmer Konferenzen aufzeichnen können. Die Optionen sind **"Keine"** oder **"Aufzeichnung aktivieren".**

- **Zulassen der Aufzeichnung von Partnerteilnehmern und anonymen Teilnehmern** Aktivieren Sie dieses Kontrollkästchen, um externen und nicht authentifizierten Teilnehmern das Aufzeichnen von Konferenzen zu ermöglichen.

- **Audio/Video** Geben Sie an, ob Teilnehmer Audio und Video verwenden können:

  - **Keine** Wählen Sie diese Option aus, um die Verwendung von Audio und Video zu verhindern.

  - **Aktivieren von IP-Audio** Wählen Sie diese Option aus, um die Verwendung von Audio, aber nicht von Video zu ermöglichen.

  - **Aktivieren von IP-Audio/Video** Wählen Sie diese Option aus, um Audio und Video zu ermöglichen.

- **Aktivieren von PSTN-Einwahlkonferenzen** Wenn Sie Audio in **Audio/Video** aktiviert haben, aktivieren Sie dieses Kontrollkästchen, um Benutzern die Einwahl in Konferenzen über das Festnetz (Public Switched Telephone Network, PSTN) zu ermöglichen.

- **Anonyme Teilnehmer dürfen sich abwählen** Aktivieren Sie dieses Kontrollkästchen, wenn Sie Benutzern das Einwählen in Konferenzen gestatten und nicht authentifizierten (anonymen) Benutzern die Teilnahme an einer Konferenz mithilfe von Abwahltelefonen ermöglichen möchten. Bei ausgehenden Telefonverbindungen ruft der Konferenzserver den Benutzer an, und der Benutzer nimmt das Gespräch an, um an der Konferenz teilzunehmen.

- **Teilnehmer, die nicht für die Enterprise-VoIP aktiviert sind, dürfen sich abwählen.** Wenn Sie Audio in **Audio/Video** aktiviert haben, aktivieren Sie dieses Kontrollkästchen, um Benutzern, die nicht für Enterprise-VoIP aktiviert sind, die Teilnahme an einer Konferenz mithilfe von Auswahltelefonie zu ermöglichen. Bei der Einwahltelefonie telefoniert der Konferenzserver mit dem Benutzer, und der Benutzer gibt das Telefon an, um an der Konferenz teil zu werden.

- **Zulassen mehrerer Videostreams** Wenn Sie Video in **Audio/Video** aktiviert haben, aktivieren Sie dieses Kontrollkästchen, damit Benutzer Konferenzen mit Dem Katalogansichtsvideo organisieren können. Wenn dieses Kontrollkästchen aktiviert ist, können Benutzer mit dieser Einstellung Konferenzen organisieren, die mehrere Videostreams senden. Wenn dieses Kontrollkästchen nicht aktiviert ist, können Benutzer nur Konferenzen organisieren, die einen einzelnen Videostream senden.

    > [!NOTE]
    > Diese Option bestimmt den Typ des Videostreams, der von der Konferenz unterstützt wird. Es bestimmt nicht, ob Teilnehmer mehrere Videostreams empfangen können. Die **Option "Teilnehmer für die Teilnahme mit mehreren Videostreams aktivieren"** bestimmt, ob Teilnehmer mehrere Videostreams empfangen können.

- **Datenzusammenarbeit** Geben Sie an, ob die Konferenz die Datenzusammenarbeit zulässt. Die Optionen sind **"Keine"** oder **"Datenzusammenarbeit aktivieren".**

    Die folgenden Einstellungen gelten für die Datenzusammenarbeit:

  - **Zulassen des Herunterladens von Inhalten durch Partnerteilnehmer und anonyme Teilnehmer** Wenn Sie die Datenzusammenarbeit zulassen, aktivieren Sie dieses Kontrollkästchen, um externen und nicht authentifizierten Benutzern das Herunterladen von Inhalten wie Folien oder Handzetteln aus einer Konferenz zu ermöglichen.

  - **Teilnehmer dürfen Dateien übertragen** Wenn Sie die Datenzusammenarbeit zulassen, aktivieren Sie dieses Kontrollkästchen, um Dateiübertragungen an alle Teilnehmer während einer Konferenz zu ermöglichen.

  - **Aktivieren von Anmerkungen** Wenn Sie die Datenzusammenarbeit zulassen, aktivieren Sie dieses Kontrollkästchen, um Teilnehmern das Erstellen von Anmerkungen auf dem Bildschirm zu Inhalten zu ermöglichen, die während der Konferenz freigegeben wurden.

  - **Aktivieren von PowerPoint-Anmerkungen** Wenn Sie Anmerkungen zulassen, aktivieren Sie dieses Kontrollkästchen, damit Teilnehmer Anmerkungen in während der Konferenz freigegebenen PowerPoint-Folien erstellen können.

  - **Aktivieren von Umfragen** Wenn Sie die Datenzusammenarbeit zulassen, aktivieren Sie dieses Kontrollkästchen, damit Teilnehmer während einer Konferenz eine Umfrage halten können.

- **Anwendungsfreigabe** Geben Sie an, ob die Konferenz die Anwendungsfreigabe zulässt. Die Optionen sind **"Anwendungsfreigabe deaktivieren" oder** **"Anwendungsfreigabe aktivieren".**

    Die folgenden Einstellungen gelten für die Anwendungsfreigabe:

  - **Teilnehmern erlauben, die Steuerung zu übernehmen** Wenn Sie die Anwendungsfreigabe zulassen, aktivieren Sie dieses Kontrollkästchen, damit Teilnehmer die Kontrolle über Anwendungen oder Desktops übernehmen können, die während der Konferenz freigegeben werden.

  - **Zulassen der Steuerung durch Partnerteilnehmer und anonyme Teilnehmer** Wenn Sie die Anwendungsfreigabe zulassen, aktivieren Sie dieses Kontrollkästchen, damit externe und nicht authentifizierte Teilnehmer die Kontrolle über Anwendungen oder Desktops übernehmen können, die während der Konferenz freigegeben werden.

- **Teilnehmerrichtlinie** Die Einstellungen in diesem Abschnitt gelten für Benutzer als Teilnehmer an einer Konferenz oder Sitzung mit zwei Teilnehmern. Da es sich bei den folgenden Einstellungen um Benutzereinstellungen handelt, kann ein Benutzer in einer Konferenz oder Sitzung mit zwei Parteien andere Funktionen haben als ein anderer Benutzer in derselben Konferenz oder Sitzung mit zwei Parteien.

    Klicken Sie auf den Nach-oben- oder Abwärtspfeil neben der Beschriftung, um den Abschnitt zu schließen oder zu öffnen.

- Wählen **Sie "Anwendungs- und Desktopfreigabe aktivieren"** aus, damit Benutzer Anwendungen oder ihren Desktop freigeben können, während sie an einer Konferenz oder Sitzung mit zwei Parteien teilnehmen. Wählen **Sie "Anwendungs- und Desktopfreigabe deaktivieren"** aus, um zu verhindern, dass Benutzer Anwendungen oder ihren Desktop freigeben, während sie an einer Konferenz oder Sitzung mit zwei Parteien teilnehmen.

- **Aktivieren der Peer-zu-Peer-Dateiübertragung** Aktivieren Sie dieses Kontrollkästchen, um Dateiübertragungen zwischen Personen (d. h. Dateiübertragungen, an denen nicht alle Teilnehmer beteiligt sind) während einer Konferenz oder Sitzung mit zwei Teilnehmern zu ermöglichen.

- **Aktivieren der Peer-zu-Peer-Aufzeichnung** Aktivieren Sie dieses Kontrollkästchen, damit Benutzer Sitzungen mit zwei Parteien aufzeichnen können.

- **Teilnehmer für die Teilnahme mit mehreren Videostreams aktivieren** Aktivieren Sie dieses Kontrollkästchen, um Teilnehmern den Empfang von Katalogansichtsvideos in Konferenzen zu ermöglichen, die dies zulassen. Wenn diese Option nicht ausgewählt ist, können Teilnehmer unabhängig davon, was die Konferenz zulässt, nur einen einzelnen Videostream empfangen.

    > [!NOTE]
    > Der **Parameter "Mehrere Videostreams zulassen"** bestimmt, ob eine Konferenz mehrere Videostreams zulässt.

Ausführliche Informationen zu den Konferenzfunktionen finden Sie unter [Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) in der Planungsdokumentation. Ausführliche Informationen zur Verwendung von Konferenzrichtlinien finden Sie unter [Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) in der Betriebsdokumentation.


