---
title: Verwalten der Integrität von Teams Geräten
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: snchatur
search.appverid: MET150
f1.keywords:
- NOCSH
description: Dieser Artikel führt Sie durch die Verwaltung der Integrität von Teams Geräten, auf Microsoft Teams installiert sind.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: fae26365a09cab2705d4c7fee5d57c2135203a65
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2021
ms.locfileid: "60045811"
---
# <a name="manage-the-health-of-teams-devices"></a>Verwalten der Integrität von Teams-Geräten


Administratoren können den Status von geräten überwachen, die mit Microsoft Teams installiert wurden, indem sie den Integritätsstatus verwenden, der den Schweregrad von Problemen angibt. Um den Integritätszustand eines Geräts zu überprüfen, können Sie zur Geräteliste wechseln, die im Abschnitt **Teams Geräte** des Teams Admin Centers angezeigt wird. Die Spalte "Integritätsstatus" in dieser Liste gibt den aktuellen Integritätsstatus des Geräts an. Wenn Sie diesen Status auswählen, wird **der Statusbereich geöffnet,** der weitere Details zu Integritätsproblemen enthält.

Viele Arten von Problemen können zum Gerätestatus beitragen, und Teams Admin Center-System wertet den Schweregrad dieser Probleme aus, sobald sie auftreten.

Der Administrator, der die Teams-Geräte für ihre Organisation verwaltet, kann entscheiden, dass der Schweregrad der Probleme für sie nicht der Standardkonfiguration Teams ist. Administratoren haben die Möglichkeit, den Schweregrad und die Auswirkungen auf die Integrität ihrer Geräte so anzupassen, dass sie den Prioritäten ihrer Organisation entsprechen.

Teams-Räume-Geräte verfügen über angeschlossene Peripheriegeräte, um ein umfassendes Besprechungserlebnis zu ermöglichen, z. B. Lautsprecher, Mikrofon, Anzeige, Kamera. Details dazu finden Sie auf der Geräteseite unter den Registerkarten Peripheriegeräte und Integrität. Die Konnektivität dieser Peripheriegeräte wirkt sich auf die Integrität des übergeordneten Geräts aus.

## <a name="feature-details"></a>Featuredetails

Wenn Sie Peripheriedetails auf einer Geräteseite anzeigen, wird nun die Option Gesundheitsbelastung  **verwalten** angezeigt. Darüber hinaus können Administratoren auch die Auswirkungen der einzelnen Peripheriegeräte auf die Integrität des Geräts anzeigen.

Standardmäßig sind alle Peripheriegeräte so eingestellt, dass sie **kritische Auswirkungen auf die** Geräteintepherie haben. Wenn ein Peripheriegerät nicht angeschlossen ist, wird  die Integrität des übergeordneten Geräts zu "Kritisch", und dieses Problem wird im Integritätsstatusbereich unter Kritische Probleme angezeigt. 

> [!NOTE]
> Die Peripheriekategorien **HDMI-Aufnahme** und **Compute** sind nicht zur Anpassung verfügbar, da sie für das Funktionieren des übergeordneten Geräts entscheidend sind.

## <a name="how-does-this-work"></a>Wie funktioniert das?

1. Ein Administrator kann die Peripheriegeräte auswählen, deren Auswirkungen auf die Gesundheit geändert werden sollen. Anschließend können sie Die Auswirkungen **auf den Gesundheitszustand verwalten auswählen.** Alternativ können sie  auf jeder Peripheriekarte auf der Registerkarte **Peripheriegeräte** die Option Gesundheitseinwirkungen verwalten finden.
1. Das **Bereich mit den** Auswirkungen auf den Integritätszustand wird geöffnet, und der Administrator kann den gewünschten Einfluss für die ausgewählten Peripheriegeräte auswählen und speichern.

| Einstellungen Optionen | Beschreibung |
|------------------|-------------|
| **Nicht dringend** | Wenn sie für eine Peripheriekategorie (z. B. eine Anzeige oder einen Lautsprecher) festgelegt ist und das Peripheriegerät getrennt wird, wird der Integritätsstatus des **Teams-Räume-Geräts** zu Nicht dringend (anstelle von **Kritisch).** Neue Probleme werden im Abschnitt Nicht **dringend** des Statusbereichs kategorisiert.|
| **Keine Auswirkung** | Wenn sie für eine Peripheriekategorie festgelegt ist und das Peripheriegerät getrennt wird, bleibt der Integritätsstatus des Teams-Räume-Geräts fehlerfrei **(anstelle** von **Kritisch).** Dieses Integritätsproblem wird nicht im Statusbereich angezeigt.|
| **Kritisch** | Wenn sie für eine Peripheriekategorie festgelegt ist und das Peripheriegerät getrennt wird, wird der Integritätsstatus des Teams-Räume zu **Critical**. Neue derartige Probleme werden im Abschnitt Kritisch **des** Statusbereichs kategorisiert.|
| **Auf Standard zurücksetzen** | Wenn sie für eine Peripheriekategorie festgelegt ist, wird die Integritätsbelastung für diese Kategorie auf Critical **zurückgesetzt.** Sobald diese Option gespeichert ist, werden die Änderungen angewendet, und die Auswirkungen auf die Integrität spiegeln diese Änderungen in Zukunft wider.|

## <a name="applicable-device-categories"></a>Anwendbare Gerätekategorien

Derzeit ist dieses Feature verfügbar, um die Gesundheitsbelastung von Peripheriegeräten zu verwalten, die mit Microsoft Teams-Räume (Windows) geräten verbunden sind.

## <a name="impact-on-other-workflows"></a>Auswirkungen auf andere Workflows

Wenn die Auswirkungen auf die Integrität der Peripheriegeräte den Schweregrad verringern, bemerken Administratoren möglicherweise keine Probleme, wenn sie auftreten. Sie sollten auf Geräte mit hoher Priorität, die eng überwacht werden müssen, gut denken.

Wenn beispielsweise eine Warnung so konfiguriert ist, dass sie für ConfRoom1 ausgelöst wird, wenn ihr Zustand zu Kritisch **wird.** Der Administrator hatte die Gesundheitsbelastung der Anzeige und des Lautsprechers für den Besprechungsraum von der Standardeinstellung **Kritisch** auf Nicht **dringend reduziert.** Wenn die Anzeige jetzt getrennt ist, wird die Integrität von ConfRoom1 zu **Nicht dringend.** In diesem Fall wird die Warnung nicht ausgelöst.
