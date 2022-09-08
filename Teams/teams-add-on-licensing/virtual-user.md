---
title: Microsoft Teams Telefon Ressourcenkontolizenzen
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
- admindeeplinkMAC
description: Erfahren Sie, wie Sie Ressourcenkonten für automatische Telefonzentralen und Anrufwarteschleifen in Ihrer Organisation Microsoft Teams Telefon Ressourcenkontolizenzen zuweisen.
ms.openlocfilehash: 56b461c2de32f32dd51d72c5468e31f51b107310
ms.sourcegitcommit: 09b77e83bc41914007606468e322d4ea47e2e8a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2022
ms.locfileid: "67630425"
---
# <a name="microsoft-teams-phone-resource-account-licenses"></a>Microsoft Teams Telefon Ressourcenkontolizenzen

In Microsoft Teams benötigen alle automatischen Telefonzentralen und Anrufwarteschleifen ein zugeordnetes Ressourcenkonto. Jedem Ressourcenkonto muss eine **Microsoft Teams Telefon Ressourcenkontolizenz** zugewiesen werden, um sicherzustellen, dass sie vom System ordnungsgemäß identifiziert werden und ordnungsgemäß funktionieren, *unabhängig davon, ob dem Ressourcenkonto eine Telefonnummer zugewiesen wird*. Organisationen mit einem Abonnement, das Microsoft Teams Phone umfasst, wird automatisch eine bestimmte Menge an **Teams Phone-Ressourcenkontolizenzen** ohne zusätzliche Kosten zugewiesen.  Ein Microsoft-Anrufplan ist nur erforderlich, wenn Sie mit diesem Ressourcenkonto einen Anruf auswählen möchten. Weitere Informationen finden Sie unter [Planen der automatischen Telefonzentrale und Anrufwarteschleifen für Teams](../plan-auto-attendant-call-queue.md#prerequisites).

> [!NOTE]
> Bisher war eine Lizenz für ein **Microsoft Teams-Telefonressourcenkonto** (einst als **virtuelle Benutzerlizenz** bezeichnet) nur erforderlich, wenn einem Ressourcenkonto eine Telefonnummer zugewiesen wurde. Jetzt müssen allen Ressourcenkonten eine Lizenz für das **Teams-Telefonressourcenkonto** zugewiesen werden, unabhängig davon, ob ihnen eine Telefonnummer zugewiesen wird oder nicht. Weisen Sie außerdem keinem Ressourcenkonto eine **Teams Telefon Standard** Lizenz zu. Wenn Sie derzeit Ressourcenkonten mit **Teams Telefon Standard-Lizenzen** konfiguriert haben, müssen Sie wie unten beschrieben zu einer **Microsoft Teams Phone-Ressourcenkontolizenz** wechseln.
 

## <a name="resource-account-license-allocation"></a>Ressourcenkonto-Lizenzzuweisung

Ihrer Organisation werden Lizenzen für **teams-Telefonressourcenkonten** basierend auf ihrer Gesamtgröße zugewiesen. Jeder Organisation, die über ein Abonnement mit Telefonsystemfeatures verfügt, z **. B. Teams Telefon Standard**- und **Teams-Telefon mit Anrufplanlizenzen**, werden 25 Lizenzen für **Teams-Telefonressourcenkonto** zugewiesen, die kostenlos zur Verfügung stehen. 

Für 10 Benutzerlizenzen von **Teams Telefon Standard** oder **Teams-Telefon mit Anrufplan** in Ihrer Organisation wird eine weitere **Lizenz für teams-Telefonressourcenkonto** verfügbar.  Die meisten Organisationen verfügen über genügend **Lizenzen für Teams-Telefonressourcenkonten** basierend auf diesem Skalierungsplan. Für den Fall, dass mehr **Lizenzen für Teams-Telefonressourcenkonten** erforderlich sind, können Sie mehr **Teams Phone-Ressourcenkontolizenzen** über die Standardzuweisung hinaus über Ihren Microsoft-Kontomitarbeiter erwerben.

### <a name="license-allocation-example"></a>Beispiel für die Lizenzzuweisung

Contoso, Inc. hat 600 Lizenzen erworben, die das Telefonsystem enthalten (eine für jeden Mitarbeiter). Contoso werden zunächst 25 plus 60 **Teams-Telefonressourcenkontolizenzen** zugewiesen, insgesamt 85. Ihre Organisation verfügt über 90 Anrufwarteschleifen und automatische Telefonzentralen. Sie müssen alle **Teams Phone-Ressourcenkontolizenzen** zuweisen und fünf zusätzliche **Teams Phone-Ressourcenkontolizenzen** erwerben. 

## <a name="how-to-obtain-microsoft-teams-phone-resource-account-licenses"></a>So erhalten Sie Microsoft Teams Telefon Ressourcenkontolizenzen

1. Melden Sie sich beim [Microsoft 365 Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2024339) an.
2. Wechseln **Sie zu** > **Add-Ons für Abrechnungskaufdienste**[](https://go.microsoft.com/fwlink/p/?linkid=868433) > .
3. Scrollen Sie, um die **Lizenz für das Microsoft Teams Telefon Ressourcenkonto** zu finden. Wählen Sie **Jetzt kaufen** aus.

   > [!NOTE]
   > Denken Sie daran, dass Sie die Lizenz auch dann **kaufen** müssen, wenn Sie sich innerhalb Ihrer Zuteilung befinden, obwohl sie kosten null ist.

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-resource-account-license"></a>Ändern eines vorhandenen Ressourcenkontos zur Verwendung einer Microsoft Teams Telefon Resource Account-Lizenz

Wenn Sie über vorhandene Ressourcenkonten verfügen, die eine **Teams Telefon Standard-Lizenz** verwenden, müssen Sie zu einer **Microsoft Teams Phone Resource Account-Lizenz** wechseln:

1. Rufen Sie die neue Lizenz für das **Microsoft Teams-Telefonressourcenkonto ab** .
2. Führen Sie die verknüpften Schritte im Microsoft 365 Admin Center aus, um [Benutzer in ein anderes Abonnement zu verschieben](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> Entfernen Sie immer eine **Teams Telefon Standard-Lizenz**, und weisen Sie die Lizenz für das **Teams-Telefonressourcenkonto** in derselben Lizenzaktivität zu. Wenn Sie die alte Lizenz entfernen, die Kontoänderungen speichern, die neue Lizenz hinzufügen und die Kontoeinstellungen erneut speichern, funktioniert das Ressourcenkonto möglicherweise nicht mehr wie erwartet, z. B. die automatischen Telefonzentralen und Anrufwarteschleifen Ihrer Organisation funktionieren nicht mehr.
>
> In diesem Fall wird empfohlen, ein neues Ressourcenkonto mithilfe der **Microsoft Teams Phone Resource Account-Lizenz** zu erstellen und das fehlerhafte Ressourcenkonto zu entfernen.

## <a name="related-information"></a>Verwandte Informationen

[Dienstaktualisierung für automatische Telefonzentrale und Anrufwarteschleifen](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Verwalten von Ressourcenkonten in Microsoft Teams](../manage-resource-accounts.md)
