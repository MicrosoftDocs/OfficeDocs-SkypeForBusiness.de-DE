---
title: Microsoft Teams Telefon Standard – Lizenzen für virtuelle Benutzer
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
ms.localizationpriority: medium
ms.custom:
- Licensing
- LIL_Placement
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie kostenlose Teams Telefon Standard – Virtual User-Lizenzen oder eine kostenpflichtige Teams Telefon Standardbenutzerlizenzen Ressourcenkonten in Ihrer Organisation zuweisen.
ms.openlocfilehash: 542d80a8cb463df01e6e232454b2454a939a457b
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2022
ms.locfileid: "63435729"
---
# <a name="microsoft-teams-phone-standard--virtual-user-licenses"></a>Microsoft Teams Telefon Standard – Lizenzen für virtuelle Benutzer

Organisationen mit Teams Telefon Standard oder Teams Telefon mit lizenzierten Benutzern des Anrufplans können entweder eine kostenlose *Microsoft Teams Telefon Standard – Virtual User-Lizenz* oder eine kostenpflichtige Teams Telefon *Standard*  Benutzerlizenz für Ressourcenkonten. Nicht immer ist ein Microsoft-Anrufplan erforderlich (siehe Planen der [automatischen](../plan-auto-attendant-call-queue.md#prerequisites) Teams-Telefonkonferenz und Anrufwarteschleifen, um die Voraussetzungen bei der Übertragung von Anrufen an eine externe Telefonnummer zu erfüllen).

Für alle automatischen Telefonkonferenzen und Anrufwarteschleifen ist ein zugeordnetes Ressourcenkonto erforderlich. Ressourcenkonten, für die eine Telefonnummer erforderlich ist, benötigen entweder eine kostenlose *Microsoft Teams Telefon Standard – Virtual User-Lizenz* oder eine kostenpflichtige *Teams Telefon Standard-Benutzerlizenz*, bevor eine Telefonnummer auf das Ressourcenkonto angewendet werden kann.

> [!TIP]
> Für Ressourcenkonten, die mit geschachtelten automatischen Telefonisten oder Anrufwarteschleifen ohne Telefonnummer verwendet werden, ist keine Lizenz erforderlich. Referenz finden Sie im folgenden Diagramm.

:::image type="content" alt-text="Lizenzen für virtuelle Benutzer." source="../media/resource-account.png":::

## <a name="virtual-user-license-allocation"></a>Lizenzzuweisung für virtuelle Benutzer

Ihrer Organisation werden je Microsoft Teams Telefon *Lizenzen für Standard – Virtuelle* Benutzer zugewiesen. Jede Organisation, die über mindestens eine Lizenz mit Teams Telefonsystem verfügt, einschließlich Teams Telefon Standard- und Teams Telefon mit Anrufplanlizenzen, verfügt über 25 Lizenzen für virtuelle Benutzer, die kostenlos zur Verfügung stehen. Wenn Sie 10 Teams Telefon Standard oder Teams Telefon mit Anrufplan-Benutzerlizenzen in Ihrer Organisation hinzufügen, wird eine weitere Microsoft Teams Telefon *Standard – Virtual User-Lizenz* verfügbar.

> [!NOTE]
> Teams Telefon Standard- und Teams Telefon Anrufplan sind Add-On-Lizenzen, die für alle Microsoft 365 zur Verfügung stehen. Teams Telefon Standardlizenzen sind ebenfalls In den Plänen Microsoft 365 E5 enthalten.

Wenn Ihre Organisation die kostenlosen *Microsoft Teams Telefon Standard – Virtual User-Lizenzen* zum Erstellen von automatischen Telefonant- oder Anrufwarteschlangenknoten verwendet, können Sie die bezahlten *Teams Telefon Standard-Lizenzen* weiterhin mit einem Ressourcenkonto verwenden. Die meisten Organisationen verfügen basierend auf dem Skalierungsplan über genügend virtuelle Benutzerlizenzen.

### <a name="license-allocation-example"></a>Beispiel für die Lizenzzuweisung

Contoso, Inc. hat 600 Lizenzen gekauft, die Telefonsystem (eine für jeden Mitarbeiter) enthalten. Contoso werden anfänglich 25 plus 60 Lizenzen für Microsoft Teams Telefon *– Virtuelle Benutzer* zugewiesen, insgesamt 85. Ihre Organisation verfügt über 90 Anrufwarteschleifen und automatische Telefonkonferenzen mit Telefonnummern. Sie müssen alle Lizenzen für Microsoft Teams Telefon *Standard – Virtual User* zuweisen und fünf Standard-Standardlizenzen *Teams Telefon erwerben*.

Contoso sollte eine Neugestaltung der automatischen Telefonanlage und des Anrufwarteschleifensystems in Erwägung ziehen. Wenn sie weniger Telefonnummern und mehr geschachtelte Knoten verwenden, für die keine Telefonnummer erforderlich ist, vereinfachen sie die Implementierung und senken die Kosten.

## <a name="how-to-buy-microsoft-teams-phone-standard--virtual-user-licenses"></a>So kaufen Sie Microsoft Teams Telefon Standard – Virtual User-Lizenzen

1. Melden Sie sich beim Microsoft 365 Admin Center an.
2. Wechseln Sie **zu** **BillingPurchase** >  **servicesAdd-ons** > .
3. Scrollen Sie bis zum Ende, um die Lizenz **Microsoft Teams Telefon Standard – Virtual User"** zu finden. Wählen Sie **Jetzt kaufen** aus.

   > [!NOTE]
   > Denken Sie daran, **dass Sie die** Lizenz weiterhin kaufen müssen, auch wenn die Kosten hier für null liegen.

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-standard--virtual-user-license"></a>Ändern eines vorhandenen Ressourcenkontos in die Verwendung einer Microsoft Teams Telefon Standard – Virtual User-Lizenz

Wenn Sie die Lizenz für Ihr Ressourcenkonto von einer *Teams Telefon Standard-Lizenz* auf eine *Microsoft Teams Telefon Standard – Virtual User-Lizenz umschalten* möchten:

1. Holen Sie sich die Microsoft Teams Telefon Standard – Virtual User-Lizenz.
2. Führen Sie die verknüpften Schritte im Microsoft 365 Admin Center aus, [um Benutzer in ein anderes Abonnement zu verschieben](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> Entfernen Sie immer eine Teams Telefon *Standard-Lizenz*, und weisen Sie die *Microsoft Teams Telefon Standard – Virtual User-Lizenz* in derselben Lizenzaktivität zu. Wenn Sie die alte Lizenz entfernen, die Kontoänderungen speichern, die neue Lizenz hinzufügen und dann die Kontoeinstellungen erneut speichern, funktioniert das Ressourcenkonto möglicherweise nicht mehr wie erwartet. In diesem Fall empfiehlt es sich, ein neues Ressourcenkonto für die Microsoft Teams Telefon *Standard – Virtual User-Lizenz* zu erstellen und das beschädigte Ressourcenkonto zu entfernen.

## <a name="related-information"></a>Verwandte Informationen

[automatische Telefonzentrale und Dienstupdate für Anrufwarteschleifen](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Verwalten von Ressourcenkonten in Microsoft Teams](../manage-resource-accounts.md)
