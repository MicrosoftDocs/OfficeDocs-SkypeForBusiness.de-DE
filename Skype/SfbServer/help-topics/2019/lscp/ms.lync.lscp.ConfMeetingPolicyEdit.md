---
title: Konferenzrichtlinie Erstellen einer neuen oder Bearbeiten einer vorhandenen
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ebd2f120-b57a-4c94-9509-20e098f4b0f4
ROBOTS: NOINDEX, NOFOLLOW
description: Eine Konferenzrichtlinie definiert die Funktionen, die Benutzern während einer Konferenz (auch als Besprechung bezeichnet) zur Verfügung stehen.
ms.openlocfilehash: 4a230f7ce9aeb0943ad754d5ea842b681c4cca48
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20994686"
---
# <a name="conferencing-policy-create-new-or-edit-existing"></a>Konferenzrichtlinie: Erstellen einer neuen oder Bearbeiten einer vorhandenen Konferenzrichtlinie
 
Eine Konferenzrichtlinie definiert die Funktionen, die Benutzern während einer Konferenz (auch als Besprechung bezeichnet) zur Verfügung stehen.
  
## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste werden die Felder der Seite beschrieben.
  
- **Bereich** Gibt den Bereich der konferenzrichtlinie, die Sie erstellen oder ändern: global, Standort oder Benutzer.
    
- **Name** Jede konferenzrichtlinie erfordert einen Namen an. Konferenzrichtlinien auf globaler Ebene und für Standorte erhalten standardmäßig einen Namen, der nicht geändert werden kann. Verwenden Sie für Konferenzrichtlinien einen beschreibenden Namen, mit dem der Benutzer oder die Benutzergruppe identifiziert wird.
    
    > [!NOTE]
    > Nachdem Sie die Konferenzrichtlinie gespeichert haben, kann der Name nicht mehr geändert werden. 
  
- **Beschreibung** Dieses Feld ist optional. Geben Sie darin zusätzliche Details zur Konferenzrichtlinie an.
    
- **Organizer-Richtlinie** Die Einstellungen in diesem Abschnitt gelten für die Benutzer, der eine Konferenz organisiert. Wenn eine Einstellung ausgewählt wird, kann der Benutzer eine Konferenz organisieren, die über das angegebene Merkmal verfügt. Wenn eine Einstellung nicht ausgewählt wird, kann der Benutzer eine Konferenz mit dem jeweiligen Merkmal nicht organisieren. Mit diesen Einstellungen wird nicht festgelegt, worauf der Benutzer als Teilnehmer anderer Konferenzen Zugriff hat.
    
    Klicken Sie neben der Bezeichnung auf den Pfeil nach oben oder unten, um den Abschnitt aus- oder einzublenden.
    
- **Maximale Besprechungsumfang** die maximale Anzahl von Benutzern, die bei einer Konferenz zulässig sind. Standardmäßig ist der maximalen konferenzgröße 250.
    
- **Anonyme Benutzer einladen von Teilnehmern gestatten** Aktivieren Sie dieses Kontrollkästchen, damit Benutzer können anonyme Benutzer auf Konferenzen einladen können. Anonyme Benutzer sind Benutzer, die keine Anmeldeinformationen in Ihrer Organisation Active Directory Domain Services, und wer, daher, nicht authentifiziert werden.
    
- **Aufzeichnen** Geben Sie an, ob Teilnehmer Konferenzen aufgezeichnet werden können. Die Optionen lauten **Keine** und **Aufzeichnung aktivieren**.
    
- **Federated zulassen und anonyme Teilnehmer zu erfassen** Aktivieren Sie dieses Kontrollkästchen, um externen und nicht authentifizierten Teilnehmern das Datensatz Konferenzen ermöglichen.
    
- **Audio-video** Geben Sie an, ob Teilnehmer Audio- und Videofunktionen verwenden können:
    
  - **None** Wählen Sie diese Option, um die Verwendung von audio und video zu verhindern.
    
  - **IP-Audio aktivieren** Wählen Sie diese Option, um die Verwendung von audio jedoch keine Videofunktionen zuzulassen.
    
  - **Aktivieren von IP-Audio/video** Wählen Sie diese Option, um audio und video zu ermöglichen.
    
- **Aktivieren von PSTN - einwahlkonferenzen** Wenn Sie im Abschnitt **Audio/Video-** Audio aktiviert, aktivieren Sie dieses Kontrollkästchen, dass Benutzer mit dem öffentlichen Telefonfestnetz (PSTN) in Konferenzen einwählen können.
    
- **Anonyme Teilnehmer zulassen anwählen** Aktivieren Sie dieses Kontrollkästchen, wenn Sie Benutzern in Konferenzen einwählen und nicht authentifizierte (anonymen) Benutzer an einer Konferenz teilnehmen, mithilfe von Client-anrufen können sollen. Bei ausgehenden Telefonverbindungen ruft der Konferenzserver den Benutzer an und der Benutzer nimmt das Gespräch an, um an der Konferenz teilzunehmen.
    
- **Teilnehmern gestatten, die nicht für Enterprise-VoIP anwählen aktiviert** Wenn Sie im Abschnitt **Audio/Video-** Audio aktiviert, wählen Sie dieses Kontrollkästchen, um Benutzern zu ermöglichen, die nicht für Enterprise-VoIP in eine Konferenz mithilfe von Anwahl anrufen aktiviert sind. Bei ausgehenden Telefonverbindungen führt der Konferenzserver einen Anruf an den Benutzer durch und der Benutzer nimmt das Gespräch an, um an der Konferenz teilzunehmen.
    
- **Mehrere Videostreams zulassen** Wenn Sie Video im Abschnitt **Audio/Video**aktiviert, wählen Sie dieses Kontrollkästchen, damit Benutzer Konferenzen mit Video Katalogansicht organisieren können. Wenn dieses Kontrollkästchen aktiviert ist, ermöglicht diese Einstellung Benutzern das Organisieren von Konferenzen, bei denen mehrere Videostreams gesendet werden. Wenn dieses Kontrollkästchen nicht aktiviert ist, können Benutzer nur Konferenzen organisieren, bei denen ein einzelner Videostream gesendet wird.
    
    > [!NOTE]
    > Mit dieser Option wird die Art des Videostreams festgelegt, die von der Konferenz unterstützt wird. Dabei wird nicht festgelegt, ob Teilnehmer mehrere Videostreams empfangen können. Mit der Option **Teilnahme mit mehreren Videostreams aktivieren** wird festgelegt, ob Teilnehmer mehrere Videostreams empfangen können.
  
- **Zusammenarbeit an Daten** Geben Sie an, ob die Konferenz Datenzusammenarbeit ermöglicht. Die Optionen lauten **Keine** und **Datenzusammenarbeit aktivieren**.
    
    Für die Datenzusammenarbeit gelten die folgenden Einstellungen:
    
  - **Federated zulassen und anonyme Teilnehmer zu zum Herunterladen von Inhalten** Wenn Sie die Datenzusammenarbeit zulassen, wählen Sie dieses Kontrollkästchen, um externen und nicht authentifizierten Benutzern den download von Inhalten, beispielsweise von Folien oder Handzettel, von einer Konferenz zu ermöglichen.
    
  - **Teilnehmern gestatten zum Übertragen von Dateien** Wenn Sie die Datenzusammenarbeit zulassen, wählen Sie dieses Kontrollkästchen, um während einer Konferenz dateiübertragungen an alle Teilnehmer zuzulassen.
    
  - **Anmerkungen aktivieren** Wenn Sie die Datenzusammenarbeit zulassen, aktivieren Sie dieses Kontrollkästchen, um Teilnehmern das auf dem Bildschirm ermöglichen bildschirmanmerkungen für Inhalte, die während der Konferenz gemeinsam genutzt.
    
  - **Aktivieren von PowerPoint-Anmerkungen** Wenn Sie Anmerkung zu ermöglichen, wählen Sie dieses Kontrollkästchen, um Teilnehmern die Anmerkungen in PowerPoint-Folien während der Konferenz gemeinsam vornehmen zu ermöglichen.
    
  - **Abstimmungen aktivieren** Wenn Sie die Datenzusammenarbeit zulassen, wählen Sie dieses Kontrollkästchen, um Teilnehmern eine abstimmungen während einer Konferenz zu ermöglichen.
    
- **Anwendungsfreigabe** Geben Sie an, ob die Konferenz Anwendungsfreigabe ermöglicht. Die Optionen lauten **Anwendungsfreigabe deaktivieren** und **Anwendungsfreigabe aktivieren**.
    
    Für die Anwendungsfreigabe gelten die folgenden Einstellungen:
    
  - **Teilnehmern gestatten, die Steuerung übernehmen** Wenn Sie die Anwendungsfreigabe zulassen, wählen Sie dieses Kontrollkästchen, um die Teilnehmer die Steuerung von Anwendungen oder Desktops, die während der Konferenz gemeinsam genutzt werden dürfen.
    
  - **Federated zulassen und anonyme Teilnehmer die Steuerung übernehmen** Wenn Sie die Anwendungsfreigabe zulassen, wählen Sie dieses Kontrollkästchen, um die externen und nicht authentifizierten Teilnehmer die Steuerung von Anwendungen oder Desktops, die während der Konferenz gemeinsam genutzt werden dürfen.
    
- **Richtlinie für Teilnehmer** Die Einstellungen in diesem Abschnitt gelten für Benutzer als Teilnehmer an einer Konferenz oder Sitzung mit zwei Teilnehmern. Da die folgenden Einstellungen pro Benutzer gelten, kann ein Benutzer in einer Konferenz oder Sitzung mit zwei Teilnehmern möglicherweise über andere Funktionen als ein anderer Benutzer derselben Konferenz oder Sitzung mit zwei Teilnehmern verfügen.
    
    Klicken Sie neben der Bezeichnung auf den Pfeil nach oben oder unten, um den Abschnitt aus- oder einzublenden.
    
- Wählen Sie die Option **Anwendungs- und Desktopfreigabe aktivieren**, um Benutzern das Freigeben von Anwendungen oder ihres Desktops zu erlauben, während diese sich in einer Konferenz oder Sitzung mit zwei Teilnehmern befinden. Wählen Sie die Option **Anwendungs- und Desktopfreigabe deaktivieren**, um für Benutzer das Freigeben von Anwendungen oder Desktops zu verhindern, während diese sich in einer Konferenz oder Sitzung mit zwei Teilnehmern befinden.
    
- **Peer-zu-Peer-Dateiübertragung aktivieren** Aktivieren Sie dieses Kontrollkästchen, um während einer Konferenz oder Sitzung mit zwei Teilnehmern dateiübertragungen zwischen Personen (d. h., dateiübertragungen, an denen nicht alle Teilnehmer beteiligt sind) zu ermöglichen.
    
- **Peer-zu-Peer-Aufzeichnung aktivieren** Aktivieren Sie dieses Kontrollkästchen, um Benutzern das Aufzeichnen von Sitzungen mit zwei Teilnehmern zu ermöglichen.
    
- **Aktivieren von Teilnehmern mit mehrere Videostreams Anmeldung** Aktivieren Sie dieses Kontrollkästchen, damit Teilnehmer Katalogansicht Video in Konferenzen zu erhalten, die es ermöglichen. Wenn diese Option nicht aktiviert ist, können Teilnehmer unabhängig von den Einstellungen der Konferenz nur einen einzelnen Videostream empfangen.
    
    > [!NOTE]
    > Mit der Option **Mehrere Videostreams zulassen** wird festgelegt, ob für eine Konferenz mehrere Videostreams zulässig sind.
  
Ausführliche Informationen zu Live Meeting-Features und Funktionen finden Sie unter [Übersicht über Konferenzen](http://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) in der Planungsdokumentation. Ausführliche Informationen zur Verwendung von konferenzrichtlinien finden Sie unter [Conferencing Policies](http://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) in der Betriebsdokumentation.
  

