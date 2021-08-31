---
title: Remoteupdate Microsoft Teams Geräte
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Aktualisieren Microsoft Teams Telefonen, Teams Panels und Zusammenarbeitsleisten remote über Teams Admin Center
ms.openlocfilehash: c35fc24be2456c4ee1583e7a073a7c4dcf8e7214
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727464"
---
# <a name="update-microsoft-teams-devices-remotely"></a>Remoteupdate Microsoft Teams Geräte

Mithilfe des Microsoft Teams Admin Centers können Sie Ihre Teams-Geräte wie Teams-Telefone, Teams-Panels und Zusammenarbeitsleisten remote aktualisieren, und Sie können das Verhalten der Firmware für automatische Updates für Geräte auswählen. Über das Admin Center Teams Sie auf Ihren Geräten Folgendes aktualisieren:

- Teams-App und Teams-Administrator-Agent
- Unternehmensportal-App
- OEM-Agent-App
- Firmware des Geräts

Firmwareupdates für Geräte können entweder automatisch angewendet oder für ein zukünftiges Datum und eine zukünftige Uhrzeit geplant werden. Andere verfügbare Geräteupdates werden nicht automatisch angewendet, können jedoch manuell oder für ein zukünftiges Datum und eine zukünftige Uhrzeit geplant werden.

> [!NOTE]
> Zwar können Firmwareupdates für Geräte geplant werden, aber wenn das geplante Datum und die geplante Uhrzeit nach der konfigurierten maximalen Verzögerung von 30 oder 90 Tage liegen, wird das Firmwareupdate angewendet, wenn die maximale Verzögerung erreicht ist. Das geplante Datum und die geplante Uhrzeit werden ignoriert. Darüber hinaus ist Microsoft Teams Remoteaktualisierung von Geräten ein Feature, das für US Government Cloud-Mandanten (GCC-High) noch nicht verfügbar ist.

Zum Verwalten von Geräten müssen Sie ein globaler Administrator, Teams Dienstadministrator oder Teams sein. Weitere Informationen zu Administratorrollen finden Sie unter Verwenden [Microsoft Teams zum Verwalten von Teams.](../using-admin-roles.md)

## <a name="choose-automatic-device-firmware-update-behavior"></a>Auswählen des Verhaltens bei automatischen Firmwareupdates für Geräte

Firmwareupdates für Geräte werden automatisch angewendet. Sie können entscheiden, ob Updates angewendet werden sollen, sobald ein Update veröffentlicht wurde (wenn Sie diese Option auswählen, werden Updates am ersten Wochenende nach der Enbst bzw. 30- oder 90-Tage-Endung eines Updates angewendet). Firmwareupdates für Geräte werden standardmäßig 30 Tage lang auf eine veröffentlichte Version angewendet.

> [!IMPORTANT]
> Die neueste Firmwareupdateversion wird nicht auf Ihr Gerät Teams angewendet. Stattdessen wird das Update, das automatisch auf Ihr Gerät angewendet wird, um eine Version verzögert. Nehmen wir beispielsweise an, dass auf Ihr Gerät Version "10" angewendet und Version "11" veröffentlicht wird. Version "11" wird noch nicht angewendet. Stattdessen wird Ihr Gerät erst auf Version "11" aktualisiert, nachdem Version "12" veröffentlicht wurde.

> [!NOTE]
> Einige Geräte unterstützen das automatische Firmwareupdate noch nicht. Die Anwendung von Einstellungen für automatische Firmwareupdates auf Geräten, die automatische Updates nicht unterstützen, hat keine Auswirkungen auf diese Geräte. Bei Fragen, ob Ihr Gerät automatische Firmwareupdates unterstützt, wenden Sie sich an den Gerätehersteller.

Gehen Sie wie folgt vor, um das Verhalten für automatische Updates für Ihre Geräte zu wählen:

1. Melden Sie sich bei Microsoft Teams Admin Center an, indem Sie https://admin.teams.microsoft.com besuchen.
2. Navigieren **Sie in**  >  **IP-Telefonen oder** **Zusammenarbeitsleisten** **Teams Geräte.**
3. Wählen Sie ein oder mehrere Geräte und dann **Aktualisieren aus.**
4. Wählen **Sie unter Firmware-Autoupdate** eine der folgenden Optionen aus:
    - **Sobald verfügbar** Das neueste Firmwareupdate für Geräte wird am ersten Wochenende nach Version des neuesten Updates angewendet.
    - **Zurückerlangen von 30 Tagen** Das neueste Firmwareupdate für Geräte wird 30 Tage nach der Version des neuesten Updates angewendet.
    - **Zurückerlangen von 90 Tagen** Das neueste Firmwareupdate für Das neueste Gerät wird 90 Tage nach der Version des neuesten Updates angewendet.
5. Wählen Sie **Aktualisieren aus.**

Wenn Sie aus gleich welchem Grund ein Firmwareupdate des Geräts wiederherstellen müssen, müssen Sie Ihr Gerät auf die Werkseinstellungen zurücksetzen. Setzen Sie Ihr Gerät anhand der Anweisungen des Herstellers zurück.  

## <a name="manually-update-remote-devices"></a>Manuelles Aktualisieren von Remotegeräten

Wenn Sie ein oder mehrere Geräte über das Admin Center aktualisieren, können Sie entscheiden, ob Sie die Geräte sofort aktualisieren oder ein Update für ein zukünftiges Datum und eine zukünftige Uhrzeit planen möchten.

Gehen Sie wie folgt vor, um Remotegeräte manuell zu aktualisieren:

1. Melden Sie sich bei Microsoft Teams Admin Center an, indem Sie https://admin.teams.microsoft.com besuchen.
2. Navigieren **Sie zu**  >  **GERÄTE-IP-Telefonen** oder **zur** Zusammenarbeitsleiste **Teams Gerätepanels**.
3. Wählen Sie ein oder mehrere Geräte und dann **Aktualisieren aus.**
4. Wählen **Sie unter Manuelle** Updates die Option **Zeitplan** aus, wenn Sie das Update auf ein zukünftiges Datum und eine zukünftige Uhrzeit planen möchten. Die Aktualisierungen werden zu dem Datum und der Uhrzeit in der Zeitzone angewendet, die in **Zeitzone ausgewählt ist.**

Was Sie sehen, hängt davon ab, ob Sie ein oder mehrere Geräte ausgewählt haben. Die linke Abbildung unten zeigt mehrere ausgewählte Geräte, während das Bild auf der rechten Seite ein einzelnes ausgewähltes Gerät zeigt.

:::image type="content" source="../media/device-update-status.png" alt-text="Einzel- und Geräteansichten im Statusbereich für Geräteupdates.":::

Wenn Sie mehrere Geräte auswählen, können Sie auswählen, welche Updatetypen auf jedes ausgewählte Gerät angewendet werden. Wählen Sie die Updatetypen aus, die Sie anwenden möchten, und wählen Sie **Dann aktualisieren aus.**

Wenn Sie ein einzelnes Gerät auswählen, werden die für das Gerät verfügbaren Updates angezeigt. Wenn für das Gerät mehrere Updatetypen verfügbar sind, wählen Sie jeden anzuwendende Updatetyp aus. Sie können die aktuelle **Version anzeigen, die** auf dem Gerät angewendet wird, und die **neue** Version, die angewendet wird. Wählen Sie die zu übernehmende(n) Aktualisierung und dann **Aktualisieren aus.**

Nachdem Sie **Update ausgewählt haben,** werden Updates auf Ihre Geräte zu dem Datum und der Uhrzeit angewendet, das/die Sie bei der geplanten Aktualisierung ausgewählt haben. Wenn Sie kein zukünftiges Datum und keine zukünftige Uhrzeit ausgewählt haben, werden Updates innerhalb weniger Minuten auf Ihre Geräte angewendet.
