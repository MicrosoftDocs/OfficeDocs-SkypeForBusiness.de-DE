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
description: Verschieben Von Benutzern vor dem Außerbetriebsetzen einer lokalen Skype for Business-Umgebung.
ms.openlocfilehash: f04ebeec51b739faa89f907de6c363f0ef70a78e
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656671"
---
# <a name="move-required-users-before-decommissioning-your-on-premises-environment"></a>Verschieben erforderlicher Benutzer vor der Außerbetriebnahme Ihrer lokalen Umgebung

In diesem Artikel wird beschrieben, wie Sie erforderliche Benutzer in die Microsoft-Cloud verschieben, bevor Ihre lokale Skype for Business-Umgebung außer Betrieb genommen wird. Dies ist Schritt 1 der folgenden Schritte zum Außerbetriebsetzen Ihrer lokalen Umgebung:

- **Schritt 1. Verschieben Sie alle erforderlichen Benutzer von lokal in online.** (Dieser Artikel)

- Schritt 2. [Deaktivieren Sie Die Hybridkonfiguration](cloud-consolidation-disabling-hybrid.md).

- Schritt 3. [Verschieben von Hybridanwendungsendpunkten von lokal in online](decommission-move-on-prem-endpoints.md).

- Schritt 4. [Entfernen Sie Ihre lokale Skype for Business-Bereitstellung.](decommission-remove-on-prem.md)


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a>Verschieben aller erforderlichen Benutzer aus der lokalen Cloud in die Cloud

Alle Benutzer, die Sie nach Abschluss der Migration weiterhin verwenden, müssen zuerst von der lokalen in die Cloud verschoben werden. Sie verschieben Benutzer mithilfe der lokalen Verwaltungstools. Weitere Informationen finden Sie unter [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).

Obwohl es Benutzern mit lokalen Skype for Business Server-Konten möglich ist, Teams zu verwenden, verfügen diese Benutzer nicht über die volle Funktionalität von Teams. Diese Benutzer können nicht mit anderen Benutzern zusammenarbeiten oder einen Verbund mit anderen Benutzern führen, die Skype for Business weiterhin verwenden (online oder lokal). Diese Benutzer können auch keine PSTN-Anrufe in ihrem Teams-Client empfangen. Daher müssen Sie diese Benutzer online verschieben. Dieser Schritt stellt außerdem sicher, dass alle in Skype for Business Server erstellten Kontakte oder Besprechungen zu Teams migriert werden.

Führen Sie das folgende Cmdlet in einem Skype for Business Server PowerShell-Fenster aus, um zu überprüfen, ob in Ihrer lokalen Bereitstellung noch Benutzer vorhanden sind.

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

Wenn Benutzer zurückgegeben werden, überprüfen Sie die Ausgabe, um festzustellen, ob Konten in die Cloud verschoben werden müssen, und führen Sie für solche Benutzer die folgenden [Schritte aus.](move-users-between-on-premises-and-cloud.md) Führen Sie für nicht mehr benötigte Benutzerkonten das folgende Skype for Business Server PowerShell-Cmdlet aus:

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> Durch Disable-CsUser werden alle Skype for Business-Attribute für alle Benutzer entfernt, die die Filterkriterien erfüllen. Vergewissern Sie sich vor dem Fortfahren, dass diese Konten in Zukunft nicht mehr benötigt werden.


Sie können nun Ihre [Hybridkonfiguration deaktivieren.](cloud-consolidation-disabling-hybrid.md)

## <a name="see-also"></a>Siehe auch

- [Außerbetriebnahme Ihrer lokalen Skype for Business-Umgebung](decommission-on-prem-overview.md)

- [Deaktivieren der Hybridkonfiguration](cloud-consolidation-disabling-hybrid.md)

- [Verschieben von Hybridanwendungsendpunkten von lokal in online](decommission-move-on-prem-endpoints.md)

- [Entfernen Ihrer lokalen Skype for Business-Bereitstellung](decommission-remove-on-prem.md)




