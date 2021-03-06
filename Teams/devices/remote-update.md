---
title: Remoteupdate für Microsoft Teams-Geräte
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
localization_priority: Normal
description: Aktualisieren von Microsoft Teams-Telefonen, Teams-Panels und Zusammenarbeitsbalken remote mithilfe des Teams Admin Centers
ms.openlocfilehash: 67b76d8330de5a801625a22c25cd1f9637048d05
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2021
ms.locfileid: "50347886"
---
# <a name="update-microsoft-teams-devices-remotely"></a>Remoteupdate für Microsoft Teams-Geräte

Mithilfe des Microsoft Teams Admin Centers können Sie Ihre Teams-Geräte, z. B. Teams-Telefone, Teams-Panels und Zusammenarbeitsbalken, remote aktualisieren und das Verhalten der Gerätefirmware für automatische Updates auswählen. Sie können folgendes auf Ihren Geräten über das Teams Admin Center aktualisieren:

- Administratormitarbeiter für Teams-Apps und Teams
- Unternehmensportal-App
- OEM-Agent-App
- Gerätefirmware

Firmwareupdates für Geräte können entweder automatisch angewendet oder für ein zukünftiges Datum und eine zukünftige Uhrzeit geplant werden. Andere verfügbare Geräteupdates werden nicht automatisch angewendet, können aber manuell angewendet oder für ein zukünftiges Datum und eine zukünftige Uhrzeit geplant werden.

> [!NOTE]
> Während Firmwareupdates für Geräte geplant werden können, wird das Firmwareupdate angewendet, wenn das geplante Datum und die geplante Uhrzeit nach der konfigurierten maximalen Verzögerung von 30 oder 90 Tage liegt, wenn die maximale Verzögerung erreicht ist. Das geplante Datum und die geplante Uhrzeit werden ignoriert. Darüber hinaus ist das Remote-Aktualisieren von Microsoft Teams-Geräten ein Feature, das für us Government Cloud Tenants (GCC-High) noch nicht verfügbar ist.

Zum Verwalten von Geräten müssen Sie globaler Administrator, Teamdienstadministrator oder Teamgeräteadministrator sein. Weitere Informationen zu Administratorrollen finden Sie unter [Verwenden von Microsoft Teams-Administratorrollen zum Verwalten von Teams.](../using-admin-roles.md)

## <a name="choose-automatic-device-firmware-update-behavior"></a>Automatisches Firmwareupdateverhalten für Geräte auswählen

Firmwareupdates für Geräte werden automatisch angewendet. Sie können entscheiden, ob Updates angewendet werden sollen, sobald ein Update veröffentlicht wird (wenn Sie diese Option auswählen, werden Updates am ersten Wochenende nach der Version eines Updates angewendet) oder 30 oder 90 Tage nach der Version eines Updates. Standardmäßig werden Gerätefirmwareupdates 30 Tage lang angewendet, die veröffentlicht wurden.

> [!IMPORTANT]
> Die neueste Firmwareupdateversion wird nicht auf Ihr Teams-Gerät angewendet. Stattdessen wird das Update, das automatisch auf Ihr Gerät angewendet wird, um eine Version verzögert. Angenommen, Ihr Gerät hat version "10" angewendet, und Version "11" wird veröffentlicht. Version "11" wird noch nicht angewendet. Stattdessen wird Ihr Gerät erst nach der Version "12" auf Version "11" aktualisiert.

> [!NOTE]
> Einige Geräte unterstützen das automatische Firmwareupdate noch nicht. Das Anwenden von Einstellungen für das automatische Firmwareupdate auf Geräten, die keine automatischen Updates unterstützen, hat keine Auswirkungen auf diese Geräte. Wenn Sie fragen möchten, ob Ihr Gerät automatische Firmwareupdates unterstützt, wenden Sie sich an den Gerätehersteller.

Gehen Sie wie folgt vor, um das automatische Updateverhalten für Ihre Geräte zu wählen:

1. Melden Sie sich beim Microsoft Teams Admin Center an, indem Sie zu https://admin.teams.microsoft.com besuchen.
2. Navigieren **Sie zu**  >  **Geräte-IP-Telefonen** oder **Kollaborationsleisten** **oder Teams-Panels.**
3. Wählen Sie ein oder mehrere Geräte und dann **Aktualisieren aus.**
4. Wählen **Sie unter Firmware auto-update** eine der folgenden Optionen aus:
    - **Sobald verfügbar** Das neueste Firmwareupdate für Geräte wird am ersten Wochenende nach der Version des neuesten Updates angewendet.
    - **Aufschub von 30 Tagen** Das neueste Firmwareupdate für Geräte wird 30 Tage nach der Version des neuesten Updates angewendet.
    - **Aufschub von 90 Tagen** Das neueste Firmwareupdate für Geräte wird 90 Tage nach der Version des neuesten Updates angewendet.
5. Wählen Sie **Aktualisieren aus.**

Wenn Sie aus welchem Grund auch immer ein Firmwareupdate des Geräts wiederherstellen müssen, müssen Sie Ihr Gerät auf die Werkseinstellungen zurücksetzen. Setzen Sie Ihr Gerät mithilfe der Anweisungen des Herstellers zurück.  

## <a name="manually-update-remote-devices"></a>Manuelles Aktualisieren von Remotegeräten

Wenn Sie ein oder mehrere Geräte über das Admin Center aktualisieren, können Sie entscheiden, ob Sie die Geräte sofort aktualisieren oder ein Update für ein zukünftiges Datum und eine zukünftige Uhrzeit planen möchten.

Gehen Sie wie folgt vor, um Remotegeräte manuell zu aktualisieren:

1. Melden Sie sich beim Microsoft Teams Admin Center an, indem Sie zu https://admin.teams.microsoft.com besuchen.
2. Navigieren **Sie zu**  >  **Geräte-IP-Telefonen** oder **Kollaborationsleisten** **oder Teams-Panels.**
3. Wählen Sie ein oder mehrere Geräte und dann **Aktualisieren aus.**
4. Wählen **Sie unter** Manuelle Updates die Option **Planen** aus, wenn Sie das Update für ein zukünftiges Datum und eine zukünftige Uhrzeit planen möchten. Die Updates werden zu dem Datum und der Uhrzeit in der Zeitzone angewendet, die in **Zeitzone ausgewählt ist.**

Was Sie sehen, hängt davon ab, ob Sie ein oder mehrere Geräte ausgewählt haben. Die linke Abbildung unten zeigt mehrere ausgewählte Geräte, während das Bild auf der rechten Seite ein einzelnes Gerät zeigt, das ausgewählt ist.

:::image type="content" source="../media/device-update-status.png" alt-text="Einzelne und mehrere Geräteansichten im Bereich "Geräteupdatestatus"":::

Wenn Sie mehrere Geräte auswählen, können Sie auswählen, welche Updatetypen für jedes ausgewählte Gerät gelten. Wählen Sie die Aktualisierungstypen aus, die Sie anwenden möchten, und wählen Sie **Aktualisieren aus.**

Wenn Sie ein einzelnes Gerät auswählen, werden Updates angezeigt, die für das Gerät verfügbar sind. Wenn für das Gerät mehrere Aktualisierungstypen verfügbar sind, wählen Sie die jeweils anzuwendende Aktualisierungsart aus. Sie können die auf das **Gerät angewendete** aktuelle Version und die **neue Version** anzeigen, die angewendet wird. Wählen Sie die Updates aus, die Sie anwenden möchten, und wählen Sie **Aktualisieren aus.**

Nachdem Sie Aktualisieren **ausgewählt** haben, werden Updates zu dem Datum und der Uhrzeit auf Ihre Geräte angewendet, die Sie ausgewählt haben, wenn Sie ein Update geplant haben. Wenn Sie kein zukünftiges Datum und keine zukünftige Uhrzeit ausgewählt haben, werden Updates innerhalb weniger Minuten auf Ihre Geräte angewendet.
