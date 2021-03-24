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
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: In diesem Artikel erfahren Sie, wie Sie Ressourcenkonten in Microsoft Teams erstellen, bearbeiten und verwalten.
ms.openlocfilehash: 21824c360e26e568ae47a9729960fca01a100ae8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094245"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Verwalten von Ressourcenkonten in Microsoft Teams

Ein Ressourcenkonto ist ein deaktiviertes Benutzerobjekt in Azure AD und kann zur Darstellung von Ressourcen im Allgemeinen verwendet werden. Beispielsweise kann ein Ressourcenkonto in Exchange verwendet werden, um Konferenzräume zu repräsentieren und ihnen die Verwendung einer Telefonnummer und eines Kalenders zu ermöglichen. Ein Ressourcenkonto kann in Microsoft 365 oder lokal unter Verwendung von Skype for Business Server 2019 verwaltet werden.

In Microsoft Teams ist für jede automatische Telefonkonferenz oder Anrufwarteschlange ein Ressourcenkonto erforderlich. Ressourcenkonten können auch Diensttelefonnummern zugewiesen werden. Auf diese Weise weisen Sie automatischen Telefonkonferenzen und Anrufwarteschlangen Telefonnummern zu, sodass Anrufer von außerhalb von Teams die automatische Telefonkonferenz oder Anrufwarteschlange erreichen können.

In diesem Artikel wird erläutert, wie Sie Ressourcenkonten erstellen und für die Verwendung mit automatischen Telefonkonferenzen und Anrufwarteschlangen bereit stellen.

Bevor Sie mit den Verfahren in diesem Artikel beginnen, stellen Sie sicher, dass Sie die folgenden Schritte durchgeführt haben:

- [Abrufen virtueller Benutzerlizenzen](#obtain-virtual-user-licenses)
- [Abrufen von Servicenummern](#obtain-service-numbers)

### <a name="obtain-virtual-user-licenses"></a>Abrufen virtueller Benutzerlizenzen

Für jedes Ressourcenkonto ist eine Lizenz erforderlich, um mit automatischen Telefonanten und Anrufwarteschlangen arbeiten zu können. Sie können eine kostenlose *Microsoft 365 Phone System - Virtual User-Lizenz* verwenden. Informationen zum Abrufen dieser Lizenzen finden Sie unter [Virtual User License](teams-add-on-licensing/virtual-user.md).

Weiter weiter in diesem Artikel wird erläutert, wie Sie die Lizenz einem Ressourcenkonto zuweisen.

Wenn Sie die Lizenz für virtuelle Benutzer erhalten möchten, wechseln Sie im Microsoft 365 Admin Center zu  >  Add-On-Abonnements für **Abrechnungskaufdienste,** und scrollen Sie bis zum Ende , und sehen Sie  >   *Telefonsystem – Virtuelle Benutzerlizenz.* Wählen Sie **Jetzt kaufen** aus. Es entstehen keine Kosten, Sie müssen jedoch dennoch die diese Schritte befolgen, um die Lizenz zu erwerben.

### <a name="obtain-service-numbers"></a>Abrufen von Servicenummern

Servicenummern sind für automatische Telefonanten und Anrufwarteschlangen optional. Sie benötigen jedoch mindestens eine Dienstnummer, damit Anrufer ihre automatische Telefonwarteschlange erreichen und die Konfiguration der Anrufwarteschlange erreichen können. Bei jeder automatischen Telefonkonferenz oder Anrufwarteschlange, die sie direkt über eine Dienstnummer erreichen möchten, müssen Sie über ein Ressourcenkonto mit einer zugeordneten Dienstnummer verfügen.

Ressourcenkonten können entweder gebührenpflichtige oder gebührenfreie Servicenummern verwenden. Sie können neue Nummern anfordern oder vorhandene Nummern von einem anderen Netzbetreiber portieren.

Informationen zum Abrufen neuer Servicenummern finden Sie unter [Abrufen von Servicetelefonnummern.](getting-service-phone-numbers.md)

Informationen zum Portieren einer Nummer von einem anderen Netzbetreiber finden Sie unter [Übertragen von Telefonnummern zu Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="create-a-resource-account"></a>Erstellen eines Ressourcenkontos

Sie können im Teams Admin Center ein Ressourcenkonto erstellen.

![Screenshot der Benutzeroberfläche des Ressourcenkontos hinzufügen](media/resource-account-add.png)

1. Erweitern Sie im Teams Admin Center **organisationsweite Einstellungen,** und klicken Sie dann auf **Ressourcenkonten.**

2. Klicken Sie auf **Hinzufügen**.

3. Füllen Sie **im Bereich Ressourcenkonto** hinzufügen **den** Anzeigenamen , **Den** Benutzernamen und den **Ressourcenkontotyp aus.** Der Ressourcenkontotyp kann entweder automatische **Telefonwarteschlange** oder Anrufwarteschlange **sein,** je nachdem, wie Sie dieses Ressourcenkonto verwenden möchten.

4. Klicken Sie auf **Speichern**.

![Screenshot einer Liste von Ressourcenkonten](media/resource-accounts-page.png)

## <a name="assign-a-license"></a>Zuweisen einer Lizenz

Für jedes Ressourcenkonto müssen Sie eine *Microsoft 365 Phone System - Virtual User-* oder *Phone System-Lizenz* zuweisen.

![Screenshot der Benutzeroberfläche zum Zuweisen von Lizenzen im Microsoft 365 Admin Center](media/resource-account-assign-virtual-user-license.png)

1. Klicken Sie im Microsoft 365 Admin Center auf das Ressourcenkonto, dem Sie eine Lizenz zuweisen möchten.

2. Wählen Sie **auf der Registerkarte** Lizenzen und Apps unter **Lizenzen** die Option **Microsoft 365 Phone System – Virtueller Benutzer aus.**

3. Klicken **Sie auf Änderungen speichern.**

## <a name="assign-a-service-number"></a>Zuweisen einer Dienstnummer

Wenn Sie planen, das Ressourcenkonto mit einer automatischen Telefonkonferenz oder Anrufwarteschlange zu verwenden, die eine Dienstnummer erfordert, weisen Sie dem Ressourcenkonto eine Nummer zu.

![Screenshot der Benutzeroberfläche "Dienstnummer zuweisen"](media/resource-account-assign-phone-number.png)

1. Wählen Sie im Teams  Admin Center auf der Seite Ressourcenkonten das Ressourcenkonto aus, dem Sie eine Dienstnummer zuweisen möchten, und klicken Sie dann auf **Zuweisen/Zuweisen.**

2. Wählen Sie **in der Dropdownliste** Telefonnummerntyp den Typ der Zu verwendende Nummer aus.

3. Suchen Sie **im Feld Zugewiesene** Telefonnummer nach der Zu verwendende Nummer, und klicken Sie auf **Hinzufügen.**

4. Klicken Sie auf **Speichern**.


Um einem Ressourcenkonto eine direkte Routing- oder Hybridnummer zuzuordnen, müssen Sie PowerShell verwenden:

`Set-CsOnlineApplicationInstance -Identity aa-contoso_main@contoso64.net -OnpremPhoneNumber +19295550150`

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie die Einrichtung des Ressourcenkontos abgeschlossen und bei Bedarf eine Dienstnummer zugewiesen haben, können Sie das Ressourcenkonto mit einer automatischen Telefonwarteschlange oder Anrufwarteschleife verwenden.

Lesen Sie die folgenden Verweise:

 - [Automatische Cloud-Telefonzentrale](create-a-phone-system-auto-attendant.md)

 - [Cloud-Anrufwarteschleife](create-a-phone-system-call-queue.md)

Sie können den **Ressourcenkontoanzeigenamen und** den **Ressourcenkontotyp** mithilfe der Option **Bearbeiten** bearbeiten. Klicken Sie abschließend auf **Speichern**.

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a>Ändern eines vorhandenen Ressourcenkontos, um eine virtuelle Benutzerlizenz zu verwenden

Wenn Sie sich entscheiden, die Lizenzen für  Ihr vorhandenes Ressourcenkonto von einer Telefonsystemlizenz in eine Lizenz für virtuelle Benutzer zu ändern, müssen Sie die kostenlose Lizenz für virtuelle Benutzer erwerben und dann die Schritte im Microsoft 365 Admin Center ausführen, um Benutzer in ein anderes Abonnement zu [verschieben.](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)

> [!WARNING]
> Entfernen Sie immer die vollständige Telefonsystemlizenz und weisen Sie die virtuelle Benutzerlizenz der gleichen Lizenzaktivität zu. Wenn Sie die alte Lizenz entfernen, die Kontoänderungen speichern, die neue Lizenz hinzufügen und dann die Kontoeinstellungen erneut speichern, funktioniert das Ressourcenkonto möglicherweise nicht mehr wie erwartet. In diesem Fall empfiehlt es sich, ein neues Ressourcenkonto für die virtuelle Benutzerlizenz zu erstellen und das beschädigte Ressourcenkonto zu entfernen.

## <a name="skype-for-business-server-2019"></a>Skype for Business Server 2019

Ressourcenkonten, die in Skype For Business Server 2019 gespeichert sind und mit Cloudanrufwarteschlangen und automatischen Cloudwarteschleifen verwendet werden können, finden Sie unter Planen von Cloudanrufwarteschlangen oder Planen von automatischen [Cloud-Telefonkonferenzen.](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant) [](/SkypeforBusiness/hybrid/plan-call-queue) Hybridimplementierung (Zahlen, die über Direct Routing homed sind) werden mithilfe des [New-CsHybridApplicationEndpoint-Cmdlets](/powershell/module/skype/new-cshybridapplicationendpoint) auf einem lokalen Skype for Business Server 2019-Server konfiguriert.

Die Anwendungs-IDs, die Sie beim Erstellen der Anwendungsinstanzen verwenden müssen, sind:

- **Automatische Telefonzentrale:** ce933385-9390-45d1-9512-c8d228074e07
- **Anrufwarteschleife:** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> Wenn Sie möchten, dass die Anrufwarteschleife oder automatische Telefonzentrale von Benutzern von Skype For Business Server 2019 durchsucht werden kann, sollten Sie Ihre Ressourcenkonten in Skype For Business Server 2019 erstellen, da Online-Ressourcenkonten nicht mit Active Directory synchronisiert werden. Wenn DNS-SRV-Einträge für sipfederationtls in Skype for Business Server  2019 aufgelöst werden, müssen Ressourcenkonten auf Skype For Business Server 2019 mithilfe der SfB-Verwaltungsshell erstellt und mit Azure AD synchronisiert werden.

Bei hybride Implementierungen mit Skype for Business Server:

   [Planen automatischer Cloudtelefonzentralen](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [Planen von Cloud-Anrufwarteschleifen](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [Konfigurieren lokalen von Ressourcenkonten](/SkypeForBusiness/hybrid/configure-onprem-ra)


## <a name="delete-a-resource-account"></a>Löschen eines Ressourcenkontos

Stellen Sie sicher, dass Sie die Telefonnummer vom Ressourcenkonto trennen, bevor Sie sie löschen, um zu verhindern, dass Ihre Dienstnummer im Modus „Ausstehend“ verbleibt.

Anschließend können Sie das Ressourcenkonto im Microsoft 365 Admin Center unter der Registerkarte Benutzer löschen.

Verwenden Sie den folgenden Cmdlet, um eine direkte Routing-Telefonnummer vom Ressourcenkonto zu trennen:

```powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```