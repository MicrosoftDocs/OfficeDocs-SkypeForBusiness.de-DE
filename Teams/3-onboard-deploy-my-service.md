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
description: Laden Sie das Playbook für die Website-Aktivierung herunter, um Teams Ihrer App zu planen und die Benutzereinführung, den Eindruck von Qualität und Zufriedenheit zu beschleunigen und zu optimieren.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b5c027da20c6c305fd5924cd6483c5cbd63b8ddd
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733540"
---
# <a name="deploy-my-service"></a>Bereitstellen des Diensts

Dieser Artikel bietet eine Übersicht über die Anforderungen für die ordnungsgemäß Bereitstellung von Cloud-Sprachdiensten. Indem Sie den vordefinierten Richtlinien für die Bereitstellung von Cloud-Sprachdiensten folgen, können Sie sicherstellen, dass alle Anforderungen erfolgreich berücksichtigt werden und Sie wiederholbare Ergebnisse erzielen.

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a>Playbook für die Website-Aktivierung Microsoft Teams Sprachauslastungen

Verwenden Sie dieses Playbook, um Ihre Organisation bei der erfolgreichen Planung und Durchführung der Microsoft Teams Sprachfeatures auf Website-für-Website-Basis zu unterstützen.

Dieses Playbook umfasst alle erforderlichen Aktivitäten, empfohlene Zeitachsen und Links zu den entsprechenden Anleitungen für jede Aktivität und enthält eine End-to-End-Anleitung, die Ihnen hilft, eine erfolgreiche Teams-Sprachbereitstellung für eine bestimmte Website zu gewährleisten, wobei der Schwerpunkt auf den Faktoren ist, die für den Benutzer wichtig sind.

Wenn Sie die Aktivitäten in diesem Playbook abschließen, kann Ihre Organisation:

-   Planen und planen Sie Ihre Teams effektiv.

-   Beschleunigen und optimieren Sie die Benutzeradzeptanz.

-   Reduzieren Sie die Supportanforderungen, und steigern Sie die Benutzerzufriedenheit.

> [!NOTE]
> Dieser Artikel und das zugeordnete Playbook sind nicht dazu gedacht, alle technischen Konfigurationsschritte zu beschreiben, die für die Dienstermöglichung oder die Bereitstellung eines Tonwahlwahl-Tons für eine bestimmte Website erforderlich sind. Stattdessen konzentrieren sie sich auf Aktivitäten und Aufgaben, die Benutzern empfohlen werden, und lassen sie sie durch einen schnellen und reibungslosen Übergang mit einer hohen Verbreitungsrate mit dem Verbrauch von Teams-Spracharbeitsauslastungen beginnen, während gleichzeitig die Supportanforderungen minimiert werden. Technische Anleitungen zum besten Konfigurieren Ihrer Umgebung für Teams-Sprache finden Sie in den Onboarding-Checklisten zum Konfigurieren von [Teams-Voice Workloads,](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)Konfigurieren von [Direct-Routing in Teams,](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)Teams-Kernfunktionen, Netzwerkfunktionen für [Teams](prepare-network.md)und Aktivieren von [Microsoft 365 oder Office 365.](onboarding-checklist-enable-office-365.md) [](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a>Playbook-Fokusbereiche

Der Fokus des Playbooks liegt auf den Faktoren, die die Wahrnehmung einer Sprachbereitstellung durch Teams des Benutzers beeinflussen. Aktivitäten und Vorgänge sind in den folgenden Schwerpunktbereichen gruppieren:

-   Überprüfung der Dienstbereitschaft
    - Audiokonferenzen
    - Anrufpläne
    - Direktes Routing

-   Benutzerermöglichung

-   Endpunkte

-   Verwendung und Qualität

-   Einführung

Das [Playbook "Site Enablement Playbook for Voice" (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) ist eine Microsoft Excel Arbeitsmappe. Jeder dieser fünf Fokusbereiche ist ein separates Arbeitsblatt in der Arbeitsmappe, und jede Bereitstellungsaufgabe und jede Bereitstellungsaktivität wird auf einer dieser Blättern gruppieren.

![Screenshot des Playbook für die Website-Aktivierung](media/deploy-my-service-image1.png "Screenshot des Playbook")

> [!NOTE]
> Sie erstellen eine separate Instanz des Playbook für jede Website im Bereich für Teams Rollout.

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a>So verwenden Sie das Playbook

Unabhängig von der Größe und Komplexität des Standorts müssen Sie ihre Aufgaben und Aktivitäten vor, während und nach dem eigentlichen Dienstrollout frühzeitig planen und in optimaler Reihenfolge ausführen. Wir empfehlen, diese Schritte auszuführen, während Sie Ihre eigene Reise planen und ausführen, Microsoft Teams zu hören.

1. Laden Sie [das "Site Enablement Playbook for Voice" (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) für Microsoft Teams herunter.

2. Erstellen Sie für jede Website eine separate Kopie des Playbook.

3. Ersetzen Sie auf der Registerkarte für das Blatt mit dem Namen **Playbook für {SiteName-Code}** **{SiteName-Code}** durch den entsprechenden Websitenamen und/oder Websitecode.

4. Geben Sie **den Websitenamen, den Websitecode** und das **geplante Startdatum** ein, wie unten dargestellt. Dies ist ein wichtiger Schritt, da die empfohlenen Termine für jede Aktivität im Playbook angepasst werden.

   ![Beispiel mit Websitename, Websitecode und geplantem Startdatum.](media/deploy-my-service-image2.png "Beispiel mit dem Websitenamen New York, dem Websitecode NY01 und dem geplanten Startdatum 20. März 2018")

5. Überprüfen Sie die einzelnen Aktivitäten, ergreifen Sie erforderliche Aktionen, und aktualisieren Sie den Status, während Sie die Zeitachse durch gehen. Status wird grafisch dargestellt, wie nachstehend beschrieben:
  
   - ![Abbildung eines grünen Häkchens](media/deploy-my-service-image3.png) **Ja oder nicht anwendbar (grün):** Die Aktivität wurde abgeschlossen oder gilt nicht für diese Website, und es sind keine weiteren Maßnahmen erforderlich.</li>
   - ![Abbildung eines gelben Ausrufezeichens](media/deploy-my-service-image4.png) <strong>Die Aktivität ist noch nicht abgeschlossen (gelb):</strong> Die Aktivität wurde noch nicht abgeschlossen und muss im Zeitplan auf Ja oder Nein aktualisiert werden.</li>
   - ![Abbildung eines roten X, das nein angibt.](media/deploy-my-service-image5.png) <strong>Nein (rot):</strong> Die Aktivität kann aufgrund eines Problems nicht abgeschlossen werden und muss in die Besprechung mit dem Projektstatus durchgeführt werden.</li></ul>

6. Der Status wird innerhalb der einzelnen Abschnitten rolliert, und die Abschnittsüberschrift wird mit einem dieser Statusindikatoren formatiert. **Der wöchentliche** Status wird ebenfalls automatisch aktualisiert.

![Screenshot der wöchentlichen Statusrollups im Playbook.](media/deploy-my-service-image6.png "Screenshot der wöchentlichen Statusrollups im Playbook")

> [!TIP]
> Wiederholen Sie die vorstehenden Schritte für alle Speicherorte, über die Sie verfügen.

> [!IMPORTANT]
> Einige Schritte gelten möglicherweise nicht für alle Speicherorte und Websites. Wenn eine bestimmte Aktivität für eine Website nicht relevant ist, müssen Sie **Für** diese Aktivität Nicht zutreffend auswählen. **LÖSCHEN SIE KEINE** Zeilen im Playbook. Wenn Sie dies tun, funktionieren die Formeln für das Rollup des Status nicht.<br/><br/>
Achten Sie auf Aktivitäten, die möglicherweise länger als geplant dauern, z. B. Nummernportierung und Beschaffungsaktivitäten. Diese Aktivitäten können sich negativ auf die Zeitachse der Websitebereitstellung auswirken. Überprüfen und aktualisieren Sie unbedingt die Aktivitätsliste und die [](./envision-steering-committee-complete-guide.md) zugehörige Zeitachse wöchentlich, und stellen Sie sie in den Besprechungen des Lenkungsgremiums dar, um sicherzustellen, dass die Beteiligten den Status der einzelnen Website und mögliche Abweichungen vom Bereitstellungszeitplan kennen.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie, ob das Playbook für die Website-Aktivierung für die Bereitstellung erforderlich ist.</li><li>Entscheiden Sie, wer für die Anpassung des Playbook für die Microsoft Teams Website, die Sie bereitstellen möchten, verantwortlich sein soll.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Nächste Schritte</td><td><ul><li><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Laden Sie das Playbook "Site Enablement" herunter.</a></li><li>Passen Sie das Playbook für die Website-Aktivierung für Ihre erste Website an.</li><li>Wiederholen Sie diesen Vorgang bei Bedarf für weitere Websites.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->