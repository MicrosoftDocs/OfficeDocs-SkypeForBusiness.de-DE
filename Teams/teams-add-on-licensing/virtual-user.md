---
title: Microsoft 365 Telefonsystem – Lizenzen für virtuelle Benutzer
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
description: Erfahren Sie, wie Sie Ressourcenkonten in Ihrer Telefonsystem eine kostenlose Telefonsystem Virtual User-Lizenz oder eine kostenpflichtige Telefonsystem-Benutzerlizenz zuweisen.
ms.openlocfilehash: 8e5322ccf7e3e7ad05c499b3dbcfdac65d0dfedb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116923"
---
# <a name="microsoft-365-phone-system--virtual-user-license"></a>Microsoft 365 Telefonsystem – Lizenz für virtuelle Benutzer

Organisationen mit Telefonsystem-Lizenzen können Ressourcenkonten entweder eine kostenlose Microsoft 365 Telefonsystem – Virtual User-Lizenz oder eine Telefonsystem zahlende Lizenz zuweisen. Ein Anrufplan ist nicht erforderlich. Für alle automatischen Telefonkonferenzen oder Anrufwarteschleifen ist ein zugeordnetes Ressourcenkonto erforderlich. Ressourcenkonten, für die eine Telefonnummer erforderlich ist, benötigen eine kostenlose Microsoft 365 Telefonsystem – Virtual User-Lizenz oder eine kostenpflichtige Telefonsystem-Benutzerlizenz, bevor eine Telefonnummer auf das Ressourcenkonto angewendet werden kann.

> [!TIP]
> Für Ressourcenkonten, die mit geschachtelten automatischen Telefonisten oder Anrufwarteschleifen ohne Telefonnummer verwendet werden, ist keine Lizenz erforderlich. Referenz finden Sie im folgenden Diagramm: 

![Lizenzen für virtuelle Benutzer](../media/resource-account.png)

## <a name="virtual-user-license-allocation"></a>Lizenzzuweisung für virtuelle Benutzer

Ihrer Organisation werden – Microsoft 365 Telefonsystem – Lizenzen für virtuelle Benutzer zugewiesen, abhängig von der Gesamtgröße. Jede Organisation, die über mindestens eine Lizenz verfügt, einschließlich Telefonsystem oder die Telefonsystem hat, verfügt über 25 Lizenzen für virtuelle Benutzer, die kostenlos zur Verfügung stehen. Wenn Sie 10 Telefonsystem in Ihrer Organisation hinzufügen, wird eine weitere Microsoft 365 Telefonsystem – Virtuelle Benutzerlizenz verfügbar.

> [!NOTE]
> Telefonsystem ist eine Add-On-Lizenz, die für E1 und E3 Microsoft 365 Office 365 E1 verfügbar ist. Telefonsystem ist auch Bestandteil von Microsoft 365 E5, Office 365 E5 und Microsoft 365 Business Voice Lizenzen.

Wenn Ihre Organisation die verfügbaren kostenlosen Microsoft 365 Telefonsystem – Virtuelle Benutzerlizenzen zum Erstellen von automatischen Telefonanlage- oder Anrufwarteschlangenknoten nutzt, können Sie die bezahlten Telefon-Systemlizenzen weiterhin mit einem Ressourcenkonto verwenden. Die meisten Organisationen verfügen basierend auf dem Skalierungsplan über genügend virtuelle Benutzerlizenzen. 

### <a name="license-allocation-example"></a>Beispiel für die Lizenzzuweisung

Contoso, Inc. hat 600 Lizenzen gekauft, Telefonsystem (eine für jeden Mitarbeiter). Contoso erhalten anfänglich 25 plus 60 Microsoft 365 Telefonsystem – Lizenzen für virtuelle Benutzer, insgesamt 85. Ihre Organisation verfügt über 90 Anrufwarteschleifen und automatische Telefonkonferenzen mit Telefonnummern. Sie müssen alle Lizenzen für Microsoft 365 Telefonsystem – virtuelle Benutzer zuweisen und fünf Lizenzen zum normalpreis Telefonsystem erwerben.

Contoso sollte eine Neugestaltung der automatischen Telefonanlage und des Anrufwarteschleifensystems in Erwägung ziehen. Wenn sie weniger Telefonnummern und mehr geschachtelte Knoten verwenden, für die keine Telefonnummer erforderlich ist, vereinfachen sie die Implementierung und senken die Kosten.

## <a name="how-to-buy-microsoft-365-phone-system--virtual-user-licenses"></a>So kaufen Sie Microsoft 365 Telefonsystem – Lizenzen für virtuelle Benutzer

1. Melden Sie sich beim Microsoft 365 Admin Center an.
2. Wechseln Sie **zum**  >  **Abrechnungskaufdienst-Add-Ons.**  >  
3. Scrollen Sie bis zum Ende, um die Lizenz **Microsoft 365 Telefonsystem – Virtueller Benutzer zu** finden. Wählen Sie **Jetzt kaufen** aus.

> [!NOTE]
> Denken Sie daran, dass  **Sie** die Lizenz weiterhin kaufen müssen, auch wenn die Kosten hier für null liegen.

## <a name="change-an-existing-resource-account-to-use-a-microsoft-365-phone-system--virtual-user-license"></a>Ändern eines vorhandenen Ressourcenkontos zur Verwendung einer Lizenz Microsoft 365 Telefonsystem – Virtueller Benutzer

Wenn Sie sich entschließen, die Lizenz für Ihr Ressourcenkonto von einer Telefonsystem-Lizenz auf eine Lizenz Microsoft 365 Telefonsystem – virtueller Benutzer umschalten:

1. Holen Sie sich die Microsoft 365 Telefonsystem – Virtual User-Lizenz.
2. Führen Sie die verknüpften Schritte im Microsoft 365 Admin Center aus, [um Benutzer in ein anderes Abonnement zu verschieben.](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)

> [!WARNING]
> Entfernen Sie immer eine Telefonsystem Lizenz, und weisen Sie die Lizenz Microsoft 365 Telefonsystem – Virtueller Benutzer in derselben Lizenzaktivität zu. Wenn Sie die alte Lizenz entfernen, die Kontoänderungen speichern, die neue Lizenz hinzufügen und dann die Kontoeinstellungen erneut speichern, funktioniert das Ressourcenkonto möglicherweise nicht mehr wie erwartet. In diesem Fall empfiehlt es sich, ein neues Ressourcenkonto für die Lizenz "Microsoft 365 Telefonsystem – Virtual User" zu erstellen und das beschädigte Ressourcenkonto zu entfernen. 

## <a name="related-information"></a>Verwandte Informationen

[automatische Telefonzentrale und Dienstupdate für Anrufwarteschleifen](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Verwalten von Ressourcenkonten in Microsoft Teams](../manage-resource-accounts.md)