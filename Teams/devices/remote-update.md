---
title: Remoteaktualisierung von Microsoft Teams-Geräten
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Devices
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Remoteaktualisierung von Microsoft Teams-Telefonen, Teams-Bereichen und Zusammenarbeitsleisten über das Teams Admin Center
ms.openlocfilehash: 36f84025feec5b88b2cbf28a52fcb89cb76aeaa5
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269460"
---
# <a name="update-microsoft-teams-devices-remotely"></a>Remoteaktualisierung von Microsoft Teams-Geräten

Mithilfe des Microsoft Teams Admin Centers können Sie Ihre Teams-Geräte, z. B. Teams-Telefone, Teams-Bereiche und Zusammenarbeitsleisten, remote aktualisieren und das automatische Updateverhalten der Gerätefirmware auswählen. Sie können Folgendes auf Ihren Geräten über das Teams Admin Center aktualisieren:

- Teams-App- und Teams-Administrator-Agent
- Unternehmensportal-App
- OEM-Agent-App
- Gerätefirmware

Gerätefirmwareupdates können entweder automatisch angewendet oder für ein zukünftiges Datum und eine zukünftige Uhrzeit geplant werden. Andere verfügbare Geräteupdates werden nicht automatisch angewendet, können aber manuell oder für ein zukünftiges Datum und eine zukünftige Uhrzeit angewendet werden.

> [!NOTE]
> Während Gerätefirmwareupdates geplant werden können, wird das Firmwareupdate angewendet, wenn das geplante Datum und die geplante Uhrzeit nach der konfigurierten maximalen Verzögerung von 30 oder 90 Tagen liegen, wenn die maximale Verzögerung erreicht ist. Das geplante Datum und die geplante Uhrzeit werden ignoriert. Darüber hinaus ist das Remoteupdaten von Microsoft Teams-Geräten ein Feature, das auf US Government Cloud-Mandanten (GCC-High) noch nicht verfügbar ist.

Zum Verwalten von Geräten müssen Sie ein globaler Administrator, Teams-Dienstadministrator oder Teams-Geräteadministrator sein. Weitere Informationen zu Administratorrollen finden Sie unter [Verwenden von Microsoft Teams-Administratorrollen zum Verwalten von Teams](../using-admin-roles.md).

## <a name="choose-automatic-device-firmware-update-behavior"></a>Automatisches Firmwareupdateverhalten für Geräte auswählen

Gerätefirmwareupdates werden automatisch angewendet. Sie können entscheiden, ob Updates angewendet werden sollen, sobald eines veröffentlicht wurde (wenn Sie diese Option auswählen, werden Updates am ersten Wochenende nach der Veröffentlichung eines Updates angewendet) oder 30 oder 90 Tage nach der Veröffentlichung eines Updates. Standardmäßig werden Gerätefirmwareupdates 30 Tage nach der Veröffentlichung angewendet.

> [!IMPORTANT]
> Die neueste Firmwareupdateversion wird nicht auf Ihr Teams-Gerät angewendet. Stattdessen wird das Update, das automatisch auf Ihr Gerät angewendet wird, um eine Version verzögert. Nehmen wir beispielsweise an, dass auf Ihrem Gerät Version "10" angewendet wurde und Version "11" veröffentlicht wird. Version "11" wird noch nicht angewendet. Stattdessen wird Ihr Gerät erst nach der Veröffentlichung von Version "12" auf Version "11" aktualisiert.

> [!NOTE]
> Einige Geräte unterstützen das automatische Firmwareupdate noch nicht. Das Anwenden von Einstellungen für automatische Firmwareupdates auf Geräten, die keine automatischen Updates unterstützen, hat keine Auswirkungen auf diese Geräte. Für Fragen, ob Ihr Gerät automatische Firmwareupdates unterstützt, wenden Sie sich an den Gerätehersteller.

Gehen Sie wie folgt vor, um das automatische Updateverhalten für Ihre Geräte auszuwählen:

1. Melden Sie sich beim Microsoft Teams Admin Center an, indem Sie den Besuch besuchen https://admin.teams.microsoft.com.
2. Navigieren Sie zu **IP-Telefonen** auf **Microsoft Teams-Geräten** >  oder **in Zusammenarbeitsleisten** oder **Teams-Bereichen**.
3. Wählen Sie ein oder mehrere Geräte und dann **"Aktualisieren"** aus.
4. Wählen Sie unter **"Automatische Firmwareaktualisierung**" eine der folgenden Optionen aus:
    - **Sobald verfügbar** Das zweitneueste Gerätefirmwareupdate wird am ersten Wochenende nach der Veröffentlichung des neuesten Updates angewendet.
    - **30 Tage zurückstellen** Das zweitneueste Gerätefirmwareupdate wird 30 Tage nach Veröffentlichung des neuesten Updates angewendet.
    - **Zurückstellen von 90 Tagen** Das zweitneueste Gerätefirmwareupdate wird 90 Tage nach der Veröffentlichung des neuesten Updates angewendet.
5. Wählen Sie **"Aktualisieren"** aus.

Wenn Sie aus irgendeinem Grund ein Gerätefirmwareupdate wiederherstellen müssen, müssen Sie Ihr Gerät auf die Werkseinstellungen zurücksetzen. Setzen Sie Ihr Gerät anhand der Anweisungen des Herstellers zurück.  

## <a name="manually-update-remote-devices"></a>Manuelles Aktualisieren von Remotegeräten

Wenn Sie ein oder mehrere Geräte über das Admin Center aktualisieren, können Sie entscheiden, ob die Geräte sofort aktualisiert oder ein Update für ein zukünftiges Datum und eine zukünftige Uhrzeit geplant werden soll.

Gehen Sie wie folgt vor, um Remotegeräte manuell zu aktualisieren:

1. Melden Sie sich beim Microsoft Teams Admin Center an, indem Sie den Besuch besuchen https://admin.teams.microsoft.com.
2. Navigieren Sie zu **IP-Telefonen** auf **Microsoft Teams-Geräten** >  oder **in Zusammenarbeitsleisten** oder **Teams-Bereichen**.
3. Wählen Sie ein oder mehrere Geräte und dann **"Aktualisieren"** aus.
4. Wählen Sie unter **"Manuelle Updates**" die Option **"Zeitplan** " aus, wenn Sie das Update für ein zukünftiges Datum und eine zukünftige Uhrzeit planen möchten. Die Aktualisierungen werden zu dem Datum und der Uhrzeit in der in der **Zeitzone ausgewählten Zeitzone** angewendet.

Was Sie sehen, hängt davon ab, ob Sie ein oder mehrere Geräte ausgewählt haben. Die linke Abbildung unten zeigt mehrere ausgewählte Geräte, während das Bild auf der rechten Seite ein einzelnes Gerät anzeigt.

:::image type="content" source="../media/device-update-status.png" alt-text="Einzelne und mehrere Geräteansichten im Statusbereich für Geräteaktualisierungen.":::

Wenn Sie mehrere Geräte auswählen, können Sie auswählen, welche Updatetypen auf jedes ausgewählte Gerät angewendet werden sollen. Wählen Sie die Updatetypen aus, die Sie anwenden möchten, und wählen Sie **"Aktualisieren"** aus.

Wenn Sie ein einzelnes Gerät auswählen, werden Updates angezeigt, die für das Gerät verfügbar sind. Wenn für das Gerät mehrere Updatetypen verfügbar sind, wählen Sie jeden anzuwendenden Updatetyp aus. Sie können die aktuelle **Version** anzeigen, die auf dem Gerät angewendet wurde, und die **neue Version** , die angewendet wird. Wählen Sie die Aktualisierung(en) aus, die Sie anwenden möchten, und wählen Sie **"Aktualisieren"** aus.

Nachdem Sie **"Aktualisieren**" ausgewählt haben, werden Updates zu dem Datum und der Uhrzeit auf Ihre Geräte angewendet, die Sie ausgewählt haben, wenn Sie ein Update geplant haben. Wenn Sie kein zukünftiges Datum und keine zukünftige Uhrzeit ausgewählt haben, werden Updates innerhalb weniger Minuten auf Ihre Geräte angewendet.
