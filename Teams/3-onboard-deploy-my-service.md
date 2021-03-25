---
title: Bereitstellen des Microsoft Teams-Cloud Voice-Diensts
author: rmw2890
ms.author: Rowille
manager: serdars
audience:
- ITPro
- admin
ms.date: 05/16/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Laden Sie das Playbook "Site Enablement" herunter, um Ihr Rollout von Teams zu planen und die Benutzereinführung, die Wahrnehmung von Qualität und Zufriedenheit zu beschleunigen und zu optimieren.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3c3f0105a04484efcabd5ab6c55d1269c3627895
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112631"
---
# <a name="deploy-my-service"></a>Bereitstellen des Diensts

Dieser Artikel enthält einen Überblick über die Anforderungen für die ordnungsgemäßen Bereitstellung von Cloud voice services. Indem Sie den vordefinierten Richtlinien für die Bereitstellung von Cloud voice services folgen, können Sie sicherstellen, dass Sie alle Anforderungen erfolgreich berücksichtigen und wiederholbare Ergebnisse liefern.

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a>Playbook zur Websiteermöglichung für Microsoft Teams-Spracharbeitsauslastungen

Verwenden Sie dieses Playbook, um Ihrer Organisation bei der erfolgreichen Planung und Durchführung des Rollouts von Microsoft Teams-Sprachfeatures auf Websitebasis zu helfen.

Dieses Playbook enthält alle erforderlichen Aktivitäten, empfohlenen Zeitachsen und Links zu den entsprechenden Anleitungen für jede Aktivität. Dieses Playbook befasst sich mit einer End-to-End-Anleitung, mit deren Hilfe eine erfolgreiche Teams-Sprachbereitstellung für eine bestimmte Website sichergestellt werden kann, wobei der Fokus auf faktoren konzentriert ist, die für den Benutzer wichtig sind.

Wenn Sie die Aktivitäten in diesem Playbook abschließen, kann Ihre Organisation:

-   Planen und planen Sie Ihren Rollout von Teams effektiv.

-   Beschleunigen und optimieren Sie die Benutzeradzeptanz.

-   Verringern Sie die Supportanforderungen, und erhöhen Sie die Benutzerzufriedenheit.

> [!NOTE]
> Dieser Artikel und das zugeordnete Playbook sollen nicht jeden technischen Konfigurationsschritt beschreiben, der für die Dienstermöglichung oder das Bereitstellen von Wähltonen für eine bestimmte Website erforderlich ist. Stattdessen konzentrieren sie sich auf Aktivitäten und Aufgaben, die Benutzern empfohlen werden, einfach zu integrieren, und lassen sie teams-Sprachworkloads über einen schnellen und reibungslosen Übergang mit hoher Akzeptanzrate verwenden, während die Supportanforderungen minimiert werden. Technische Anleitungen zum besten Konfigurieren Ihrer Umgebung für Teams Voice finden Sie in den Onboarding-Prüflisten zum Konfigurieren von [Teams-Voiceworkloads,](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)konfigurieren von [Direct Routing in Teams,](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md) [Kernfunktionen](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)von Teams, Netzwerken für [Teams](prepare-network.md)und Aktivieren von [Microsoft 365 oder Office 365.](onboarding-checklist-enable-office-365.md)

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a>Playbook-Fokusbereiche

Der Fokus des Playbooks liegt darauf, die Faktoren zu berücksichtigen, die die Wahrnehmung einer Teams-Sprachbereitstellung durch den Benutzer beeinflussen. Aktivitäten und Aufgaben sind in die folgenden Fokusbereiche einge gruppieren:

-   Überprüfung der Dienstbereitschaft
    - Audiokonferenzen
    - Anrufpläne
    - Direktes Routing

-   Benutzerermöglichung

-   Endpunkte

-   Verwendung und Qualität

-   Einführung

Das [Playbook "Site Enablement" für Voice (Playbook) ist](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) eine Microsoft Excel-Arbeitsmappe. Jeder dieser fünf Fokusbereiche ist ein separates Blatt in der Arbeitsmappe, und jede Bereitstellungsaufgabe und -aktivität ist in einem dieser Blätter gruppieren.

![Screenshot des Playbooks für die Websiteermöglichung](media/deploy-my-service-image1.png "Screenshot des Playbook")

> [!NOTE]
> Sie erstellen eine separate Instanz des Playbooks für jede Website im Bereich für Ihr Rollout von Teams.

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a>Verwenden des Playbooks

Unabhängig von der Größe und Komplexität des Standorts erfordert das Aktivieren jeder Website, dass Sie Ihre Aufgaben und Aktivitäten vor, während und nach dem tatsächlichen Dienstrollout frühzeitig planen und in optimaler Reihenfolge ausführen. Wir empfehlen, diese Schritte auszuführen, während Sie Ihre eigene Reise zu Microsoft Teams Voice planen und ausführen.

1. Laden Sie [das Playbook "Site Enablement" für Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) für Microsoft Teams Voice herunter.

2. Erstellen Sie eine separate Kopie des Playbooks für jede Website.

3. Ersetzen Sie auf der Registerkarte für das Blatt **"Playbook" für {SiteName-Code}** **{SiteName-Code}** durch den entsprechenden Websitenamen und/oder Websitecode.

4. Geben Sie **den Websitenamen, den Websitecode** und **das geplante Startdatum ein,** wie unten dargestellt. Dies ist ein wichtiger Schritt, da die empfohlenen Termine für jede Aktivität im Playbook angepasst werden.

   ![Beispiel mit Websitename, Websitecode und geplantem Startdatum](media/deploy-my-service-image2.png "Beispiel mit dem Websitenamen von New York, dem Websitecode NY01 und dem geplanten Startdatum vom 20. März 2018")

5. Überprüfen Sie jede Aktivität, nehmen Sie die erforderlichen Aktionen vor, und aktualisieren Sie den Status, während Sie die Zeitachse durchschauen. Der Status wird grafisch dargestellt, wie unten beschrieben:
  
   - ![Abbildung eines grünen Häkchens Ja oder nicht anwendbar ](media/deploy-my-service-image3.png) **(grün):** Die Aktivität wurde abgeschlossen oder gilt nicht für diese Website, und es ist keine weitere Aktion erforderlich.</li>
   - ![Abbildung eines gelben Ausrufezeichens Die Aktivität ist noch nicht abgeschlossen ](media/deploy-my-service-image4.png) <strong>(gelb):</strong> Die Aktivität wurde noch nicht abgeschlossen und muss im Zeitplan auf Ja oder Nein aktualisiert werden.</li>
   - ![Abbildung eines roten X, das kein Nein (rot) angibt: Die Aktivität kann aufgrund eines Problems nicht abgeschlossen werden und muss in die ](media/deploy-my-service-image5.png) <strong></strong> Projektstatussitzung durchgeführt werden.</li></ul>

6. Der Status wird in den einzelnen Abschnitten gerollt, und die Abschnittsüberschrift ist mit einem dieser Statusindikatoren formatiert. **Der wöchentliche** Status wird ebenfalls automatisch aktualisiert.

![Screenshot der wöchentlichen Statusrollups im Playbook](media/deploy-my-service-image6.png "Screenshot der wöchentlichen Statusrollups im Playbook")

> [!TIP]
> Wiederholen Sie die vorstehenden Schritte für alle Speicherorte, die Sie haben.

> [!IMPORTANT]
> Einige Schritte gelten möglicherweise nicht für alle Speicherorte und Websites. Wenn eine bestimmte Aktivität für eine Website nicht relevant ist, müssen Sie **Für** diese Aktivität Nicht zutreffend auswählen. **LÖSCHEN SIE KEINE** Zeilen im Playbook. Wenn Sie dies tun, funktionieren die Statusrollupformeln nicht.<br/><br/>
Achten Sie auf Aktivitäten, die möglicherweise länger dauern als geplant, z. B. Nummernportierung und Beschaffungsaktivitäten. Diese Aktivitäten können sich negativ auf die Zeitachse der Websitebereitstellung auswirken. Achten Sie darauf, die Aktivitätsliste und die zugehörige [](./envision-steering-committee-complete-guide.md) Zeitachse wöchentlich zu überprüfen und zu aktualisieren, und stellen Sie sie bei Denkausschussbesprechungen vor, um sicherzustellen, dass die Projektbeteiligten den Status der einzelnen Website und mögliche Abweichungen vom Bereitstellungszeitplan kennen.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie, ob das Playbook für die Websiteermöglichung für Ihre Bereitstellung erforderlich ist.</li><li>Entscheiden Sie, wer für die Anpassung des Playbook "Website enablement" für Microsoft Teams für jede website, die Sie bereitstellen möchten, zuständig ist.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Nächste Schritte</td><td><ul><li><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Laden Sie das Playbook "Site Enablement" herunter.</a></li><li>Passen Sie das Playbook "Website enablement" für Ihre erste Website an.</li><li>Wiederholen Sie diesen Vorgang bei Bedarf für weitere Websites.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->