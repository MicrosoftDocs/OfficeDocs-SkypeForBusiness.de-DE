---
title: Bereitstellen des Microsoft Teams-Cloud Voice-Diensts
author: rmw2890
ms.author: Rowille
manager: serdars
audience: admin
ms.date: 05/16/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Laden Sie das Textbuch zur Website Aktivierung herunter, um den Rollout ihrer Teams zu planen und die Benutzerakzeptanz, die Wahrnehmung von Qualität und Zufriedenheit zu beschleunigen und zu optimieren.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e77127d6840473cfb6238d9150ac692230181e1
ms.sourcegitcommit: fa567451f8f7af6d915e33809d88f26b415db54c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "44610047"
---
# <a name="deploy-my-service"></a>Bereitstellen des Diensts

Dieser Artikel enthält eine Übersicht über die Anforderungen für die ordnungsgemäße Bereitstellung von Cloud-VoIP-Diensten. Indem Sie die normativen Anleitungen für die Bereitstellung von Cloud Voice Services befolgen, können Sie sicherstellen, dass Sie alle Anforderungen erfolgreich berücksichtigen und wiederholbare Ergebnisse liefern.

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a>Textbuch zur Website Aktivierung für Microsoft Teams-sprach Auslastungen

Verwenden Sie dieses Textbuch, um Ihre Organisation beim erfolgreichen planen und Durchführen des Rollouts der Microsoft Teams-Sprachfeatures für eine Website-für-Standort-Basis zu unterstützen.

Dieses Textbuch umfasst alle erforderlichen Aktivitäten, Empfohlene Zeitpläne und Links zu den entsprechenden Anleitungen für die einzelnen Aktivitäten und behandelt die End-to-End-Anleitung, um eine erfolgreiche Bereitstellung von Teams für eine bestimmte Website zu gewährleisten, wobei der Schwerpunkt auf Faktoren liegt, die für den Benutzer wichtig sind.

Durch Abschluss der Aktivitäten in diesem Textbuch kann Ihre Organisation:

-   Planen und planen Sie Ihren Rollout für Teams effektiv.

-   Beschleunigen und Optimieren der Benutzerakzeptanz

-   Verringern Sie den Supportbedarf, und erhöhen Sie die Benutzerzufriedenheit.

> [!NOTE]
> In diesem Artikel und dem dazugehörigen Textbuch sollen nicht alle technischen Konfigurationsschritte beschrieben werden, die für die Dienstaktivierung oder die Bereitstellung von Wählton für eine bestimmte Website erforderlich sind. Stattdessen konzentrieren Sie sich auf die Aktivitäten und Aufgaben, die für Onboard-Benutzer empfohlen werden, und Sie können die Arbeitsauslastung von Teams über einen schnellen und reibungslosen Übergang mit hoher Akzeptanzrate unter minimieren, während die Supportanforderungen minimiert werden. Technische Anleitungen zur optimalen Konfiguration Ihrer Umgebung für Teams-VoIP finden Sie in den Checklisten für das Konfigurieren von [Teams-sprach Auslastungen](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md), [Konfigurieren des direkten Routings in Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md), [Team-Kernfunktionen](onboarding-checklist-configure-microsoft-teams-core-capabilities.md), [Netzwerk für Teams](prepare-network.md)und [Aktivieren von Microsoft 365 oder Office 365](onboarding-checklist-enable-office-365.md).

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a>Textbuch-Fokusbereiche

Der Schwerpunkt des Textbuch liegt darin, die Faktoren zu berücksichtigen, die die Wahrnehmung einer Teams-sprach Bereitstellung beeinflussen. Aktivitäten und Aufgaben werden in die folgenden Schwerpunkte gruppiert:

-   Überprüfung der Servicebereitschaft
    - Audiokonferenzen
    - Anrufpläne
    - Direktes Routing

-   Benutzeraktivierung

-   Endpunkte

-   Verwendung und Qualität

-   Zur Einführung

Das Textbuch [für die Website Aktivierung (Manuskript)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) ist eine Microsoft Excel-Arbeitsmappe. Jeder dieser fünf Fokusbereiche ist ein separates Blatt in der Arbeitsmappe, und alle Bereitstellungsaufgaben und-Aktivitäten sind auf einem dieser Blätter gruppiert.

![Screenshot des Textbuch zur Website Aktivierung](media/deploy-my-service-image1.png "Screenshot des Manuskripts")

> [!NOTE]
> Sie erstellen eine separate Instanz des Textbuch für jede Website im Bereich für das Rollout Ihres Teams.

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a>Verwenden des Manuskripts

Unabhängig von der Größe und Komplexität des Standorts erfordert das Aktivieren jeder Website, dass Sie Ihre Aufgaben und Aktivitäten früh genug planen und in optimaler Reihenfolge ausführen – vor, während und nach dem eigentlichen Dienst Rollout. Wir empfehlen, dass Sie die folgenden Schritte ausführen, während Sie Ihre eigene Reise zu Microsoft Teams Voice planen und ausführen.

1. Laden Sie das [Website-Enablement-Manuskript für Voice (](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) Textbuch) für Microsoft Teams Voice herunter.

2. Erstellen Sie eine separate Kopie des Textbuch für jede Website.

3. Ersetzen Sie auf der Registerkarte für das Arbeitsbogen mit dem Namen Textbuch **für {Sitename-Code}** **{Sitename-Code}** durch den entsprechenden Websitenamen und/oder Website Code.

4. Geben Sie den **Websitenamen, den Standortcode**und das **geplante Startdatum**ein, wie unten dargestellt. Dies ist ein entscheidender Schritt, da er die empfohlenen Stichtage für jede Aktivität im Textbuch anpasst.

   ![Beispiel mit dem Websitenamen, dem Website Code und dem geplanten Startdatum](media/deploy-my-service-image2.png "Beispiel mit dem Websitenamen von New York, Website Code NY01 und geplantem Startdatum von 20-Mrz-18")

5. Überprüfen Sie die einzelnen Aktivitäten, führen Sie die erforderlichen Aktionen aus, und aktualisieren Sie den Status, während Sie die Zeitachse durchlaufen. Der Status wird grafisch dargestellt, wie nachstehend beschrieben:
  
   - ![Abbildung eines grünen Häkchens " ](media/deploy-my-service-image3.png) **Ja" oder "nicht zutreffend" (grün):** die Aktivität wurde abgeschlossen, oder Sie gilt nicht für diese Website, und es ist keine weitere Aktion erforderlich.</li>
   - ![Abbildung eines gelben Ausrufezeichens ](media/deploy-my-service-image4.png) <strong>die Aktivität ist noch nicht abgeschlossen (gelb):</strong> die Aktivität wurde noch nicht abgeschlossen und muss in Ihrem Terminplan auf "Ja" oder "Nein" aktualisiert werden.</li>
   - ![Abbildung eines roten X, das Nein ](media/deploy-my-service-image5.png) <strong>Nein (rot) angibt:</strong> die Aktivität kann aufgrund eines Problems nicht abgeschlossen werden und muss in der Projektstatusbesprechung durchgeführt werden.</li></ul>

6. Der Status wird in jedem Abschnitt zusammengerollt, und die Abschnittsüberschrift wird mit einer dieser Statusindikatoren formatiert. Der **wöchentliche Status** wird ebenfalls automatisch aktualisiert.

![Screenshot der wöchentlichen Status-Rollups im Textbuch](media/deploy-my-service-image6.png "Screenshot der wöchentlichen Status-Rollups im Textbuch")

> [!TIP]
> Wiederholen Sie die obigen Schritte für alle Speicherorte.

> [!IMPORTANT]
> Einige Schritte gelten möglicherweise nicht für alle Standorte und Websites. Wenn eine bestimmte Aktivität für eine Website nicht relevant ist, müssen Sie für diese Aktivität **nicht anwendbar** auswählen. **Löschen Sie** keine Zeilen im Textbuch; in diesem Fall funktionieren die Rollup-Formeln für den Status nicht.<br/><br/>
Achten Sie auf Aktivitäten, die mehr Zeit in Anspruch nehmen können, als Sie geplant haben, beispielsweise Nummernportierung und Beschaffungsaktivitäten. Diese Aktivitäten können sich negativ auf die Zeitachse der Website Bereitstellung auswirken. Achten Sie darauf, die Aktivitätsliste und die zugehörige Zeitachse wöchentlich zu überprüfen und zu aktualisieren, und zeigen Sie Sie in den [Sitzungen des Lenkungsausschusses](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) an, um sicherzustellen, dass die Beteiligten den Status der einzelnen Websites und mögliche Abweichungen vom Bereitstellungszeitplan kennen.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie, ob das Textbuch zur Website Aktivierung für Ihre Bereitstellung erforderlich ist.</li><li>Entscheiden Sie, wer für die Anpassung des Textbuch der Website Aktivierung für Microsoft Teams für jede bereitzustellende Website verantwortlich ist.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Nächste Schritte</td><td><ul><li><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Laden Sie das Textbuch zur Website Aktivierung herunter</a>.</li><li>Anpassen des Manuskripts für die Website Aktivierung für Ihre erste Website</li><li>Wiederholen Sie diese Schritte für weitere Websites.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->