---
title: Microsoft 365 Phone System – Lizenzen für virtuelle Benutzer
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: waseemh
ms.topic: reference
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom:
- Licensing
- LIL_Placement
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie Ressourcenkonten in Ihrer Organisation eine kostenlose Lizenz für telefonsystem-virtuelle Benutzer oder eine kostenpflichtige Benutzerlizenz für Telefonsystem zuweisen.
ms.openlocfilehash: 8e5322ccf7e3e7ad05c499b3dbcfdac65d0dfedb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116923"
---
# <a name="microsoft-365-phone-system--virtual-user-license"></a>Microsoft 365 Phone System – Lizenz für virtuelle Benutzer

Organisationen mit lizenzierten Benutzern des Telefonsystems können Ressourcenkonten entweder eine kostenlose Microsoft 365 Phone System – Virtual User-Lizenz oder eine kostenpflichtige Benutzerlizenz für Telefonsystem zuweisen. Ein Anrufplan ist nicht erforderlich. Für alle automatischen Telefonkonferenzen oder Anrufwarteschlangen ist ein zugeordnetes Ressourcenkonto erforderlich. Ressourcenkonten, die eine Telefonnummer erfordern, benötigen eine kostenlose Microsoft 365 Phone System – Virtual User-Lizenz oder eine kostenpflichtige Benutzerlizenz für Telefonsystem, bevor eine Telefonnummer auf das Ressourcenkonto angewendet werden kann.

> [!TIP]
> Für Ressourcenkonten, die mit geschachtelten automatischen Telefonkonferenzen oder Anrufwarteschlangen verwendet werden, denen keine Telefonnummer zugewiesen ist, ist keine Lizenz erforderlich. Referenz finden Sie im folgenden Diagramm: 

![Lizenzen für virtuelle Benutzer](../media/resource-account.png)

## <a name="virtual-user-license-allocation"></a>Lizenzzuweisung für virtuelle Benutzer

Ihrer Organisation wird Microsoft 365 Phone System zugewiesen – Lizenzen für virtuelle Benutzer je nach Gesamtgröße. Jede Organisation, die über mindestens eine Lizenz verfügt, einschließlich Telefonsystem oder hinzugefügtes Telefonsystem, verfügt über 25 Virtuelle Benutzerlizenzen ohne Kosten. Wenn Sie 10 Benutzerlizenzen für Telefonsystem in Ihrer Organisation hinzufügen, wird eine weitere Microsoft 365 Phone System – Virtual User-Lizenz verfügbar.

> [!NOTE]
> Phone System ist eine Add-On-Lizenz, die mit Microsoft 365 und Office 365 E1 und E3 verfügbar ist. Das Telefonsystem ist auch Bestandteil von Microsoft 365 E5-, Office 365 E5- und Microsoft 365 Business Voice-Lizenzen.

Wenn Ihre Organisation die verfügbaren kostenlosen Microsoft 365 Phone System – Virtual User-Lizenzen zum Erstellen von automatischen Telefonkonferenz- oder Anrufwarteschlangeknoten verwendet, können Sie weiterhin die kostenpflichtigen Telefonsystemlizenzen mit einem Ressourcenkonto verwenden. Die meisten Organisationen verfügen über genügend Virtuelle Benutzerlizenzen, die auf dem Skalierungsplan basieren. 

### <a name="license-allocation-example"></a>Beispiel für die Lizenzzuweisung

Contoso, Inc. hat 600 Lizenzen erworben, die Telefonsystem enthalten (eine für jeden Mitarbeiter). Contoso erhalten zunächst 25 plus 60 Microsoft 365 Phone System – Virtuelle Benutzerlizenzen, insgesamt 85. Ihre Organisation verfügt über 90 Anrufwarteschlangen und automatische Telefonwarteschlangen mit Telefonnummern. Sie müssen alle Microsoft 365 Phone System – Virtuelle Benutzerlizenzen zuweisen und fünf lizenzen für Telefonsystem mit regulärem Preis erwerben.

Contoso sollte eine Neugestaltung der automatischen Telefonanlage und des Anrufwarteschleifensystems in Erwägung ziehen. Wenn sie weniger Telefonnummern und mehr geschachtelte Knoten verwenden, die keine Telefonnummer benötigen, vereinfachen sie die Implementierung und verringern die Kosten.

## <a name="how-to-buy-microsoft-365-phone-system--virtual-user-licenses"></a>Kaufen von Microsoft 365 Phone System – Lizenzen für virtuelle Benutzer

1. Melden Sie sich beim Microsoft 365 Admin Center an.
2. Wechseln Sie **zu**  >  **Abrechnungskauf-Add-Ons**  >  
3. Scrollen Sie bis zum Ende, um die **Microsoft 365 Phone System – Virtual User-Lizenz zu** finden. Wählen Sie **Jetzt kaufen** aus.

> [!NOTE]
> Denken Sie daran, dass  **Sie** die Lizenz trotzdem kaufen müssen, obwohl die Kosten gleich null sind.

## <a name="change-an-existing-resource-account-to-use-a-microsoft-365-phone-system--virtual-user-license"></a>Ändern eines vorhandenen Ressourcenkontos zur Verwendung einer Microsoft 365 Phone System – Virtual User-Lizenz

Wenn Sie die Lizenz für Ihr Ressourcenkonto von einer Telefonsystemlizenz auf eine Microsoft 365 Phone System – Virtual User-Lizenz umschalten möchten:

1. Holen Sie sich die neue Microsoft 365 Phone System – Virtual User-Lizenz.
2. Führen Sie die verknüpften Schritte im Microsoft 365 Admin Center aus, um [Benutzer in ein anderes Abonnement zu verschieben.](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)

> [!WARNING]
> Entfernen Sie immer eine vollständige Telefonsystemlizenz, und weisen Sie die Microsoft 365 Phone System – Virtual User-Lizenz in derselben Lizenzaktivität zu. Wenn Sie die alte Lizenz entfernen, die Kontoänderungen speichern, die neue Lizenz hinzufügen und dann die Kontoeinstellungen erneut speichern, funktioniert das Ressourcenkonto möglicherweise nicht mehr wie erwartet. In diesem Fall empfiehlt es sich, ein neues Ressourcenkonto für die Microsoft 365 Phone System – Virtual User-Lizenz zu erstellen und das defekte Ressourcenkonto zu entfernen. 

## <a name="related-information"></a>Verwandte Informationen

[automatische Telefonzentrale und Serviceupdate für Anrufwarteschlangen](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Verwalten von Ressourcenkonten in Microsoft Teams](../manage-resource-accounts.md)