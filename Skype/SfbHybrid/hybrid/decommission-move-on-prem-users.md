---
title: Verschieben von Benutzern in die Cloud
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Verschieben von Benutzern vor der Außerbetriebnahme einer Skype for Business lokalen Umgebung.
ms.openlocfilehash: bc98ebfcfb7ad4d4b2c64942b5f84500a98cdc84
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510716"
---
# <a name="move-required-users-before-decommissioning-your-on-premises-environment"></a>Verschieben der erforderlichen Benutzer vor der Außerbetriebnahme Ihrer lokalen Umgebung

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

In diesem Artikel wird beschrieben, wie Sie erforderliche Benutzer in die Microsoft-Cloud verschieben, bevor Sie Ihre lokale Skype for Business Umgebung außer Betrieb setzen. Dies ist Schritt 1 der folgenden Schritte zum Außerbetriebsetzen Ihrer lokalen Umgebung:

- **Schritt 1. Verschieben Sie alle erforderlichen Benutzer aus der lokalen Umgebung in die Onlineumgebung.** (Dieser Artikel)

- Schritt 2. [Deaktivieren Sie Ihre Hybridkonfiguration.](cloud-consolidation-disabling-hybrid.md)

- Schritt 3: [Migrieren Sie Hybridanwendungsendpunkte von lokalen zu online.](decommission-move-on-prem-endpoints.md) Beachten Sie, dass alle vorhandenen Hybridanwendungsendpunkte zwischen der Ausführung von Schritt 2 oben nicht gefunden werden können, bis Sie diesen Schritt abgeschlossen haben. Sie sollten planen, beide Schritte 2 und 3 im gleichen Wartungsfenster auszuführen.

- Schritt 4. [Entfernen Sie Ihre lokale Skype for Business Bereitstellung.](decommission-remove-on-prem.md)


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a>Verschieben aller erforderlichen Benutzer aus der lokalen Umgebung in die Cloud

Alle Benutzer, die Sie nach Abschluss der Migration weiterhin verwenden, müssen zuerst aus der lokalen Umgebung in die Cloud verschoben werden. Sie verschieben Benutzer mithilfe der lokalen Verwaltungstools. Ausführliche Informationen finden Sie unter [Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud.](move-users-between-on-premises-and-cloud.md)

Es ist zwar möglich, dass Benutzer mit lokalen Skype for Business Server-Konten Teams verwenden, diese Benutzer verfügen jedoch nicht über die vollständige Funktionalität von Teams. Diese Benutzer können nicht mit einem anderen Benutzer zusammenarbeiten oder einen Verbund mit anderen Benutzern herstellen, die weiterhin Skype for Business (online oder lokal) verwenden. Diese Benutzer können auch keine PSTN-Anrufe in ihrem Teams-Client empfangen. Daher müssen Sie diese Benutzer in die Online-App verschieben. Mit diesem Schritt wird außerdem sichergestellt, dass alle in Skype for Business Server erstellten Kontakte oder Besprechungen zu Teams migriert werden.

Führen Sie das folgende Cmdlet in einem Skype for Business Server PowerShell-Fenster aus, um zu überprüfen, ob in Ihrer lokalen Bereitstellung noch Benutzer vorhanden sind.

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

Wenn Benutzer zurückgegeben werden, überprüfen Sie die Ausgabe, um festzustellen, ob Konten in die Cloud verschoben werden müssen, und führen Sie für solche Benutzer die [hier beschriebenen](move-users-between-on-premises-and-cloud.md)Schritte aus. Führen Sie für Benutzerkonten, die nicht mehr benötigt werden, das folgende Skype for Business Server PowerShell-Cmdlet aus:

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> Wenn Sie Disable-CsUser ausführen, werden alle Skype for Business Attribute für alle Benutzer entfernt, die die Filterkriterien erfüllen. Bevor Sie fortfahren, vergewissern Sie sich, dass diese Konten in Zukunft nicht mehr benötigt werden.


Sie können jetzt [Ihre Hybridkonfiguration deaktivieren.](cloud-consolidation-disabling-hybrid.md)

## <a name="see-also"></a>Mehr dazu

- [Außerbetriebnahme Ihrer lokalen Skype for Business-Umgebung](decommission-on-prem-overview.md)

- [Deaktivieren der Hybridkonfiguration](cloud-consolidation-disabling-hybrid.md)

- [Verschieben von Hybridanwendungsendpunkten von der lokalen Umgebung zur Onlinebereitstellung](decommission-move-on-prem-endpoints.md)

- [Entfernen Ihrer lokalen Skype for Business-Bereitstellung](decommission-remove-on-prem.md)




