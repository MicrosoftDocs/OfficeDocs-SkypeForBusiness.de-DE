---
title: Verwalten von Ressourcenkonten in Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: In diesem Artikel erfahren Sie, wie Sie Ressourcenkonten in Microsoft Teams erstellen, bearbeiten und verwalten können.
ms.openlocfilehash: 7ccc7a26c83357d68147381101ef8a97184f03f4
ms.sourcegitcommit: 247b2587a60b1609947310ec82d51f47cf829703
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2020
ms.locfileid: "48993517"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Verwalten von Ressourcenkonten in Microsoft Teams

Ein Ressourcenkonto ist ein deaktiviertes Benutzerobjekt in Azure AD und kann verwendet werden, um Ressourcen im allgemeinen darzustellen. So kann beispielsweise ein Ressourcenkonto in Exchange verwendet werden, um Konferenzräume darzustellen und Ihnen eine Telefonnummer und einen Kalender zu ermöglichen. Ein Ressourcenkonto kann in Microsoft 365 oder lokal unter Verwendung von Skype for Business Server 2019 verwaltet werden.

In Microsoft Teams ist für jede automatische Telefonzentrale oder Anrufwarteschlange ein Ressourcenkonto erforderlich. Ressourcenkonten können auch Service-Telefonnummern zugewiesen werden. So weisen Sie den automatischen Telefonzentralen und Anrufwarteschlangen Telefonnummern zu, die es den Anrufern von außerhalb der Teams ermöglichen, die automatische Telefonzentrale oder die Anrufwarteschlange zu erreichen.

In diesem Artikel wird erläutert, wie Ressourcenkonten erstellt und für die Verwendung mit automatischen Telefonzentralen und Anrufwarteschlangen bereitgestellt werden.

Bevor Sie mit den Verfahren in diesem Artikel beginnen, stellen Sie sicher, dass Sie die folgenden Schritte ausgeführt haben:

- [Abrufen von Lizenzen für virtuelle Benutzer](#obtain-virtual-user-licenses)
- [Abrufen von Servicenummern](#obtain-service-numbers)

### <a name="obtain-virtual-user-licenses"></a>Abrufen von Lizenzen für virtuelle Benutzer

Für jedes Ressourcenkonto ist eine Lizenz erforderlich, damit Sie mit automatischen Telefonzentralen und Anrufwarteschlangen arbeiten können. Sie können eine ﻿kostenlose *Microsoft 365-Telefon System-virtuelle Benutzer* Lizenz verwenden. Informationen zum Abrufen dieser Lizenzen finden Sie unter [Lizenz für virtuelle Benutzer](teams-add-on-licensing/virtual-user.md).

Es wird erläutert, wie Sie die Lizenz einem Ressourcenkonto später in diesem Artikel zuweisen.

Wenn Sie die Lizenz für virtuelle Benutzer erhalten möchten, wechseln Sie im Microsoft 365 Admin Center zu den Abonnements für **Billing**  >  **Purchase Services** -  >  **Add-on** , und Scrollen Sie bis zum Ende – Sie sehen die Lizenz für das *Telefon System-Virtual User* . Wählen Sie **Jetzt kaufen** aus. Es entstehen keine Kosten, Sie müssen jedoch dennoch die diese Schritte befolgen, um die Lizenz zu erwerben.

### <a name="obtain-service-numbers"></a>Abrufen von Servicenummern

Dienstnummern sind für automatische Telefonzentralen und Anrufwarteschlangen optional, Sie benötigen jedoch mindestens eine Dienstnummer, damit Anrufer Ihre automatische Telefonzentrale und die Konfiguration der Anrufwarteschlange erreichen können. Für jede automatische Telefonzentrale oder Anrufwarteschlange, deren direkte Erreichbarkeit durch eine Dienstnummer erfolgen soll, müssen Sie über ein Ressourcenkonto mit einer zugehörigen Servicenummer verfügen.

Ressourcenkonten können entweder gebührenpflichtige oder gebührenfreie Servicenummern verwenden. Sie können neue Nummern anfordern oder vorhandene Nummern von einem anderen Netzbetreiber portieren.

Informationen zum Abrufen neuer Servicenummern finden Sie unter [Abrufen von Telefonnummern für Dienstleistungen](getting-service-phone-numbers.md).

Informationen zum Portieren einer Nummer von einem anderen Netzbetreiber finden Sie unter [übertragen von Telefonnummern in Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).

## <a name="create-a-resource-account"></a>Erstellen eines Ressourcenkontos

Sie können ein Ressourcenkonto im Team Admin Center erstellen.

![Screenshot der Benutzeroberfläche "Ressourcenkonto hinzufügen"](media/resource-account-add.png)

1. Erweitern Sie im Team Admin Center **organisationsweite Einstellungen** , und klicken Sie dann auf **Ressourcenkonten**.

2. Klicken Sie auf **Hinzufügen**.

3. Füllen Sie im Bereich **Ressourcenkonto hinzufügen** die **Anzeigename** , den **Benutzernamen** und den **Typ des Ressourcenkontos** aus. Der Typ des Ressourcenkontos kann eine **automatische Telefonzentrale** oder eine **Anrufwarteschlange** sein, je nachdem, wie Sie dieses Ressourcenkonto verwenden möchten.

4. Klicken Sie auf **Speichern**.

![Screenshot einer Liste von Ressourcenkonten](media/resource-accounts-page.png)

## <a name="assign-a-license"></a>Zuweisen einer Lizenz

Für jedes Ressourcenkonto müssen Sie eine *Microsoft 365-Telefonsystem-virtuelle Benutzer* Lizenz oder eine *Telefonsystem* Lizenz zuweisen.

![Screenshot der Benutzeroberfläche "Lizenzen zuweisen" im Microsoft 365 Admin Center](media/resource-account-assign-virtual-user-license.png)

1. Klicken Sie im Microsoft 365 Admin Center auf das Ressourcenkonto, dem Sie eine Lizenz zuweisen möchten.

2. Wählen Sie auf der Registerkarte **Lizenzen und apps** unter **Lizenzen** den Eintrag **Microsoft 365 Phone System – Virtual User** aus.

3. Klicken Sie auf **Änderungen speichern**.

## <a name="assign-a-service-number"></a>Zuweisen einer Servicenummer

Wenn Sie beabsichtigen, das Ressourcenkonto mit einer automatischen Telefonzentrale oder einer Anrufwarteschlange zu verwenden, für die eine Dienstnummer erforderlich ist, weisen Sie dem Ressourcenkonto eine Nummer zu.

![Screenshot der Benutzeroberfläche "Dienstnummer zuweisen"](media/resource-account-assign-phone-number.png)

1. Wählen Sie im Team Admin Center auf der Seite **Ressourcenkonten** das Ressourcenkonto aus, dem Sie eine Dienstnummer zuweisen möchten, und klicken Sie dann auf **zuweisen/** Aufheben der Zuweisung.

2. Wählen Sie in der Dropdownliste **Telefonnummerntyp** den Typ der Nummer aus, die Sie verwenden möchten.

3. Suchen Sie im Feld **zugewiesene Rufnummer** nach der Nummer, die Sie verwenden möchten, und klicken Sie auf **Hinzufügen**.

4. Klicken Sie auf **Speichern**.


Wenn Sie einem Ressourcenkonto eine direkte Routing-oder Hybrid Nummer zuweisen möchten, müssen Sie PowerShell verwenden:

`Set-CsOnlineApplicationInstance -Identity aa-contoso_main@contoso64.net -OnpremPhoneNumber +19295550150`

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie die Einrichtung des Ressourcenkontos abgeschlossen und bei Bedarf eine Dienstnummer zugewiesen haben, können Sie das Ressourcenkonto mit einer automatischen Telefonzentrale oder einer Anrufwarteschlange verwenden.

Sehen Sie sich die folgenden Verweise an:

 - [Automatische Cloud-Telefonzentrale](create-a-phone-system-auto-attendant.md)

 - [Cloud-Anrufwarteschleife](create-a-phone-system-call-queue.md)

Mit der Option **Bearbeiten** können Sie den **Anzeigenamen** und den **Ressourcen** Kontotyp des Ressourcenkontos bearbeiten. Klicken Sie abschließend auf **Speichern**.

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a>Ändern eines vorhandenen Ressourcenkontos, um eine virtuelle Benutzerlizenz zu verwenden

Wenn Sie sich entscheiden, die Lizenzen für Ihr vorhandenes Ressourcenkonto von einer **Telefon System** Lizenz zu einer virtuellen Benutzerlizenz zu wechseln, müssen Sie die ﻿kostenlose virtuelle Benutzerlizenz erwerben und dann die Schritte im Microsoft 365 Admin Center ausführen, um [Benutzer in ein anderes Abonnement zu verschieben](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> Entfernen Sie immer die vollständige Telefonsystemlizenz und weisen Sie die virtuelle Benutzerlizenz der gleichen Lizenzaktivität zu. Wenn Sie die alte Lizenz entfernen, die Kontoänderungen speichern, die neue Lizenz hinzufügen und dann die Kontoeinstellungen erneut speichern, funktioniert das Ressourcenkonto möglicherweise nicht mehr wie erwartet. In diesem Fall empfiehlt es sich, ein neues Ressourcenkonto für die virtuelle Benutzerlizenz zu erstellen und das beschädigte Ressourcenkonto zu entfernen.

## <a name="skype-for-business-server-2019"></a>Skype for Business Server 2019

Informationen zu Ressourcenkonten in Skype for Business Server 2019, die mit Cloud-Anrufwarteschlangen und automatischen Cloud-Telefonzentralen verwendet werden können, finden Sie unter [Planen von Cloud-Anrufwarteschlangen](/SkypeforBusiness/hybrid/plan-call-queue) oder [Planen automatischer Cloud-Telefonzentralen](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant). Hybrid Implementierungen (Zahlen, die im direkten Routing verwaltet werden) werden mithilfe des Cmdlets [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint) auf einem lokalen Skype for Business Server 2019-Server konfiguriert.

Die Anwendungs-IDs, die Sie beim Erstellen der Anwendungsinstanzen verwenden müssen, sind:

- **Automatische Telefonzentrale:** ce933385-9390-45d1-9512-c8d228074e07
- **Anrufwarteschleife:** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> Wenn Sie möchten, dass die Anrufwarteschleife oder automatische Telefonzentrale von Benutzern von Skype For Business Server 2019 durchsucht werden kann, sollten Sie Ihre Ressourcenkonten in Skype For Business Server 2019 erstellen, da Online-Ressourcenkonten nicht mit Active Directory synchronisiert werden. Wenn DNS-SRV-Einträge für sipfederationtls in Skype for Business Server 2019 aufgelöst werden, **müssen** in Skype for Business Server 2019 mithilfe der SFB-Verwaltungsshell Ressourcenkonten erstellt und mit Azure AD synchronisiert werden.

Bei hybride Implementierungen mit Skype for Business Server:

   [Planen automatischer Cloudtelefonzentralen](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [Planen von Cloud-Anrufwarteschleifen](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [Konfigurieren lokalen von Ressourcenkonten](/SkypeForBusiness/hybrid/configure-onprem-ra)


## <a name="delete-a-resource-account"></a>Löschen eines Ressourcenkontos

Stellen Sie sicher, dass Sie die Telefonnummer vom Ressourcenkonto trennen, bevor Sie sie löschen, um zu verhindern, dass Ihre Dienstnummer im Modus „Ausstehend“ verbleibt.

Anschließend können Sie das Ressourcenkonto im Microsoft 365 Admin Center auf der Registerkarte Benutzer löschen.

Verwenden Sie den folgenden Cmdlet, um eine direkte Routing-Telefonnummer vom Ressourcenkonto zu trennen:

```powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```
