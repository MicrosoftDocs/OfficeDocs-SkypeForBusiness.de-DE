---
title: Konferenzrichtlinie zum Erstellen neuer oder Bearbeiten vorhandener Daten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ConfMeetingPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ebd2f120-b57a-4c94-9509-20e098f4b0f4
description: Eine Konferenzrichtlinie definiert die Funktionen, die Benutzern während einer Konferenz (auch als Besprechung bezeichnet) zur Verfügung stehen.
ms.openlocfilehash: 9e01aa430939d78e616c20c6feccdd94262dfa45
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41686908"
---
# <a name="conferencing-policy-create-new-or-edit-existing"></a>Konferenzrichtlinie: Erstellen einer neuen oder Bearbeiten einer vorhandenen Konferenzrichtlinie

Eine Konferenzrichtlinie definiert die Funktionen, die Benutzern während einer Konferenz (auch als Besprechung bezeichnet) zur Verfügung stehen.

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste werden die Felder der Seite beschrieben.

- **Bereich** Identifiziert den Bereich der konferenzrichtlinie, die Sie erstellen oder ändern: Global, Site oder User.

- **Name** Für jede konferenzrichtlinie ist ein Name erforderlich. Konferenzrichtlinien auf globaler Ebene und für Standorte erhalten standardmäßig einen Namen, der nicht geändert werden kann. Verwenden Sie für Konferenzrichtlinien einen beschreibenden Namen, mit dem der Benutzer oder die Benutzergruppe identifiziert wird.

    > [!NOTE]
    > Nachdem Sie die Konferenzrichtlinie gespeichert haben, kann der Name nicht mehr geändert werden.

- **Beschreibung** Dieses Feld ist optional. Geben Sie darin zusätzliche Details zur Konferenzrichtlinie an.

- **Organisator-Richtlinie** Die Einstellungen in diesem Abschnitt gelten für den Benutzer, der eine Konferenz organisiert. Wenn eine Einstellung ausgewählt wird, kann der Benutzer eine Konferenz organisieren, die über das angegebene Merkmal verfügt. Wenn eine Einstellung nicht ausgewählt wird, kann der Benutzer eine Konferenz mit dem jeweiligen Merkmal nicht organisieren. Mit diesen Einstellungen wird nicht festgelegt, worauf der Benutzer als Teilnehmer anderer Konferenzen Zugriff hat.

    Klicken Sie neben der Bezeichnung auf den Pfeil nach oben oder unten, um den Abschnitt aus- oder einzublenden.

- **Maximale Besprechungsgröße** die maximale Anzahl von Benutzern, die bei einer Konferenz zulässig sind. Standardmäßig beträgt die maximale Konferenzgröße 250.

- **Teilnehmern erlauben, anonyme Benutzer einzuladen** Aktivieren Sie dieses Kontrollkästchen, damit Benutzer anonyme Benutzer zu Konferenzen einladen können. Anonyme Benutzer sind Benutzer, die keine Anmeldeinformationen in den Active Directory-Domänendiensten Ihrer Organisation haben und daher nicht authentifiziert sind.

- **Aufzeichnung** Geben Sie an, ob Teilnehmer Konferenzen aufzeichnen können. Die Optionen lauten **Keine** und **Aufzeichnung aktivieren**.

- **Zulassen, dass verbundene und anonyme Teilnehmer Daten aufzeichnen** Aktivieren Sie dieses Kontrollkästchen, damit externe und nicht authentifizierte Teilnehmer Konferenzen aufzeichnen können.

- **Audio/Video** Geben Sie an, ob Teilnehmer Audio und Video verwenden können:

  - **Keine** Wählen Sie diese Option aus, um die Verwendung von Audio und Video zu verhindern.

  - **Aktivieren von IP-Audio** Wählen Sie diese Option aus, um die Verwendung von Audio, aber nicht Video zu ermöglichen.

  - **Aktivieren von IP-Audio/-Video** Wählen Sie diese Option aus, um Audio und Video zuzulassen.

- **Aktivieren von PSTN-Einwahlkonferenzen** Wenn Sie Audiofunktionen in **Audio/Video**aktiviert haben, aktivieren Sie dieses Kontrollkästchen, damit sich Benutzer über das öffentlich geschaltete Telefonnetz (PSTN) in Konferenzen einwählen können.

- **Anonymen Teilnehmern das abwählen erlauben** Aktivieren Sie dieses Kontrollkästchen, wenn Sie Benutzern das Einwählen in Konferenzen gestatten und nicht authentifizierten (anonymen) Benutzern die Teilnahme an einer Konferenz mithilfe von Wähl anrufen gestatten möchten. Bei ausgehenden Telefonverbindungen führt der Konferenzserver einen Anruf an den Benutzer durch und der Benutzer nimmt das Gespräch an, um an der Konferenz teilzunehmen.

- **Zulassen, dass Teilnehmer, die nicht für Enterprise-VoIP aktiviert sind, anrufen** Wenn Sie Audio **/Video**aktiviert haben, aktivieren Sie dieses Kontrollkästchen, damit Benutzer, die nicht für Enterprise-VoIP aktiviert sind, mithilfe von Wähl Anrufen an einer Konferenz teilnehmen können. Bei ausgehenden Telefonverbindungen führt der Konferenzserver einen Anruf an den Benutzer durch und der Benutzer nimmt das Gespräch an, um an der Konferenz teilzunehmen.

- **Zulassen mehrerer Videodatenströme** Wenn Sie Video in **Audio/Video**aktiviert haben, aktivieren Sie dieses Kontrollkästchen, damit Benutzer Konferenzen mit der Video Galerieansicht organisieren können. Wenn dieses Kontrollkästchen aktiviert ist, ermöglicht diese Einstellung Benutzern das Organisieren von Konferenzen, bei denen mehrere Videostreams gesendet werden. Wenn dieses Kontrollkästchen nicht aktiviert ist, können Benutzer nur Konferenzen organisieren, bei denen ein einzelner Videostream gesendet wird.

    > [!NOTE]
    > Mit dieser Option wird die Art des Videostreams festgelegt, die von der Konferenz unterstützt wird. Dabei wird nicht festgelegt, ob Teilnehmer mehrere Videostreams empfangen können. Mit der Option **Teilnahme mit mehreren Videostreams aktivieren** wird festgelegt, ob Teilnehmer mehrere Videostreams empfangen können.

- **Zusammenarbeit mit Daten** Geben Sie an, ob die Konferenzdaten Zusammenarbeit zulässt. Die Optionen lauten **Keine** und **Datenzusammenarbeit aktivieren**.

    Für die Datenzusammenarbeit gelten die folgenden Einstellungen:

  - **Zulassen, dass verbundene und anonyme Teilnehmer Inhalte herunterladen** Wenn Sie die Datenzusammenarbeit zulassen, aktivieren Sie dieses Kontrollkästchen, damit externe und nicht authentifizierte Benutzer Inhalte wie Folien oder Handzettel aus einer Konferenz herunterladen können.

  - **Teilnehmern die Übertragung von Dateien erlauben** Wenn Sie die Datenzusammenarbeit zulassen, aktivieren Sie dieses Kontrollkästchen, um Dateiübertragungen an alle Teilnehmer während einer Konferenz zu ermöglichen.

  - **Aktivieren von Anmerkungen** Wenn Sie die Datenzusammenarbeit zulassen, aktivieren Sie dieses Kontrollkästchen, damit Teilnehmer auf dem Bildschirm Anmerkungen zu Inhalten erstellen können, die während der Konferenz freigegeben wurden.

  - **Aktivieren von PowerPoint-Anmerkungen** Wenn Sie Anmerkungen zulassen, aktivieren Sie dieses Kontrollkästchen, um Teilnehmern die Möglichkeit zu geben, Anmerkungen in PowerPoint-Folien zu erstellen, die während der Konferenz freigegeben werden.

  - **Umfragen aktivieren** Wenn Sie die Datenzusammenarbeit zulassen, aktivieren Sie dieses Kontrollkästchen, damit Teilnehmer während einer Konferenz eine Umfrage durchführen können.

- **Anwendungsfreigabe** Geben Sie an, ob die Konferenz die Anwendungsfreigabe zulässt. Die Optionen lauten **Anwendungsfreigabe deaktivieren** und **Anwendungsfreigabe aktivieren**.

    Für die Anwendungsfreigabe gelten die folgenden Einstellungen:

  - **Zulassen, dass Teilnehmer die Kontrolle übernehmen** Wenn Sie die Anwendungsfreigabe zulassen, aktivieren Sie dieses Kontrollkästchen, um Teilnehmern die Steuerung von Anwendungen oder Desktops zu ermöglichen, die während der Konferenz freigegeben werden.

  - **Zulassen, dass Verbund-und anonyme Teilnehmer die Kontrolle übernehmen** Wenn Sie die Anwendungsfreigabe zulassen, aktivieren Sie dieses Kontrollkästchen, damit externe und nicht authentifizierte Teilnehmer die Kontrolle über Anwendungen oder Desktops übernehmen können, die während der Konferenz freigegeben werden.

- **Teilnehmer Richtlinie** Die Einstellungen in diesem Abschnitt gelten für Benutzer als Teilnehmer an einer Konferenz oder zwei-Parteien-Sitzung. Da die folgenden Einstellungen pro Benutzer gelten, kann ein Benutzer in einer Konferenz oder Sitzung mit zwei Teilnehmern möglicherweise über andere Funktionen als ein anderer Benutzer derselben Konferenz oder Sitzung mit zwei Teilnehmern verfügen.

    Klicken Sie neben der Bezeichnung auf den Pfeil nach oben oder unten, um den Abschnitt aus- oder einzublenden.

- Wählen Sie die Option **Anwendungs- und Desktopfreigabe aktivieren**, um Benutzern das Freigeben von Anwendungen oder ihres Desktops zu erlauben, während diese sich in einer Konferenz oder Sitzung mit zwei Teilnehmern befinden. Wählen Sie die Option **Anwendungs- und Desktopfreigabe deaktivieren**, um für Benutzer das Freigeben von Anwendungen oder Desktops zu verhindern, während diese sich in einer Konferenz oder Sitzung mit zwei Teilnehmern befinden.

- **Aktivieren der Peer-to-Peer-Dateiübertragung** Aktivieren Sie dieses Kontrollkästchen, um die Übertragung von personenbezogenen Dateien (also Dateiübertragungen, die nicht alle Teilnehmer betreffen) während einer Konferenz oder einer zwei Parteien Sitzung zu ermöglichen.

- **Aktivieren der Peer-to-Peer-Aufzeichnung** Aktivieren Sie dieses Kontrollkästchen, damit Benutzer zwei Parteien Sitzungen aufzeichnen können.

- **Teilnehmern die Teilnahme an mehreren Videoströmen ermöglichen** Aktivieren Sie dieses Kontrollkästchen, um Teilnehmern das Empfangen von Galerieansicht-Video in Konferenzen zu ermöglichen, die dies zulassen. Wenn diese Option nicht aktiviert ist, können Teilnehmer unabhängig von den Einstellungen der Konferenz nur einen einzelnen Videostream empfangen.

    > [!NOTE]
    > Mit der Option **Mehrere Videostreams zulassen** wird festgelegt, ob für eine Konferenz mehrere Videostreams zulässig sind.

Ausführliche Informationen zu den Konferenzfunktionen finden Sie in der Planungsdokumentation unter [Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx). Ausführliche Informationen zur Verwendung von Konferenzrichtlinien finden Sie in der Betriebsdokumentation unter [Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx).


